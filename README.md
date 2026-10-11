# Médiathèque API

API REST backend de gestion d'une médiathèque de quartier (projet fil rouge de la formation Spring Boot / JPA).

## Table des endpoints (conception — séance 1)

URL de base : http://localhost:8080/mediatheque-api

| Méthode | URL | Succès | Erreurs |
|---|---|---|---|
| POST | /api/v1/auteurs | 201 + Location | 400 |
| GET | /api/v1/auteurs?page=&size= | 200 | |
| GET, PUT, DELETE | /api/v1/auteurs/{id} | 200 / 200 / 204 | 404, 409 (auteur avec livres) |
| POST, GET | /api/v1/categories | 201 / 200 | 400, 409 (libellé existant) |
| POST | /api/v1/livres | 201 + Location | 400, 404 (auteur), 409 (ISBN existant) |
| GET | /api/v1/livres?titre=&page=&size= | 200 | |
| GET, PUT, DELETE | /api/v1/livres/{id} | 200 / 200 / 204 | 404, 409 |
| POST | /api/v1/adherents | 201 + Location | 400, 409 (email existant) |
| GET | /api/v1/adherents | 200 | |
| GET, PUT | /api/v1/adherents/{id} | 200 | 404, 409 |
| PATCH | /api/v1/adherents/{id}/desactivation | 200 | 404 |
| POST | /api/v1/emprunts | 201 + Location | 400, 404, 409 (quota, retard, indisponible) |
| GET | /api/v1/emprunts/{id} | 200 | 404 |
| PATCH | /api/v1/emprunts/{id}/retour | 200 | 404, 409 (déjà rendu) |
| GET | /api/v1/emprunts/en-retard | 200 | |
| GET | /api/v1/adherents/{id}/emprunts | 200 | 404 |
