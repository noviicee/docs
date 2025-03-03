---
title: Configurar diretrizes para os contribuidores do repositório
intro: Você pode criar diretrizes para informar como as pessoas devem contribuir com o projeto.
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
redirect_from:
  - /articles/how-do-i-set-up-guidelines-for-contributors
  - /articles/setting-guidelines-for-repository-contributors
  - /github/building-a-strong-community/setting-guidelines-for-repository-contributors
topics:
  - Community
shortTitle: Diretrizes de contribuidor
---

## Sobre diretrizes de contribuição
Para ajudar os contribuidores do projeto a fazer um bom trabalho, você pode adicionar um arquivo com diretrizes de contribuição às pastas raiz, `docs` ou `.github` do repositório do projeto. Quando alguém abrir uma pull request ou criar um problema, verá um link para esse arquivo. O link para as diretrizes de contribuição também aparece na página `contribuir` do seu repositório. Para obter um exemplo da página de `contribuir`, consulte [github/docs/contribua](https://github.com/github/docs/contribute).

![diretrizes de contribuição](/assets/images/help/pull_requests/contributing-guidelines.png)

Para o proprietário do repositório, as diretrizes de contribuição são uma forma de informar como as pessoas devem contribuir.

Para contribuidores, as diretrizes ajudam a verificar se eles estão enviando pull requests corretas e abrindo problemas úteis.

Para proprietários e contribuidores, as diretrizes de contribuição economizam tempo e evitam aborrecimentos causados por pull requests ou problemas incorretos que precisam ser rejeitados e enviados novamente.

{% ifversion fpt or ghes or ghec %}

Você pode criar diretrizes de contribuição padrão para sua organização{% ifversion fpt or ghes or ghec %} ou conta pessoal{% endif %}. Para obter mais informações, consulte "[Criando um arquivo padrão de integridade da comunidade](//communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)."

{% endif %}

{% tip %}

**Dica:** os mantenedores de repositório podem configurar diretrizes específicas para problemas criando um modelo de problema ou pull request para o repositório. Para obter mais informações, consulte "[Sobre modelos de problema e pull request](/articles/about-issue-and-pull-request-templates)".

{% endtip %}

## Adicionar um arquivo *CONTRIBUTING*

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.files.add-file %}
3. Decida se deseja armazenar as diretrizes de contribuição no diretório root, `docs` ou `.github` do repositório. Em seguida, no campo de nome do arquivo, digite o nome e a extensão do arquivo. Os nomes de arquivos com diretrizes de contribuição não são sensíveis a maiúsculas de minúsculas. Os arquivos são renderizados no formato de texto rich se a extensão do arquivo estiver em um formato compatível. Para obter mais informações, consulte "[Trabalhando com arquivos sem código](/repositories/working-with-files/using-files/working-with-non-code-files#rendering-differences-in-prose-documents)". ![Nome do novo arquivo](/assets/images/help/repository/new-file-name.png)
    - Para tornar as diretrizes de contribuição visíveis no diretório raiz do repositório, digite *CONTRIBUTING*.
    - Para tornar as diretrizes de contribuição visíveis no diretório `docs` do repositório, digite *docs/* para criar o diretório e, em seguida, digite *CONTRIBUTING*.
    - Se um repositório contiver mais de um arquivo *CONTRIBUTING*, o arquivo mostrado em links será escolhido entre locais na seguinte ordem: diretório do `.github`, em seguida, o diretório raiz do repositório e, finalmente, o diretório de `docs`.
4. Adicione as diretrizes de contribuição ao novo arquivo. Elas podem conter:
    - Etapas para criar bons problemas ou pull requests.
    - Links para documentações externas, listas de distribuição ou um código de conduta.
    - Expectativas de comportamento e da comunidade.
{% data reusables.files.write_commit_message %}
{% data reusables.files.choose_commit_branch %}
{% data reusables.files.propose_new_file %}

## Exemplos de diretrizes de contribuição

Caso tenha dúvidas, estes são alguns bons exemplos de diretrizes de contribuição:

- [Diretrizes de contribuição](https://github.com/atom/atom/blob/master/CONTRIBUTING.md) do editor Atom.
- [Diretrizes de contribuição](https://github.com/rails/rails/blob/main/CONTRIBUTING.md) do Ruby on Rails.
- [Diretrizes de contribuição](https://github.com/opengovernment/opengovernment/blob/master/CONTRIBUTING.md) do Open Government.

## Leia mais
- Seção "[Iniciar um projeto de código aberto](https://opensource.guide/starting-a-project/)" de Guias de código aberto{% ifversion fpt or ghec %}
- [{% data variables.product.prodname_learning %}]({% data variables.product.prodname_learning_link %}){% endif %}{% ifversion fpt or ghes or ghec %}
- "[Adicionar uma licença a um repositório](/articles/adding-a-license-to-a-repository)"{% endif %}
