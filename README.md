# Projet RabbitMQ - Tutoriel Docker & Interface Web

Ce projet guide la mise en place d'un serveur RabbitMQ via Docker et la manipulation de ses composants via l'interface web d'administration.

##  Objectif

Mettre en place RabbitMQ via Docker, puis manipuler l'interface web pour :
- Créer un exchange
- Créer une queue
- Effectuer un binding
- Publier un message
- Lire les messages depuis la queue

##  Prérequis

- Docker installé (Docker Desktop sous Windows, ou Docker Engine sous Linux)
- Accès à Internet (pour télécharger l'image Docker)
- Navigateur web moderne

##  Démarrage Rapide

### Étape 1 — Identifier et télécharger l'image Docker

```bash
docker pull rabbitmq:3.12.9-management
```

### Étape 2 — Lancer le conteneur RabbitMQ

```bash
docker run -d \
  --hostname rabbit \
  --name rabbit-server \
  -p 15672:15672 \
  -p 5672:5672 \
  rabbitmq:3.12.9-management
```

**Paramètres :**
- `-d` : exécution en arrière-plan (mode détaché)
- `--hostname rabbit` : nom d'hôte interne du serveur
- `--name rabbit-server` : nom du conteneur
- `-p 15672:15672` : port pour l'interface web
- `-p 5672:5672` : port pour les clients AMQP

### Étape 3 — Vérifier l'état du conteneur

```bash
docker ps
```



##  Commandes Docker Utiles

```bash
# Voir les logs du conteneur
docker logs rabbit-server

# Arrêter le conteneur
docker stop rabbit-server

# Redémarrer le conteneur
docker start rabbit-server

# Supprimer le conteneur
docker rm rabbit-server

# Accéder au shell du conteneur
docker exec -it rabbit-server bash
```

##  Nettoyage

Pour arrêter et supprimer le conteneur :

```bash
docker stop rabbit-server
docker rm rabbit-server
```

Pour supprimer également l'image :

```bash
docker rmi rabbitmq:3.12.9-management
```

##  Concepts Clés

- **Exchange** : Point d'entrée des messages, route les messages vers les queues
- **Queue** : File d'attente qui stocke les messages
- **Binding** : Règle de routage entre un exchange et une queue
- **Message** : Donnée transmise entre producteur et consommateur
- **Producer** : Application qui publie des messages
- **Consumer** : Application qui lit des messages

##  Dépannage

### Le conteneur ne démarre pas
```bash
docker logs rabbit-server
```


### Problèmes d'authentification
- Les identifiants par défaut sont `guest`/`guest`
- Vérifiez que vous accédez depuis `localhost`

##  Ressources
![WhatsApp Image 2025-12-23 at 21 48 18](https://github.com/user-attachments/assets/3b9d42ed-381b-4007-950d-22de63668444)
![WhatsApp Image 2025-12-23 at 21 48 18 (1)](https://github.com/user-attachments/assets/f0767bbe-034d-4eb8-b339-5bde47b5c174)
![WhatsApp Image 2025-12-23 at 21 48 19](https://github.com/user-attachments/assets/6f664cb6-e32c-4bfc-99d3-e9aae5400557)
![WhatsApp Image 2025-12-23 at 21 48 19 (1)](https://github.com/user-attachments/assets/3999e908-5cb0-4e54-9245-86519c167678)
![WhatsApp Image 2025-12-23 at 21 48 20](https://github.com/user-attachments/assets/2b69ca9f-7bcc-46a4-a0be-23fa57f2e2a5)
![WhatsApp Image 2025-12-23 at 21 48 20 (1)](https://github.com/user-attachments/assets/51d8e4f8-67aa-4720-bc73-2e7a6c9c2bfc)
![WhatsApp Image 2025-12-23 at 21 48 21](https://github.com/user-attachments/assets/f0d534b4-d4fe-4723-81a8-fea398f53f70)

![WhatsApp Image 2025-12-23 at 21 51 00](https://github.com/user-attachments/assets/97e9ee04-376a-4517-b18b-83d426b7713e)





---


