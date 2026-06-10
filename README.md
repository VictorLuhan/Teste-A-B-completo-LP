# 🧪 Análise Completa de A/B Test — SaaSify

**Autor:** Victor Luhan · Marketing Analytics Pleno  
**Ferramentas:** Excel · Python · Pandas · SciPy · Statsmodels · Matplotlib  
**Período do experimento:** 14 dias · 15.000 usuários

---

## 📌 Contexto do Problema

A **SaaSify** é um software de agendamento online voltado para pequenas e médias empresas (salões, clínicas, consultórios). O canal de aquisição principal é Google Ads (Search).

**Hipótese testada:**  
> Mudar o headline da landing page de uma comunicação focada em **funcionalidade** para um **benefício emocional** aumentará a taxa de conversão para trial.

| | Versão |
|---|---|
| **Controle (A)** | *"Software de Agendamento Online"* — "Simples, flexível e poderoso. Integre com seu site em minutos." |
| **Variação (B)** | *"Pare de Atender o Telefone."* — "Deixe seus clientes agendarem online e recupere seu tempo livre." |

---

## 📊 Resultados

| Métrica | Controle (A) | Variação (B) | Diferença |
|---|---|---|---|
| Usuários | 7.505 | 7.495 | −10 |
| Conversões | 742 | 921 | +179 |
| Taxa de conversão | 9,89% | 12,29% | +2,40 pp |
| Lift absoluto | — | — | **+2,40 pp** |
| Lift percentual | — | — | **+24,29%** |

### Significância Estatística

- **Z-statistic:** 4,6839
- **p-value:** 0,0000028 ✅ (α = 0,05)
- **IC 95% da diferença:** [+1,40 pp ; +3,41 pp] — zero excluído
- **Poder estatístico:** 99,68%
- **Bootstrap (10k iterações):** 100% das reamostras com lift positivo

### Veredicto

✅ **Implementar a Variação B.** O resultado é estatisticamente significativo com ampla margem. O headline emocional *"Pare de Atender o Telefone."* converte significativamente mais do que o funcional.

---

## 🗂️ Estrutura do Repositório

```
.
├── index.html              # Relatório interativo completo
├── ab_test_analysis.ipynb  # Notebook com toda a análise em Python
├── ab_test_data.csv        # Dataset do experimento (15.000 linhas)
└── README.md               # Este arquivo
```

---

## 🚀 Como Executar o Notebook

### Pré-requisitos

```bash
pip install pandas numpy scipy statsmodels matplotlib seaborn
```

### Execução

```bash
jupyter notebook ab_test_analysis.ipynb
```

Ou abra diretamente no [Google Colab](https://colab.research.google.com/) fazendo upload do `.ipynb`.

---

## 📐 Metodologia

### 1. Teste de Proporções (Z-test)
Escolhido para comparar duas taxas de conversão independentes com amostras grandes (n > 1.000 por grupo). Mais adequado que o Qui-Quadrado para este cenário específico, pois fornece diretamente o Z-score e permite calcular o intervalo de confiança da diferença.

### 2. Intervalo de Confiança (95%)
Calculado para a **diferença absoluta** entre as taxas. Permite interpretar o resultado além do binário "significativo/não significativo" — mostrando o intervalo plausível do efeito real.

### 3. Análise de Poder Estatístico
Cohen h usado como medida do tamanho do efeito para proporções. Poder calculado para validar que a amostra coletada foi suficiente para detectar o efeito observado.

### 4. Bootstrap (validação não-paramétrica)
10.000 reamostras com reposição para validar os resultados sem assumir distribuição normal. Serve como checagem independente do Z-test.

---

## 📈 Impacto de Negócio

Com investimento mensal de **R$ 60.000** e **30.000 visitantes/mês**:

| Cenário | CR | Trials/mês | CPA |
|---|---|---|---|
| Controle (A) | 3,00% | 900 | R$ 66,67 |
| Variação (B) | 4,09% | 1.227 | R$ 48,90 |
| **Ganho** | **+1,09 pp** | **+327** | **−26%** |

**Projeção anual:** +3.924 trials · Economia de R$ 17,77 por trial.

---

## 📬 Contato

**Victor Luhan** · Marketing Analytics Pleno  
[LinkedIn](#) · [GitHub](#)
