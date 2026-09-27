# BINGO Habillage TV — page de téléchargement

Page publique du logiciel gratuit **BINGO Habillage TV** (habillage à l'écran d'un
bingo télévisé, Mac Apple Silicon et PC Windows). Trois fichiers, aucune dépendance :

```
index.html   toute la page
style.css    l'habillage
images/      captures de l'édition publique (scripts/capture-site.cjs dans le projet de l'app)
```

En ligne : <https://bingotca.github.io/bingo-habillage-tv/> (GitHub Pages, branche `main`).

## Le fichier à télécharger vit dans les Releases

Les liens de la page pointent toujours vers la **dernière** version :

```
https://github.com/bingoTCA/bingo-habillage-tv/releases/latest/download/BINGO-Habillage-TV-mac.dmg
https://github.com/bingoTCA/bingo-habillage-tv/releases/latest/download/BINGO-Habillage-TV-windows.exe
```

Pour publier une mise à jour, dans le projet de l'app :

```bash
npm run dist:public        # Mac
npm run dist:public:win    # PC → dist-public/BINGO-Habillage-TV-windows.exe
cp "dist-public/BINGO Habillage TV-<version>-arm64.dmg" /tmp/BINGO-Habillage-TV-mac.dmg
gh release create v<version> /tmp/BINGO-Habillage-TV-mac.dmg dist-public/BINGO-Habillage-TV-windows.exe --repo bingoTCA/bingo-habillage-tv --title "BINGO Habillage TV <version>"
```

Garder **les mêmes noms de fichier** (`BINGO-Habillage-TV-mac.dmg`, `BINGO-Habillage-TV-windows.exe`) :
ce sont eux qui rendent les liens de la page permanents. Mettre à jour le numéro de version et le
poids affichés dans `index.html` (tuiles « Mac » et « PC »).

⚠️ Ne jamais déposer le `.dmg` ni le `.exe` dans le dépôt lui-même : il va dans les Releases.

## Version d'essai

La page porte `<meta name="robots" content="noindex">` : elle n'apparaît pas dans les
moteurs de recherche tant que la base de cartes n'est pas complète. Retirer la ligne le
jour du lancement officiel.
