# Primeiro Estágio
FROM alpine:3.14 AS primeiro-estagio

WORKDIR /site

COPY config.toml config.toml
COPY index.html /site/layouts/index.html
COPY _index.md /site/content/_index.md

# Instala o ferramenta Hugo na nossa imagem Docker
RUN apk add hugo
# Este comando gera as páginas finais em HTML
RUN hugo --minify --gc

# Segundo Estágio
FROM nginx:1.21.3-alpine AS segundo-estagio

# Neste momento, o que será copiado será o produto(as páginas html criadas pelo hugo) do estágio anterior.
COPY --from=primeiro-estagio /site/public/ /usr/share/nginx/html

ENTRYPOINT ["nginx", "-g", "daemon off;"]

# docker rm -f meu-container
# docker run -p=8080:80 --rm -d --name=meu-container-hugo site-hugo