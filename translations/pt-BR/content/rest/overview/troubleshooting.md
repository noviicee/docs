---
title: Solução de Problemas
intro: Aprenda a resolver os problemas mais comuns que as pessoas enfrentam na API REST.
redirect_from:
  - /v3/troubleshooting
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - API
---



Se você estiver encontrando algumas situações estranhas na API, aqui está uma lista de resoluções de alguns dos problemas que você pode estar enfrentando.

## Erro `404` para um repositório existente

Normalmente, enviamos um erro `404` quando seu cliente não está autenticado corretamente. Nesses casos, você pode esperar ver um `403 Forbidden`. No entanto, como não queremos fornecer _nenhuma_ informação sobre repositórios privados, a API retorna um erro `404`.

Para solucionar problemas, certifique-se de [você está efetuando a autenticação corretamente](/guides/getting-started/), [seu token de acesso OAuth tenha os escopos necessários](/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/), [restrições do aplicativo de terceiros][oap-guide] não estejam bloqueando o acesso, e [o token não venceu ou foi revogado](/github/authenticating-to-github/keeping-your-account-and-data-secure/token-expiration-and-revocation).

## Nem todos os resultados retornados

A maioria das chamadas da API que acessam uma lista de recursos (_por exemplo,_, usuários, issues, _etc._) é compatível com a paginação. Se você está fazendo solicitações e recebendo um conjunto incompleto de resultados, provavelmente você só está vendo a primeira página. Você precisará solicitar as páginas restantes para obter mais resultados.

É importante *não* tentar adivinhar o formato da URL de paginação. Nem todas as chamadas de API usam a mesma estrutura. Em vez disso, extraia as informações de paginação do [Cabeçalho do link](/rest#pagination), que é enviado com cada solicitação.

{% ifversion fpt or ghec %}
## Erros de autenticação básica

Em 13 de novembro de 2020 a autenticação de nome de usuário e senha da API REST e da API de Autorizações OAuth tornaram-se obsoletas e já não funcionaram mais.

### Usar `nome de usuário`/`senha` para autenticação básica

Se você estiver usando um `nome de usuário` e `senha` para chamadas de API, eles não são conseguirão mais efetuar a autenticação. Por exemplo:

```bash
curl -u my_user:my_password https://api.github.com/user/repos
```

Em vez disso, use um [token de acesso pessoal](/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) ao testar pontos de extremidade ou fazer desenvolvimento local:

```bash
curl -H 'Authorization: token my_access_token' https://api.github.com/user/repos
```

Para aplicativos OAuth, você deve usar o [fluxo de aplicativo web](/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow) para gerar um token do OAuth para usar no cabeçalho da chamada da API:

```bash
curl -H 'Authorization: token my-oauth-token' https://api.github.com/user/repos
```

## Tempo esgotado

Se  {% data variables.product.product_name %} demorar mais de 10 segundos para processar uma solicitação de API, {% data variables.product.product_name %} encerrará a solicitação e você receberá uma resposta de tempo esgotado.

{% endif %}

[oap-guide]: https://developer.github.com/changes/2015-01-19-an-integrators-guide-to-organization-application-policies/
