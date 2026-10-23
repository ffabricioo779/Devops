# Projeto DevOps

Este projeto foi desenvolvido como parte das atividades da faculdade, com o objetivo de colocar em prática conceitos de **DevOps**, utilizando Git, GitHub e GitHub Actions.

Para isso, criamos uma página web simples e configuramos automações para acompanhar as alterações realizadas no repositório. Durante o desenvolvimento, também trabalhamos com versionamento de código, commits e geração automática de um histórico de mudanças.

## Equipe

- **Fabrício da Silva** (ffabricioo779) — RA 250285
- **Gustavo Oliveira Alves** — RA 250274

## Estrutura do repositório

```text
.
├── .github/
│   └── workflows/
│       ├── hello.yml        # Workflow de CI
│       └── changelog.yml    # Automação do histórico
├── CHANGELOG.md             # Histórico de alterações
├── pagina-simples.html      # Página principal do projeto
└── README.md                # Documentação do projeto
```

## Sobre a página desenvolvida

Criamos uma página simples utilizando **HTML, CSS e JavaScript**, reunidos em um único arquivo.

A página contém textos de apresentação, um layout que se adapta a diferentes tamanhos de tela e um botão interativo que mostra quantas vezes foi clicado.

A intenção foi utilizar essa página como base para praticar o uso do GitHub e das ferramentas de automação.

## Automações implementadas (GitHub Actions)

O projeto conta com dois workflows configurados na pasta `.github/workflows`.

| Workflow | Quando executa | O que faz |
|---|---|---|
| **CI** | Ao realizar um push ou abrir um pull request na branch `main`, ou manualmente | Executa comandos de exemplo em um ambiente Ubuntu para demonstrar o funcionamento da integração contínua. |
| **Changelog** | A cada push na branch `main` | Atualiza automaticamente o arquivo `CHANGELOG.md` utilizando o histórico de commits. |

### Integração contínua (CI)

O workflow `hello.yml` foi criado para demonstrar como funciona a execução automática de tarefas pelo GitHub Actions.

Sempre que uma alteração é enviada para a branch principal ou um pull request é aberto, o GitHub inicia o workflow, que executa comandos simples no terminal.

Esse processo nos ajudou a entender o funcionamento básico da integração contínua e como essas automações podem ser utilizadas em outros projetos.

### Changelog automático

O workflow `changelog.yml` é responsável por manter o histórico de mudanças atualizado.

Quando um novo commit é enviado para a branch `main`, a automação consulta os últimos 30 commits e registra as informações no arquivo `CHANGELOG.md`.

Esse histórico contém a descrição da alteração, a identificação do commit, o responsável e a data.

Também configuramos uma condição com `[skip ci]` para evitar que os commits feitos pela própria automação provoquem novas execuções desnecessárias.

## Changelog

O arquivo `CHANGELOG.md` permite acompanhar as modificações feitas durante o desenvolvimento, facilitando a identificação das contribuições de cada integrante.

Por exemplo, quando alteramos algum texto da página ou adicionamos um novo arquivo, essa mudança pode aparecer no histórico após o envio do commit para a branch principal.

## Como executar o projeto

1. Acesse o repositório no GitHub: [ffabricioo779/Devops](https://github.com/ffabricioo779/Devops).
2. Clique em **Code → Download ZIP** ou clone o repositório.
3. Extraia os arquivos, caso tenha baixado o ZIP.
4. Abra o arquivo `pagina-simples.html` em qualquer navegador.
5. Teste o botão interativo disponível na página.

Para acompanhar as automações, acesse a aba **Actions** do repositório, onde é possível visualizar as execuções e seus resultados.

## Histórico de atividades realizadas

- Criação e configuração do repositório no GitHub.
- Desenvolvimento de uma página simples em HTML, CSS e JavaScript.
- Realização de commits pelos integrantes.
- Configuração do workflow de integração contínua.
- Implementação da geração automática do changelog.
- Testes e alterações na página.
- Organização da documentação do projeto.

## Tecnologias e ferramentas

- **HTML:** estrutura da página.
- **CSS:** estilização e aparência visual.
- **JavaScript:** funcionalidade do botão interativo.
- **Git:** controle de versões do projeto.
- **GitHub:** armazenamento e compartilhamento dos arquivos.
- **GitHub Actions:** execução das automações.
- **YAML:** configuração dos workflows.

## Conclusão

Com esse projeto, conseguimos conhecer melhor o funcionamento do GitHub e entender como o GitHub Actions pode facilitar algumas tarefas durante o desenvolvimento.

A atividade também nos ajudou a praticar o trabalho em equipe, o controle de versões e a organização do histórico de alterações.

Mesmo sendo um projeto simples, foi uma oportunidade de aplicar na prática conceitos importantes de DevOps que poderão ser utilizados em projetos futuros.
