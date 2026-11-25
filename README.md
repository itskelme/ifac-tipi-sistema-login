# Sistema de login em PHP (tela inicial)

> Interface da tela de login de um sistema em PHP, montada com Bootstrap 5 e includes de cabeçalho e rodapé.

**Contexto:** IFAC · Técnico em Informática para Internet (TIPI) · 2º ano · 2022

## Sobre

Início de um sistema de login e cadastro em PHP. O que foi feito até aqui é a parte visual: a página de login com campos de usuário e senha, um botão que leva à página de cadastro e o layout dividido em `header.php` e `footer.php`, reaproveitados com `include`.

A parte de servidor (sessão, banco de dados, verificação de senha) não chegou a ser escrita. Para estudar essa etapa foram usados como referência dois projetos prontos, guardados como forks na mesma conta (links em [Referências](#referências)).

O objetivo foi praticar a organização de páginas PHP com `include` e o uso do Bootstrap para montar um formulário centralizado.

## Funcionalidades

- Tela de login com campos **Nome** (usuário ou e-mail) e **Senha** e botão **Entrar**. Os campos têm `required`, mas o formulário usa `novalidate` e não há o script de validação do Bootstrap, então o navegador não bloqueia o envio vazio.
- Botão **Não tem conta?** que leva para `cadastro.php`.
- Cabeçalho e rodapé compartilhados via `include 'header.php'` e `include 'footer.php'`.
- Caixa de login escura, centralizada com classes do Bootstrap, sobre um fundo em degradê azul e vermelho.

O que ainda **não** existe:

- O formulário envia para o próprio `index.php`, que não processa os dados; a página apenas recarrega.
- `cadastro.php` só inclui o cabeçalho e mostra uma página em branco.
- Não há conexão com banco de dados nem uso de `session_start()`.

## Tecnologias

- PHP (`include`)
- HTML5
- Bootstrap 5.2.2 (via CDN jsDelivr)
- CSS3 (`style.css`)

## Estrutura do projeto

| Caminho | Descrição |
|---|---|
| `index.php` | Tela de login. |
| `cadastro.php` | Página de cadastro (por enquanto só o cabeçalho). |
| `header.php` | Abertura do HTML, metatags, Bootstrap e `style.css`. |
| `footer.php` | Fechamento de `</body>` e `</html>`. |
| `style.css` | Fundo em degradê e estilo da caixa de login. |

## Como rodar

### Pré-requisitos

- PHP 7.4 ou superior, **ou** o XAMPP.
- Conexão com a internet (o Bootstrap é carregado de CDN).

Não precisa de banco de dados.

### Passo a passo

```bash
git clone https://github.com/itskelme/ifac-tipi-sistema-login.git
cd ifac-tipi-sistema-login
php -S localhost:8000
```

Abra http://localhost:8000

No XAMPP, copie a pasta para `C:\xampp\htdocs\`, inicie o Apache e acesse http://localhost/ifac-tipi-sistema-login/

## Como usar

1. Abra a página inicial para ver a tela de login.
2. Clique em **Não tem conta?** para ir à página de cadastro (em branco).
3. O botão **Entrar** envia o formulário, mas nenhum login é feito.

## Referências

- [Bootstrap 5.2: formulários](https://getbootstrap.com/docs/5.2/forms/overview/)
- [PHP: `include`](https://www.php.net/manual/pt_BR/function.include.php)
- [PHP: sessões](https://www.php.net/manual/pt_BR/book.session.php) e [`password_hash`](https://www.php.net/manual/pt_BR/function.password-hash.php) (para a parte que falta)
- [itskelme/Complete-Login-System-in-PHP](https://github.com/itskelme/Complete-Login-System-in-PHP), fork de [anpapadakis/Complete-Login-System-in-PHP](https://github.com/anpapadakis/Complete-Login-System-in-PHP)
- [itskelme/Sistema-de-login-com-PHP-e-MySQL](https://github.com/itskelme/Sistema-de-login-com-PHP-e-MySQL), fork de [rafasl1/Sistema-de-login-com-PHP-e-MySQL](https://github.com/rafasl1/Sistema-de-login-com-PHP-e-MySQL)

## Autores

- Diego Kelme Santos da Silva — [@itskelme](https://github.com/itskelme)

## Licença

Este projeto está sob a licença [CC BY-NC 4.0](LICENSE): uso pessoal e modificação permitidos com atribuição; uso comercial proibido.
