# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## Chinook Music

### 1. Projet
- re-créer une BDD via un seed
- aller dans le fichier "seeds.rb"
- puis lancer : `rails db:seed`

### 2. Questions
#### a. Niveau facile
- Quel est le nombre total d'objets `Album` contenus dans la base (sans regarder les id bien sûr) ? => `tp Album.count`
- Qui est l'auteur de la chanson "White Room" ? => `tp Track.select(:artist).find_by(title:'White Room')`
- Quelle chanson dure exactement 188133 milliseconds ? => ``
- Quel groupe a sorti l'album "Use Your Illusion II" ? => ``
#### b. Niveau Moyen
- Combien y a t'il d'albums dont le titre contient "Great" ? (indice) => ``
- Supprime tous les albums dont le nom contient "music". => ``
- Combien y a t'il d'albums écrits par AC/DC ? => ``
- Combien de chanson durent exactement 158589 millisecondes ? => ``
#### c. Niveau Difficile
- puts en console tous les titres de AC/DC. => ``
- puts en console tous les titres de l'album "Let There Be Rock". => ``
- Calcule le prix total de cet album ainsi que sa durée totale. => ``
- Calcule le coût de l'intégralité de la discographie de "Deep Purple". => ``
- Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist. => ``