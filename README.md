# Greet User Action

Cette action salue un utilisateur avec un message personnalisé.

## Inputs

| Nom       | Description                | Obligatoire | Valeur par défaut |
|-----------|----------------------------|-------------|--------------------|
| `username`| Nom de l'utilisateur       | Oui         | -                  |
| `greeting`| Message de salutation      | Non         | Bonjour            |

## Outputs

| Nom       | Description                |
|-----------|----------------------------|
| `message` | Le message complet de salutation |

## Exemple d'utilisation

```yaml
name: "Exemple de workflow"
on:
  push:
    branches:
      - main

jobs:
  greet-user:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Dire bonjour
      uses: ./ # Utilise l'action locale
      with:
        username: "Jean"
        greeting: "Salut"
```
Initialiser un dépôt Git et le pousser sur GitHub :

git init     
git add .
git commit -m "Ajout de l'action personnalisée"
git branch -M main
git remote add origin <URL_DU_DEPOT>
git push -u origin main
Créer un workflow .github/workflows/test.yaml pour tester votre action

name: "Exemple de workflow"
on:
  push:
    branches:
      - main

jobs:
  greet-user:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Dire bonjour
      uses: ./ # Utilise l'action locale
      with:
        username: "Jean"
        greeting: "Salut"
        