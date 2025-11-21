# Sistema de Autenticação (Simulado)

Este projeto é uma implementação Single Page Application (SPA) de um sistema de autenticação completo, desenvolvido em um único arquivo HTML. Ele simula o comportamento de um cadastro e login com persistência de estado em memória (RAM).

### Funcionalidades

- Cadastro de Usuário
- Validação de campos obrigatórios.
- Validação de senha forte em tempo real.
- Verificação de credenciais baseada no usuário cadastrado na sessão.
- Feedback visual para erros de autenticação.
- Área protegida acessível apenas após login.
- Exibição dos dados do usuário logado.
- Botão de Logout.
- Bloqueio de ações enquanto os dados não são válidos.
- Feedback visual (cores e ícones) para guiar o usuário.

 ### Tecnologias Utilizadas

- O projeto foi construído utilizando a abordagem Serverless/Buildless via CDN, permitindo execução imediata sem necessidade de instalação de Node.js.
- HTML5: Estrutura semântica.
- React (v18): Biblioteca para construção da interface e gerenciamento de estado (useState, useEffect).
- Tailwind CSS: Estilização utilitária para design responsivo e moderno.
- Babel: Transpilação de código JSX em tempo real no navegador.
- Lucide React: Ícones vetoriais para interface.

### Como Executar

Como este projeto é stand-alone (arquivo único), não é necessário instalar dependências (npm install) ou configurar ambiente.

**1.** Baixe o arquivo Crud_com_senha.html.

**2.** Dê um duplo clique no arquivo.

**3.** O projeto abrirá automaticamente no seu navegador padrão.

### Regras de Validação
Para garantir a segurança (simulada), a senha deve atender aos seguintes critérios:
 - Mínimo de 4 caracteres.
 - Pelo menos uma Letra Maiúscula.
 - Pelo menos uma Letra Minúscula.
 - Pelo menos um Número.
 - Pelo menos um Caractere Especial (!@#...).


### Observação Técnica

Este sistema utiliza persistência em memória. Isso significa que, como não há um banco de dados real conectado, atualizar a página (F5) limpará os usuários cadastrados. Para testes, complete o fluxo de cadastro e login na mesma sessão.

### Contribuição
Este projeto foi desenvolvido por
- Lucas Santos
- Diego
- Luís Guilherme
