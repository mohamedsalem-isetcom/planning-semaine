# Planning de la semaine

Un planning hebdomadaire interactif pour toutes les semaines : 7 jours, 24 heures chacun. Une seule page HTML, sans installation, sans serveur, sans compte.

## Fonctionnalités

- **Toutes les semaines** : flèches précédente/suivante, sélecteur de date et bouton « Aujourd'hui ». Chaque semaine a ses propres activités.
- **Activités répétées** : cochez « Répéter chaque semaine » pour qu'une activité apparaisse dans toutes les semaines (cours, sommeil, sport).
- **Heures à la minute près** : saisissez par exemple 11:42 ou 12:07.
- **Import automatique de votre planning d'étude** : choisissez un fichier ou déposez-le sur la page. Formats : Excel (.xlsx, .xls), CSV, texte, calendrier (.ics), JSON, PDF et image. Vous voyez la liste des activités trouvées, puis un clic les ajoute (chaque semaine ou cette semaine seulement). Les captures d'écran, images et PDF d'emploi du temps (blocs colorés) sont lus directement dans votre navigateur par reconnaissance de texte (OCR), sans IA ni compte : les blocs sont détectés, les horaires sont lus à la minute et le jour/la semaine viennent de l'en-tête. Vérifiez la liste : un titre mal lu se corrige avant l'ajout. Internet est nécessaire (bibliothèques Tesseract.js, pdf.js, SheetJS chargées depuis un CDN).
- **Grille 7 jours × 24 h** Cliquez sur une case pour ajouter une activité, cliquez sur un bloc pour le modifier ou le supprimer.
- **Catégories colorées** : Travail, Études, Sport, Repas, Sommeil, Loisirs, Autre.
- **Plusieurs jours à la fois** : cochez les jours concernés pour répéter une activité.
- **Activités de nuit** : un bloc qui finit après minuit (par exemple 23:00 → 07:00) passe sur le jour suivant. Un dimanche soir qui finit après minuit se poursuit le lundi de la semaine suivante.
- **Votre nom** dans l'en-tête, repris dans le PDF.
- **Thème au choix** : Auto, Clair ou Sombre.
- **Statistiques** de la semaine affichée : taux d'occupation, heures actives, sommeil moyen, jour le plus chargé et le plus léger, plus longue plage libre, plus long bloc, répartition de chaque journée et rythme par heure.
- **Export PDF** de la semaine affichée : A4 paysage sur fond blanc, grille en page 1 et statistiques en page 2.
- **Sauvegarde automatique** dans le navigateur (`localStorage`). Aucune donnée n'est envoyée ailleurs.

## Utilisation

1. Téléchargez ce dépôt, ou clonez-le :
   ```bash
   git clone https://github.com/<votre-compte>/<votre-depot>.git
   ```
2. Ouvrez `index.html` dans votre navigateur.

La page charge la police (Google Fonts) et la bibliothèque PDF (jsPDF, via cdnjs) depuis Internet. Les lecteurs Excel (SheetJS) et PDF (pdf.js) ne se chargent qu'au moment d'un import. Sans connexion, le planning fonctionne mais avec une police de secours, et l'export et l'import de fichiers Excel ou PDF sont indisponibles.

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

Le planning, le nom et le thème sont enregistrés dans la clé `planning-semaine-v3` du `localStorage` de votre navigateur. Ils restent sur votre appareil. Vider les données du site efface le planning.

## Technologies

HTML, CSS et JavaScript sans framework. [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 pour l'export PDF, [SheetJS](https://sheetjs.com) 0.18.5 pour l'import Excel et [pdf.js](https://mozilla.github.io/pdf.js/) 3.11.174 pour l'import PDF.

## Licence

Distribué sous licence MIT. Voir le fichier [LICENSE](LICENSE).
