# Sistema de Autenticação (Simulado)

Este projeto é uma implementação Single Page Application (SPA) de um sistema de autenticação completo e criptografado, desenvolvido em um único arquivo HTML. Ele simula o comportamento de um cadastro, login e área administrativa com persistência de dados segura no navegador (LocalStorage).


### Funcionalidades

Autenticação & Segurança:
- Cadastro de Usuário: Criptografia automática de dados sensíveis antes do armazenamento.
- Login Seguro: Descriptografia em tempo real para validação de credenciais.
- Validação de Senha Forte: Feedback visual instantâneo dos requisitos de segurança.
- Criptografia Simétrica: Implementação didática de cifra XOR + Base64 para proteção de dados em repouso.
- 2FA (Simulado): Toggle para ativar Autenticação de Dois Fatores com notificações de sistema.
- Recuperação de Conta: Cadastro seguro de e-mail de recuperação (criptografado no banco).

 ### Tecnologias Utilizadas

O projeto adota uma arquitetura Serverless/Buildless via CDN, executando diretamente no navegador sem build steps.

- HTML5: Estrutura semântica.
- React (v18): Gerenciamento de estado (useState, useEffect) e renderização de componentes.
- Tailwind CSS: Design responsivo, Dark Mode e estilização moderna.
- Babel: Transpilação de JSX in-browser.
- LocalStorage: Banco de dados NoSQL simulado no cliente.
- Lucide React: Ícones vetoriais.

### Como Executar

Como este projeto é stand-alone (arquivo único), não é necessário instalar dependências (npm install) ou configurar ambiente.

**1.** Baixe o arquivo Crud_com_senha.html.

**2.** Dê um duplo clique no arquivo.

**3.** O projeto abrirá automaticamente no seu navegador padrão.

### Regras de Validação
Para garantir a segurança (simulada), a senha deve atender aos seguintes critérios:
 - Mínimo de 8 caracteres.
 - Pelo menos uma Letra Maiúscula.
 - Pelo menos uma Letra Minúscula.
 - Pelo menos um Número.
 - Pelo menos um Caractere Especial (!@#...).
 - Criptografia (Educacional):
Os dados sensíveis (E-mail, Senha e E-mail de Recuperação) são protegidos utilizando uma cifra XOR com uma chave privada, seguida de codificação Base64. Isso impede a leitura direta dos dados inspecionando o LocalStorage.

### Observação Técnica

O sistema utiliza persistência local. Embora os dados sobrevivam ao fechamento do navegador (graças ao LocalStorage), limpar o cache do navegador apagará os usuários cadastrados.

### Contribuição
Este projeto foi desenvolvido por:
- Lucas dos Santos
- Diego Bento
- Luís Guilherme
