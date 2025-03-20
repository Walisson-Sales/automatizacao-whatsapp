<h1 align="center">Integração do Evolution API com n8n</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Concluído-brightgreen" alt="Status do Projeto">
  <img src="https://img.shields.io/badge/Plataforma-n8n-blue" alt="Plataforma">
  <img src="https://img.shields.io/badge/API-Evolution%20API-orange" alt="API">
</p>

<p align="center">
  Este projeto visa integrar a <strong>Evolution API</strong> com o <strong>n8n</strong> para automatizar fluxos de trabalho envolvendo o WhatsApp.
</p>

---

## 🌟 Visão Geral

A **Evolution API** é uma solução poderosa para integração com o WhatsApp, permitindo o envio e recebimento de mensagens de forma programática. Já o **n8n** é uma ferramenta de automação de fluxos de trabalho que facilita a criação de integrações entre diferentes serviços.

Esta integração permite:
- Enviar mensagens via WhatsApp de forma automatizada.
- Receber e processar mensagens do WhatsApp.
- Criar fluxos de trabalho personalizados utilizando o n8n.

---

## 🛠️ Pré-requisitos

Antes de começar, certifique-se de ter:

- **Docker** instalado e configurado na sua máquina ou servidor.
- Um contêiner Docker rodando a **Evolution API** (certifique-se de ter o token de autenticação e a URL do servidor).
- Um contêiner Docker com o **n8n** configurado e em execução.
- Um servidor n8n configurado (local ou em nuvem).
- Credenciais de acesso à API (token, URL do servidor, etc.).
- Conhecimento básico de como o n8n funciona e como gerenciar contêineres Docker.

---

## 🚀 Instalação e Configuração
### 1. Clone o Repositório
- `git clone https://github.com/Walisson-Sales/automatizacao-whatsapp.git`
- Acesse a pasta onde você fez a clonagem, exemplo: `cd "D:/projetos/automatizacao-whatsapp"`

### 2. Configuração do arquivo .env
- Renomeie o arquivo `.env.example` para `.env`
- Edite o `.env` com suas credenciais do n8n e da evolution api

### 3. Inicie os Contêineres com Docker Compose
- Abra um terminal no docker e execute o seguinte comando: `docker-compose up -d`

  #### Isso irá:
    - Criar uma rede Docker personalizada.
    - Iniciar o Evolution API na porta `8080`.
    - Iniciar o n8n na porta `5678`.

### 4. Configuração da Evolution API
- Acesse o painel manager da Evolution API atráves de `http://localhost:8080/manager` (padrão)
- Entre com as credenciais que você configurou no arquivo `.env` (token e URL do servidor).
- Adicione uma nova instância, click no símbolo de configuraçõe, em seguida, gere e escaneie o qr code com seu telefone.
- Em **"Events/Webhook"** você poderar abilitar e configurar o seu webhook.

### 5. Configuração do n8n
- Acesse o n8n através do `http://localhost:5678`. (padrão)
- Crie a sua conta no n8n.

---

## 🎯 Como Usar
### 2. **Receber Mensagens**:
- No n8n, adicione um novo **nó de Webhook** para se conectar à Evolution API.
- Configure o nó alterando o **HTTP Method para POST**, você também pode alterar o path (opcional).
- Mude para **Production URL e copie a URL**.
- No canto superior direito, ative o workflow (mude de "inactive" para "active").
- Abra a parte de **Executions** do n8n.
- **No painel da Evolution API, cole a URL copiada na seção de configuração do webhook e salve.**.
- Teste a conexão enviando ou recebendo alguma mensagem.

---

## 📊 Status do Projeto

✅ **Funcionalidades Atuais**
- Docker, Evolution API e n8n estão configurados e funcionando.
- Comunicação entre os serviços está estabelecida.
- Envio/recebimento de textos via WhatsApp com respostas em tempo real.

⚠️ **Em Desenvolvimento**
- Testar cenários avançados de envio/recebimento de mensagens.  
- Adicionar exemplos de workflows na documentação.
-Suporte a Mídias:
  -Identificação de áudios, imagens e figurinhas.
  -Armazenamento em cloud ou sistema local.
-Aprimoramento da IA:
  -Respostas contextualizadas com histórico de conversas.
  -Filtragem de conteúdo sensível.
-Monitoramento: Dashboard para acompanhamento de métricas e logs.

---

## 🛠️ Exemplo de Fluxo  
![Workflow no n8n](./imagens/fluxo%20basico%20no%20n8n.png)  
*Fluxo atual: Mensagem recebida → IA processa → Resposta enviada via Evolution API.*  

---

## 🤝 Contribuição

Contribuições são bem-vindas! Siga os passos abaixo:

1. Faça um fork do projeto.
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`).
3. Commit suas mudanças (`git commit -m 'Adicionando nova feature'`).
4. Push para a branch (`git push origin feature/nova-feature`).
5. Abra um Pull Request.

---

<p align="center">
  Feito por <strong>Wálisson Sales</strong>
</p>