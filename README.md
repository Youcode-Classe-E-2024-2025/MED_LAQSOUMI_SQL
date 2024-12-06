# Gestion d'une base de données : Librairie

## Contexte de l'exercice
Une petite librairie souhaite gérer ses livres et ses clients à l'aide d'une base de données. Ce projet met en place la structure nécessaire pour répondre à leurs besoins et inclut des requêtes SQL pour effectuer diverses opérations.

---

## Objectifs
- Créer une base de données appelée **Librairie**.
- Ajouter et gérer les tables **Livres** et **Clients**.
- Effectuer des opérations comme l'ajout, la mise à jour, et la suppression de données, ainsi que des requêtes de sélection.

---
## Instructions pour exécuter le projet

1. Créer la base de données.
2. Utiliser la base de données.
3. Créer les tables.
4. Insérer les données initiales.

---

## Structure des tables

### Table `Livres`
| Colonne   | Type         | Contraintes                      |
|-----------|--------------|-----------------------------------|
| `id`      | INT          | PRIMARY KEY, AUTO_INCREMENT      |
| `titre`   | VARCHAR(255) | NOT NULL                         |
| `auteur`  | VARCHAR(255) | NOT NULL                         |
| `prix`    | DECIMAL(5,2) | NOT NULL                         |
| `stock`   | INT          | NOT NULL                         |

### Table `Clients`
| Colonne           | Type         | Contraintes                      |
|--------------------|--------------|-----------------------------------|
| `id`              | INT          | PRIMARY KEY, AUTO_INCREMENT      |
| `nom`             | VARCHAR(255) | NOT NULL                         |
| `email`           | VARCHAR(255) | NOT NULL, UNIQUE                 |
| `date_inscription`| DATE         | NOT NULL                         |

---

## Données initiales

### Livres
| Titre                                    | Auteur                  | Prix   | Stock |
|------------------------------------------|-------------------------|--------|-------|
| Les Misérables                           | Victor Hugo             | 20.50  | 12    |
| Le Petit Prince                          | Antoine de Saint-Exupéry| 15.99  | 5     |
| 1984                                     | George Orwell           | 18.00  | 8     |
| Harry Potter et la pierre philosophale   | J.K. Rowling            | 25.00  | 10    |

### Clients
| Nom           | Email                     | Date d'inscription |
|---------------|---------------------------|---------------------|
| Jean Dupont   | jean.dupont@email.fr      | 2024-01-10          |
| Alice Martin  | alice.martin@email.fr     | 2024-02-15          |
| Bob Robert    | bob.robert@email.fr       | 2024-03-20          |

---

## Requêtes à réaliser

1. Listez tous les livres disponibles avec leur titre, auteur, et prix :
    SELECT titre, auteur, prix FROM Livres;
2. Trouvez tous les livres dont le prix est supérieur à 20 euros :
    SELECT * FROM Livres WHERE prix > 20;
3. Trouvez tous les clients inscrits après le 1er février 2024 :
    SELECT * FROM Clients WHERE date_inscription > '2024-02-01';
4. Réduisez le stock de 1 pour le livre "1984" (simulatez une vente) :
    UPDATE Livres SET stock = stock - 1 WHERE titre = '1984';
5. Supprimez un client dont l'email est "bob.robert@email.fr" :
    DELETE FROM Clients WHERE email = 'bob.robert@email.fr';
6. Ajoutez un nouveau livre :
    INSERT INTO Livres (titre, auteur, prix, stock) 
    VALUES ('Le Seigneur des Anneaux', 'J.R.R. Tolkien', 30.00, 7);


