# BINGO Habillage TV — page de téléchargement

Page publique du logiciel gratuit **BINGO Habillage TV** (habillage à l'écran d'un
bingo télévisé, Mac Apple Silicon). Trois fichiers, aucune dépendance :

```
index.html   toute la page
style.css    l'habillage
images/      captures de l'édition publique (scripts/capture-site.cjs dans le projet de l'app)
```

En ligne : <https://bingotca.github.io/bingo-habillage-tv/> (GitHub Pages, branche `main`).

## Le fichier à télécharger vit dans les Releases

Le lien de la page pointe toujours vers la **dernière** version :

```
https://github.com/bingoTCA/bingo-habillage-tv/releases/latest/download/BINGO-Habillage-TV-mac.dmg
```

Pour publier une mise à jour, dans le projet de l'app :

```bash
npm run dist:public
cp "dist-public/BINGO Habillage TV-<version>-arm64.dmg" /tmp/BINGO-Habillage-TV-mac.dmg
gh release create v<version> /tmp/BINGO-Habillage-TV-mac.dmg --repo bingoTCA/bingo-habillage-tv --title "BINGO Habillage TV <version>"
```

Garder **le même nom de fichier** (`BINGO-Habillage-TV-mac.dmg`) : c'est lui qui rend le
lien de la page permanent. Mettre à jour le numéro de version et le poids affichés dans
`index.html` (tuile « Mac »).

⚠️ Ne jamais déposer le `.dmg` dans le dépôt lui-même : il va dans les Releases.

## Version d'essai

La page porte `<meta name="robots" content="noindex">` : elle n'apparaît pas dans les
moteurs de recherche tant que la base de cartes n'est pas complète. Retirer la ligne le
jour du lancement officiel.
