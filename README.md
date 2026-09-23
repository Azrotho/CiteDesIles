# Cité des Îles

![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Discord JDA](https://img.shields.io/badge/Discord-JDA-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%234479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-%23C71A36.svg?style=for-the-badge&logo=Apache%20Maven&logoColor=white)

Repo principal du projet Cité des Îles. Il regroupe juste les différents plugins, chacun est dans son propre dépôt.

Ce repo utilise des submodules, il n'y a pas de code ici directement.

Merci beaucoup à [@Raraph84](https://github.com/Raraph84) pour l'aide :3

## Les projets

- `cite/` : [cdi-plugin-cite](https://github.com/Azrotho/cdi-plugin-cite)
  Le plugin du serveur Cité (Paper 1.21.5). Éco, shop, NPCs, hologrammes de classement, tout ce qui tourne sur la Cité.

- `land/` : [CDI-Plugin-Land](https://github.com/Azrotho/CDI-Plugin-Land)
  Le plugin du serveur Land (Paper 1.21.4). Gestion des objectifs, de la corruption et des events. Attention, ce dépôt est sur `master`.

- `proxy/` : [cdi-plugin-proxy](https://github.com/Azrotho/cdi-plugin-proxy)
  Le plugin du proxy BungeeCord. Il gère les horaires de connexion : kick auto entre 1h et 7h, avec une bypass-list via `/padmin`.

- `inscriptionbot/` : [cdi-inscription-pluginbot](https://github.com/Azrotho/cdi-inscription-pluginbot)
  Le plugin du serveur inscription, avec le bot Discord intégré (JDA). Gère les `/link`, les invitations et les équipes.

Tous en Maven, avec MySQL via HikariCP derrière (sauf le proxy).

## Récupérer le projet

```bash
git clone --recurse-submodules https://github.com/azrotho/citedesiles.git
```

Si vous avez déjà cloné sans les submodules :

```bash
git submodule update --init --recursive
```

Pour mettre à jour :

```bash
git submodule update --remote --merge
```

## Build

Aller dans chaque dossier et builder séparément :

```bash
cd cite && mvn package
```

Il faut JDK 21 (17 pour le proxy), Maven, et un MySQL. Pour `cite` et `land` il faut aussi FancyNpcs et FancyHolograms sur le serveur.

## Comment ça marche

On bosse dans chaque repo séparément, puis ici on met juste à jour le pointeur :

```bash
cd cite
# modifs, commit, push

cd ..
git add cite
git commit -m "maj cite"
```

## La vidéo

Le projet vient de cette vidéo : [J'ai organisé une Cité Minecraft et ça s'est pas passé comme prévu](https://www.youtube.com/watch?v=9cgjIH6-Vqo).