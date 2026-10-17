# Sites de cours

Le code de toutes les pages intégrées dans les Google Sites, à un seul endroit.

## Organisation

```
commun/                    styles partagés (modifier ici = modifier partout)
  base.css                 réinitialisation commune
  themes/circuit-imprime.css   thème des sites Arduino & ESP32
  sommaire.css             pages d'accueil et sommaires
fr/<niveau>/<site>/        une page HTML par widget Google Sites
  index.html               sommaire du site
  brouillon/               jamais publié
index.html                 accueil de tous les cours
inventaire.csv             quelle page va dans quel Google Site
```

## Mettre en ligne (une seule fois)

1. Créer un dépôt **privé** sur GitHub et y déposer tout ce dossier.
2. Sur github.com, *Add file → Create new file*, nommer le fichier `.github/workflows/publier.yml`
   et y coller le contenu de `outils/publier.yml` (c'est lui qui publie le site en excluant les brouillons).
3. *Settings → Pages → Source* : choisir **GitHub Actions**.
4. Après une à deux minutes, le site est en ligne à `https://<compte>.github.io/<dépôt>/`.

## Intégrer une page dans Google Sites

*Intégrer → Code intégré*, puis :

```html
<iframe src="https://<compte>.github.io/<dépôt>/fr/pei5/arduino-esp32/Atelier-Arduino-ESP32.html"
        style="width:100%;height:100%;border:0"></iframe>
```

Ajuster ensuite la hauteur du bloc dans l'éditeur.

## Au quotidien

- Modifier une page : ouvrir le fichier sur github.com, crayon ✏️, *Commit changes*. En ligne en 1 à 2 minutes.
- Cacher une page : la déplacer dans `brouillon/`. La publier : la remettre dans le dossier du site.
- Nouvelle page : copier une page existante, garder les deux lignes `commun/...` dans l'en-tête.
