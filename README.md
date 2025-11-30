# AITaskRefiner 🚀

O **AITaskRefiner** é uma ferramenta de Engenharia de Prompt assistida por IA que ajuda desenvolvedores a refinarem seus pedidos para LLMs, utilizando técnicas avançadas como *Chain-of-Thought*, *Few-Shot Prompting* e RAG.

O projeto é dividido em:
- **Backend:** Python com FastAPI, LangChain e ChromaDB/FAISS.
- **Frontend:** React com Vite.

---

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:
1.  **Python (3.10 ou superior):** [Baixar Python](https://www.python.org/downloads/)
2.  **Node.js (Versão LTS):** [Baixar Node.js](https://nodejs.org/)

---

## ⚙️ Instalação e Configuração

### 1. Configurar o Backend (API)

Entre na pasta do backend:
```
cd back
```

#### Passo 1.1: Criar as Chaves de Acesso 

Crie um arquivo chamado .env dentro da pasta back e adicione sua chave da OpenAI:
```
OPENAI_API_KEY=sk-proj-sua-chave-aqui...
```
#### Passo 1.2: Instalar Dependências
 Como o projeto utiliza bibliotecas específicas de IA e vetores, rode o seguinte comando para instalar tudo de uma vez:

 ```
pip install fastapi "uvicorn[standard]" pydantic python-dotenv openai langchain langchain-community langchain-openai chromadb tiktoken faiss-cpu
 ```

 **Nota:** Usamos faiss-cpu para garantir compatibilidade com a maioria dos computadores sem GPU dedicada.

### 2. Configurar o Frontend (Interface)
Abra um novo terminal, volte para a raiz e entre na pasta do frontend:
```
cd front
```

Instale as dependências do Node:
```
npm install
```
**Erro no Windows?** Se receber um erro sobre "execução de scripts desabilitada", rode este comando no PowerShell como Administrador (ou apenas para o usuário atual) e tente o npm install novamente: Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

## 🚀 Como Executar o Projeto
Você precisará de dois terminais abertos simultaneamente.

Terminal 1: Rodar a API (Backend)
Dentro da pasta back (```cd back```), inicie o servidor com o Uvicorn:

```
uvicorn api:app --reload
```
Aguarde aparecer a mensagem: *Application startup complete.*

Terminal 2: Rodar a Interface (Frontend)
Dentro da pasta front (```cd front```), inicie o servidor de desenvolvimento:

```
npm run dev
```

Agora, abra o navegador no link indicado (geralmente http://localhost:5173) e utilize a ferramenta.

## 🛠️ Solução de Problemas Comuns

| Erro | Solução |
| -------- | ----- |
| ModuleNotFoundError: No module named 'faiss' | Você instalou a versão errada. Rode pip install faiss-cpu. |
| O termo 'npm' não é reconhecido | Você não instalou o Node.js. Instale e reinicie o VS Code. |
| Erro de conexão no Frontend | Verifique se o terminal do Backend (Python) está rodando sem erros. |