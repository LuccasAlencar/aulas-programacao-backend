# Meu Site de Aulas 🎓

Site de aulas criado com MkDocs e Material Theme, hospedado gratuitamente no GitHub Pages.

## 🚀 Como usar este projeto

### Pré-requisitos

- Python 3.x instalado
- Git instalado
- Conta no GitHub

### Instalação Local

1. Clone este repositório:
```bash
git clone https://github.com/seu-usuario/meu-site-aulas.git
cd meu-site-aulas
```

2. Instale as dependências:
```bash
pip install mkdocs-material
```

3. Execute localmente:
```bash
mkdocs serve
```

4. Acesse no navegador: `http://127.0.0.1:8000`

## 📝 Como adicionar conteúdo

### Adicionar uma nova aula

1. Crie um arquivo `.md` na pasta `docs/aulas/`:
```bash
touch docs/aulas/aula04.md
```

2. Escreva o conteúdo em Markdown

3. Adicione a aula no arquivo `mkdocs.yml` na seção `nav`:
```yaml
nav:
  - Aulas:
    - Aula 4 - Novo Tópico: aulas/aula04.md
```

### Estrutura de pastas

```
meu-site-aulas/
├── docs/
│   ├── index.md              # Página inicial
│   ├── sobre.md              # Página sobre
│   ├── aulas/                # Pasta de aulas
│   │   ├── aula01.md
│   │   ├── aula02.md
│   │   └── aula03.md
│   └── exercicios/           # Pasta de exercícios
│       └── lista01.md
├── .github/
│   └── workflows/
│       └── ci.yml            # GitHub Actions config
├── mkdocs.yml                # Configuração do MkDocs
├── .gitignore
└── README.md
```

## 🌐 Deploy no GitHub Pages

### Primeira vez - Configuração

1. Crie um repositório no GitHub

2. Faça o primeiro commit:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/seu-usuario/meu-site-aulas.git
git push -u origin main
```

3. Nas configurações do repositório:
   - Vá em **Settings** > **Pages**
   - Em **Source**, selecione **Deploy from a branch**
   - Selecione a branch **gh-pages**
   - Clique em **Save**

4. Aguarde alguns minutos. Seu site estará disponível em:
   `https://seu-usuario.github.io/meu-site-aulas/`

### Atualizações automáticas

Depois da configuração inicial, toda vez que você fizer push para a branch `main`, o GitHub Actions vai automaticamente:

1. Compilar o site
2. Fazer deploy no GitHub Pages

```bash
# Edite seus arquivos
git add .
git commit -m "Adiciona nova aula"
git push
```

Em alguns minutos seu site estará atualizado!

## 🎨 Personalização

### Mudar cores

No arquivo `mkdocs.yml`, altere:
```yaml
theme:
  palette:
    primary: indigo  # Troque por: red, pink, purple, blue, etc.
    accent: indigo
```

### Mudar logo ou favicon

1. Adicione a imagem em `docs/img/`
2. Configure no `mkdocs.yml`:
```yaml
theme:
  logo: img/logo.png
  favicon: img/favicon.ico
```

## 📚 Recursos úteis

- [Documentação MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [Guia de Markdown](https://www.markdownguide.org/)
- [GitHub Pages](https://pages.github.com/)

## 💡 Dicas

- Use `mkdocs serve` durante o desenvolvimento para ver mudanças em tempo real
- Organize seu conteúdo em pastas lógicas
- Use as features do Material: admonitions, tabs, code blocks, etc.
- Aproveite os emojis para deixar o conteúdo mais visual! 🎉

## 📄 Licença

MIT License - Livre para usar e modificar!

---

**Criado com ❤️ usando MkDocs e Material Theme**
