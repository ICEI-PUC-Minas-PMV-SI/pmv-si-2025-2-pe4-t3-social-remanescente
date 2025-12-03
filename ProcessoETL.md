## PROCESSO DE ETL E DEMONSTRAÇÃO DOS JOBS

3.1. Visão Geral da Solução de ETL
Para este projeto, em vez de uma ferramenta de ETL tradicional (como Pentaho ou Talend), optamos por uma solução de ETL em tempo real (event-driven), 100% baseada em nuvem, utilizando componentes do Google Workspace (Forms, Sheets e Apps Script).	
O objetivo deste ETL é: Capturar, transformar e carregar os dados de doações instantaneamente, sem necessidade de intervenção manual, disponibilizando-os para análise (Etapa 7) assim que são criados.	

•	Fonte de Dados (Extração): Google Forms.
•	Ferramenta de Transformação (O "Job"): Google Apps Script.
•	Destino (Carga): Google Sheets (atuando como Data Warehouse / Data Mart).

3.1.1. O "Job" (A Tarefa Automatizada)
Em nossa arquitetura, o "Job" (tarefa automatizada) não é executado em um horário fixo (batch), mas sim disparado por um evento.
•	Função do Job: onFormSubmit(e)
•	Gatilho (Trigger): O script é acionado automaticamente "ao enviar formulário".
•	Função: O Job é responsável por executar todas as etapas de Transformação e Carga no instante em que a Extração acontece.

3.2. Detalhamento do Processo ETL
O fluxo de dados segue rigorosamente as três etapas clássicas do ETL:
3.2.1. E - Extração (Extract)
A.	Origem: Os dados são inseridos pelo doador através do Google Form ("Formulário de Doação").
B.	Evento: Quando o doador clica em "Enviar", o Google Forms "extrai" os dados e os envia como um objeto de evento (e) para o nosso Job no Google Apps Script.


C.	Dados Extraídos:

-	Carimbo de data/hora
-	Nome do doador
-	Telefone de contato
-	Tipo de doação
-	Descrição da doação

3.2.2 T - Transformação (Transform)
Uma vez que o "Job" (onFormSubmit) recebe os dados, ele executa duas transformações principais em tempo real:
A. Transformação 1: Enriquecimento de Dados (ID Sequencial)
   - Descrição: O script lê a planilha, verifica qual foi o último "Nº Doação" (ID) utilizado na linha anterior (currentRow - 1) e soma 1.
   - Objetivo: Criar uma chave primária (ID sequencial) única para cada doação, facilitando o rastreamento e prevenindo duplicidade.
   - Código-chave: var newId = lastId + 1;
B. Transformação 2: Formatação para Notificação
   - Descrição: O script formata os dados extraídos (Perguntas e Respostas) em um corpo de texto (String) legível.
   - Objetivo: Preparar os dados para o envio da notificação por e-mail.
   - Código-chave: body += "► " + question + ": \n" + submittedData[question][0] + "\n\n";

3.2.3. L - Carga (Load)
Após a transformação, os dados são carregados em dois destinos simultaneamente:
A. Carga 1: Data Warehouse (Google Sheets)
   - Descrição: O dado transformado (o newId) é carregado na sua respectiva coluna (Coluna F: Nº Doação) na linha que acabou de ser criada na planilha "Respostas ao formulário 1".
   - Resultado: A planilha é populada com dados brutos + dados transformados (limpos e enriquecidos), pronta para ser consumida pela camada de visualização (Etapa 7).
   - Código-chave: sheet.getRange(currentRow, idColumnIndex).setValue(newId);
B. Carga 2: Sistema de Notificação (E-mail)
   - Descrição: Os dados formatados (Transformação 2) são "carregados" como corpo de um e-mail.
   - Resultado: O gestor exemplo do projeto (Felipebarros15984@gmail.com) recebe uma notificação instantânea da nova doação.
   - Código-chave: MailApp.sendEmail(emailAddress, subject, body);

C. Demonstração dos Jobs
A demonstração do nosso processo é composta por 3 evidências: a configuração do Job (Gatilho) e os resultados de sua execução (Antes e Depois).
•	Demonstração 1: O Job (Gatilho)
A imagem abaixo comprova a configuração do "Job" (onFormSubmit) sendo acionado pelo gatilho "Ao enviar formulário", garantindo a execução automática do ETL.

<img width="989" height="370" alt="image" src="https://github.com/user-attachments/assets/099f901e-869b-4928-985d-50c4eeb122d4" />


Demonstração 2: Resultados da Execução (Antes e Depois)

Antes (A Extração):
O usuário preenche os dados no Google Forms. 

<img width="600" height="673" alt="image" src="https://github.com/user-attachments/assets/8856fced-8442-425f-9c8d-9bebf2ade74a" />

<br/> <br/>

Depois (A Carga):
Após o envio, os dados são transformados e carregados com sucesso, como visto na planilha (ID 12) e na notificação por e-mail.

<img width="989" height="175" alt="image" src="https://github.com/user-attachments/assets/0b5c48e9-d373-4f39-b7ee-a75fb397f91a" />

<img width="989" height="106" alt="image" src="https://github.com/user-attachments/assets/f5329655-0578-4b59-9f2f-132b689cce3e" />

(Destaque: a coluna "Nº Doação"foi preenchida sozinha).

D. Conclusão da Etapa 6
O processo de ETL foi implementado com sucesso. Ele é 100% automatizado, não requer manutenção e fornece dados limpos e enriquecidos em tempo real para a plataforma de BI.



