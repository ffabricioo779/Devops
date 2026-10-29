
# Projeto DevOps

Este projeto foi desenvolvido como parte das atividades da faculdade, com o objetivo de colocar em prática conceitos de DevOps, utilizando Git, GitHub e GitHub Actions.

Criamos uma página web simples e configuramos automações para registrar alterações no código e publicar versões do projeto.

## Equipe

- **Fabrício da Silva** (ffabricioo779) — RA 250285
- **Gustavo Oliveira Alves** — RA 250274

## Estrutura do repositório

```text
.
├── .github/
│   └── workflows/
│       ├── hello.yml
│       ├── changelog.yml
│       └── release.yml
├── CHANGELOG.md
├── pagina-simples.html
└── README.md
```

## Sobre o projeto

Desenvolvemos uma página utilizando HTML, CSS e JavaScript.

A página possui textos de apresentação, layout responsivo e um botão interativo que mostra a quantidade de cliques.

O objetivo principal foi utilizar esse projeto para aprender sobre GitHub Actions e automações DevOps.

## Automações implementadas

O projeto possui três workflows configurados na pasta `.github/workflows`.

| Workflow | Função |
|---|---|
| CI | Executa tarefas automáticas para demonstrar integração contínua. |
| Changelog | Registra automaticamente o histórico de commits. |
| Release Package | Compacta e publica uma versão do projeto. |

### 1. Integração contínua (CI)

O arquivo `hello.yml` executa automaticamente comandos de exemplo quando são feitas alterações na branch `main` ou quando um pull request é aberto.

Essa automação demonstra o funcionamento básico da integração contínua.

### 2. Changelog automático

O arquivo `changelog.yml` é responsável por atualizar o histórico de alterações do projeto.

Quando um commit é enviado para a branch `main`, a Action consulta os últimos 30 commits e registra as informações no arquivo `CHANGELOG.md`.

O histórico contém:
- Mensagem do commit.
- Identificação do commit.
- Autor da alteração.
- Data da alteração.

Também utilizamos `[skip ci]` para evitar execuções desnecessárias provocadas pelos próprios commits da automação.

### 3. Publicação de Release

O arquivo `release.yml` permite criar e publicar novas versões do projeto automaticamente.

A Action é iniciada manualmente pela aba **Actions** do GitHub, onde informamos o número da versão.

Após a execução, ela compacta os arquivos em um ZIP e publica a versão na seção **Releases** do repositório.

#### Explicação do código da Release

**Etapa 1 — Compactação do projeto**

```yaml
# Nome da etapa responsável pela compactação
- name: Zip folder

# Compacta os arquivos do commit atual em release.zip
  run: git archive --format=zip -o release.zip HEAD
```

**Etapa 2 — Publicação da versão**

```yaml
# Nome da etapa que cria a Release
- name: Create GitHub Release

# Configura o token de autenticação
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

# Executa o comando de publicação
  run: |
    gh release create ${{ github.event.inputs.version }} release.zip \
      --title "Release ${{ github.event.inputs.version }}" \
      --generate-notes
```

**Explicação dos comandos:**

- `GITHUB_TOKEN`: permite que a Action publique a Release.
- `gh release create`: cria uma nova versão no GitHub.
- `github.event.inputs.version`: utiliza o número da versão informado.
- `release.zip`: anexa o arquivo compactado à Release.
- `--title`: define o nome da versão.
- `--generate-notes`: gera automaticamente as notas da versão.

**Resumindo:** a primeira etapa compacta os arquivos do projeto e a segunda publica a versão no GitHub, disponibilizando o ZIP para download.

## Changelog

O arquivo `CHANGELOG.md` armazena automaticamente o histórico de alterações feitas no projeto.

Isso permite acompanhar as modificações realizadas pelos integrantes, facilitando a organização e o controle das mudanças.

## Releases e versionamento

As Releases são utilizadas para publicar versões específicas do projeto.

A versão **v1.0.1** já foi publicada e está disponível no GitHub.

[Visualizar Release v1.0.1](https://github.com/ffabricioo779/Devops/releases/tag/v1.0.1)

### Como publicar uma nova versão

1. Acesse a aba **Actions** do repositório.
2. Selecione o workflow **Release Package**.
3. Clique em **Run workflow**.
4. Informe a versão desejada, por exemplo, `v1.0.2`.
5. Execute o workflow.
6. Acesse a seção **Releases** para visualizar a nova versão e baixar o arquivo `release.zip`.

## Como executar o projeto

1. Acesse o repositório no GitHub.
2. Clique em **Code → Download ZIP** ou baixe o pacote da Release.
3. Extraia os arquivos no computador.
4. Abra o arquivo `pagina-simples.html` no navegador.
5. Teste o botão interativo da página.

Para acompanhar as automações, basta acessar a aba **Actions** do GitHub.

## Histórico de atividades realizadas

- Criação do repositório no GitHub.
- Desenvolvimento da página HTML, CSS e JavaScript.
- Realização de commits pelos integrantes.
- Configuração do workflow de CI.
- Implementação do Changelog automático.
- Criação da Action de Release.
- Publicação da versão v1.0.1.
- Testes das automações.
- Organização da documentação.

## Tecnologias utilizadas

- **HTML:** estrutura da página.
- **CSS:** aparência e estilização.
- **JavaScript:** funcionamento do botão interativo.
- **Git:** controle de versões.
- **GitHub:** armazenamento do repositório.
- **GitHub Actions:** execução das automações.
- **YAML:** configuração dos workflows.
- **GitHub CLI (gh):** publicação das Releases.

## Conclusão

Com este trabalho, aprendemos a utilizar o GitHub Actions para automatizar tarefas relacionadas ao desenvolvimento de software.

Conseguimos implementar o registro automático de alterações por meio do Changelog e a publicação de versões utilizando a Action de Release.

O projeto permitiu colocar em prática conceitos importantes de DevOps, como automação, versionamento e organização do desenvolvimento.
