## DESCRIÇÃO
<p align="justify">
O presente projeto tem como objetivo desenvolver uma aplicação simples e acessível, estruturada na forma de um site integrado ao Power BI. A solução permitirá o cadastro de voluntários, famílias e crianças atendidas por meio de formulários online, além da gestão de listas de espera e vagas disponíveis. Também será possível automatizar a comunicação com a comunidade e parceiros por meio do disparo de e-mails.
</p>

<p align="justify">
A integração com o Power BI possibilitará a criação de dashboards dinâmicos, facilitando a visualização de indicadores sociais e o acompanhamento do impacto do programa. Dessa forma, o projeto busca não apenas otimizar a gestão e a comunicação, mas também fortalecer a transparência e apoiar a tomada de decisões estratégicas.
</p>


## Casos de Uso

| **Persona**                 | **Funcionalidade**                                                | **Motivo**                                                                 |
|-----------------------------|-------------------------------------------------------------------|----------------------------------------------------------------------------|
| Família Carente             | Consultar a quantidade de vagas disponíveis no projeto            | Inscrever seus filhos para participação no programa                       |
| Família Carente             | Realizar a solicitação de matrícula da criança                    | Garantir a participação da criança no projeto                              |
| Voluntário do projeto       | Receber notificações sobre abertura de vagas                      | Manter-se informada e matricular a criança no momento oportuno             |
| Voluntário do projeto       | Receber e analisar solicitações de matrícula de crianças           | Acolher mais crianças no programa e apoiar seu desenvolvimento             |
| Assistente social da cidade | Anunciar novas vagas disponíveis                                  | Ampliar o alcance e possibilitar que mais famílias sejam atendidas         |
| Família Carente             | Realizar solicitação de matrícula para crianças vulneráveis       | Garantir oportunidades a crianças carentes sob sua responsabilidade        |
| Assistente social da cidade | Consultar informações sobre crianças cadastradas 


## ARQUITETURA DO PROJETO

<p align="justify">
A arquitetura do projeto foi planejada para garantir a centralização, integração e visualização eficiente dos dados relacionados às atividades do projeto social da Igreja Remanescente Família de Deus. A estrutura proposta envolve os seguintes componentes principais:
</p>

- Coleta de Dados: informações sobre crianças, famílias, voluntários, transporte e doações são registradas inicialmente em planilhas (Excel ou Google Sheets), garantindo flexibilidade e fácil atualização.
- Integração e Conexão: essas planilhas são conectadas diretamente ao Power BI, permitindo que os dados sejam atualizados automaticamente à medida que novas informações são inseridas.
- Tratamento e Limpeza de Dados: por meio do Power Query, os dados brutos são padronizados, tratados e organizados, garantindo consistência e confiabilidade para análise.
- Modelagem de Dados: as tabelas são relacionadas de forma estruturada, permitindo cruzamento de informações entre famílias, crianças, voluntários, doações e transporte.
- Visualização e Dashboards Interativos: a partir da modelagem, são construídos dashboards dinâmicos e interativos, incluindo indicadores-chave de atendimento, doações, voluntariado e impacto social. A ferramenta permite consultas em tempo real, análises estratégicas e monitoramento contínuo das atividades.
- Acesso Online: os dashboards são disponibilizados via link online, possibilitando que gestores, voluntários e parceiros tenham acesso fácil, seguro e atualizado às informações, fortalecendo a transparência e a tomada de decisão baseada em dados.

<p align="center">
<img width="1536" height="1024" alt="Arquitetura Social Remanescente" src="https://github.com/user-attachments/assets/bb819205-8951-4f6a-b8b5-290bd43c1aa6" />
Imagem 2.2 - Fluxo de dados
</p>

### Estrutura Tecnológica

A estrutura tecnológica adotada neste projeto visa atender aos requisitos de **acessibilidade**, **baixo custo** e **aplicabilidade em contexto social**.  
Dessa forma, foram utilizadas exclusivamente ferramentas de fácil acesso e ampla disponibilidade educacional:  
**Power BI** para análise de dados e **Google Sites** como portal de publicação.

A arquitetura tecnológica está composta da seguinte forma:

| **Camada**           | **Ferramenta Utilizada** | **Função**                      |
|-----------------------|---------------------------|----------------------------------|
| Coleta de Dados       | Formulários Google        | Inserção de cadastros            |
| Base de Dados         | Google Sheets             | Armazenamento estruturado        |
| Análise e Indicadores | Power BI                  | Dashboards e relatórios          |
| Publicação            | Google Sites              | Portal de acesso aos resultados  |


