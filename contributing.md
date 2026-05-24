# Guia de Contribuição - projetoNexus

Este documento define as diretrizes para contribuir com o desenvolvimento do **projetoNexus**. A adesão a estas regras garante a organização do repositório, a qualidade do código e a eficiência do trabalho em equipe.

## 1. Estrutura de Branches

O fluxo de trabalho utiliza o modelo de Feature Branch. A branch `main` deve conter apenas código testado, estável e funcional. 

Para iniciar um novo desenvolvimento, crie uma branch a partir da `main` utilizando os seguintes prefixos de categorização:

*   `feat/`: Para o desenvolvimento de novas funcionalidades (ex: `feat/autenticacao-supabase`).
*   `fix/`: Para correção de bugs (ex: `fix/erro-login-frontend`).
*   `docs/`: Para inclusão ou alteração na documentação (ex: `docs/atualiza-readme`).
*   `refactor/`: Para refatoração de código sem alteração de comportamento lógico.
*   `test/`: Para criação ou ajustes de testes.

## 2. Padrão de Commits

O projeto adota o padrão do [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/). As mensagens de commit devem ser precisas, escritas no imperativo e seguir o formato:

`<tipo>: <descrição breve>`

Tipos mais comuns utilizados no repositório:
*   `feat`: Adição de nova funcionalidade.
*   `fix`: Resolução de um bug.
*   `chore`: Atualizações de tarefas de build, configuração de pacotes ou dependências.
*   `style`: Formatação de código (espaçamento, ponto e vírgula ausente, etc.) que não afeta a lógica.

*Exemplo:* `feat: integra endpoint de cadastro de usuários com o backend em Python`

## 3. Padrões de Código e Arquitetura

O repositório é dividido claramente entre o frontend e o backend. Siga as práticas recomendadas para cada ambiente:

### Backend (Python)
*   Siga estritamente as diretrizes de formatação da PEP 8.
*   Utilize *type hints* nas assinaturas de funções e métodos para garantir clareza e facilitar a manutenção.
*   Documente funções complexas utilizando docstrings apropriadas.

### Frontend (TypeScript)
*   Mantenha a tipagem estrita. O uso de `any` deve ser evitado ao máximo.
*   Componentize as interfaces visando a reutilização lógica de código.
*   Certifique-se de aplicar o linting e a formatação padrão do projeto antes de comitar.

### Integração de Dados (Supabase)
*   Qualquer alteração, criação de nova tabela ou modificação de políticas de segurança (RLS) no banco de dados deve ser devidamente documentada.
*   **Atenção:** Nunca exponha chaves secretas, tokens de API ou credenciais do Supabase no código-fonte. Utilize exclusivametne arquivos de variáveis de ambiente (`.env`), garantindo que estejam listados no `.gitignore`.

## 4. Processo de Pull Request (PR)

Todo código desenvolvido deve passar por revisão antes de ser mesclado à branch principal. Para abrir um PR de forma adequada:

1.  Certifique-se de que sua branch está sincronizada e atualizada com os commits mais recentes da `main`.
2.  Verifique localmente se a aplicação compila sem erros nos dois ambientes (frontend e backend).
3.  Abra o PR com um título objetivo.
4.  Na descrição do PR, forneça o contexto da alteração, respondendo:
    *   Qual problema ou funcionalidade este PR resolve?
    *   Como as alterações foram testadas?
5.  Atribua o PR aos membros da equipe para revisão. O *merge* só deve ser realizado após a aprovação do código e a resolução de todas as discussões ou comentários pontuados.

## 5. Relato de Bugs e Problemas

Caso identifique um erro no sistema ou tenha uma sugestão de melhoria técnica, abra uma **Issue** no repositório. Descreva a situação de forma técnica e detalhada, incluindo:
*   Passos exatos para reproduzir o problema.
*   Comportamento esperado versus comportamento atual.
*   Logs de erro ou capturas de tela, se aplicável.