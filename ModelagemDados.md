## Protótipo do Projeto

Este protótipo apresenta a concepção inicial de um **site para a Igreja Remanescente**, visando proporcionar uma presença digital acessível.  
O objetivo é criar uma plataforma que **fortaleça a comunicação entre a igreja e seus membros**, facilitando o acesso a informações.  

Este modelo constitui uma **etapa inicial**, permitindo a realização de **testes e ajustes** antes do desenvolvimento completo.


<img width="500" height="640" alt="image" src="https://github.com/user-attachments/assets/50510ded-eeb8-4200-99ec-f428521f1189" />

<img width="500" height="640" alt="image" src="https://github.com/user-attachments/assets/be9b04db-cc19-4c03-bc50-137d5d5fd4f6" />

<img width="500" height="640" alt="image" src="https://github.com/user-attachments/assets/fb52c47b-5d61-48ca-960b-7518cb62a840" />



## 2.9 Modelagem de Dados

A fundação da solução de **Business Intelligence (BI)** proposta reside em um **modelo de dados bem estruturado**.  
A modelagem foi concebida utilizando a abordagem **Star Schema (Esquema Estrela)**, uma metodologia consolidada e amplamente utilizada para **consultas analíticas** e para a **criação de dashboards** em ferramentas como o **Power BI**.

Essa escolha metodológica visa atender diretamente aos requisitos de:

- **Desempenho (RNF-05)**  
- **Escalabilidade (RNF-06)**  
- **Clareza na geração de relatórios (RF-03, RF-04)**  

O modelo é composto por dois tipos principais de tabelas:

- **Tabelas de Dimensão** → armazenam dados cadastrais e descritivos (*quem, o quê, onde*);  
- **Tabelas de Fatos** → registram eventos e métricas transacionais (*o que aconteceu*).  

Essa separação garante que os dados sejam **organizados**, **íntegros** e que as análises possam ser realizadas de forma **rápida e intuitiva**.

---

### 2.9.1 Modelo Dimensional do Projeto

O **Modelo Dimensional** a seguir ilustra visualmente a estrutura do banco de dados, representando as tabelas, seus respectivos campos e os relacionamentos que as conectam.  

Ele serve como um **mapa lógico** que orienta tanto a **coleta de dados nas planilhas de origem** quanto a **configuração das relações** no ambiente do **Power BI**.


<img width="1001" height="552" alt="der" src="https://github.com/user-attachments/assets/7b481400-e7b4-47f5-9e1a-b5805a735230" />


<img width="1072" height="523" alt="diagrama-classe drawio" src="https://github.com/user-attachments/assets/134fb19f-8244-49ee-8b81-94816f2ea34e" />


---

### 2.9.2 Dicionário de Dados

O **Dicionário de Dados** detalha a finalidade de cada tabela e descreve o propósito de cada um de seus campos.  
Essa documentação técnica é essencial para:

- Desenvolvimento e manutenção da solução;  
- Padronização das informações;  
- Clareza e consistência nas análises e relatórios.

---

### 2.9.3 Tabelas de Dimensão

As **Tabelas de Dimensão** contêm os **dados mestres e descritivos** do projeto.  
Elas constituem a base para a **filtragem**, **segmentação** e **contextualização** dos indicadores apresentados nos dashboards.
