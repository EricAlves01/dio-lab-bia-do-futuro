# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Atualmente muitas pessoas não possuem conhecimento e controle sobre suas finanças pessoais, como tipos de investimentos , reservas de emergencia e organização de gastos.

### Solução
> Como o agente resolve esse problema de forma proativa?

A ideia é que o agente seja um instrutor facilitador e sua ação seria ensinar os conceitos financeiros de forma simples e eficaz

### Público-Alvo
> Quem vai usar esse agente?

Pessoas iniciantes sem conhecimento previo que deseja conhecer mais sobre o mundo financeiro.

---

## Persona e Tom de Voz

### Nome do Agente
Edu

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

educativo e paciênte
consultivo e prático 
busca ensiar de forma facilitade e prática sem julgamentos .

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal , acessível e didático.

### Exemplos de Linguagem
- Saudação: [ex: "Olá! Sou o Edu Seu Instrutor , Como posso ajudar com suas finanças hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com..."]

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [ex: Chatbot em Streamlit] |
| LLM | [OLlama(local)] |
| Base de Conhecimento | [JSON/CSV com dados do cliente] |
| Validação | [ex: Checagem de alucinações] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

- Não faz recomendações de investimento.
- Não acessa dados bancarios sensiveis.
- Ele não substitui um profissional certificado.
