# Simulation côtière – XBeach NH et Celeris Boussinesq

> Stage de recherche de Master 1 – Laboratoire M2C (CNRS UMR 6143 / Université de Rouen Normandie), en collaboration avec IH Cantabria (Espagne)  
> Avril – Août 2026 · Étretat et Villers-sur-Mer, Normandie

---

## Contexte

Pendant ce stage, j'ai travaillé sur la modélisation des vagues de tempête et du run-up sur deux plages normandes, Étretat et Villers-sur-Mer. Le travail s'inscrit dans un projet de système d'alerte précoce aux submersions côtières.

---

## Ce que j'ai fait

- Simulations avec deux solveurs de nature différente : XBeach en mode non hydrostatique, et Celeris (équations de Boussinesq, calcul sur GPU).
- Étude de sensibilité aux paramètres des modèles et comparaison entre les deux solveurs.
- Chaîne de post-traitement en Python pour automatiser les calculs, l'analyse des séries temporelles et la génération des figures.
- Confrontation des résultats à des mesures indépendantes.

---

## Modèles utilisés

| Modèle | Type | Application |
|---|---|---|
| **XBeach Non-Hydrostatic (NH)** | Vagues courtes résolues | Run-up, swash, submersion |
| **XBeach Surfbeat** | Ondes longues (infragravitaires) | Set-up |
| **Celeris** | Équations de Boussinesq, GPU | Simulation rapide |

---

## Données utilisées

- Bathymétrie et topographie côtière
- Conditions de houle, de marée et de surcote
- Images de caméra de plage (timestacks)
- Imagerie satellite Pléiades

---

## Pourquoi ce dépôt ne contient ni code ni données

Les données de terrain, les configurations de calcul et les résultats appartiennent au laboratoire M2C et à IH Cantabria. Ils ne sont pas publiés ici : ce dépôt décrit uniquement le travail réalisé pendant le stage.

---

## Outils

`Python` `NumPy` `Matplotlib` `Pandas` `XBeach` `Celeris` `QGIS` `ParaView`
