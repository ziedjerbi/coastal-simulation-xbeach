# Coastal Simulation – XBeach NH, Surfbeat & Celeris Boussinesq

> Stage de recherche – Laboratoire M2C, CNRS UMR 6143 / Université de Rouen Normandie / IH Cantabria  
> Avril – Août 2026 | Villers-sur-Mer & Étretat, Normandie, France

---

## Contexte

Ce dépôt présente les travaux de simulation numérique réalisés dans le cadre d'un système d'alerte précoce aux **submersions côtières** sur deux sites normands (Étretat et Villers-sur-Mer).

Le projet combine modélisation hydrodynamique, traitement de données multi-sources et validation croisée par imagerie satellite et caméra de plage.

---

## Modèles utilisés

| Modèle | Type | Application |
|---|---|---|
| **XBeach Non-Hydrostatic (NH)** | Ondes courtes résolues | Run-up, swash, submersion |
| **XBeach Surfbeat** | Ondes longues | Infragravité, setup |
| **Celeris Boussinesq WebGPU** | Équations de Boussinesq | Simulation rapide GPU |

- 96+ simulations réalisées sur 3 tempêtes avec 3 approches de forçage
- Écart relatif inter-modèle : **1,7% sur le run-up**

---

## Données traitées

- Bathymétrie et topographie (MNT côtier)
- Données hydrodynamiques (houle, marée, surcote)
- Imagerie caméra / timestack de plage
- Imagerie satellite Pléiades
- Données QGIS géoréférencées

---

## Scripts Python (post-traitement)

```python
# Exemple : analyse de séries temporelles du run-up
import numpy as np
import matplotlib.pyplot as plt

# Chargement sortie XBeach
runup = np.loadtxt('xbeach_output/zs.dat')
time  = np.linspace(0, 3600, len(runup))

# Calcul R2% (runup dépassé 2% du temps)
R2 = np.percentile(runup, 98)

plt.figure(figsize=(10, 4))
plt.plot(time, runup, lw=0.8, color='steelblue')
plt.axhline(R2, color='red', linestyle='--', label=f'R2% = {R2:.2f} m')
plt.xlabel('Temps (s)')
plt.ylabel('Run-up (m NGF)')
plt.title('Analyse du run-up – Tempête Klaus')
plt.legend()
plt.tight_layout()
plt.savefig('figures/runup_analysis.png', dpi=150)
```

---

## Stack technique

`Python` `NumPy` `Matplotlib` `Pandas` `XBeach` `Celeris` `QGIS` `ParaView`

---

## Collaboration

Projet réalisé en collaboration avec **IH Cantabria** (Espagne) dans le cadre d'un système d'alerte précoce aux submersions côtières.