## METODOLOGIA DO PROJETO

<p align="justify">
A metodologia adotada no projeto segue uma abordagem prática, iterativa e orientada a resultados, garantindo que cada etapa seja aplicada ao contexto real do projeto social:
</p>

- Levantamento de Requisitos: identificação das necessidades da igreja, dos gestores do projeto e da comunidade atendida, incluindo critérios de priorização de famílias, escalas de voluntários e controle de doações.
- Planejamento e Estruturação de Dados: definição das tabelas, campos e formatos necessários para organizar as informações em planilhas de coleta e posteriormente no Power BI.
- Implementação Técnica: integração das planilhas ao Power BI, tratamento de dados com Power Query, criação de relacionamentos e construção dos dashboards interativos conforme os indicadores estratégicos definidos (crianças atendidas, voluntários, doações, transporte, impacto social).
- Testes e Validação: execução de testes de consistência, atualização e usabilidade dos dashboards, garantindo que as informações apresentadas estejam corretas e que os usuários consigam interagir de forma intuitiva.
- Treinamento e Capacitação: orientação dos gestores e voluntários sobre como utilizar os dashboards, interpretar os indicadores e atualizar dados, promovendo autonomia na gestão do projeto.
- Monitoramento Contínuo: acompanhamento periódico dos dados e ajustes nos dashboards conforme novas necessidades surgirem, garantindo que o projeto evolua com base em informações confiáveis e em tempo real.

<p align="center">
<img width="1536" height="1024" alt="Diagrama de arquitetura" src="https://github.com/user-attachments/assets/5acf766b-3e33-4a6c-a4a0-b063332a7f2e" />
Imagem 2.3 - Diagrama de arquitetura da solução
</p>

## REQUISITOS

<p align="justify">
Os requisitos funcionais e não funcionais principais a serem atendidos são apresentados abaixo. De acordo com a ordem de prioridade eles serão implementados. As restrições também são apresentadas abaixo:
</p>

# 2.4.1. REQUISITOS FUNCIONAIS

| Código  | Título                        | Descrição                                                                                          | Prioridade |
|---------|-------------------------------|--------------------------------------------------------------------------------------------------|------------|
| RF-01   | Cadastro de Famílias e Crianças | Permitir o registro centralizado de famílias e crianças atendidas pelo projeto, incluindo dados pessoais, endereço e situação de vulnerabilidade. | Alta       |
| RF-02   | Lista de Espera               | Gerar e manter atualizada uma lista de espera de famílias e crianças que ainda não foram atendidas, com critérios de prioridade. | Alta       |
| RF-03   | Dashboard de Indicadores      | Exibir painéis dinâmicos com indicadores sociais (número de famílias atendidas, crianças beneficiadas, doações recebidas, etc.). | Alta       |
| RF-04   | Relatórios Periódicos         | Exibir relatórios sobre o impacto social, para apoio à gestão e prestação de contas.              | Média      |
| RF-05   | Gestão de Doações             | Exibir doações recebidas (alimentos, roupas, recursos financeiros) e sua destinação.             | Média      |

| RF-06   | Notificações Internas         | Enviar avisos internos (ex.: novos cadastros de usuários, nova doação, novo contato). | Baixa      |


### REQUISITOS NÃO FUNCIONAIS

| Código  | Título               | Descrição                                                                 | Prioridade |
|---------|----------------------|---------------------------------------------------------------------------|------------|
| RNF-01  | Usabilidade          | O sistema deve ser simples e intuitivo, adequado para voluntários com baixo nível de familiaridade tecnológica. | Alta       |
| RNF-02  | Segurança de Dados   | Garantir a proteção de dados pessoais das famílias e crianças, seguindo a LGPD. | Alta       |
| RNF-03  | Disponibilidade Online | A solução deve ser acessível em ambiente online, permitindo o uso por voluntários de diferentes locais. | Alta       |
| RNF-04  | Acessibilidade       | A interface deve ser compatível com diferentes dispositivos (computador, tablet, celular). | Médio      |
| RNF-05  | Desempenho           | Os dashboards e relatórios devem carregar em tempo aceitável (até 5 segundos para consultas padrão). | Alta       |
| RNF-06  | Escalabilidade       | O sistema deve comportar o crescimento no número de famílias cadastradas sem perda significativa de desempenho. | Alta       |
| RNF-07  | Backup e Recuperação | Deve existir rotina de backup automático dos dados para evitar perdas em caso de falhas técnicas. | Alta       |
| RNF-08  | Padronização Visual  | Os dashboards devem adotar uma identidade visual clara, com uso de cores e ícones padronizados para fácil interpretação. | Médio      |
| RNF-09  | Transparência        | O sistema deve permitir extração de dados para prestação de contas junto a parceiros e órgãos públicos. | Média      |
| RNF-10  | Suporte e Atualizações | A solução deve prever atualizações periódicas e suporte básico para ajustes e melhorias. | Média      |

