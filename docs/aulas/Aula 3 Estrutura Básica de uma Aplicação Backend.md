# Aula 3: Estrutura Básica de uma Aplicação Back-End

**Código da Aula:** [SIS]ANO2C2B1S1A3  
**Duração:** 50 minutos  
**Semana:** 1

---

## 🎯 O que você vai aprender hoje?

Nesta aula você vai:
- Compreender a estrutura básica de uma aplicação back-end
- Conhecer a arquitetura MVC (Model-View-Controller)
- Entender como organizar código de forma profissional
- Aplicar conceitos de separação de responsabilidades

---

## 🤔 Momento de Reflexão (3 minutos)

**Pense nisso:**

Quando você arruma seu guarda-roupa, provavelmente separa as roupas por tipo: camisetas, calças, meias, etc. Por que fazemos isso? Para encontrar as coisas mais rápido e manter tudo organizado!

💬 **Discussão rápida:** Como vocês organizam seus arquivos no computador? Por pastas? Por tipo de arquivo? Por matéria da escola?

---

## 📚 Contexto: Por que organizar código?

Imagine um projeto com centenas ou milhares de arquivos de código. Se tudo estiver jogado em uma única pasta, seria um caos! 

Por isso, desenvolvedores usam **arquiteturas** - padrões de organização que todo mundo no mercado conhece.

A arquitetura mais comum é o **MVC**.

---

## 🏗️ Arquitetura MVC

### O que significa MVC?

- **M** = Model (Modelo)
- **V** = View (Visualização)
- **C** = Controller (Controlador)

### Como funciona?
```
┌─────────────┐
│    VIEW     │ ← O que o usuário vê
│ (Interface) │
└──────┬──────┘
       │
┌──────▼──────────┐
│   CONTROLLER    │ ← Recebe pedidos e decide o que fazer
│ (Intermediário) │
└──────┬──────────┘
       │
┌──────▼──────┐
│    MODEL    │ ← Dados e regras de negócio
│   (Dados)   │
└─────────────┘
```

---

## 💡 Entendendo Cada Parte

### 🗂️ MODEL (Modelo)

**O que é?** A parte que cuida dos dados.

**Exemplo prático:**
Em um sistema de cadastro de usuários, o Model define:
- Como os dados do usuário são estruturados (nome, email, senha)
- Como salvar no banco de dados
- Como buscar usuários

**Analogia:** É como o arquivo de uma loja que guarda informações de clientes.

---

### 🎨 VIEW (Visualização)

**O que é?** A parte que apresenta informações ao usuário.

**Exemplo prático:**
- Páginas HTML
- Respostas JSON para apps mobile
- Templates de email

**Analogia:** É a vitrine da loja - o que o cliente vê.

---

### 🎮 CONTROLLER (Controlador)

**O que é?** A parte que processa as requisições.

**Exemplo prático:**
Quando um usuário clica em "Cadastrar":
1. Controller recebe os dados
2. Valida se estão corretos
3. Chama o Model para salvar
4. Retorna uma resposta (View)

**Analogia:** É o vendedor que atende o cliente e coordena tudo.

---

## 🎤 Momento de Discussão (5 minutos)

**Vamos analisar juntos:**

Um aplicativo de delivery de comida. Identifique:

1. **O que seria o MODEL?**
   - (Dica: pense nos dados que precisam ser guardados)

2. **O que seria o VIEW?**
   - (Dica: o que você vê no celular?)

3. **O que seria o CONTROLLER?**
   - (Dica: o que acontece quando você faz um pedido?)

💬 Vamos ouvir algumas respostas!

---

## 💻 Atividade Prática: Organize o Sistema (20 minutos)

### Cenário:
Você está desenvolvendo um sistema de biblioteca escolar.

**Funcionalidades:**
- Cadastrar livros
- Cadastrar alunos
- Emprestar livros
- Devolver livros
- Ver histórico de empréstimos

### Sua Tarefa (em grupos de 3-4):

**1. Identifique os Models necessários (8 min)**
   - Quais dados precisam ser guardados?
   - Faça uma lista

**2. Desenhe a estrutura de pastas (7 min)**
   - Como você organizaria os arquivos?
   - Crie um esquema no papel

