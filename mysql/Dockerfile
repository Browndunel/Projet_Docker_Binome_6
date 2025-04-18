FROM mysql:latest

# Set the environment variable for MySQL root password
ENV MYSQL_ROOT_PASSWORD=rootpassword
ENV MYSQL_DATABASE=mydatabase
ENV MYSQL_USER=myuser
ENV MYSQL_PASSWORD=mypassword

COPY conf/ /etc/mysql/conf.d/

EXPOSE 5655

HEALTHCHECK --interval= --timeout=5s --retries=3 CMD mysqladmin ping -h localhost || exit 1