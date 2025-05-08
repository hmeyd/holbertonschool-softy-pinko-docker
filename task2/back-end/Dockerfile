FROM ubuntu:latest

# Empêcher les messages interactifs
ENV DEBIAN_FRONTEND=noninteractive

# Mettre à jour les paquets et installer Python3, pip3
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y python3 python3-pip

# Corriger le problème EXTERNALLY-MANAGED s'il existe
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED || true

# Installer Flask via pip3
RUN pip3 install flask

# Copier le fichier Python dans le conteneur
COPY api.py /app/api.py

# Définir le répertoire de travail
WORKDIR /app

# Exposer le port utilisé par Flask
EXPOSE 5252

# Lancer le serveur Flask
CMD ["python3", "api.py"]