**3. Defina responsabilidades (5 min)**
   - O que cada Controller faria?
   - Liste as ações

**Exemplo de estrutura:**
```
biblioteca/
  ├── models/
  │   ├── livro.js
  │   └── aluno.js
  ├── controllers/
  │   ├── livroController.js
  │   └── alunoController.js
  └── views/
      └── templates/
```

---

## ✅ Verificação de Aprendizado

**Responda no seu caderno:**

1. O que cada letra do MVC significa?
2. Qual parte do MVC é responsável por salvar dados?
3. Por que separar o código em Models, Views e Controllers é importante?
4. Em um sistema de vendas, onde ficaria a lógica de calcular o troco?

---

## 🎯 Quiz Rápido

**Seu professor vai fazer perguntas. Prepare-se para responder!**

**Situação 1:** Um usuário preenche um formulário de login.
- Qual componente MVC recebe primeiro? (Controller)

**Situação 2:** Preciso alterar a cor do botão na tela.
- Onde mexo? (View)

**Situação 3:** Preciso mudar a forma como as senhas são salvas.
- Onde mexo? (Model)

---

## 💡 Conceitos-Chave

### Separação de Responsabilidades

**Princípio:** Cada parte do código tem uma função específica.

**Benefícios:**
- ✅ Código mais fácil de entender
- ✅ Mais fácil de manter
- ✅ Vários desenvolvedores podem trabalhar ao mesmo tempo
- ✅ Menos bugs
- ✅ Reutilização de código

**Exemplo do mundo real:**
Em uma cozinha de restaurante:
- **Chef** (Controller) - coordena tudo
- **Despensa** (Model) - guarda ingredientes
- **Pratos montados** (View) - o que vai para o cliente

---

## 🏆 Boas Práticas

### Como Nomear Arquivos?

✅ **BOM:**
```
userModel.js
userController.js
productModel.js
```

❌ **RUIM:**
```
arquivo1.js
teste.js
coisa.js
```

### Como Organizar Pastas?

✅ **BOM:**
```
projeto/
  ├── models/
  ├── controllers/
  ├── views/
  ├── config/
  └── utils/
```

❌ **RUIM:**
```
projeto/
  └── tudo_junto.js
```

---

## 📝 Atividade para Casa

### Mini-Projeto: Planeje sua Aplicação

**Escolha UM sistema:**
- Sistema de controle de notas escolares
- App de lista de tarefas
- Sistema de agendamento de consultas

**Faça no caderno:**

1. **Liste os Models necessários (5)**
   - Exemplo: Model Aluno (nome, matrícula, turma)

2. **Liste as ações dos Controllers (5)**
   - Exemplo: cadastrar aluno, buscar aluno por matrícula

3. **Desenhe uma estrutura de pastas**
   - Onde cada arquivo ficaria?

4. **Explique com suas palavras**
   - Por que você organizou assim?

**Formato:** Pode ser desenho, lista ou texto. O importante é mostrar que entendeu!

---

## 🔗 Material de Apoio

- 📊 Slides da aula: [Disponível no AVA]
- 📖 Artigo: "Padrão MVC" - Dev.to
- 🎥 Vídeo complementar: "Arquitetura de Software" - Código Fonte TV
- 💾 Exemplo de código MVC simples: [Repositório GitHub]

---

## 🤔 Reflexão Final (2 minutos)

**Pense sobre o que aprendeu hoje:**

✏️ Complete mentalmente:
- "Antes eu pensava que back-end era ______"
- "Agora eu sei que é importante ______"
- "Uma coisa que vou aplicar é ______"

---

## 📌 Entrega

Tire uma foto da sua atividade prática (estrutura do sistema de biblioteca) e envie no AVA até a próxima aula.

---

## 🚀 Próxima Semana

**Tema:** Introdução a linguagens de programação back-end  
**Prepare-se:** Vamos começar a programar de verdade! 💻

---

## 💭 Frase da Aula

> "Código limpo não é escrito seguindo regras. Código limpo é escrito por desenvolvedores que se importam com o código." - Robert C. Martin

---

**Dica Extra:** Quando estiver desenvolvendo, sempre pergunte: "Isso está na camada certa?" 🎯