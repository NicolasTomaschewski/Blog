---
title: "Sistema de Diagnóstico com IA"
descricao: "Pipeline de análise de imagens médicas utilizando modelos de aprendizado profundo para apoio ao diagnóstico clínico."
tecnologias: ["Python", "PyTorch", "FastAPI", "Docker", "PostgreSQL"]
status: "concluído"
periodo: "2024"
date: 2024-06-01
---

## Contexto

O projeto surgiu como parte de uma iniciativa de pesquisa aplicada com o objetivo de explorar a viabilidade do uso de redes neurais convolucionais no auxílio ao diagnóstico de condições específicas a partir de imagens médicas.

A motivação central não era substituir o julgamento clínico — e isso ficou claro desde o início —, mas investigar se modelos treinados poderiam atuar como uma segunda opinião automatizada, reduzindo a carga cognitiva sobre profissionais de saúde em contextos de alto volume de exames.

## Objetivo

Construir um pipeline completo de processamento de imagens médicas, desde a ingestão de dados brutos até a entrega de predições com métricas de confiança interpretáveis.

## Arquitetura

O sistema foi estruturado em três camadas independentes:

**Camada de dados** — responsável pelo pré-processamento, normalização e augmentation das imagens. Implementada em Python com suporte a paralelismo para processamento em batch.

**Camada de inferência** — modelo baseado em arquitetura ResNet fine-tuned para o domínio específico. Servido via FastAPI com suporte a requisições síncronas e assíncronas.

**Camada de persistência** — PostgreSQL para armazenamento de metadados, histórico de predições e logs de auditoria.

```python
# Exemplo simplificado do pipeline de inferência
class DiagnosticPipeline:
    def __init__(self, model_path: str):
        self.model = self._load_model(model_path)
        self.transform = build_transforms()

    def predict(self, image: np.ndarray) -> dict:
        tensor = self.transform(image).unsqueeze(0)
        with torch.no_grad():
            logits = self.model(tensor)
        probs = torch.softmax(logits, dim=1)
        return {
            "class": probs.argmax().item(),
            "confidence": probs.max().item(),
        }
```

## Desafios

O maior desafio foi a qualidade e quantidade dos dados de treinamento. Dados médicos são escassos, sensíveis e frequentemente desbalanceados. Técnicas de augmentation e o uso de modelos pré-treinados em domínios relacionados foram fundamentais para superar essa limitação.

A interpretabilidade das predições também foi um ponto crítico. Um modelo que simplesmente retorna uma classe sem explicação não tem utilidade clínica real. Implementamos mapas de ativação (Grad-CAM) para visualizar quais regiões da imagem influenciaram cada predição.

## Resultados

Após o ciclo de treinamento e validação:

- Acurácia de 87% no conjunto de teste
- Sensibilidade de 91% para a classe positiva
- Tempo médio de inferência de 120ms por imagem

## Aprendizados

Minha compreensão após este projeto é que a engenharia de dados é pelo menos tão importante quanto a arquitetura do modelo. A maioria dos ganhos de performance veio de melhorias no pré-processamento e na curadoria dos dados, não de ajustes no modelo em si.

Também aprendi que métricas de acurácia não contam a história completa em problemas de classificação desbalanceada. Sensibilidade e especificidade são os indicadores que realmente importam em contexto clínico.
