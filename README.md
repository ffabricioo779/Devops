Projeto DevOps
Este projeto foi desenvolvido como parte das atividades da faculdade, com o objetivo de colocar em prática conceitos de DevOps, utilizando Git, GitHub e GitHub Actions.

Para isso, criamos uma página web simples e configuramos automações para acompanhar as alterações realizadas no repositório. Durante o desenvolvimento, também trabalhamos com versionamento de código, commits, geração automática de um histórico de mudanças e publicação de versões do projeto.
Equipe
- Fabrício da Silva (ffabricioo779) — RA 250285
- Gustavo Oliveira Alves — RA 250274


Estrutura do repositório
.
├── .github/
│   └── workflows/
│       ├── hello.yml        # Workflow de CI
│       ├── changelog.yml    # Automação do histórico
│       └── release.yml      # Geração e publicação de releases
├── CHANGELOG.md             # Histórico de alterações
├── pagina-simples.html      # Página principal do projeto
└── README.md                # Documentação do projeto
Sobre a página desenvolvida
Criamos uma página simples utilizando HTML, CSS e JavaScript, reunidos em um único arquivo.

A página contém textos de apresentação, um layout que se adapta a diferentes tamanhos de tela e um botão interativo que mostra quantas vezes foi clicado.

A intenção foi utilizar essa página como base para praticar o uso do GitHub e das ferramentas de automação.
Automações implementadas (GitHub Actions)
O projeto conta com três workflows configurados na pasta .github/workflows.
Workflow	Quando executa	O que faz
CI	Ao realizar um push ou abrir um pull request na branch main, ou manualmente	Executa comandos de exemplo em um ambiente Ubuntu para demonstrar o funcionamento da integração contínua.
Changelog	A cada push na branch main	Atualiza automaticamente o arquivo CHANGELOG.md utilizando o histórico de commits.
Release Package	Quando iniciado manualmente pela aba Actions	Gera um arquivo ZIP do projeto e publica uma release com a versão informada.


Integração contínua (CI)
O workflow hello.yml foi criado para demonstrar como funciona a execução automática de tarefas pelo GitHub Actions.

Sempre que uma alteração é enviada para a branch principal ou um pull request é aberto, o GitHub inicia o workflow, que executa comandos simples no terminal.

Esse processo nos ajudou a entender o funcionamento básico da integração contínua e como essas automações podem ser utilizadas em outros projetos.
Changelog automático
O workflow changelog.yml é responsável por manter o histórico de mudanças atualizado.

Quando um novo commit é enviado para a branch main, a automação consulta os últimos 30 commits e registra as informações no arquivo CHANGELOG.md.

Esse histórico contém a descrição da alteração, a identificação do commit, o responsável e a data.

Também configuramos uma condição com [skip ci] para evitar que os commits feitos pela própria automação provoquem novas execuções desnecessárias.
Publicação de releases
O workflow release.yml foi criado para facilitar a publicação de versões do projeto.

Ele é iniciado manualmente pela aba Actions, informando o número da versão desejada. Depois disso, o GitHub Actions reúne os arquivos do repositório em um pacote chamado release.zip e publica uma release com esse arquivo disponível para download.

A release v1.0.1 já foi publicada e pode ser acessada aqui: Release v1.0.1.

Com isso, aprendemos a organizar e disponibilizar versões do projeto sem precisar criar os pacotes manualmente.
Changelog
O arquivo CHANGELOG.md permite acompanhar as modificações feitas durante o desenvolvimento, facilitando a identificação das contribuições de cada integrante.

Por exemplo, quando alteramos algum texto da página ou adicionamos um novo arquivo, essa mudança pode aparecer no histórico após o envio do commit para a branch principal.
Releases e versionamento
As releases servem para registrar versões específicas do projeto e disponibilizar os arquivos para download.

No nosso repositório, publicamos a versão v1.0.1, que pode ser baixada pela página de Releases.
Como publicar uma nova versão
1. Acesse a aba Actions do repositório.
2. Selecione o workflow Release Package.
3. Clique em Run workflow.
4. Informe o número da versão, por exemplo, v1.0.2.
5. Execute o workflow e acompanhe o resultado.
6. Após a publicação, acesse Releases para encontrar a nova versão e baixar o arquivo release.zip.
Como executar o projeto
1. Acesse o repositório no GitHub: ffabricioo779/Devops.
2. Clique em Code → Download ZIP ou baixe o arquivo release.zip na página da versão publicada.
3. Extraia os arquivos em seu computador.
4. Abra o arquivo pagina-simples.html em qualquer navegador.
5. Teste o botão interativo disponível na página.
Para acompanhar as automações, acesse a aba Actions do repositório, onde é possível visualizar as execuções e seus resultados.
Histórico de atividades realizadas
- Criação e configuração do repositório no GitHub.
- Desenvolvimento de uma página simples em HTML, CSS e JavaScript.
- Realização de commits pelos integrantes.
- Configuração do workflow de integração contínua.
- Implementação da geração automática do changelog.
- Criação do workflow de publicação de releases.
- Publicação da release v1.0.1, com o pacote release.zip.
- Testes e alterações na página.
- Organização da documentação do projeto.
Tecnologias e ferramentas
- HTML: estrutura da página.
- CSS: estilização e aparência visual.
- JavaScript: funcionalidade do botão interativo.
- Git: controle de versões do projeto.
- GitHub: armazenamento e compartilhamento dos arquivos.
- GitHub Actions: execução das automações e publicação de releases.
- YAML: configuração dos workflows.
- GitHub CLI (gh): criação da release por meio da automação.
Conclusão
Com esse projeto, conseguimos conhecer melhor o funcionamento do GitHub e entender como o GitHub Actions pode facilitar algumas tarefas durante o desenvolvimento.

A atividade também nos ajudou a praticar o trabalho em equipe, o controle de versões, a organização do histórico de alterações e a publicação de uma versão do projeto.

Mesmo sendo um projeto simples, foi uma oportunidade de aplicar na prática conceitos importantes de DevOps que poderão ser utilizados em projetos futuros.