### RESTRIÇÕES

| ID   | Descrição da Restrição                                                                 |
|------|---------------------------------------------------------------------------------------|
| 001  | O projeto deverá ser entregue no final do semestre letivo, não podendo extrapolar a data de 07/12/2025. |
| 002  | A plataforma deve se restringir às tecnologias básicas utilizando ferramentas de desenvolvimento pré-estabelecidas. |
| 003  | A equipe não pode subcontratar o desenvolvimento do trabalho.                         |
| 004  | A plataforma se compromete em não compartilhar históricos de pesquisa e dados sensíveis dos usuários. |


## Produto Mínimo Viável (MVP)

O presente projeto apresenta como **Produto Mínimo Viável (MVP)** uma solução digital que integra **coleta**, **organização** e **visualização de dados socioassistenciais** do Projeto Social Remanescente.  
O MVP será desenvolvido utilizando exclusivamente as ferramentas **Power BI** e **Google Sites**, possibilitando a centralização das informações e seu acesso de forma **simples**, **gratuita** e **online**.

O escopo do MVP contempla:

- Cadastro básico de famílias, crianças e voluntários;  
- Estruturação de dados em planilhas organizadas;  
- Visualização de indicadores iniciais no Power BI;  
- Publicação dos resultados em um portal informativo desenvolvido no Google Sites.

### Roadmap de Evolução

Após a validação do MVP com o parceiro comunitário detalhado acima, prevê-se o seguinte **Roadmap**:

| **Fase**                                | **Evolução do Sistema**                                 |
|----------------------------------------|----------------------------------------------------------|
| **Fase 01 – Levantamento de dados**    | Coleta de dados básicos                                 |
| **Fase 02 – Tratamento de dados**      | Organização e agrupamento dos dados                      |
| **Fase 03 – Elaboração de Dashboards** | Dashboards de indicadores sociais detalhados             |
| **Fase 04 – Publicação da análise**    | Relatórios de desempenho e prestação de contas           |
| **Fase 05 – Publicação de índices e resultados** | Transparência pública e análise de impacto        |

---

## Evidências da Ação Extensionista

Este projeto caracteriza-se como uma ação extensionista por promover a integração entre a universidade e a comunidade local por meio do desenvolvimento de uma solução tecnológica aplicada ao contexto social. As evidências de extensão foram coletadas ao longo de todo o processo e incluem:

•	Levantamento das necessidades diretamente com lideranças do projeto social;
•	Participação em reuniões com voluntários e representantes comunitários;
•	Diagnóstico situacional construído com dados reais;
•	Desenvolvimento de ferramenta gratuita e acessível para uso continuado pela comunidade;
•	Estímulo à transparência e à tomada de decisão fundamentada em dados.

Ao reunir com a representante da equipe do projeto de apoio infantil Luciane Nayane, foi realizado o levantamento das principais necessidades da comunidade assistida e os requisitos necessários para o desenvolvimento do projeto Social Remanescente. Encontro foi registrado em ATA em setembro de 2025. (Documento em anexo – Ata de Reunião Social Remanescente)

Assim, o projeto reforça o compromisso social da instituição de ensino ao aplicar conhecimentos tecnológicos em benefício direto da comunidade parceira.


---

## Processamento de Dados Baseados na LGPD

O tratamento de dados obtidos no projeto Social Remanescente, será estritamente regido pela LGPD (Lei Geral de Proteção de Dados), dada a sensibilidade das informações envolvidas, como a título de exemplo, a condição socioeconômica e dados de crianças. A base legal para o processamento de dados se apoia no Legítimo Interesse da entidade social e na Execução de Políticas Públicas de assistência, garantindo a legalidade de todo o processo obtenção e tratamentos dos dados refente ao projeto Social Remanescente. <br/>

Seguindo os princípios da LGPD, coletaremos apenas os dados essenciais para a execução da atividade desempenhada. No Power BI, a privacidade será garantida através da pseudonimização e agregação dos dados para análise de indicadores, com acesso estritamente restrito aos gestores autorizados. O Google Sites, por sua vez, exibirá unicamente indicadores consolidados e estratégicos para o público, assegurando a transparência sem expor dados sensíveis.


