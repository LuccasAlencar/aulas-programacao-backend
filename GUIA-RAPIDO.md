# 🚀 Guia Rápido - Comandos Essenciais

## Instalação Inicial

```bash
# Instalar MkDocs Material
pip install mkdocs-material

# Ou usando o requirements.txt
pip install -r requirements.txt
```

## Comandos para Desenvolvimento

```bash
# Rodar servidor local (http://127.0.0.1:8000)
mkdocs serve

# Rodar em outra porta
mkdocs serve -a localhost:8080

# Compilar o site (gera pasta /site)
mkdocs build
```

## Comandos Git

```bash
# Primeira vez - Inicializar repositório
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/SEU-REPO.git
git push -u origin main

# Atualizações posteriores
git add .
git commit -m "Descrição da alteração"
git push

# Ver status
git status

# Ver histórico
git log --oneline
```

## Checklist de Deploy

### Antes do primeiro deploy:

1. ✅ Criar repositório no GitHub
2. ✅ Fazer push do código
3. ✅ Aguardar GitHub Actions executar (aba Actions no GitHub)
4. ✅ Configurar GitHub Pages:
   - Settings > Pages
   - Source: Deploy from a branch
   - Branch: gh-pages
   - Save
5. ✅ Aguardar alguns minutos
6. ✅ Acessar: https://seu-usuario.github.io/seu-repo/

### Para cada atualização:

1. ✅ Editar arquivos .md
2. ✅ Testar localmente com `mkdocs serve`
3. ✅ Fazer commit e push
4. ✅ GitHub Actions faz deploy automático!

## Estrutura de um arquivo .md de aula

```markdown
# Título da Aula

## 🎯 Objetivos
- Objetivo 1
- Objetivo 2

## 📖 Conteúdo

### Tópico 1
Conteúdo aqui...

```python
# Código de exemplo
print("Hello World")
```

### Tópico 2
Mais conteúdo...

!!! note "Nota"
    Informação importante!

## 📝 Exercícios
1. Exercício 1
2. Exercício 2

## 🔗 Referências
- Link 1
- Link 2
```

## Elementos Markdown Úteis

### Admonitions (Caixas de Destaque)

```markdown
!!! note "Título"
    Conteúdo da nota

!!! tip "Dica"
    Conteúdo da dica

!!! warning "Atenção"
    Conteúdo do aviso

!!! danger "Perigo"
    Conteúdo do alerta

!!! example "Exemplo"
    Conteúdo do exemplo
```

### Bloco de código expansível

```markdown
??? note "Clique para expandir"
    Conteúdo oculto que pode ser expandido
```

### Tabelas

```markdown
| Coluna 1 | Coluna 2 |
|----------|----------|
| Valor 1  | Valor 2  |
```

### Links

```markdown
[Texto do link](https://exemplo.com)
[Link para outra aula](aula02.md)
```

### Imagens

```markdown
![Texto alternativo](caminho/para/imagem.png)
```

## Solução de Problemas

### Site não atualiza após push
- Verifique a aba Actions no GitHub
- Veja se há erros no workflow
- Aguarde alguns minutos

### Erro de build local
```bash
# Limpar cache e reinstalar
pip uninstall mkdocs-material
pip install mkdocs-material
```

### Página em branco
- Verifique se o arquivo está listado no nav do mkdocs.yml
- Confirme que não há erros de sintaxe no YAML

---

**Dica**: Salve este arquivo para consulta rápida! 📌
