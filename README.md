# EDEN — Loot prio P3

Filtre de priorité de butin pour **Hyjal Summit** et **Black Temple** (TBC Classic, phase 3),
guilde EDEN.

👉 **[Ouvrir le site](https://eden-guilde.github.io/eden-loot-prio-p3/)**

Chaque raideur choisit sa classe et voit :

- **ce qu'il peut équiper** (type d'armure, armes utilisables, jetons T6 de sa classe) ;
- **où il est prioritaire**, avec son rang dans la chaîne de priorité (`Prio 2 / 4`) ;
- le niveau de prio de la guilde : Obligatoire, Importante, Stratégique, ou ouvert `MS > OS`.

Filtres complémentaires : spécialisation, emplacement, raid, niveau de priorité, recherche libre.
Au survol d'un objet, son tooltip Wowhead complet s'affiche (stats, en français) ; un clic ouvre
la page Wowhead. Le tooltip demande une connexion : hors ligne, les liens restent de simples liens.

## Mettre à jour

Le site est un fichier unique et autonome : `index.html` (données incluses, aucune dépendance).
Il est généré depuis le Google Sheet de la guilde par le script `regenerer_bdd.py` du dossier
parent. Pour publier une nouvelle version :

```bash
git add index.html && git commit -m "Maj des prios" && git push
```

GitHub Pages redéploie tout seul en une minute environ.

## Règles de priorité encodées

Les priorités viennent telles quelles du sheet de la guilde. Le site se contente de décoder le
jargon pour rendre le tout filtrable (`RSHAM` → Chaman Restauration, `Boomy` → Druide Équilibre,
`Enhance` → Chaman Amélioration, `Ret` → Paladin Vindicte…).

Deux précisions ajoutées par la guilde :

- les **jetons T6** listent les trois classes qui peuvent les utiliser, même quand la priorité
  n'en nomme que deux ;
- le **jeton Vanquisher** est prioritaire pour le Druide Farouche **DPS et Tank**, à égalité.

En cas de litige, la colonne « Priorité » du Google Sheet fait foi.
