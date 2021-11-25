#image de base
FROM ubuntu

# indique des metadatas sur l'image
LABEL autor="Aristide MASSAGA"
LABEL version="1.0"
LABEL description="Cours docker 5gi 2021"


# mettre à jour la source des paquets 
RUN apt update

# installer la jdk 8
RUN apt install -y openjdk-8-jdk 

# test de la version
RUN	java -version

# crée une variable d'environnement valable dans ce fichier
ARG JAR_FILE=*.jar

# cette instruction est équivalente à faire un cd le ligne de commande
# elle change le répertoire d'exécution des commandes qui viennent après elle
WORKDIR /

# copie les fichiers à l'intérieur du document
COPY ${JAR_FILE} app.jar

# déclare que l'application dans ce container tourne sur le port 8080
EXPOSE 8080

# produira la création d'un volume docker lors de la constru 
#VOLUME /bin

# c'est l'instruction de l'instruction qui est exécutée au démarrage du docker
ENTRYPOINT ["java","-jar","/app.jar"]
