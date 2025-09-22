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
| RF-06   | Integração com CRAS           | Disponibilizar espaço para importação de dados ou relatórios do CRAS, apoiando a identificação de novos casos. | Baixa      |
| RF-07   | Notificações Internas         | Enviar avisos aos voluntários (ex.: necessidade de transporte, palestras agendadas, mudanças de escala). | Baixa      |
| RF-08   | Vagas Disponíveis             | Exibir informativos sobre disponibilidade de vagas.                                              | Média      |
| RF-09   | Notificar Vagas Disponíveis   | Enviar avisos no formato de email sobre a disponibilidade de vagas.                              | Média      |

### 2.4.2. REQUISITOS NÃO FUNCIONAIS

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

### 2.4.3. RESTRIÇÕES

| ID   | Descrição da Restrição                                                                 |
|------|---------------------------------------------------------------------------------------|
| 001  | O projeto deverá ser entregue no final do semestre letivo, não podendo extrapolar a data de 07/12/2025. |
| 002  | A plataforma deve se restringir às tecnologias básicas utilizando ferramentas de desenvolvimento pré-estabelecidas. |
| 003  | A equipe não pode subcontratar o desenvolvimento do trabalho.                         |
| 004  | A plataforma se compromete em não compartilhar históricos de pesquisa e dados sensíveis dos usuários. |
