# Farmer Crousty

Site vitrine du restaurant **Farmer Crousty — Poulet & Co.**, à la gare de
Garges-Sarcelles (95140 Garges-lès-Gonesse).

Site statique : du HTML, du CSS, deux vidéos. Aucun outil à installer, aucune
compilation. On ouvre `index.html` dans un navigateur et ça marche.

## Les fichiers

```
index.html             Accueil
les-menus.html         Les cinq formules
la-carte.html          La carte complète et les prix
le-crousty.html        Le plat signature
nous-trouver.html      Horaires, adresse, plan Google Maps
faq.html               Questions fréquentes
contact.html           Formulaire de contact
merci.html             Page de confirmation après envoi du formulaire
404.html               Page d'erreur personnalisée
mentions-legales.html  Mentions légales
cgu.html               Conditions générales d'utilisation
confidentialite.html   Données personnelles (RGPD)

style.css              Toute la mise en forme, partagée par les pages
images/                Photos (JPEG + WebP), logo, image de partage
icons/                 Favicons et icônes d'application
poulet.mp4             Vidéo de fond de l'accueil
mijote.mp4             Vidéo de fond de la page des menus
sitemap.xml            Plan du site pour les moteurs de recherche
robots.txt             Règles d'exploration
site.webmanifest       Nom et icônes quand le site est ajouté à l'écran d'accueil
.nojekyll              Évite le traitement Jekyll sur GitHub Pages
```

Chaque entrée du menu ouvre une page à part entière, et on arrive toujours
en haut de cette page.

## À compléter avant la mise en ligne

Ces repères sont écrits en commentaire dans le code, en majuscules, faciles
à retrouver avec une recherche.

| Repère | Fichier | À remplacer par |
| --- | --- | --- |
| `VOTRE-COMPTE.github.io` | toutes les pages | l'adresse réelle du site |
| `VOTRE-CLE-WEB3FORMS` | `contact.html` | la clé du service d'envoi du formulaire |
| `VOTRE-DOMAINE` | toutes les pages | le domaine déclaré dans Plausible |
| `TÉLÉPHONE` | `contact.html`, `nous-trouver.html` | le numéro de commande |
| `HORAIRES` | `nous-trouver.html` | les horaires réels |
| `ADRESSE` | `nous-trouver.html` | l'adresse exacte de la boutique |
| `VIDÉO` | `index.html` | la vidéo du hero sous licence |

### Le formulaire de contact

Un site statique ne peut pas traiter un formulaire lui-même : il n'y a pas de
serveur pour recevoir l'envoi. L'envoi passe donc par un service externe.

1. Créer un compte gratuit sur [web3forms.com](https://web3forms.com) — 250
   messages par mois, sans carte bancaire.
2. Indiquer l'adresse e-mail qui recevra les messages.
3. Coller la clé reçue dans `contact.html`, à la place de `VOTRE-CLE-WEB3FORMS`.

Le formulaire vérifie déjà les champs côté navigateur et bloque les robots par
deux moyens : un champ piège invisible pour un humain, et un délai minimum de
trois secondes entre l'ouverture de la page et l'envoi.

### La mesure d'audience

Le code de [Plausible](https://plausible.io) est en place dans le script, en bas
de chaque page. Il ne se charge **que** si le visiteur accepte via le bandeau.
Remplacer `VOTRE-DOMAINE` par le domaine déclaré dans Plausible. Pour utiliser
Matomo à la place, remplacer ce bloc par le code fourni par Matomo, au même
endroit.

## Mettre le site en ligne avec GitHub Pages

1. Onglet **Settings** du dépôt, puis **Pages** dans la colonne de gauche.
2. Source : **Deploy from a branch**, branche `main`, dossier `/ (root)`, **Save**.
3. Cocher **Enforce HTTPS** un peu plus bas sur la même page. C'est ce réglage
   qui force le site en HTTPS ; les pages demandent déjà que toute ressource
   appelée en http bascule en https.
4. Une à deux minutes plus tard, le site est en ligne.

Pour un nom de domaine à soi : ajouter à la racine un fichier `CNAME` contenant
seulement le domaine, puis le faire pointer vers GitHub chez le registrar.

La page 404 est servie automatiquement par GitHub Pages pour toute adresse
inconnue. Ses liens sont relatifs : si le site est publié dans un sous-dossier
et qu'une erreur survient à plusieurs niveaux de profondeur, ajouter
`<base href="/farmer-crousty/">` dans son `<head>`.

## Ce qui est déjà en place

**Référencement** — un titre et une description propres à chaque page, un lien
canonique, un sitemap, un robots.txt, des données structurées Schema.org pour le
restaurant, et une image de partage 1200 × 630 pour les réseaux sociaux.

**Vitesse** — feuille de style unique mise en cache, photos en WebP avec repli
JPEG (60 % plus légères), dimensions inscrites sur chaque image pour éviter les
sauts de mise en page, chargement différé de ce qui est hors écran, et
pré-chargement de la page survolée pour que le clic paraisse instantané.

**Accessibilité** — contrastes vérifiés au niveau AA sur toutes les pages et
toutes les largeurs, texte alternatif sur chaque image, un seul titre principal
par page, navigation au clavier avec lien d'évitement, zones tactiles d'au moins
44 pixels, et respect du réglage « réduire les animations ».

**Vie privée** — aucun cookie publicitaire, aucun traceur par défaut. Le seul
élément stocké est la réponse au bandeau de consentement, dans le navigateur du
visiteur. Le lien « Préférences de confidentialité » en bas de page permet de
revenir sur ce choix à tout moment.

## Modifier le contenu

Les textes sont en clair dans les fichiers `.html` : on peut les changer depuis
GitHub, avec le bouton crayon, sans rien installer.

Les couleurs, les polices et l'échelle des titres se règlent tout en haut de
`style.css`, dans le bloc `:root`. Changer une seule ligne suffit à modifier
l'orange sur tout le site.

## Polices

**Sora** pour les titres, **Archivo** pour les textes, **Courier Prime** pour les
adresses et les prix. Toutes gratuites, libres d'usage commercial, chargées
depuis Google Fonts.

## Crédits

Les photos des plats sont recadrées depuis les visuels du restaurant. La vidéo
de fond de l'accueil est pour l'instant un aperçu filigrané d'iStock : il faut
acheter la licence et remplacer `poulet.mp4` avant toute mise en ligne publique.
