Contrat de cession
==================

Modèle LaTeX pour la création des contrats de cession Libre de l'AMMD


Création d'un nouveau contrat
=============================

Nouveau contrat vierge
----------------------

1. création de la copie local du dépôt git : `git clone https://github.com/AMMD/contrat_de_cession.git`
2. on se déplace dans le nouveau répertoire créé : `cd contrat_de_cession`
3. création de la nouvelle branche de travail : `git checkout -b nomDuGroupe-lieu-date-WIP`
4. réaliser les modifications dans le fichier `config.tex`
5. modifier les articles du contrat dans le fichier `main.tex` (si besoin, et en discussion avec l'organisateur)
6. ajouter les fichiers modifiés à la liste de la prochaine validation git : `git add config.tex main.tex`
7. valider les modifications faites dans git : `git commit -m "Message de validation"`
8. pousser les validation sur le dépôt central : `git push origin nomDuGroupe-lieu-date-WIP`
9. refaire les points 4, 5, 6, 7 et 8 tant que le contrat n'est pas validé par les deux partenaires (tourneur et organisateur)
10. lorsque le contrat est validé par les deux partenaires : `git tag nomDuGroupe-lieu-date` (on peut faire une signature numérique GPG du tag en ajoutant l'option `-s`)
11. on pousse sur le dépôt central le tag nouvellement créé : `git push nomDuGroupe-lieu-date`
12. puis supprimer la branche sur laquelle nous travaillions : `git branch -D nomDuGroupe-lieu-date-WIP`
13. on pousse sur le dépôt central la suppression de branche : `git push origin --delete nomDuGroupe-lieu-date-WIP`


Nouveau contrat depuis un existant
----------------------------------

1. `git clone https://github.com/AMMD/contrat_de_cession.git`
2. `cd contrat_de_cession`
3. on change de branche pour aller dans celle qui contient déjà des informations : `git checkout branche-ou-tag-existant`
4. création de la nouvelle branche de travail : `git checkout -b nomDuGroupe-lieu-date-WIP`
5. réaliser les modifications dans le fichier `config.tex`
6. modifier les articles du contrat dans le fichier `main.tex` (si besoin, et en discussion avec l'organisateur)
7. ajouter les fichiers modifiés à la liste de la prochaine validation git : `git add config.tex main.tex`
8. valider les modifications faites dans git : `git commit -m "Message de validation"`
9. pousser les validation sur le dépôt central : `git push origin nomDuGroupe-lieu-date-WIP`
10. refaire les points 4, 5, 6, 7 et 8 tant que le contrat n'est pas validé par les deux partenaires (tourneur et organisateur)
11. lorsque le contrat est validé par les deux partenaires : `git tag nomDuGroupe-lieu-date` (on peut faire une signature numérique GPG du tag en ajoutant l'option `-s`)
12. on pousse sur le dépôt central le tag nouvellement créé : `git push nomDuGroupe-lieu-date`
13. puis supprimer la branche sur laquelle nous travaillions : `git branch -D nomDuGroupe-lieu-date-WIP`
14. on pousse sur le dépôt central la suppression de branche : `git push origin --delete nomDuGroupe-lieu-date-WIP`


Compilation d'un contrat de cession
===================================

1. première compilation LaTeX : `pdflatex main`
2. deuxième compilation LaTeX pour avoir les références internes correctes : `pdflatex main`
3. affichage du contrat de cession : `evince main.pdf`


Ajout du contrat de cession validé à la facture dans le Dolibarr
================================================================

1. récupérer la version du contrat de cession adaptée (Cf. Nouveau contrat)
2. compiler le contrat de cession (Cf. Compilation d'un contrat de cession)
3. renommer le fichier de contrat de cession : `mv main.pdf nomDuGroup-lieu-date.pdf`
4. charger en tant que *fichier joint* le fichier `nomDuGroupe-lieu-date.pdf` à la facture client
