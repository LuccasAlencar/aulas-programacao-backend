# Aula 2 – Configuração do Ambiente de Desenvolvimento Back-End
**Componente:** Programação Back-End  
**Unidade:** Introdução à Programação Back-End e Conceitos de Desenvolvimento para Web  
**Duração aproximada:** 50 minutos  
**Ano:** 3º ano do Ensino Médio Técnico (ANO2)

---

# 1. Antes de codar, você precisa de um ambiente!

Na aula passada você aprendeu o que é back-end. Agora vem a próxima pergunta:

> **Onde o desenvolvedor back-end escreve e roda o código?**

A resposta é: no **ambiente de desenvolvimento** — um conjunto de ferramentas instaladas no computador que permitem criar, testar e executar aplicações.

Pense assim:

> **Cozinheiro sem fogão, facas e panelas** não cozinha nada. 👨‍🍳  
> **Desenvolvedor sem ambiente configurado** não desenvolve nada. 💻

Configurar o ambiente é o **primeiro passo prático** de qualquer projeto back-end.

---

# 2. O que compõe um ambiente de desenvolvimento?

Um ambiente back-end bem configurado tem três partes principais:

| Parte | O que é | Exemplos |
|-------|---------|---------|
| **Editor de código (IDE)** | Onde você escreve o código | VS Code, IntelliJ |
| **Servidor / Runtime** | O que executa o código no servidor | Node.js, Apache |
| **Gerenciador de dependências** | Instala e organiza bibliotecas | npm, pip, Maven |

Cada linguagem back-end tem suas ferramentas preferidas. Vamos conhecer as principais!

---

# 3. O Editor de Código — VS Code

O **Visual Studio Code (VS Code)** é o editor mais usado por desenvolvedores back-end no mundo. É gratuito, leve e funciona em Windows, Mac e Linux.

### Por que o VS Code é tão popular?

- Suporta **todas as linguagens** back-end: Python, JavaScript, Java, C# e muito mais
- Tem **destaque de sintaxe** — o código fica colorido, mais fácil de ler
- Permite instalar **extensões** que adicionam funcionalidades extras
- Possui **terminal integrado** — você não precisa sair do editor para rodar comandos
- Integra com **Git** para controle de versão

> 💡 **VS Code não é compilador nem servidor** — ele é só o lugar onde você *escreve* o código. Para *executar*, você precisa de outra ferramenta.

---

# 4. O Servidor — Node.js e Apache

Depois de escrever o código, alguém precisa **executá-lo** e **responder às requisições** dos usuários. Esse é o papel do servidor.

### Node.js

O **Node.js** permite que o JavaScript — que você provavelmente já usou no front-end — rode também no servidor (back-end).

- Criado em 2009 por Ryan Dahl
- Baseado no motor V8 do Google Chrome
- Ideal para aplicações em **tempo real** (chats, notificações ao vivo)
- Usa o conceito de **fluxo de dados assíncrono** — consegue atender muitos usuários ao mesmo tempo sem travar

> 🍕 **Analogia:** Imagine um garçom que, em vez de esperar cada pedido ficar pronto antes de atender o próximo, anota todos os pedidos e avisa cada mesa quando o prato chega. Isso é o Node.js: eficiente e não-bloqueante.

### Apache HTTP Server

O **Apache** é um dos servidores web mais antigos e confiáveis do mundo, criado em 1995.

- Atua como **intermediário** entre o navegador do usuário e a aplicação back-end
- Gerencia as **requisições HTTP**
- Oferece recursos avançados de **segurança** (SSL/TLS, controle de acesso)
- Muito usado com PHP e aplicações web tradicionais

| | Node.js | Apache |
|-|---------|--------|
| Linguagem principal | JavaScript | PHP, Python, etc. |
| Melhor para | Tempo real, APIs | Sites tradicionais |
| Modelo | Assíncrono | Baseado em processos |

---

# 5. Atividade 1 – Responda no Caderno

1. O que é um ambiente de desenvolvimento?
2. Qual é a diferença entre um editor de código (como o VS Code) e um servidor (como o Node.js)?
3. Para que serve o Apache?

---

# 6. Gerenciamento de Dependências

Quando você desenvolve uma aplicação, não precisa criar tudo do zero. Existem **bibliotecas** — pacotes de código pronto — que resolvem problemas comuns.

**Dependências** são essas bibliotecas que seu projeto precisa para funcionar.

