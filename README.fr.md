[English](README.md) | [Français](README.fr.md)

# github-readme-weather

Des badges météo gratuits pour un README GitHub, un profil, une signature de forum ou toute page qui affiche une image. Chaque badge est un petit SVG servi par [weatheo.com](https://weatheo.com) et indique la météo actuelle d'un lieu.

Badge en ligne, thème clair et sombre :

[![Météo Gien](https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg)](https://weatheo.com/fr/fr/centre-val-de-loire/gien)
[![Météo Gien, thème sombre](https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg?theme=dark)](https://weatheo.com/fr/fr/centre-val-de-loire/gien)

Badge carte (495x120), thème clair et sombre :

[![Météo Gien, carte](https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg?style=card)](https://weatheo.com/fr/fr/centre-val-de-loire/gien)
[![Météo Gien, carte sombre](https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg?style=card&theme=dark)](https://weatheo.com/fr/fr/centre-val-de-loire/gien)

## Trouver votre ville

1. Ouvrez [weatheo.com](https://weatheo.com) et cherchez votre ville.
2. Sur la page de la ville, copiez la partie de l'adresse après la langue. Pour `https://weatheo.com/fr/fr/centre-val-de-loire/gien`, c'est `fr/centre-val-de-loire/gien`.
3. Placez-la dans l'adresse du badge : `https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg`.

Vous pouvez aussi utiliser l'API de recherche : `https://weatheo.com/api/v1/search?q=gien`. Le champ `key` de chaque entrée de `results` est le chemin à utiliser.

## Extraits à copier

Remplacez le chemin par le vôtre, et gardez un lien vers la page de la ville dans la même langue que le badge.

### Markdown (README ou profil GitHub)

```markdown
[![Météo Gien](https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg)](https://weatheo.com/fr/fr/centre-val-de-loire/gien)
```

### HTML

```html
<a href="https://weatheo.com/fr/fr/centre-val-de-loire/gien"><img src="https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg" alt="Météo Gien" height="24"></a>
```

### BBCode (forums)

```bbcode
[url=https://weatheo.com/fr/fr/centre-val-de-loire/gien][img]https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg[/img][/url]
```

Certains forums refusent les images SVG dans les balises `[img]`. Si le badge ne s'affiche pas, c'est à l'administrateur du forum d'autoriser les SVG ; rien ne se règle du côté du badge. C'est le cas possible de forums comme Kikourou, Camptocamp ou Randonner-léger.

### reStructuredText

```rst
.. image:: https://weatheo.com/badge/fr/centre-val-de-loire/gien.svg
   :target: https://weatheo.com/fr/fr/centre-val-de-loire/gien
   :alt: Météo Gien
```

## Paramètres

| Paramètre | Valeurs | Défaut |
| --- | --- | --- |
| `style` | `line` (une ligne, par exemple `Gien (45500) \| 5°C · Ciel couvert · AQI 26`), `card` (carte 495x120 : icône, grande température, ville, conditions, maximale et minimale) | `line` |
| `theme` | `light`, `dark` | `light` |
| `lang` | `en`, `fr`, `de`, `zh`, `zh-hant`, `es`, `it`, `pt`, `ja`, `ko`, `ru`, `ar` | `fr` pour les lieux français, `en` ailleurs |
| `units` | `metric`, `imperial` | `metric` |

Une valeur inconnue revient à la valeur par défaut. L'AQI est un indice de type US-EPA, affiché sur le badge en ligne quand il est disponible. Pour les communes françaises qui n'ont qu'un code postal, il est affiché après le nom.

## FAQ

**À quelle fréquence le badge est-il mis à jour ?** Environ toutes les 15 minutes. Le proxy d'images de GitHub peut garder une ancienne copie un peu plus longtemps.

**Pourquoi GitHub affiche-t-il une ancienne valeur ?** GitHub passe par son propre cache d'images (camo). Il se renouvelle tout seul ; il suffit d'attendre.

**Que se passe-t-il pour un lieu inconnu ?** Le badge affiche « lieu introuvable » et le serveur répond HTTP 404. Vérifiez le chemin avec l'API de recherche.

**Quelles langues sont disponibles ?** Anglais, français, allemand, chinois simplifié et traditionnel, espagnol, italien, portugais, japonais, coréen, russe et arabe, avec le paramètre `lang`.

**Et les degrés Fahrenheit ?** Ajoutez `units=imperial`.

**Est-ce gratuit ?** Oui. Pas de JavaScript, pas de suivi, pas de cookie, pas de clé d'API.

**D'où viennent les données ?** Voir la [méthodologie](https://weatheo.com/fr/blog/methodology).

**Comment signaler une prévision fausse ou un bug ?** Ouvrez une issue dans ce dépôt avec l'adresse du badge et ce que vous attendiez.

## Projets liés

- [weatheo-ui](https://github.com/weatheo-com/weatheo-ui) : composants React.
- [mcp-server-weatheo](https://github.com/weatheo-com/mcp-server-weatheo) : serveur MCP.
- [climate-data](https://github.com/weatheo-com/climate-data) : fichiers CSV ouverts.
- API JSON : `https://weatheo.com/api/v1/weather?place=fr/centre-val-de-loire/gien`

## Licence

MIT, voir [LICENSE](LICENSE).
