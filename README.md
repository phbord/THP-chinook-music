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
- Quel est le nombre total d'objets `Album` contenus dans la base (sans regarder les id bien sûr) ? => `Album.count`
- Qui est l'auteur de la chanson "White Room" ? => `tp Track.select(:artist).find_by(title:'White Room')`
- Quelle chanson dure exactement 188133 milliseconds ? => `tp Track.select(:title).find_by(duration:'188133')`
- Quel groupe a sorti l'album "Use Your Illusion II" ? => `tp Album.select(:artist).find_by(title:'Use Your Illusion II')`
#### b. Niveau Moyen
- Combien y a t'il d'albums dont le titre contient "Great" ? => `Album.where('title like ?', '%Great%').count`
- Supprime tous les albums dont le nom contient "music". => `tp Album.where('title like ?','%music%').destroy_all`
- Combien y a t'il d'albums écrits par AC/DC ? => `Album.select(:title).where('artist like ?','%AC/DC%').count`
- Combien de chanson durent exactement 158589 millisecondes ? => `Track.select(:title).where('duration like ?', '158589').count`
#### c. Niveau Difficile
Effectuer des _boucles_ dans la console Rails
- `puts` en console tous les titres de AC/DC.
  - => `Track.where('artist like ?','AC/DC').each do |t|
    puts t.title
end`
- `puts` en console tous les titres de l'album "Let There Be Rock".
  - => `Track.where(artist:'AC/DC', album:'Let There Be Rock').find_each do |t|
    puts t.title
end`
- Calcule le prix total de cet album ainsi que sa durée totale.
  - => `Track.where(artist:'AC/DC', album:'Let There Be Rock').pluck("SUM(price), SUM(duration)")`
- Calcule le coût de l'intégralité de la discographie de "Deep Purple".
  - => `Track.where(artist:'Deep Purple').pluck("SUM(price)")`
- Modifie (via une _boucle_) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.
  - => `Track.where(artist:'Eric Clapton').update_all("artist = 'Britney Spears'")`