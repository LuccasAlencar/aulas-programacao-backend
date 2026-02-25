# Aula 4 – Fundamentos de Redes e Protocolos
**Componente:** Programação Back-End  
**Unidade:** Redes e Segurança em Desenvolvimento para Web  
**Duração aproximada:** 50 minutos  
**Ano:** 3º ano do Ensino Médio Técnico (ANO2)

---

# 1. Como dois computadores se entendem?

Você já parou para pensar no que acontece quando você digita um endereço no navegador e a página aparece?

> Você está em São Paulo. O servidor pode estar nos Estados Unidos. Em menos de 1 segundo, uma mensagem foi enviada, recebida e respondida — atravessando continentes. 🌎

Isso só é possível porque existem **protocolos** — regras padronizadas que todos os dispositivos seguem para se comunicar.

É como um **idioma universal das máquinas**: sem ele, cada computador "falaria" de um jeito diferente e ninguém se entenderia.

---

# 2. O que é um Protocolo?

Um **protocolo de rede** é um conjunto de regras que define:
- Como os dados são **formatados**
- Como são **enviados**
- Como são **recebidos**
- O que fazer quando algo **dá errado**

> 🤝 **Analogia:** Pense em uma ligação telefônica. Existe um "protocolo humano": você atende, diz "alô", a pessoa se identifica, vocês conversam em turnos, um diz "tchau" para encerrar. Sem essas regras, a comunicação viraria caos.

---

# 3. TCP/IP — A Espinha Dorsal da Internet

O **TCP/IP** (Transmission Control Protocol / Internet Protocol) é o conjunto de protocolos que faz a internet funcionar. Todo dado que trafega pela internet passa pelo TCP/IP.

Ele é organizado em **quatro camadas**, cada uma com uma função:

| Camada | Nome | O que faz | Exemplo |
|--------|------|-----------|---------|
| 4 | **Aplicação** | Interface com o usuário | HTTP, HTTPS, FTP |
| 3 | **Transporte** | Garante que os dados chegam | TCP, UDP |
| 2 | **Internet** | Endereçamento e roteamento | IP |
| 1 | **Rede/Acesso** | Transmissão física dos dados | Wi-Fi, cabo |

> 💡 Pense nas camadas como os andares de um prédio: cada andar cuida de uma parte do trabalho, e juntos fazem o prédio funcionar.

### O papel do TCP

O **TCP** (Transmission Control Protocol) garante que os dados cheguem **completos e na ordem certa**. Se um pacote se perder no caminho, o TCP pede reenvio automaticamente.

### O papel do IP

O **IP** (Internet Protocol) é responsável pelo **endereçamento** — cada dispositivo conectado à internet tem um endereço IP único, como um CEP da internet.

Exemplo de endereço IP: `192.168.1.1` (IPv4) ou `2001:db8::1` (IPv6)

---

# 4. HTTP — A Linguagem da Web

**HTTP** (Hypertext Transfer Protocol) é o protocolo que o seu navegador usa para conversar com servidores web. Toda vez que você acessa um site, está usando HTTP.

### Como funciona o ciclo HTTP:

```
Você digita uma URL no navegador
         ↓
Navegador envia uma REQUISIÇÃO HTTP ao servidor
         ↓
Servidor processa a requisição
         ↓
Servidor envia uma RESPOSTA HTTP
         ↓
Navegador exibe o resultado para você
```

### Os Métodos HTTP

Toda requisição HTTP usa um **método** que indica o que o cliente quer fazer:

| Método | O que faz | Exemplo real |
|--------|-----------|--------------|
| **GET** | Busca dados | Carregar uma página |
| **POST** | Envia dados | Fazer login, enviar formulário |
| **PUT** | Atualiza dados | Editar perfil |
| **DELETE** | Remove dados | Deletar uma conta |

### Os Códigos de Status

Toda resposta HTTP vem com um **código de status** que informa o resultado:

| Código | Significado | Quando acontece |
|--------|-------------|----------------|
| **200** | OK — Sucesso ✅ | Página carregou normalmente |
| **201** | Criado ✅ | Cadastro realizado |
| **404** | Não encontrado ❌ | Página inexistente |
| **500** | Erro do servidor ❌ | Bug na aplicação |

> 🔍 **Curiosidade:** Você provavelmente já viu o erro 404 — ele aparece quando você tenta acessar uma página que não existe mais!

---

# 5. Atividade 1 – Responda no Caderno

1. O que é um protocolo de rede? Por que ele é necessário?
2. Qual é a diferença entre TCP e IP?
3. Cite dois métodos HTTP e explique para que servem.
4. O que significa o código de status 404?

---

# 6. HTTPS — O HTTP com Segurança

