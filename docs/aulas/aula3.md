# Aula 3 – Estrutura Básica de uma Aplicação Back-End
**Componente:** Programação Back-End  
**Unidade:** Introdução à Programação Back-End e Conceitos de Desenvolvimento para Web  
**Duração aproximada:** 50 minutos  
**Ano:** 3º ano do Ensino Médio Técnico (ANO2)

---

# 1. Como o código back-end é organizado?

Nas aulas anteriores você aprendeu o que é back-end e como configurar o ambiente. Agora vem a próxima pergunta:

> **Quando um sistema cresce, com dezenas de arquivos e funcionalidades, como não virar um caos?**

A resposta é: usando uma **arquitetura** — uma forma padronizada de organizar o código.

Pense assim:

> **Uma cozinha sem organização** vira bagunça: ingredientes misturados, pratos em lugares errados. 🍳  
> **Uma cozinha organizada** tem cada coisa no seu lugar: despensa, fogão, pia. 🏠

No back-end, a arquitetura mais famosa e usada no mundo é a **MVC**.

---

# 2. O que é MVC?

**MVC** significa **Model – View – Controller** (Modelo – Visão – Controlador).

É um padrão que divide a aplicação em **três partes**, cada uma com uma responsabilidade bem clara:

| Parte | Nome em português | O que faz |
|-------|------------------|-----------|
| **Model** | Modelo | Representa os dados e as regras de negócio |
| **View** | Visão | Formata e apresenta a resposta ao usuário |
| **Controller** | Controlador | Recebe a requisição, coordena Model e View |

> 💡 **Cada parte cuida de uma coisa só.** Isso é o princípio da responsabilidade única — e é uma das boas práticas mais importantes no desenvolvimento de software.

---

# 3. Entendendo cada parte com um exemplo real

Imagine um sistema de **cadastro de usuários** de uma escola. Veja como o MVC funciona nesse contexto:

### 🗄️ Model — Os dados

O Model define a **estrutura dos dados** e as **regras sobre eles**.

Exemplo: o que é um "usuário" no sistema?
- nome
- e-mail
- senha
- data de cadastro

O Model também garante regras como: *"o e-mail não pode se repetir"* ou *"a senha precisa ter pelo menos 8 caracteres"*.

---

### 🖥️ View — A resposta formatada

No back-end, a View não é uma tela visual — é a **formatação da resposta** que será enviada para o front-end ou para outro sistema.

Exemplo: quando o cadastro é feito com sucesso, a View decide como informar isso:

```
{
  "mensagem": "Usuário cadastrado com sucesso!",
  "id": 42
}
```

---

### ⚙️ Controller — O intermediário

O Controller é o **cérebro da operação**. Ele:
1. Recebe a requisição do usuário
2. Chama o Model para manipular os dados
3. Chama a View para formatar a resposta
4. Devolve a resposta final

> 🍕 **Analogia:** Se o sistema fosse um restaurante, o Controller seria o garçom — recebe o pedido, leva para a cozinha (Model), e traz o prato formatado (View) para o cliente.

---

# 4. O Fluxo MVC na prática

Veja como uma requisição percorre as três camadas:

```
Usuário faz uma requisição
        ↓
   [CONTROLLER]
   Recebe e coordena
        ↓              ↓
    [MODEL]          [VIEW]
  Busca/salva      Formata a
    os dados        resposta
        ↓              ↓
   [CONTROLLER]
   Une tudo e responde
        ↓
  Resposta chega ao usuário
```

---

# 5. A Estrutura de Pastas de um Projeto MVC

Uma das grandes vantagens do MVC é que ele define como **organizar os arquivos** do projeto. Veja um exemplo de estrutura de pastas:

```
UserManagement/
│
├── models/
│   └── userModel.js       ← define os dados do usuário
│
├── views/
│   └── userView.js        ← formata as respostas
│
├── controllers/
│   └── userController.js  ← lógica das requisições
│
└── index.js               ← ponto de entrada da aplicação
```

