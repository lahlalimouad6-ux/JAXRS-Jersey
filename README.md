# Ms-Banque : Spring Boot, JPA, JAX-RS (Jersey)

Ce projet est une application de gestion de comptes bancaires développée avec Spring Boot, Spring Data JPA, H2 Database et Jersey (JAX-RS). Elle permet de gérer des opérations CRUD sur des comptes bancaires via une API RESTful supportant les formats **JSON** et **XML**.

## 🚀 Fonctionnalités
- Gestion des comptes (Créer, Lire, Mettre à jour, Supprimer).
- Support multi-format : **JSON** et **XML**.
- Base de données en mémoire **H2**.
- Initialisation automatique de données au démarrage.

## 🛠️ Technologies utilisées
- **Java 17**
- **Spring Boot 3.1.5**
- **Spring Data JPA**
- **H2 Database**
- **Jersey (JAX-RS)**
- **Lombok**
- **JAXB** (pour le support XML)

## 📁 Structure du Projet
Le projet suit une architecture en couches classique :
- `entities` : Définition de l'entité `Compte` et de l'énumération `TypeCompte`.
- `repositories` : Interface `CompteRepository` pour l'accès aux données.
- `controllers` : API REST JAX-RS `CompteRestJaxRSAPI`.
- `config` : Configuration de Jersey via `ResourceConfig`.

## ⚙️ Configuration
Le serveur est configuré sur le port **8082**.
La base de données H2 est accessible à l'adresse : `http://localhost:8082/h2-console`
- **JDBC URL** : `jdbc:h2:mem:banque`
- **User** : `sa`
- **Password** : (vide)

## 📡 API Endpoints

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| GET | `/banque/comptes` | Récupérer tous les comptes |
| GET | `/banque/comptes/{id}` | Récupérer un compte par son ID |
| POST | `/banque/comptes` | Ajouter un nouveau compte |
| PUT | `/banque/comptes/{id}` | Mettre à jour un compte |
| DELETE | `/banque/comptes/{id}` | Supprimer un compte |

## 🧪 Tests
### Récupérer les comptes en JSON
```bash
curl -X GET "http://localhost:8082/banque/comptes" -H "Accept: application/json"
```

### Récupérer les comptes en XML
```bash
curl -X GET "http://localhost:8082/banque/comptes" -H "Accept: application/xml"
```

## 📸 Screenshots
### Console H2
![Console H2](https://coresg-normal.trae.ai/api/ide/v1/text_to_image?prompt=H2%20database%20console%20interface%20showing%20a%20table%20named%20COMPTE%20with%20data%20rows%20containing%20ID,%20SOLDE,%20DATE_CREATION,%20TYPE&image_size=landscape_16_9)

### Test avec Postman (JSON)
![Test JSON](https://coresg-normal.trae.ai/api/ide/v1/text_to_image?prompt=Postman%20API%20test%20showing%20a%20GET%20request%20to%20http://localhost:8082/banque/comptes%20returning%20a%20list%20of%20bank%20accounts%20in%20JSON%20format&image_size=landscape_16_9)

### Test avec Postman (XML)
![Test XML](https://coresg-normal.trae.ai/api/ide/v1/text_to_image?prompt=Postman%20API%20test%20showing%20a%20GET%20request%20to%20http://localhost:8082/banque/comptes%20returning%20a%20list%20of%20bank%20accounts%20in%20XML%20format&image_size=landscape_16_9)
