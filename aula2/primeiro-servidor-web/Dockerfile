FROM httpd:2.4.54

COPY index.html /usr/local/apache2/htdocs
COPY style.css /usr/local/apache2/htdocs

EXPOSE 80

CMD [ "httpd-foreground" ]

# O comando "httpd-foreground" é um script utilitário (um wrapper)
# A sua única e principal função é iniciar o servidor Apache e mantê-lo rodando obrigatoriamente em primeiro plano (foreground) dentro do container.

# docker build -t meu-servidor .
# docker run -d -p=8080:80 --name=container-site meu-servidor