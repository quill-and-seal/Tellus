# Tellus

> *Un monde qui vit entre les sessions.*

**Tellus** est un module pour [Foundry VTT](https://foundryvtt.com/) qui simule le développement et l'évolution d'un écosystème complet : la faune, la flore, et les peuples qui en vivent. Forêts, troupeaux, villages et factions s'influencent les uns les autres au fil du temps, et les actes des joueurs y laissent leur marque.

Tellus fait partie de la collection **quill and seal**.

> ⚠️ **Statut : en conception.** Le module n'est pas encore utilisable. Ce dépôt suit son développement.

---

## Principes

- **Nature et civilisations liées.** Un village qui défriche fait reculer la forêt ; une forêt qui recule fait fuir le gibier ; un gibier qui manque affame le village.
- **Des chiffres précis, un niveau lisible.** Le moteur calcule des populations et des stocks exacts, et chaque valeur est aussi traduite en niveau général (*abondant*, *stable*, *en déclin*, *rare*). Le MJ peut ajuster l'un ou l'autre.
- **Les joueurs comptent, sans tout casser.** Leurs actions ont des conséquences réelles, mais l'écosystème est résilient : les chocs s'étalent dans le temps, tendent à se résorber, et les crises s'annoncent avant d'arriver.
- **Agnostique.** Tellus ne dépend d'aucun système de jeu.

## Fonctionnalités prévues

### Régions-biomes
Les Régions de scène deviennent des biomes : forêt, plaine, marais, montagne… Chacune possède ses ressources (gibier, bois, eau, minerai, cultures) et une capacité de charge.

### Populations
Espèces animales et végétales avec croissance, prédation et variations saisonnières. Les relations proies/prédateurs forment un réseau alimentaire propre à chaque monde.

### Établissements
Villages, villes et factions avec une population, une prospérité et des besoins. Ils exploitent les Régions voisines et réagissent à leur état : expansion, migration, déclin.

### Événements
Sécheresse, surchasse, famine, épidémie, migration… déclenchés par des seuils et toujours précédés de signaux d'alerte.

### Le temps
- **Automatique** : synchronisé avec le temps du monde Foundry.
- **Manuel** : le MJ avance d'un jour, d'une semaine ou d'une saison, avec un aperçu des changements avant validation.

### Chronique
Chaque avancée du temps produit une chronique lisible dans un journal : ce qui a prospéré, ce qui a décliné, ce qui menace.

## Fondements du modèle

Les algorithmes de Tellus s'inspirent de modèles scientifiques reconnus, simplifiés pour le jeu :

| Couche | Modèle de référence |
|---|---|
| Faune et flore | Croissance logistique, modèle proie-prédateur de **Rosenzweig-MacArthur** (réponse fonctionnelle de Holling type II) |
| Peuples ↔ ressources | Modèle de **Brander & Taylor** (1998), et sa variante à seuil d'irréversibilité (D'Alessandro, 2007) |
| Sociétés et effondrement | Modèle **HANDY** (Motesharrei, Rivas & Kalnay, 2014), capacité de charge comme signal précoce |
| Décisions des établissements | Modélisation multi-agents type **Artificial Anasazi** (vallée de Long House) |

La simulation est agrégée par Région et calculée uniquement sur le client du MJ actif, pour rester légère.

## Intégrations optionnelles

Tellus fonctionne seul, mais dialogue avec les autres modules quill and seal lorsqu'ils sont présents :

- **Mint** : l'abondance ou la rareté locale influence les prix des boutiques.
- **Errant** : troupeaux et migrations prennent la forme de chemins automatisés.
- **Ember** et **Vesper** : effets visuels et ambiances sonores selon la saison et la faune présente.
- **Scry** : la chronique se synchronise avec un vault Obsidian.

## Feuille de route

- [ ] **MVP** : Régions-biomes, quelques espèces, un type d'établissement, ticks manuels, chronique
- [ ] Synchronisation avec le temps du monde
- [ ] Événements à seuils et alertes
- [ ] Tableau de bord MJ par Région
- [ ] Intégrations quill and seal
- [ ] Export de l'état du monde (JSON) pour une visualisation externe

## Installation

Une fois la première version publiée, dans Foundry VTT : **Modules complémentaires → Installer un module**, puis coller l'URL du manifeste :

```
https://github.com/quill-and-seal/Tellus/releases/latest/download/module.json
```

## Compatibilité

- Foundry VTT **v14**
- Tous systèmes de jeu