**HTTPS** (HTTP Secure) é a versão **segura** do HTTP. A diferença está na letra **S**, que significa que a comunicação é **criptografada**.

### O que é criptografia?

Criptografar significa **embaralhar os dados** de forma que só quem tem a "chave" consegue ler. É como enviar uma mensagem em código secreto.

O HTTPS usa o protocolo **SSL/TLS** para fazer essa criptografia.

### HTTP x HTTPS

| | HTTP | HTTPS |
|-|------|-------|
| Criptografia | ❌ Não | ✅ Sim |
| Dados protegidos | ❌ Não | ✅ Sim |
| Cadeado no navegador | ❌ Não | ✅ Sim |
| Ideal para | Sites informativos simples | Qualquer site com login ou pagamento |

> 🔒 **Regra de ouro:** Se um site pede sua senha ou dados de cartão, verifique se o endereço começa com `https://` e se há um cadeado 🔒 na barra do navegador. Se não tiver, **não insira seus dados!**

### Por que isso importa para o back-end?

Como desenvolvedor(a) back-end, é **sua responsabilidade** garantir que a aplicação use HTTPS. Se você deixar dados de usuários trafegarem sem criptografia, você está colocando em risco senhas, dados pessoais e informações financeiras.

---

# 7. O Modelo Cliente-Servidor

Todo o tráfego da internet segue o **modelo cliente-servidor**:

- **Cliente** = quem faz o pedido (navegador, app, outro sistema)
- **Servidor** = quem responde o pedido (sua aplicação back-end)

```
[CLIENTE]                    [SERVIDOR]
Navegador  ──requisição──►  Aplicação back-end
           ◄──resposta────  (Node.js, Python, etc.)
```

Esse modelo define como você vai **projetar e desenvolver** qualquer aplicação web. Toda vez que você cria uma rota no back-end, você está programando o que o servidor vai responder quando o cliente fizer um determinado pedido.

---

# 8. Atividade Principal – Proposta de Segurança no Caderno

### Situação:
Você é desenvolvedor(a) back-end numa startup que vai lançar um app de pagamentos. O gerente de projeto pediu uma proposta escrita explicando como garantir a segurança na comunicação entre os usuários e o servidor.

### Sua tarefa:

Escreva no caderno uma **proposta de segurança** respondendo às perguntas abaixo. Use o que aprendeu sobre HTTP, HTTPS, TCP/IP e o modelo cliente-servidor.

**1. Por que o app deve usar HTTPS e não HTTP?**  
Explique em suas próprias palavras o risco de usar HTTP em um app de pagamentos.

**2. O que é o SSL/TLS e qual é a sua função?**  
Descreva o que ele faz sem precisar entrar em detalhes técnicos profundos.

**3. Complete o fluxo abaixo no caderno, descrevendo o que acontece em cada etapa:**

```
Usuário abre o app de pagamentos
             ↓
     [etapa 1 — o que acontece?]
             ↓
     [etapa 2 — o que acontece?]
             ↓
     [etapa 3 — o que acontece?]
             ↓
  Pagamento confirmado na tela
```

---

### Gabarito esperado:

**1.** O HTTP não criptografa os dados, então qualquer pessoa "escutando" a rede poderia interceptar senhas e números de cartão. Um app de pagamentos lida com informações extremamente sensíveis — usar HTTP seria um risco inaceitável para os usuários.

**2.** O SSL/TLS é o protocolo que criptografa (embaralha) os dados antes de enviá-los. Ele garante que mesmo que alguém intercepte os dados no caminho, não conseguirá ler as informações sem a chave correta.

**3. Fluxo sugerido:**
```
Usuário abre o app de pagamentos
             ↓
  [1] App (cliente) envia requisição HTTPS ao servidor
             ↓
  [2] Servidor processa o pagamento e consulta o banco de dados
             ↓
  [3] Servidor envia resposta HTTPS com confirmação criptografada
             ↓
  Pagamento confirmado na tela
```

---

# 9. Revisão – O que aprendemos hoje?

✔ O que são protocolos de rede e por que existem  
✔ Como o TCP/IP organiza a comunicação na internet em camadas  
✔ O funcionamento do HTTP: métodos e códigos de status  
✔ A diferença entre HTTP e HTTPS e por que isso importa  
✔ O modelo cliente-servidor como base das aplicações web

---

# 10. Para aprender mais

- [Como funciona o TCP/IP (Instrutor Henrique Morais)](https://www.youtube.com/watch?v=iWy6HD0E9hA)
- [Modelo OSI e TCP/IP (Léo Matos)](https://www.youtube.com/watch?v=KOrWZnGbx7s)
- [O que é HTTPS? (Alura)](https://www.alura.com.br/artigos/o-que-e-ssl-tls)