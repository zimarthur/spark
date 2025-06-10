# 🚀 Spark Local Cluster com Docker

Este repositório configura um cluster local do Apache Spark usando Docker Compose. Ele inclui:

- Um **Spark Master**
- Dois **Spark Workers**
- Um **Jupyter Notebook** com suporte a PySpark
- Um **Notebook** com exemplos para aprender Spark

---

## 🧱 Estrutura do Projeto

- docker-compose.yml # Configuração do cluster Spark + Jupyter
- notebooks/tutorial.ipynb #notebook com exercicios do Spark
- notebooks/datasets #local onde as fontes de dados devem estar

## ⚙️ Requisitos

Certifique-se de ter os seguintes requisitos instalados:

- [Docker](https://www.docker.com/)

---

## 📦 Serviços

| Serviço        | Descrição                         | Porta Exposta                 |
| -------------- | --------------------------------- | ----------------------------- |
| `spark-master` | Nó mestre do cluster Spark        | `8080` (UI), `7077`           |
| `spark-worker` | Nós trabalhadores do cluster      | -                             |
| `jupyter`      | Ambiente de notebooks com PySpark | `8888` (UI), `4040`(Spark UI) |

---

## ▶️ Como Usar

### 1. Clone o repositório

```bash
git clone git@github.com:zimarthur/spark.git
cd seu-repo
```

### 2. Baixe os datasets de demonstração

Google drive:
https://drive.google.com/drive/folders/18ODSwR8QKpdnZ3W77iLHp4Z1pq43NYqE?usp=drive_link

Depois de baixar, coloque os arquivos na pasta:

```
notebooks/datasets
```

### 3. Inicie o cluster

Execute o comando para iniciar os containers descritos no docker-compose.yml.

```
docker-compose up
```

(se aparecer algum erro como "unable to get image...", verifique se o serviço do docker está ativo)

### 4. Abra o notebook dentro do Jupyter

Veja nos logs da inicialização do container, um link de acesso para o Jupyter.  
Vai ser um link apontando para a porta 8888 no localhost (como definimos no docker-compose), como esse:

```
http://127.0.0.1:8888/lab?token=63fbe81a824f213558ffe552aa18ebef464b7ac67aa59ad4
```

### 5. Execute as consultas no notebook

Dentro do Jupyter, entre no arquivo tutorial.ipynb e comece a fazer suas consultas.  
Não esqueça de iniciar a sessão do Spark
