## Protótipo do Projeto

Este protótipo apresenta a concepção inicial de um **site para a Igreja Remanescente**, visando proporcionar uma presença digital acessível.  
O objetivo é criar uma plataforma que **fortaleça a comunicação entre a igreja e seus membros**, facilitando o acesso a informações.  

Este modelo constitui uma **etapa inicial**, permitindo a realização de **testes e ajustes** antes do desenvolvimento completo.


<img width="500" height="640" alt="image" src="https://github.com/user-attachments/assets/50510ded-eeb8-4200-99ec-f428521f1189" />

<img width="500" height="640" alt="image" src="https://github.com/user-attachments/assets/be9b04db-cc19-4c03-bc50-137d5d5fd4f6" />

<img width="500" height="640" alt="image" src="https://github.com/user-attachments/assets/fb52c47b-5d61-48ca-960b-7518cb62a840" />



## Modelagem de Dados

A fundação da solução de Business Intelligence proposta reside em um modelo de dados bem estruturado. A modelagem foi concebida utilizando a abordagem de Star Schema (Esquema Estrela), uma metodologia consolidada e otimizada para consultas analíticas e a criação de dashboards em ferramentas como o Power BI. Esta escolha metodológica visa atender diretamente aos requisitos de desempenho (RNF-05), escalabilidade (RNF-06) e clareza na geração de relatórios (RF-03, RF-04).

O modelo é composto por dois tipos principais de tabelas: Tabelas de Dimensão, que armazenam os dados cadastrais e descritivos (quem, o quê, onde), e Tabelas de Fatos, que registram os eventos e as métricas transacionais (o que aconteceu). Essa separação garante que os dados sejam organizados, íntegros e que as análises possam ser realizadas de forma rápida e intuitiva


### 2.9.1 Modelo Dimensional do Projeto

O **Modelo Dimensional** a seguir ilustra visualmente a estrutura do banco de dados, representando as tabelas, seus respectivos campos e os relacionamentos que as conectam.  

Ele serve como um **mapa lógico** que orienta tanto a **coleta de dados nas planilhas de origem** quanto a **configuração das relações** no ambiente do **Power BI**.

<img width="991" height="552" alt="image" src="https://github.com/user-attachments/assets/b5d418f0-4754-4536-8154-98554edd00e4" />


---

### Diagrama Entidade Relacionamento (DER)

<img width="933" height="514" alt="image" src="https://github.com/user-attachments/assets/e117b460-8392-4282-b884-61027677374f" />


---

### Diagrama de Classes

<img width="1072" height="523" alt="diagrama-classe drawio" src="https://github.com/user-attachments/assets/134fb19f-8244-49ee-8b81-94816f2ea34e" />
