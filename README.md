# EDEN — Loot prio P3

Filtre de priorité de butin pour **Hyjal Summit** et **Black Temple** (TBC Classic, phase 3),
guilde EDEN.

👉 **[Ouvrir le site](https://eden-guilde.github.io/eden-loot-prio-p3/)**

Chaque raideur choisit sa classe et voit :

- **ce qu'il peut équiper** (type d'armure, armes utilisables, jetons T6 de sa classe) ;
- **où il est prioritaire**, sous forme de médaille (or, argent, bronze, puis pastille numérotée),
  avec la mention `ex æquo` quand le sheet met deux classes à égalité avec un `=` ;
- **combien de pièces T6 la classe vise** sur un jeton (`2p T6`, `4p T6`), repris du texte de priorité ;
- le niveau de prio de la guilde : Obligatoire, Importante, Stratégique, ou ouvert `MS > OS`.

Filtres complémentaires : spécialisation, **boss**, emplacement, raid, niveau de priorité
(pastilles multi-sélection) et recherche libre. Chaque raideur peut cocher **« obtenu »** sur ce
qu'il a déjà loot — mémorisé dans son navigateur, avec une option pour masquer ces lignes.
Les objets marqués BiS dans le sheet et ceux dont la priorité est conditionnelle portent un badge.

**Les filtres sont dans l'URL** : la barre d'adresse suit les clics, donc un lien par classe se
colle sur le Discord et chacun peut mettre sa vue en favori.

| Classe | Lien |
|---|---|
| Guerrier | `…/?c=Guerrier` |
| Paladin | `…/?c=Paladin` |
| Chasseur | `…/?c=Chasseur` |
| Voleur | `…/?c=Voleur` |
| Prêtre | `…/?c=Pr%C3%AAtre` |
| Chaman | `…/?c=Chaman` |
| Mage | `…/?c=Mage` |
| Démoniste | `…/?c=D%C3%A9moniste` |
| Druide | `…/?c=Druide` |

On peut préciser : `?c=Chaman&s=Chaman%20Restauration&p=Obligatoire,Importante`.
Au survol d'un objet, son tooltip Wowhead complet s'affiche ; un clic ouvre la page Wowhead.
Le sélecteur **FR / EN** en haut à droite bascule les noms d'objets et les tooltips ; la recherche,
elle, accepte les deux langues quelle que soit la position du sélecteur. Le tooltip demande une
connexion : hors ligne, les liens restent de simples liens.

## Onglet « Mon stuff »

Chaque raideur compose son set à partir du butin de Hyjal et du Black Temple : 17 emplacements,
seuls les objets équipables par sa classe sont proposés, et le choix est mémorisé dans son
navigateur. Le bouton **Ouvrir WoWSims** pointe vers le simulateur de sa spé, et le JSON généré
s'importe directement : dans WoWSims,  →  → coller → .

L'export a été vérifié sur wowsims.com : le simulateur place chaque objet d'après son type, pas
d'après sa position, donc seuls les emplacements remplis sont exportés. Les **jetons T6** ne sont
pas des objets équipables : ils sont signalés et exclus de l'export, la pièce T6 correspondante
se choisit dans le simulateur.

Le planificateur ne connaît que le butin de ces deux raids — ce n'est pas un Sixty Upgrades
complet : ni pré-BiS, ni objets de T4/T5, ni enchantements, ni gemmes.

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
