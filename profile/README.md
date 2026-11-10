# Meiuka Futebol e Cana

Organização da patota **Meiuka Futebol e Cana**: futebol semanal entre amigos, com resenha e confraternizações.
Aqui ficam o código e a infraestrutura do ecossistema digital que apoia a patota no dia a dia.

Site oficial: [meiukafutebol.com.br](https://www.meiukafutebol.com.br/)
Discussions: [github.com/meiukafutebol/.github/discussions](https://github.com/meiukafutebol/.github/discussions)

## O que é o projeto

Plataforma web para organizar a patota: divulgar a história, gerir agenda de jogos e eventos, planos de mensalidade, perfil dos jogadores, confirmação de presença, avaliações pós-jogo, notificações e classificação.

- **Site institucional**: história, galeria, jogos, eventos, planos e classificação.
- **Área logada do jogador**: perfil, confirmação de presença, avaliação dos companheiros e notificações (webapp, Web Push, e-mail e SMS).
- **Painel administrativo**: cadastro de jogos, eventos, planos, jogadores/papéis e configurações (Board/Admin).
- **Classificação**: pontos, desempate e variação de posição, calculados a partir da planilha operacional da patota.

## Repositórios

| Repositório | Descrição |
|---|---|
| `frontend` | Site institucional e área logada (Angular SSR) |
| `lambda` | Funções serverless (APIs e rotinas agendadas), uma por diretório, versionadas e publicadas de forma independente |
| `infra` | Infraestrutura como código (Terraform) na AWS |
| `ranking` | Página de classificação (descontinuada, agora parte do site) |

Alguns repositórios são privados.

## Arquitetura em resumo

- **Frontend**: Angular com SSR, servido via CloudFront.
- **Backend**: API Gateway + Lambda (Node.js) + DynamoDB, autenticação com Cognito.
- **Eventos**: EventBridge e SQS para desacoplar notificações e invalidação de cache.
- **Infra**: Terraform, CI/CD com GitHub Actions e OIDC (sem chaves estáticas).
- **Custo**: desenhado para caber quase todo no free tier da AWS.

## Convenções

- Commits seguem [Conventional Commits](https://www.conventionalcommits.org/) com Gitmoji.
- Versionamento e releases automatizados com semantic-release.
- Mudanças entram por Pull Request.

## Participe

Use as [Discussions](https://github.com/meiukafutebol/.github/discussions) para ideias, dúvidas e sugestões sobre a plataforma e a patota.
