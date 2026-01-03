## Car Rental Corporate Assistant 🚗🤖

Este projeto é uma aplicação Spring Boot que utiliza a biblioteca LangChain4j para integrar o modelo Google Gemini. O objetivo é fornecer um assistente inteligente capaz de processar solicitações sobre aluguéis de carros de uma locadora corporativa, utilizando chamadas de ferramentas (Function Calling) para acessar dados em tempo real.

🚀 Funcionalidades
Processamento de Linguagem Natural: Interação fluida com o cliente através do Google Gemini.

Agentic AI: O assistente não apenas responde perguntas, mas também executa ações através da classe AssistantTools.

Integração Spring: Utiliza as anotações do Spring para gerenciar o ciclo de vida do serviço e das configurações.

## 🛠️ Tecnologias Principais
Java 17+

Spring Boot 3.x

LangChain4j: Integração simplificada com LLMs.

Google Gemini API: O "cérebro" do assistente.

## Dependências Maven (Principais)

  
    <dependency>
        <groupId>dev.langchain4j</groupId>
        <artifactId>langchain4j-google-ai-gemini-spring-boot-starter</artifactId>
        <version>1.7.1-beta14</version>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>

## ⚙️ Como Funciona
Entrada do Usuário: O cliente envia uma mensagem via AssistantController.

Orquestração: O AssistantAiService envia a mensagem para o Google Gemini.

Execução de Ferramentas: Se o modelo identificar que precisa de informações específicas (ex: preços, disponibilidade), ele aciona os métodos anotados na classe AssistantTools.

Resposta: O modelo processa o retorno da ferramenta e entrega uma resposta humanizada ao cliente.

## 🔧 Configuração e Execução
Chave de API: Obtenha uma chave de API do Google AI Studio.

Application Properties: Adicione sua chave ao arquivo src/main/resources/application.properties:

Properties

    langchain4j.google-ai-gemini.api-key=${GOOGLE_AI_GEMINI_API_KEY}
    langchain4j.google-ai-gemini.model-name=gemini-1.5-flash

## Executar:

Bash

mvn spring-boot:run


## 📝 Exemplo de Uso
Request: POST /assistant/chat

JSON

{
  "message": "Quais carros econômicos estão disponíveis para a próxima segunda-feira?"
}

## Response:

JSON

{
  "response": "Atualmente temos o VW Gol e o Fiat Uno disponíveis na categoria econômica para esta data. Gostaria de prosseguir com a reserva?"
}
