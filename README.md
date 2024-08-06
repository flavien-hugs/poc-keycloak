# Keycloak POC

## Description

Ce projet est une preuve de concept (PoC) démontrant l'utilisation de Keycloak avec le package `python-keycloak`.
Il inclut des tests effectués avec Jupyter Notebook pour valider les fonctionnalités d'authentification
et d'autorisation.

## Table des matières

<list>
<li><a anchor="installation">Installation</a></li>
<li><a anchor="configuration">Configuration</a></li>
<li><a anchor="utilisation">Utilisation</a></li>
<li><a anchor="tests">Tests</a></li>
<li><a anchor="contribuer">Contribuer</a></li>
<li><a anchor="licence">Licence</a></li>
</list>

## Installation

### Prérequis

- Python 3.8+
- Docker (pour exécuter Keycloak)
- Jupyter Notebook

### Étapes d'installation

1. Clonez le dépôt :

    ```bash
    git clone https://github.com/votre-utilisateur/keycloak-poc.git
    cd keycloak-poc
    ```

2. Créez et activez un environnement virtuel :

    ```bash
    python -m venv venv
    source venv/bin/activate  # Sur Windows : venv\Scripts\activate
    ```

3. Installez les dépendances :

    ```bash
    pip install -r requirements.txt
    ```

4. Lancez Keycloak via Docker :

    ```bash
    docker compose up
    ```

## Configuration

### Keycloak

1. Accédez à l'interface d'administration de Keycloak à `http://localhost:8080`.
2. Connectez-vous avec les informations d'identification administrateur (`admin` / `admin`).
3. Créez un nouveau **Realm**.
4. Créez un **Client** dans ce realm.
5. Configurez les **Rôles** et les **Utilisateurs** nécessaires.

### Fichier de configuration

Créez un fichier `.env` à la racine du projet avec les informations suivantes :

    ```plaintext
    KEYCLOAK_URL=http://localhost:8080
    KEYCLOAK_REALM=nom_du_realm
    KEYCLOAK_CLIENT_ID=nom_du_client
    KEYCLOAK_CLIENT_SECRET=secret_du_client
    KEYCLOAK_ADMIN_USERNAME=admin
    KEYCLOAK_ADMIN_PASSWORD=admin
    ```

## Utilisation

### Lancer l'application

L'application principale est conçue pour être utilisée via des notebooks Jupyter. Lancez Jupyter Notebook :

    ```bash
    jupyter notebook
    ```

Ouvrez le fichier `keycloak-admin-connect.ipynb` et `openid-keycloak-connect.ipynb` et exécutez les cellules
pour interagir avec Keycloak en utilisant le package `python-keycloak`.

## Tests

Les tests sont inclus dans le notebook `keycloak-admin-connect.ipynb` et `openid-keycloak-connect.ipynb`.
Chaque cellule contient des commandes qui testent différentes fonctionnalités de l'intégration Keycloak.
Assurez-vous que votre serveur Keycloak est en cours d'exécution avant d'exécuter les tests.

## Contribuer

Les contributions sont les bienvenues ! Veuillez suivre les étapes suivantes pour contribuer :

1. Forkez le dépôt.
2. Créez une branche pour votre fonctionnalité (`git checkout -b ma-nouvelle-fonctionnalité`).
3. Commitez vos modifications (`git commit -am 'Ajouter ma fonctionnalité'`).
4. Poussez la branche (`git push origin ma-nouvelle-fonctionnalité`).
5. Ouvrez une Pull Request.