O **gerenciador de dependências** é a ferramenta que:
- Baixa as bibliotecas automaticamente
- Garante que as versões sejam compatíveis
- Facilita o trabalho em equipe (todos usam as mesmas versões)

### Principais gerenciadores por linguagem

| Linguagem | Gerenciador | Comando para instalar algo |
|-----------|-------------|---------------------------|
| JavaScript (Node.js) | **npm** | `npm install nome-da-biblioteca` |
| Python | **pip** | `pip install nome-da-biblioteca` |
| Java | **Maven** | Configurado no arquivo `pom.xml` |
| C# (.NET) | **NuGet** | `dotnet add package nome` |

> 📝 **Exemplo prático:** Imagine que você quer enviar e-mails pela sua aplicação. Em vez de programar tudo isso do zero, você instala uma biblioteca de e-mail com um único comando. É isso que o gerenciador de dependências faz!

---

# 7. O Fluxo Completo do Ambiente

Veja como as ferramentas se conectam no dia a dia de um desenvolvedor:

```
[VS Code] → você escreve o código
    ↓
[Node.js / Apache] → executa o código no servidor
    ↓
[npm / pip / Maven] → garante que as bibliotecas necessárias estão instaladas
    ↓
[Aplicação rodando] → responde às requisições dos usuários
```

Cada peça tem seu papel. Remova uma e o processo trava.

---

# 8. Atividade Principal – Montando seu Ambiente (no Caderno)

### Situação:
Você foi contratado(a) como desenvolvedor(a) júnior em uma startup. Seu primeiro projeto é criar uma **API de cadastro de usuários**. Seu gerente te pediu para escolher e justificar as ferramentas do ambiente de desenvolvimento.

### Sua tarefa:

Monte uma tabela no caderno com as seguintes colunas:

| Ferramenta | Categoria | Por que escolheu? |
|------------|-----------|-------------------|
| (preencha) | (preencha) | (preencha) |

**Escolha uma opção para cada categoria:**

- **Editor de código:** VS Code *ou* Notepad (editor simples)
- **Servidor/Runtime:** Node.js *ou* nenhum (escrever no papel)
- **Gerenciador de dependências:** npm *ou* baixar tudo manualmente

### Reflexão (responda no caderno):
Qual seria o problema de tentar desenvolver sem essas ferramentas configuradas?

---

### Gabarito esperado:

| Ferramenta | Categoria | Por que escolheu? |
|------------|-----------|-------------------|
| VS Code | Editor de código | Suporta várias linguagens, tem terminal integrado e extensões |
| Node.js | Servidor/Runtime | Executa JavaScript no servidor, ideal para APIs |
| npm | Gerenciador de dependências | Instala e controla as versões das bibliotecas automaticamente |

**Reflexão:** Sem as ferramentas, o código não executaria, as bibliotecas precisariam ser baixadas e gerenciadas manualmente (risco de erros de versão), e o desenvolvimento seria muito mais lento e propenso a problemas.

---

# 9. Desafio Extra — Ser Sempre +

### Situação real:

Você está configurando o ambiente e descobre que o projeto usa **Node.js**, mas você nunca trabalhou com essa tecnologia — só conhece Python.

**Responda no caderno:**

1. Como você avaliaria se o Node.js é a ferramenta certa para o projeto?
2. Que estratégias usaria para aprender rapidamente?
3. Como comunicaria essa situação ao seu gerente sem perder a confiança dele?

> 💬 **Dica:** Desenvolvedores back-end aprendem novas ferramentas o tempo todo. A curiosidade e a persistência são habilidades tão importantes quanto saber programar.

---

# 10. Revisão – O que aprendemos hoje?

✔ O que é um ambiente de desenvolvimento back-end  
✔ O papel do editor de código (VS Code)  
✔ A diferença entre Node.js e Apache  
✔ O que são dependências e para que serve o gerenciador  
✔ Como as ferramentas se conectam no fluxo de desenvolvimento

---

# 11. Para aprender mais

- [O que é Node.js? (Código Fonte TV)](https://www.youtube.com/watch?v=vYekSMBCCiM)  
- [VS Code para iniciantes (Curso em Vídeo)](https://www.youtube.com/watch?v=uxln1gHMV0I)  
- [Boas práticas de programação com Fabio Akita (Alura)](https://www.youtube.com/watch?v=GUanHEGlje4)  
- https://nodejs.org/pt — Site oficial do Node.js (em português)
