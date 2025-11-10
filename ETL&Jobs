# Documentação do Processo de ETL e Demonstração dos Jobs


## 1\. Visão Geral da Solução de ETL

Para este projeto, em vez de uma ferramenta de ETL tradicional (como Pentaho ou Talend), optamos por uma solução de ETL em tempo real (event-driven), 100% baseada em nuvem, utilizando componentes do Google Workspace (Forms, Sheets e Apps Script).

O objetivo deste ETL é: Capturar, transformar e carregar os dados de doações instantaneamente, sem necessidade de intervenção manual, disponibilizando-os para análise (Etapa 7) assim que são criados.

**Fonte de Dados (Extração): Google Forms.
Ferramenta de Transformação (O "Job"): Google Apps Script.
Destino (Carga): Google Sheets (atuando como Data Warehouse / Data Mart).**

## 2\. O "Job" (A Tarefa Automatizada)

Em nossa arquitetura, o "Job" (tarefa automatizada) não é executado em um horário fixo (batch), mas sim disparado por um evento.

**Função do Job: onFormSubmit(e)
Gatilho (Trigger): O script é acionado automaticamente "Ao enviar formulário".
Função: O Job é responsável por executar todas as etapas de Transformação e Carga no instante em que a Extração acontece.**

## 3\. Detalhamento do Processo ETL

O fluxo de dados segue rigorosamente as três etapas clássicas do ETL:

### 3.1. E - Extração (Extract)

**1\. Origem:** Os dados são inseridos pelo doador através do Google Form ("Formulário de Doação").
**2\. Evento:** Quando o doador clica em "Enviar", o Google Forms "extrai" os dados e os envia como um objeto de evento (e) para o nosso Job no Google Apps Script.
**3\. Dados Extraídos:**

   - Carimbo de data/hora

   - Nome do Doador

   - Telefone de Contato

   - Tipo de Doação

   - Descrição da Doação

### 3.2. T - Transformação (Transform)

Uma vez que o "Job" (onFormSubmit) recebe os dados, ele executa duas transformações principais em tempo real:

##### 1\. Transformação 1: Enriquecimento de Dados (ID Sequencial)

**   - Descrição:** O script lê a planilha, verifica qual foi o último "Nº Doação" (ID) utilizado na linha anterior (currentRow - 1) e soma 1.

**   - Objetivo: **Criar uma chave primária (ID sequencial) única para cada doação, facilitando o rastreamento e prevenindo duplicidade.

**   - Código-chave: **var newId = lastId + 1;

##### 2\. Transformação 2: Formatação para Notificação

**   - Descrição**: O script formata os dados extraídos (Perguntas e Respostas) em um corpo de texto (String) legível.

**   - Objetivo:** Preparar os dados para o envio da notificação por e-mail.

**   - Código-chave: **body += "► " + question + ": \\n" + submittedData\[question\]\[0\] + "\\n\\n";

### 3.3. L - Carga (Load)

Após a transformação, os dados são carregados em dois destinos simultaneamente:

##### 1\. Carga 1: Data Warehouse (Google Sheets)

**   - Descrição:** O dado transformado (o newId) é carregado na sua respectiva coluna (Coluna F: Nº Doação) na linha que acabou de ser criada na planilha "Respostas ao formulário 1".

**   - Resultado:** A planilha é populada com dados brutos + dados transformados (limpos e enriquecidos), pronta para ser consumida pela camada de visualização (Etapa 7).

**   - Código-chave: **sheet.getRange(currentRow, idColumnIndex).setValue(newId);

##### 2\. Carga 2: Sistema de Notificação (E-mail)

   **- Descrição: **Os dados formatados (Transformação 2) são "carregados" como corpo de um e-mail.

   **- Resultado:** O gestor exemplo do projeto (Felipebarros15984@gmail.com) recebe uma notificação instantânea da nova doação.

   **- Código-chave:** MailApp.sendEmail(emailAddress, subject, body);

\---

## 4\. Demonstração dos Jobs

A demonstração do nosso processo é composta por 3 evidências: a configuração do Job (Gatilho) e os resultados de sua execução (Antes e Depois).

##### #### Demonstração 1: O Job (Gatilho)

A imagem abaixo comprova a configuração do "Job" (onFormSubmit) sendo acionado pelo gatilho "Ao enviar formulário", garantindo a execução automática do ETL.

![Demonstração do Job (Gatilho)](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe4-t3-social-remanescente/blob/main/Img/ImagemdosAcionadores.png?raw=true)

##### Demonstração 2: Resultados da Execução (Antes e Depois)

**Antes (A Extração):**

![Formulário de Doação Preenchido](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe4-t3-social-remanescente/blob/main/Img/ImagemFormPreenchido.png?raw=true)

O usuário preenche os dados no Google Forms.

**Depois (A Carga):**

https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe4-t3-social-remanescente/blob/main/Img/ImagemTabela.png?raw=true

Após o envio, os dados são transformados e carregados com sucesso, como visto na planilha (ID 12) e na notificação por e-mail.

![Notificação por E-mail Recebida](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe4-t3-social-remanescente/blob/main/Img/ImagemEmailChegando.png?raw=true)


(Destaque: a coluna "Nº Doação"foi preenchida sozinha).

\---

## 5\. Conclusão da Etapa 6

O processo de ETL foi implementado com sucesso. Ele é 100% automatizado, não requer manutenção e fornece dados limpos e enriquecidos em tempo real para a plataforma de BI.
