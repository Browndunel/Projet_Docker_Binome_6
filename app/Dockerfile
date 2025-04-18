FROM alpine:3.17

# Installer Python et les outils nécessaires
RUN apk add --no-cache python3 py3-pip py3-virtualenv curl

# Créer un répertoire d'application
WORKDIR /app

# Copier le code source
COPY src/ /app

# Créer un environnement virtuel et activer
RUN python3 -m venv venv && \
    . venv/bin/activate && \
    pip install --no-cache-dir flask mysql-connector-python

# Exposer le port utilisé par Flask
EXPOSE 4743

# Commande de démarrage
CMD ["sh", "-c", ". venv/bin/activate && python3 app.py"]
