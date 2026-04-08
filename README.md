# Learning_Log

Projeto Django para registrar topicos e anotacoes de estudo.

## Deploy no Render

Este projeto esta configurado para deploy no Render usando:

- gunicorn para servir a aplicacao Django
- WhiteNoise para arquivos estaticos
- PostgreSQL via variavel DATABASE_URL
- render.yaml para criar o servico web e o banco

### Variaveis de ambiente

No Render, configure ou mantenha estas variaveis:

- SECRET_KEY
- DEBUG=false
- DATABASE_URL
- ALLOWED_HOSTS opcional, separado por virgula
- CSRF_TRUSTED_ORIGINS opcional, separado por virgula

O proprio Render tambem fornece RENDER_EXTERNAL_HOSTNAME em runtime, que ja e aproveitado na configuracao.

### Deploy

1. Envie o projeto para um repositorio Git.
2. No Render, crie um Blueprint e selecione o repositorio.
3. O arquivo render.yaml cria o web service e um banco PostgreSQL.
4. O build executa collectstatic e migrate automaticamente.

### Execucao local

Para desenvolvimento local, o projeto continua funcionando com SQLite quando DATABASE_URL nao estiver definida.
