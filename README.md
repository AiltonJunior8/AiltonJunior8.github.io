# Página de perfil acadêmico — Ailton Junior

Site pessoal construído com [Quarto](https://quarto.org), publicado via GitHub
Pages. Três seções (About, CV, Projects), em inglês na raiz e em português em `pt/`. Ao mudar uma página, mude também a equivalente no outro idioma.

## Estrutura

```
.
├── _quarto.yml       # configuração do site (navbar, rodapé, tema); inglês como padrão
├── index.qmd         # About (página inicial, inglês)
├── cv.qmd            # CV (inglês)
├── projects.qmd      # Projects (inglês)
├── pt/               # versão em português: index.qmd, curriculo.qmd, projetos.qmd
├── lang-switch.html  # botão EN/PT: traduz o menu em pt/ e guarda a escolha do visitante
├── styles.scss       # tema claro + regras (paleta, fontes, componentes)
├── theme-dark.scss   # cores do modo escuro
├── assets/           # imagens (foto de perfil)
└── .github/workflows/publish.yml   # deploy automático
```

## Rodar localmente

Com o Quarto instalado:

```bash
quarto preview      # servidor local com hot-reload
quarto render       # gera o site estático em _site/
```

## Conteúdo e tema

- O currículo (`curriculo.qmd`) foi montado a partir do Currículo Lattes
  (atualização de 14/09/2026). Ao atualizar o Lattes, atualize também esta página.
- `styles.scss` define a paleta clara e todas as regras; `theme-dark.scss` só
  sobrescreve as cores do modo escuro (botão na navbar).
- Componentes: `.hero`, `.section-grid` (rótulo à esquerda, conteúdo à direita),
  `.entry` (data + conteúdo), `.ref-links` (links de referência), `.project`.
- Troque `assets/perfil.svg` pela sua foto (ex.: `perfil.jpg`) e ajuste o
  caminho em `index.qmd`.

## Publicar no GitHub Pages

Como é um **site de usuário**, o repositório deve se chamar
`AiltonJunior8.github.io`.

1. Crie o repositório `AiltonJunior8.github.io` no GitHub (vazio).
2. Conecte e envie:
   ```bash
   git init
   git add .
   git commit -m "Site de perfil acadêmico"
   git branch -M main
   git remote add origin https://github.com/AiltonJunior8/AiltonJunior8.github.io.git
   git push -u origin main
   ```
3. No GitHub: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
4. A cada `push`, a Action renderiza e publica. O site fica em
   `https://AiltonJunior8.github.io`.

### Alternativa manual (sem Actions)

```bash
quarto publish gh-pages
```

Cria/atualiza a branch `gh-pages`. Nesse caso, em **Settings → Pages**, defina a
Source como a branch `gh-pages`.
