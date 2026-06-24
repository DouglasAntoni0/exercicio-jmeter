# Exercício JMeter - Plano de Teste com Massa CSV

![JMeter](https://img.shields.io/badge/Apache%20JMeter-performance-D22128?style=for-the-badge&logo=apachejmeter&logoColor=white)
![CSV](https://img.shields.io/badge/CSV-massa%20de%20dados-0A66C2?style=for-the-badge)
![QA](https://img.shields.io/badge/QA-performance%20testing-7D64FF?style=for-the-badge)

Projeto de prática com Apache JMeter para estruturar um plano de teste com massa de dados externa, simulando requisições parametrizadas e execução orientada a evidências.

## O que este projeto demonstra

| Competência | Evidência |
| --- | --- |
| Performance testing | Plano `.jmx` organizado para execução no JMeter |
| Parametrização | Uso de `dados-do-youtube.csv` como massa de entrada |
| Reprodutibilidade | Artefatos versionados para repetir a execução |
| Análise técnica | Base para observar resposta, carga e comportamento do alvo testado |

## Estrutura

```text
.
└── Teste-JMeter-Youtube/
    ├── Test Plan - ebac youtube.jmx
    └── dados-do-youtube.csv
```

## Como executar

Pelo modo gráfico do JMeter:

1. Abra o Apache JMeter.
2. Carregue `Teste-JMeter-Youtube/Test Plan - ebac youtube.jmx`.
3. Verifique o caminho do CSV, se necessário.
4. Execute o plano e analise os listeners configurados.

Pelo terminal, usando o modo não interativo:

```bash
jmeter -n -t "Teste-JMeter-Youtube/Test Plan - ebac youtube.jmx" -l resultados.jtl
```

## Resultado técnico

Este repositório evidencia visão de qualidade voltada a comportamento sob carga e uso de dados parametrizados. Mesmo como exercício, ele reforça uma habilidade importante para QA: transformar uma hipótese de performance em plano executável e repetível.
