# Cinéma Creuse : moteur de recommandation de films 

**Résumé** :

Application web Streamlit pour un cinéma de la Creuse qui passe au numérique. 
Elle propose un catalogue de films de type Netflix, un système de recommandation par machine learning et un tableau de bord de KPI pour l’administrateur.

_Contexte_ :

Le client est un cinéma en perte de vitesse dans la Creuse qui veut un site pour les locaux, avec un moteur de recommandations de films. 
Aucun client n’a renseigné ses préférences : c’est une situation de cold start. Le client fournit une base IMDb et un jeu complémentaire TMDB (budget, recettes, pays des sociétés de production, chemins des posters).

Nous sommes 3 collaborateurs a travailler sur ce projet pour livrer le produit dans les meilleures conditions. 

## Fonctionnalités

**Côté client**

1. _Accueil_ : carrousel défilant des 25 films les plus populaires, puis bandeaux « Les mieux notés », « Les plus populaires », « Les plus récents » et les 6 genres les plus fréquents.

2. _Recherche et filtres_ : saisie avec suggestions, filtre par genre traduit en français, grille de 4 colonnes, 20 films par page.

3. _Fiche film_ : image de fond, affiche, synopsis en français (API TMDB), note et votes IMDb, bande-annonce YouTube, 10 films similaires.

4. _Avis spectateurs_ : sentiment positif, négatif ou neutre, traduction automatique en français, affichage 3 par 3.

**Côté administrateur (accès protégé par identifiants fictive)**

1. _Chiffres clés_ : nombre de films, note moyenne, nombre de genres, période couverte.

2. _Genres_ : classement, évolution par décennie, durée moyenne par décennie.

3. _Classements_ : acteurs, réalisateurs, scénaristes, compositeurs, pays, sociétés de production.
Distributions de la durée et des notes.

4. Rentabilité (ROI) moyenne par genre.

5. Avis positifs_ et négatifs par film.

6. Archives PDF_ : ajout, téléchargement, suppression.

## Moteur de recommandation 

Similarité entre films, calculée sur un vecteur combinant :


| Variable | Traitement |
|---|---|
| Synopsis |TF-IDF (1 000 termes) |
| Genres |MultiLabelBinarizer |
| Réalisateur, acteur, compositeur (premier cité) | OneHotEncoder |
| Pays et studios de production | MultiLabelBinarizer |
| Année |StandardScaler|

Les 10 films les plus proches du film consulté sont affichés.

**Exemple** : 

Un utilisateur ouvre "Inception", le moteur cherche les films qui lui ressemblent le plus par le genre, le synopsis, l’équipe et l’époque

## Stack

- [x] Méthode SCRUM
- [x] Python
- [x] Pandas, NumPy
- [x] Streamlit
- [x] Scikit-Learn
- [x] SciPy
- [x] Plotly
- [x] Requests
- [x] API TMDB
- [x] Deep-translator (Google Translate)

