##Processos de Obtenção das Medidas (DAX – Power BI)


1. Total de Crianças no Projeto
A medida foi criada a partir da contagem de linhas da tabela 'Criancas', considerando apenas os registros em que o campo [Participa_Projeto] possui o valor “Sim”.
Total Crianças no Projeto = CALCULATE(COUNTROWS('Criancas'),'Criancas'[Participa_Projeto] = "Sim")


2. Total de Voluntários Ativos
A medida representa a contagem de voluntários distintos cadastrados na tabela 'Voluntarios', utilizando a coluna [ID_Voluntario] como identificador único.
Total de Voluntários Ativos = DISTINCTCOUNT(Voluntarios[ID_Voluntario])


3. % de Famílias em Alta Vulnerabilidade

O cálculo dessa métrica foi dividido em duas etapas:

•	Etapa 1 – Identificação das Famílias em Alta Vulnerabilidade:	
 Realizou-se a contagem de famílias distintas na tabela 'Familias', filtrando os registros com [Vulnerabilidade_Social] = "Alta".
Famílias em Alta Vulnerabilidade = CALCULATE(DISTINCTCOUNT(Familias[ID_Familia]), Familias[Vulnerabilidade_Social] = "Alta")

•	Etapa 2 – Cálculo do Percentual:	
 Após obter o número de famílias em alta vulnerabilidade (numerador), foi realizada a divisão dessa medida pela medida [Total de Famílias Atendidas] (denominador). O resultado é exibido em formato percentual.
% Famílias em Alta Vulnerabilidade = DIVIDE([Famílias em Alta Vulnerabilidade],[Total de Famílias Atendidas])


4. Total de Famílias Atendidas
A medida foi criada com base na contagem distinta da coluna [ID_Familia] da tabela 'Familias', representando o total de famílias participantes do projeto.
Total de Famílias Atendidas = DISTINCTCOUNT(Familias[ID_Familia])


5. Valor Total de Doações Financeiras (R$)
Essa medida calcula o valor total de doações financeiras somando os valores da coluna [Quantidade] da tabela 'Doacoes', considerando apenas os registros em que o campo [Tipo_Doacao] é igual a “Financeira”.
Valor Total de Doações Financeiras (R$) = CALCULATE(SUM('Doacoes'[Quantidade]),'Doacoes'[Tipo_Doacao] = "Financeira")

O painel Social Remanescente foi construído com a ferramenta PowerBi Desktop 

<img width="989" height="494" alt="image" src="https://github.com/user-attachments/assets/5c95f992-05ea-4b30-8f4a-47c2f5e7c3cb" />
Unidade 02 – KPI’s Projeto Social Remanescente

<img width="989" height="495" alt="image" src="https://github.com/user-attachments/assets/2521191c-7128-4097-b8ab-5b13f44eb845" />
Unidade 03 – Gráficos, filtros e medidas
