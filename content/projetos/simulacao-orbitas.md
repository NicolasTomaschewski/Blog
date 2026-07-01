---
title: "Simulação Computacional de Troca de Órbitas"
descricao: "Simulação numérica de manobras orbitais utilizando métodos de integração de equações diferenciais ordinárias."
tecnologias: ["Python", "NumPy", "SciPy", "Matplotlib", "Jupyter"]
status: "concluído"
periodo: "2024"
date: 2024-03-01
---

## Contexto

Projeto desenvolvido como parte de uma disciplina de física computacional, com foco na aplicação de métodos numéricos para simulação de sistemas dinâmicos.

O problema escolhido foi a simulação de transferências orbitais — especificamente a manobra de Hohmann, que é o método mais eficiente de transferência entre duas órbitas circulares coplanares.

## Objetivo

Implementar um simulador que:

1. Modelasse a dinâmica orbital de um corpo em campo gravitacional central
2. Calculasse os parâmetros necessários para uma transferência de Hohmann
3. Visualizasse a trajetória antes, durante e após a manobra

## Arquitetura

O problema foi formulado como um sistema de equações diferenciais ordinárias (EDOs) de segunda ordem, reduzido a um sistema de primeira ordem para integração numérica:

$$\ddot{\mathbf{r}} = -\frac{\mu}{|\mathbf{r}|^3}\mathbf{r}$$

Onde $\mu = GM$ é o parâmetro gravitacional padrão.

```python
def equations_of_motion(t, state, mu=MU_EARTH):
    """
    state = [x, y, vx, vy]
    returns [vx, vy, ax, ay]
    """
    x, y, vx, vy = state
    r = np.sqrt(x**2 + y**2)
    ax = -mu * x / r**3
    ay = -mu * y / r**3
    return [vx, vy, ax, ay]
```

A integração foi realizada com o método RK45 (Runge-Kutta de quarta e quinta ordem com controle adaptativo de passo), disponível via `scipy.integrate.solve_ivp`.

## Desafios

A principal dificuldade foi garantir a conservação de energia ao longo da simulação. Integradores explícitos acumulam erro ao longo do tempo, o que se manifesta como deriva na energia orbital.

A solução foi usar um integrador simplético para a propagação de longa duração e limitar o passo de tempo máximo a uma fração do período orbital.

Outro desafio foi a implementação correta do impulso de velocidade na manobra. A mudança de velocidade precisa ser aplicada de forma instantânea (em termos do modelo) mas no ponto exato da órbita previsto pela teoria.

## Resultados

O simulador reproduz com fidelidade as propriedades analíticas da manobra de Hohmann:

- Erro relativo na energia orbital final: < 0.01%
- Conservação do momento angular: verificada com precisão de máquina
- Visualização da trajetória elíptica de transferência corretamente representada

## Aprendizados

Este projeto me mostrou a distância entre uma equação bonita no papel e sua implementação estável em código. Métodos numéricos têm características próprias — estabilidade, precisão, custo computacional — que precisam ser entendidas antes de escolher um integrador.

Após implementar e depurar este simulador, minha compreensão de sistemas dinâmicos e integração numérica é fundamentalmente diferente do que era depois de apenas estudar a teoria.
