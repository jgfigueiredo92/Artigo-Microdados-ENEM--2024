# Análise de Desempenho e Disparidades Regionais em Biologia: Enem 2024

Repositório com o pipeline computacional e tabelas agregadas para reprodução das análises estatísticas sobre as 11 habilidades de Biologia da prova regular de Ciências da Natureza e suas Tecnologias do Enem 2024.

---

## 1. Fonte dos Dados Primários e Matriz de Referência

Os microdados brutos do exame e a matriz avaliativa são disponibilizados publicamente pelo Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira (Inep):

* **Portal de Microdados do Enem (Inep):**  
  [https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem)
* **Matriz de Referência para o Enem 2009:**  
  [https://download.inep.gov.br/download/enem/matriz_referencia.pdf](https://download.inep.gov.br/download/enem/matriz_referencia.pdf)

---

## 2. Instruções para Download e Configuração dos Caminhos Locais

Devido ao tamanho censitário da base de dados do Enem (arquivos de múltiplos gigabytes), os arquivos brutos não estão armazenados neste repositório. Para executar o pipeline completo, siga as etapas abaixo:

1. Acesse o portal do Inep pelo link acima e faça o download do pacote compactado referente à edição de 2024 (`microdados_enem_2024.zip`).
2. Descompacte o arquivo no seu computador e localize a pasta `DADOS`, contendo:
   * `RESULTADOS_2024.csv` (ou arquivo de participantes/resultados da edição)
   * `ITENS_PROVA_2024.csv`
3. **Ajuste obrigatório no código Python:**  
   Antes de rodar o script ou o Jupyter Notebook (`Análise de Biologia ENEM 2024.ipynb`), abra a célula de configuração inicial e **modifique a variável de caminho** para apontar para a pasta onde você descompactou os arquivos no seu computador:

```python
# Modifique a variável BASE com o endereço do seu diretório local
BASE = r"./DADOS"  # Exemplo de caminho relativo, ou caminho absoluto local
CAMINHO_ITENS = os.path.join(BASE, "ITENS_PROVA_2024.csv")
CAMINHO_RESULTADOS = os.path.join(BASE, "RESULTADOS_2024.csv")

---

## 3. Bases Consolidadas Disponíveis neste Repositório

Para consulta direta sem necessidade de reprocessar a base bruta do Inep, este repositório disponibiliza as tabelas finais geradas:

* `acerto_biologia_por_uf_CORRIGIDO.csv`: Percentual médio de acertos em Biologia e nota padronizada de Ciências da Natureza nas 27 Unidades da Federação.
* `acerto_biologia_por_uf_habilidade_CORRIGIDO.csv`: Desempenho detalhado cruzando cada Unidade da Federação com as 11 habilidades da Matriz de Referência.
* `gap_regional_habilidades_biologia_CORRIGIDO.csv`: Ranking da Amplitude de Gap Regional ordenado pela maior disparidade territorial em pontos percentuais.