> 📝 **Regra de ouro:** Se alguém novo entrar no projeto, deve conseguir entender onde cada coisa está só olhando a estrutura de pastas.

---

# 6. Atividade 1 – Responda no Caderno

1. O que significa a sigla MVC?
2. Qual parte do MVC é responsável pelos dados e pelas regras de negócio?
3. O que o Controller faz?
4. Por que organizar o código em camadas é uma boa prática?

---

# 7. Por que usar MVC?

| Sem MVC | Com MVC |
|---------|---------|
| Código misturado e difícil de ler | Cada responsabilidade no lugar certo |
| Difícil de encontrar bugs | Fácil de identificar onde está o problema |
| Complicado trabalhar em equipe | Vários devs podem trabalhar em partes diferentes |
| Difícil de expandir o sistema | Fácil de adicionar novas funcionalidades |

> 🤝 **Cooperação:** O MVC facilita o trabalho em equipe porque um desenvolvedor pode mexer no Model sem interferir no trabalho de outro que está no Controller. Cada um cuida da sua parte!

---

# 8. Atividade Principal – Desenhando seu MVC no Caderno

### Situação:
Você foi designado(a) para criar a estrutura back-end de um **sistema de biblioteca escolar**. O sistema deve permitir: cadastrar livros, buscar livros e registrar empréstimos.

### Sua tarefa:

**Parte A — Estrutura de pastas**

Desenhe no caderno a estrutura de pastas do projeto seguindo o padrão MVC. Crie pelo menos um arquivo dentro de cada pasta.

**Parte B — Responsabilidades**

Preencha a tabela abaixo no caderno:

| Funcionalidade | Qual parte do MVC? | Por quê? |
|---------------|-------------------|----------|
| Guardar os dados de um livro (título, autor, ISBN) | | |
| Receber a requisição "buscar livro por título" | | |
| Formatar a lista de livros para enviar como resposta | | |
| Verificar se o livro já está emprestado | | |

**Parte C — Reflexão**

Responda no caderno:
1. Como o MVC ajuda a manter o código organizado e escalável?
2. O que aconteceria se colocássemos toda a lógica em um único arquivo?

---

### Gabarito esperado:

**Parte A — Estrutura sugerida:**
```
BibliotecaEscolar/
├── models/
│   ├── livroModel.js
│   └── emprestimoModel.js
├── views/
│   └── livroView.js
├── controllers/
│   ├── livroController.js
│   └── emprestimoController.js
└── index.js
```

**Parte B — Tabela:**

| Funcionalidade | Qual parte do MVC? | Por quê? |
|---------------|-------------------|----------|
| Guardar dados de um livro | **Model** | É a estrutura dos dados |
| Receber requisição de busca | **Controller** | Coordena a operação |
| Formatar lista de livros | **View** | Apresenta os dados |
| Verificar se livro está emprestado | **Model** | É uma regra de negócio |

**Parte C:** O MVC separa as responsabilidades, tornando mais fácil manter e expandir o sistema. Sem essa separação, um único arquivo enorme ficaria impossível de entender, testar e modificar com segurança.

---

# 9. Revisão – O que aprendemos hoje?

✔ O que é a arquitetura MVC e para que serve  
✔ O papel de cada camada: Model, View e Controller  
✔ Como organizar a estrutura de pastas de um projeto back-end  
✔ Por que separar responsabilidades torna o código melhor  
✔ Como o MVC facilita o trabalho em equipe

---

# 10. Para aprender mais

- [O que é MVC? (Código Fonte TV)](https://www.youtube.com/watch?v=mMDt9g7bMjk)
- [Arquitetura MVC explicada (Alura)](https://www.alura.com.br/artigos/mvc-arquitetura)
- [Boas práticas de programação com Fabio Akita](https://www.youtube.com/watch?v=GUanHEGlje4)