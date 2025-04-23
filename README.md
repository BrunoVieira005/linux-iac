  # Projeto de Infrastructure as Code com Bash Script

Este projeto contém um **Bash Script** que automatiza a criação de usuários, grupos de usuários, diretórios e permissões no sistema Linux, de forma segura e padronizada.

## Descrição

O script realiza o provisionamento completo de uma estrutura de diretórios e usuários com suas permissões adequadas (Infrastructure as Code). Ele cria diretórios específicos para os departamentos da empresa, cria os grupos de usuários correspondentes e define as permissões de acesso de forma que os usuários possam acessar apenas os diretórios de seu respectivo grupo.

## Funcionalidades

- **Criação dos seguintes diretórios**:
  - `/publico` (acessível por todos os usuários)
  - `/adm`, `/ven` e `/sec` (acessíveis apenas pelos grupos respectivos)

- **Criação de grupos de usuários**:
  - `GRP_ADM`, `GRP_VEN` e `GRP_SEC`

- **Criação de usuários e associação aos respectivos grupos**:
  - Usuários do grupo `GRP_ADM` têm acesso total ao diretório `/adm`.
  - Usuários do grupo `GRP_VEN` têm acesso total ao diretório `/ven`.
  - Usuários do grupo `GRP_SEC` têm acesso total ao diretório `/sec`.
  - Todos os usuários têm acesso total ao diretório `/publico`, e nenhum acesso aos repositórios pertencentes a outro grupo.

## Requisitos

- Sistema Linux (com **bash** disponível)
- Acesso **root**

## Como usar?

1. Faça o download ou clone o repositório para sua máquina.

2. Abra o terminal e acesse a pasta do repositório.

3. Torne o script executável:

    ```bash
    chmod +x iac.sh
    ```

4. Execute o script:

    ```bash
    ./iac.sh
    ```

    O script criará os diretórios, grupos, usuários e configurará as permissões automaticamente.

## Explicação do Script

- **Criação de diretórios**: O script cria os diretórios necessários e define o usuário `root` como dono de todos eles.
  
- **Criação de grupos de usuários**: São criados três grupos: `GRP_ADM`, `GRP_VEN` e `GRP_SEC`.

- **Criação de usuários**: O script cria usuários com uma senha padrão e os associa aos seus respectivos grupos. Cada grupo terá permissão total em seu diretório de acesso, e todos os usuários terão permissão total no diretório `/publico`.

- **Permissões**: As permissões são configuradas de acordo com a necessidade de cada grupo e diretório, garantindo a segurança e a organização no sistema.

## Contribuições

Contribuições são bem-vindas! Se você tiver sugestões, melhorias ou correções, fique à vontade para abrir uma **issue** ou enviar um **pull request**.
