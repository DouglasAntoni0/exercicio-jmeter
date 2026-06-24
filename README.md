# Exercício JMeter - Plano de Teste com Massa CSV

![JMeter](https://img.shields.io/badge/Apache%20JMeter-performance-D22128?style=for-the-badge&logo=apachejmeter&logoColor=white)
![CSV](https://img.shields.io/badge/CSV-massa%20de%20dados-0A66C2?style=for-the-badge)
![QA](https://img.shields.io/badge/QA-performance%20testing-7D64FF?style=for-the-badge)
![Evidência](https://img.shields.io/badge/Evidencia-resultados%20JTL-2E7D32?style=for-the-badge)

Projeto de prática com Apache JMeter para estruturar um plano de teste com massa de dados externa, simulando requisições parametrizadas e execução orientada a evidências.

O foco deste repositório é demonstrar a base de performance testing: montar um plano executável, parametrizar entrada com CSV e produzir resultado analisável. Mesmo como exercício, ele reforça uma habilidade importante para QA: transformar uma hipótese de carga em um artefato técnico reprodutível.

## Objetivo do projeto

O objetivo é praticar:

- criação de plano `.jmx` no Apache JMeter;
- uso de massa de dados externa em CSV;
- execução manual pelo modo gráfico;
- execução não interativa pelo terminal;
- geração de arquivo de resultado `.jtl`;
- análise inicial de comportamento sob carga.

## O que este projeto demonstra

| Competência | Evidência | Valor técnico |
| --- | --- | --- |
| Performance testing | Plano `.jmx` organizado para execução no JMeter | Permite simular comportamento sob carga |
| Parametrização | Uso de `dados-do-youtube.csv` como massa de entrada | Evita testes estáticos e repetitivos |
| Reprodutibilidade | Artefatos versionados para repetir a execução | Ajuda a comparar execuções |
| Execução CLI | Comando `jmeter -n` documentado | Facilita automação futura |
| Análise técnica | Base para observar resposta, carga e comportamento | Aproxima de cenários reais de performance |

## Estrutura

```text
.
└── Teste-JMeter-Youtube/
    ├── Test Plan - ebac youtube.jmx
    └── dados-do-youtube.csv
```

## Papel de cada arquivo

| Arquivo | Função |
| --- | --- |
| `Test Plan - ebac youtube.jmx` | Plano de teste principal do JMeter |
| `dados-do-youtube.csv` | Massa de dados usada para parametrização |

## Como executar pelo JMeter GUI

1. Abra o Apache JMeter.
2. Carregue `Teste-JMeter-Youtube/Test Plan - ebac youtube.jmx`.
3. Verifique se o caminho do CSV está correto.
4. Execute o plano.
5. Analise os listeners configurados.
6. Observe erros, tempos de resposta e comportamento das requisições.

## Como executar pelo terminal

Modo não interativo:

```bash
jmeter -n -t "Teste-JMeter-Youtube/Test Plan - ebac youtube.jmx" -l resultados.jtl
```

Gerando relatório HTML a partir do `.jtl`:

```bash
jmeter -g resultados.jtl -o relatorio-html
```

## O que observar em um teste de performance

Ao analisar uma execução, alguns pontos importantes são:

- taxa de erro;
- tempo médio de resposta;
- tempo máximo de resposta;
- throughput;
- comportamento com massa variável;
- estabilidade durante o período de execução;
- gargalos ou respostas inconsistentes.

## Leitura de QA

Performance testing não é apenas “rodar carga”. Um bom teste começa com pergunta clara:

- o endpoint suporta determinado volume?
- a resposta permanece estável?
- há erro quando a massa varia?
- o tempo de resposta é aceitável?
- o comportamento piora ao longo da execução?

Este repositório trabalha a base desse raciocínio.

## Critérios de aceite para evolução

Uma evolução natural deste exercício seria definir thresholds explícitos, como percentual máximo de erro e tempo de resposta aceitável. Isso transforma a execução em uma decisão objetiva de qualidade, aproximando o plano de um teste automatizado de performance.

## Resultado técnico

Este repositório evidencia visão de qualidade voltada a comportamento sob carga e uso de dados parametrizados. Mesmo como exercício, ele reforça uma habilidade importante para QA: transformar uma hipótese de performance em plano executável e repetível.

## Competências evidenciadas

- Uso básico/intermediário do Apache JMeter.
- Parametrização com CSV.
- Execução de plano `.jmx`.
- Geração de resultado `.jtl`.
- Pensamento de performance testing.
- Organização de artefatos de teste.

## Possíveis evoluções

- Adicionar relatório HTML gerado como exemplo.
- Documentar critérios de aceitação de performance.
- Criar cenários com diferentes níveis de carga.
- Versionar resultados de execução controlados.
- Integrar execução JMeter em pipeline.

## Conclusão

Este projeto mostra um ponto importante da maturidade em QA: qualidade também envolve estabilidade, tempo de resposta e comportamento sob carga. O plano JMeter com CSV cria uma base para evoluir de exercício para análise técnica mais profunda.
