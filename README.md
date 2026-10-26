# 3ESSAS — Sécurité intelligente de quartier

> Écosystème marocain de gardiennage, stationnement et supervision assistée par IA
> **Synthèse conceptuelle — version 1.0 — 23 octobre 2026**

Ce dépôt contient la **note de cadrage** du projet 3ESSAS : un document de synthèse (PDF + source LaTeX) décrivant la vision, les acteurs et le fonctionnement d'une plateforme de sécurité de proximité coordonnant gardiens de parkings, gardiens d'immeubles, habitants et gestionnaires.

---

## 1. Vision

Créer un système coordonné de sécurité de proximité associant gardiens de parkings, gardiens d'immeubles, habitants et gestionnaires, soutenu par une plateforme de supervision et des outils d'intelligence artificielle.

Objectifs : améliorer l'organisation du quartier, la sécurité, la traçabilité des activités et la qualité du service rendu.

## 2. Problématique

Comment gérer la sécurité d'un quartier en coordonnant les agents, les parkings et les immeubles, tout en identifiant les utilisateurs, en suivant les opérations et en traitant efficacement les incidents ?

## 3. Les six composantes fonctionnelles

| # | Composante | Description |
|---|------------|-------------|
| 01 | **Agents identifiés** | Gilet avec identifiant visible, carte professionnelle pour pointer/dépointer, affectation et historique. |
| 02 | **Parking dynamique** | État des places (libre / occupée / indisponible), orientation du conducteur vers une place disponible. |
| 03 | **Carte des habitants** | Carte liée au profil et à l'immatriculation, solde rechargeable auprès d'un agent habilité, historique des transactions. |
| 04 | **Caméras et IA** | Détection d'anomalies (fumée/incendie, intrusion, dégradation…) dans les zones autorisées. **Toute alerte exige une vérification humaine.** |
| 05 | **Supervision centralisée** | Agents, sites, pointages, cartes, soldes, transactions, places et incidents, avec contrôle d'accès par rôle et journal d'audit. |
| 06 | **Pilotage et amélioration** | Tableaux de bord : occupation, incidents ouverts/clôturés, délais de prise en charge, couverture des missions. |

## 4. Acteurs

- **Agent de parking** — oriente les conducteurs, suit l'occupation, signale les incidents, réalise les recharges autorisées.
- **Agent d'immeuble** — missions de surveillance et suivi d'accès selon affectation.
- **Habitant / usager** — utilise sa carte et consulte ses opérations autorisées.
- **Syndic / gestionnaire** — organise sites et agents, suit le service et les signalements.
- **Responsable sécurité** — vérifie les alertes, coordonne le traitement des incidents.
- **Administrateur** — paramètre la plateforme et les droits d'accès.
- **Autorités compétentes** — interviennent dans le périmètre de leurs prérogatives légales.

## 5. Déploiement progressif

1. **Pilote** — un site délimité : agents, cartes, occupation des places, incidents, supervision.
2. **Extension** — habitations et immeubles supplémentaires, outils gestionnaires et rapports.
3. **Avancé** — analyse vidéo par IA et automatisations, après validation technique et juridique.

## 6. Contenu du dépôt

```
3ESSAS.MA/
├── 3ESSAS_PROJECT_SYNTHESE.pdf    # Note de cadrage finale (3 pages, A4)
├── 3ESSAS_LaTeX_Source.zip        # Source LaTeX + assets
│   ├── 3ESSAS_Synthese.tex
│   └── 3essas_assets/
│       ├── logo.png
│       └── mindmap.png
├── c19b4b9f-….png                 # Logo BESSAS (œil / bouclier / skyline)
└── README.md
```

## 7. Compiler le document

### Prérequis

Une distribution LaTeX complète (TeX Live ou MiKTeX) et les paquets suivants :

`babel-french`, `mathpazo`, `helvet`, `microtype`, `geometry`, `xcolor`, `graphicx`, `tabularx`, `booktabs`, `multicol`, `enumitem`, `tcolorbox`, `fancyhdr`, `titlesec`, `hyperref`.

### Étapes

```bash
# 1. Décompresser les sources
unzip 3ESSAS_LaTeX_Source.zip -d build

# 2. Compiler deux fois (table des références / liens)
cd build
pdflatex -interaction=nonstopmode 3ESSAS_Synthese.tex
pdflatex -interaction=nonstopmode 3ESSAS_Synthese.tex

# 3. Résultat
# → 3ESSAS_Synthese.pdf
```

> Sur Overleaf : importer le ZIP tel quel, le fichier principal est `3ESSAS_Synthese.tex`, compilateur **pdfLaTeX**.

### Charte typographique

| Élément | Valeur |
|---------|--------|
| Bleu primaire | `#1267BC` |
| Bleu foncé (titres) | `#18283B` |
| Gris texte | `#59677A` |
| Fond clair | `#F2F6FB` |
| Accent turquoise | `#159B9C` |

## 8. Cadre juridique et points de vigilance

> ⚠️ **La synthèse décrit une vision fonctionnelle, pas un dispositif déjà autorisé ou validé techniquement.**

Trois dimensions sont à instruire avant tout cahier des charges :

- **Gardiennage** — champ d'application, autorisations, qualification et limites des missions (**loi marocaine n° 27-06**).
- **Données personnelles** — identité, plaques, images, opérations et journalisation ; finalités, habilitations, conservation et formalités **CNDP** (**loi n° 09-08**).
- **Vidéosurveillance** — lieux et angles autorisés, information des personnes, conformité et vérification humaine des alertes. La **CNDP exclut l'utilisation de caméras pour surveiller spécifiquement un ou plusieurs employés** ; la captation continue de chaque agent doit donc être revue.

**Références**

- Loi 27-06 — [texte via SURTYMAR](https://www.surtymar.com/hubfs/R%C3%A8glementations/R%C3%A9glementation%20Marocaine/Loi%2027-06%20%28liens%29.pdf)
- CNDP — [obligations loi 09-08](https://www.cndp.ma/conditions/)
- CNDP — [fiche vidéosurveillance au travail](https://www.cndp.ma/wp-content/uploads/2023/01/fiche_CNDP_VS_RT_fr.pdf)

Les modalités précises doivent être confirmées par un conseil juridique compétent.

---

**Statut :** concept en phase d'étude — non validé opérationnellement.
