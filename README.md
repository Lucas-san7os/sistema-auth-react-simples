# 🔐 React Auth Flow & Web Crypto API

Implementação de uma Single Page Application (SPA) de autenticação client-side desenvolvida com **React 18** e arquitetura *buildless*, integrando criptografia simétrica **AES-GCM de 256 bits** via Web Crypto API nativa do navegador para proteção de credenciais e persistência segura em `LocalStorage`.

---

## 📐 Visão Geral da Arquitetura e Engenharia Frontend

O projeto resolve o desafio de prover um fluxo completo de autenticação e gestão de sessão sem dependência de um backend dedicado (*Serverless/Buildless*). A aplicação executa inteiramente no *runtime* do navegador, utilizando transpilação de JSX em tempo de execução e APIs nativas de segurança da W3C.

### Destaques Arquiteturais e Decisões Técnicas
* **Arquitetura Buildless (Zero-Dependency Tooling):** Execução direta no navegador via CDNs para React 18, Babel Standalone e Tailwind CSS, eliminando etapas de compilação (*Webpack*, *Vite* ou *Node.js*).
* **Criptografia Simétrica de Alta Performance (AES-GCM 256-bit):** Utilização da interface nativa `window.crypto.subtle` (Web Crypto API) para cifra e decifra de dados sensíveis antes do salvamento na camada de persistência.
* **Derivação de Chave Forte (PBKDF2):** Geração de chaves criptográficas a partir da senha do usuário utilizando PBKDF2 (*Password-Based Key Derivation Function 2*) com algoritmo de hash SHA-256.
* **Vetor de Inicialização (IV) Único por Operação:** Cada registro gera um vetor de inicialização de 96 bits aleatório, garantindo *indistinguibilidade* (entradas idênticas produzem *ciphertexts* completamente distintos).
* **Gerenciamento de Estado Reativo:** Controle de rotas protegidas, sessão de usuário e fluxo de Autenticação de Dois Fatores (2FA simulado) gerenciados via *hooks* do React (`useState`, `useEffect`).

---

## 🛡️ Engenharia de Criptografia e Segurança de Dados

### Pipeline de Proteção de Credenciais

```text
[Senha em Texto Puro] ──> PBKDF2 (SHA-256) ──> [Chave AES-256]
                                                      │
[Payload: E-mail/Dados] + [IV Aleatório (96-bit)] ────┴─> AES-GCM ──> [Payload Criptografado no LocalStorage]
```

### Mecanismos de Proteção Implementados

| Mecanismo | Especificação Técnica | Objetivo de Segurança |
| :--- | :--- | :--- |
| **Cifra Simétrica** | `AES-GCM` (Galois/Counter Mode) | Confidencialidade e autenticidade (dados autenticados com tag). |
| **Derivação de Chave** | `PBKDF2` com `HMAC-SHA-256` | Proteção contra ataques de força bruta e tabelas rainbow. |
| **Entropia de IV** | `crypto.getRandomValues()` (96 bits) | Prevenção de análise de padrões em payloads criptografados. |
| **Sanitização de Input** | Validação por Expressões Regulares (RegEx) | Garantia de complexidade mínima de senha no lado do cliente. |

---

## 🗄️ Matriz de Tecnologias

| Tecnologia / Biblioteca | Função Arquitetural no Sistema |
| :--- | :--- |
| **React 18** | Renderização reativa de interface, gestão de estado global e ciclo de vida de componentes. |
| **Web Crypto API (`SubtleCrypto`)** | Interface nativa do navegador para execução de operações criptográficas de alto nível. |
| **Tailwind CSS** | Framework utilitário para estilização responsiva, componentes visuais e *Dark Mode*. |
| **Babel Standalone** | Transpilação *in-browser* de código JSX e sintaxe ES6+ para compatibilidade no navegador. |
| **LocalStorage API** | Camada de persistência relacional/NoSQL simulada no *client-side*. |
| **Lucide React** | Conjunto de ícones vetoriais para sinalização de status de segurança e feedback visual. |

---

## 📋 Regras de Validação de Senha

Para garantir a higienização de dados e resistência a ataques de dicionário, a aplicação impõe a validação em tempo real dos seguintes critérios:

* **Comprimento Mínimo:** 8 caracteres.
* **Caractere Maiúsculo:** Ao menos uma letra maiúscula (`A-Z`).
* **Caractere Minúsculo:** Ao menos uma letra minúscula (`a-z`).
* **Caractere Numérico:** Ao menos um dígito (`0-9`).
* **Caractere Especial:** Ao menos um símbolo (`!@#$%^&*()_+-=[]{}|;:,.<>?`).

---

## 🚀 Como Executar

Por se tratar de uma aplicação *stand-alone* (arquivo único), não é necessária a instalação de pacotes via `npm` ou configuração de ambiente local.

### Opção 1: Execução Direta no Navegador

1. **Clonar o repositório:**
   ```bash
   git clone [https://github.com/Lucas-san7os/React-auth-flow.git](https://github.com/Lucas-san7os/React-auth-flow.git)
   cd React-auth-flow
   ```

2. **Abrir o arquivo:**
   * Dê um duplo clique no arquivo `Crud_com_senha.html` (ou abra diretamente no navegador de sua preferência: Chrome, Edge, Firefox ou Safari).

### Opção 2: Servidor Estático Local (VSCode Live Server / Python)

Para testar a aplicação em um servidor local estático:

```bash
# Executando via Python 3
python -m http.server 8000
```
Acesse `http://localhost:8000/Crud_com_senha.html` no seu navegador.

---

## ⚠️ Observações Técnicas de Persistência

* **Escopo de Dados:** Os dados de usuários registrados são mantidos na instância de `LocalStorage` associada à origem (domínio/protocolo) do navegador.
* **Ciclo de Vida:** A exclusão do cache ou limpeza de dados de navegação removerá as chaves criptografadas armazenadas.

---

## 👥 Autores & Colaboradores

- **Lucas Santos**
- **Diego Bento**
- **Luís Guilherme**


