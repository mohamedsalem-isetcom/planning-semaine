# Planning de la semaine

Un planning hebdomadaire interactif : 7 jours, 24 heures chacun. Une seule page HTML, sans installation, sans serveur, sans compte.

## Fonctionnalités

- **Grille 7 jours × 24 h** avec un pas d'une demi-heure. Cliquez sur une case pour ajouter une activité, cliquez sur un bloc pour le modifier ou le supprimer.
- **Catégories colorées** : Travail, Études, Sport, Repas, Sommeil, Loisirs, Autre.
- **Plusieurs jours à la fois** : cochez les jours concernés pour répéter une activité.
- **Activités de nuit** : un bloc qui finit après minuit (par exemple 23:00 → 07:00) passe sur le jour suivant.
- **Votre nom** dans l'en-tête, repris dans le PDF.
- **Thème au choix** : Auto, Clair ou Sombre.
- **Statistiques** : taux d'occupation, heures actives, sommeil moyen, jour le plus chargé et le plus léger, plus longue plage libre, plus long bloc, répartition de chaque journée et rythme par heure.
- **Export PDF** : A4 paysage sur fond blanc, grille de la semaine en page 1 et statistiques en page 2.
- **Sauvegarde automatique** dans le navigateur (`localStorage`). Aucune donnée n'est envoyée ailleurs.

## Utilisation

1. Téléchargez ce dépôt, ou clonez-le :
   ```bash
   git clone https://github.com/<votre-compte>/<votre-depot>.git
   ```
2. Ouvrez `index.html` dans votre navigateur.

La page charge la police (Google Fonts) et la bibliothèque PDF (jsPDF, via cdnjs) depuis Internet. Sans connexion, le planning fonctionne mais avec une police de secours, et l'export PDF est indisponible.

## Publier avec GitHub Pages

1. Poussez les fichiers sur GitHub.
2. Dans le dépôt : **Settings → Pages**.
3. Source : **Deploy from a branch**, branche `main`, dossier `/ (root)`.
4. Votre planning est en ligne à `https://<votre-compte>.github.io/<votre-depot>/`.

## Personnaliser

Tout est dans `index.html` :

- **Couleurs et polices** : variables CSS au début de la balise `<style>` (`--c-work`, `--c-sleep`, etc.).
- **Catégories** : tableau `CATS` dans le script, et les couleurs du PDF dans `PDF_COLORS`.
- **Hauteur d'une heure** : variable `--hh` (CSS) et constante `HH` (script), à garder identiques.

## Données

Le planning, le nom et le thème sont enregistrés dans la clé `planning-semaine-v1` du `localStorage` de votre navigateur. Ils restent sur votre appareil. Vider les données du site efface le planning.

## Technologies

HTML, CSS et JavaScript sans framework. [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 pour l'export PDF.

## Licence

Distribué sous licence MIT. Voir le fichier [LICENSE](LICENSE).
