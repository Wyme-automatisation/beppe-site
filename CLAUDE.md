# Site beppe.fr — cahier des charges pour Claude Code

## Le projet
Site vitrine de **Beppe**, atelier local qui fabrique des outils numériques sur mesure (IA, automatisation, développement) pour les artisans, TPE et PME (de quelques personnes à une centaine de salariés), en Maine-et-Loire et alentours (basé à Cholet et Angers). Zone affichée sur le site : « Maine-et-Loire » uniquement ; des villes de Vendée ou d'ailleurs peuvent être citées si besoin.

- Exploitant : WYME SASU (nom commercial « Beppe »). WYME n'apparaît que dans les mentions légales.
- Domaine : beppe.fr — e-mail de contact : bonjour@beppe.fr
- Langue : français uniquement.
- Version : v1 de lancement, 5 pages. Le site grandira ensuite (pages solutions, secteurs) quand des projets réels seront livrés.

## Message (ne pas reformuler sans demander)
- Nom : Beppe
- Promesse : « On fabrique vos outils sur mesure. »
- Métiers : IA · Automatisation · Développement
- Offre d'entrée : « Le diagnostic Beppe » — 1 h chez le client ou en visio, offert et sans engagement : les 3 tâches qui coûtent le plus de temps, ce qu'on peut en faire, un ordre de grandeur du temps à gagner et de l'effort.
- Histoire : Beppe est le petit nom des Giuseppe, comme Geppetto, le menuisier qui sculpta Pinocchio. Geppetto n'est nommé qu'une seule fois, dans l'encadré « D'où vient son nom ? » de l'accueil.

## Pages (v1)
1. `/` Accueil — haut de page olive (promesse, métiers, 2 boutons), « Ce qui grippe vos journées » (6 irritants), « Ce qu'on fabrique » (3 outils), « Le diagnostic Beppe », « Qui est Beppe ? » (portrait + histoire en 3 temps + encadré du nom), « Pour qui », appel à l'action, pied de page.
2. `/solutions` — 3 solutions sur une seule page (ancres #interventions, #comptes-rendus, #demandes), chacune en avant / après + « pour qui », puis « Votre problème n'est pas dans la liste ? ».
3. `/atelier` — 3 métiers, méthode en 4 étapes (On écoute, On dessine, On fabrique, Ça tourne tout seul), principes, bandeau « Vos outils restent les vôtres. On fabrique les pièces qui manquent. »
4. `/contact` — formulaire (nom, entreprise, e-mail, téléphone, type de demande, secteur, message) + « Et ensuite ? » + coordonnées.
5. `/mentions-legales` — texte fourni avec des [champs à compléter].

Le contenu exact (textes, ordre, sections) est dans `maquette-v1/` : reprendre les textes à l'identique. Les fichiers `.dc.html` sont des maquettes d'un éditeur de design : s'en servir comme référence de contenu et de style, pas comme code à copier tel quel (ignorer `support.js`, `<x-dc>`, `<dc-import>`, `<helmet>`, les balises de script DCLogic).
- `V1Header` = menu, `V1Footer` = pied de page, `V1Cta` = bloc d'appel à l'action, `Hero` = en-tête des pages intérieures (props fil, surtitre, titre, chapo).
- `Main.dc.html` = planche de la charte, `Mascotte.dc.html` = le personnage Beppe (SVG).

## Charte graphique
Couleurs :
- Beige atelier `#F3ECE1` (fond) · Beige foncé `#EAE2D3` (sections alternées) · Olive `#394429` (marque, fonds forts) · Étincelle `#D4FF33` (petites touches sur fond olive uniquement) · Brique `#C2361F` (accents sur fond clair) · Encre `#1E1F17` (texte, pied de page) · Texte secondaire `#4A4D3C`.
- Pas de violet.

Typographies (Google Fonts) :
- Fraunces (italique, 600–800) : nom Beppe, titres, promesse.
- Familjen Grotesk (400–700) : textes, menus, boutons, surtitres en capitales espacées.

Logo : croix de marionnettiste aux trois fils coupés + étincelle jaune, à côté du mot « Beppe » en Fraunces italique 800. SVG dans les maquettes : l'extraire dans un composant réutilisable (versions olive sur clair, beige sur foncé). Le logo n'a jamais de texte collé dessous.

Personnage Beppe : SVG au trait (casquette, barbe, loupe d'horloger avec étincelle). Usage discret : filigrane ~12–15 % d'opacité ou pastille ronde. Jamais collé au logo. Ne pas s'inspirer du Geppetto de Disney.

Style : néo-rétro, sobre, beaucoup d'air, coins arrondis (14–16 px cartes, pilule pour boutons), pas de dégradés, pas d'emoji, pas d'images de stock.

## Contraintes techniques
- Site statique, rapide, simple à maintenir. Stack conseillée : **Astro + Tailwind CSS** (tokens de la charte dans la config), sans framework JS lourd.
- Responsive (mobile d'abord : beaucoup de dirigeants consulteront sur téléphone).
- Accessible : contrastes AA, vrais `<button>`/`<a>`/`<label>`, `alt` sur les images, navigation au clavier.
- SEO local : balises title/description par page, données structurées LocalBusiness (zone : Maine-et-Loire), sitemap, robots.txt, Open Graph.
- Formulaire : envoi en POST vers une URL de webhook configurable par variable d'environnement (`PUBLIC_FORM_ENDPOINT`), prévue pour un workflow n8n. Message de confirmation affiché sur la page, gestion d'erreur, protection anti-spam simple (champ caché « honeypot »). Pas de stockage côté site.
- Aucun cookie ni outil de suivi tant que ce n'est pas décidé (pas de bannière cookies nécessaire dans ce cas).
- Pas de faux contenu : pas de témoignages, logos clients, chiffres ou prix inventés. Garder les [champs à compléter] visibles.

## Règles de travail
- Avancer page par page, montrer le résultat en local (`npm run dev`) avant de passer à la suivante.
- Ne pas ajouter de pages, de sections ou de promesses qui ne sont pas dans les maquettes sans demander.
- Ne jamais mentionner ADINFO, ni d'offres de type logiciel de gestion, devis/facturation, CRM, dématérialisation ou reporting ERP.
