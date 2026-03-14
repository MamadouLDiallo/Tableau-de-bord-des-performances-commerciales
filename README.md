# 📊 Tableau de bord des performances commerciales – Power BI

## 📖 Présentation du projet

Ce projet consiste à concevoir un **tableau de bord interactif d’analyse des ventes** à l’aide de **Power BI**.
L’objectif est de transformer un ensemble de données brutes en **indicateurs décisionnels pertinents** afin d’analyser la performance commerciale, identifier les produits les plus performants et suivre l’évolution du chiffre d’affaires dans le temps.

Ce projet illustre les différentes étapes d’un **processus complet d’analyse de données**, allant du **nettoyage des données** à la **visualisation des résultats**.

---

## 🎯 Objectifs du projet

* Analyser les **performances commerciales**
* Identifier les **produits les plus rentables**
* Étudier l’**évolution du chiffre d’affaires dans le temps**
* Faciliter la **prise de décision basée sur les données**

---

## 🧹 Nettoyage et préparation des données

Avant la création du tableau de bord, plusieurs étapes de **préparation des données** ont été réalisées afin d’assurer la qualité et la fiabilité des analyses :

* Vérification de la présence de **lignes vides**
* Identification et suppression des **valeurs manquantes**
* Suppression des **doublons**
* Suppression des **valeurs incohérentes** (quantités négatives ou prix anormaux)
* Nettoyage des variables texte (suppression des espaces dans les noms de produits)
* Vérification de la **cohérence métier** entre les variables

Lors de cette étape, une incohérence a été détectée dans la variable **LineTotal**.
Pour corriger ce problème, le chiffre d’affaires a été recalculé à partir de la formule suivante :

Chiffre_Affaires = OrderQty × UnitPrice

Cette nouvelle variable a été utilisée pour toutes les analyses.

---

## 📐 Mesures DAX utilisées

Plusieurs mesures DAX ont été créées afin de calculer les indicateurs clés :

**Total des ventes**

```id="t9n3c2"
Total_Ventes = SUM(Sales[Chiffre_Affaires])
```

**Nombre de transactions**

```id="p1dk8u"
Nb_Transactions = COUNT(Sales[SalesOrderID])
```

**Moyenne des ventes**

```id="7w5m92"
Moyenne_Ventes = AVERAGE(Sales[Chiffre_Affaires])
```

**Contribution des ventes (%)**

```id="a6d0qk"
Contribution_Ventes_% =
DIVIDE(
SUM(WorksSales[Chiffre_Affaires]),
CALCULATE(SUM(WorksSales[Chiffre_Affaires]), ALL(WorksSales)),
0)
```

Cette mesure permet d’identifier la **contribution de chaque produit au chiffre d’affaires total**.

---

## 📊 Fonctionnalités du tableau de bord

Le tableau de bord permet d’analyser plusieurs indicateurs clés :

* 📈 **Évolution du chiffre d’affaires par année**
* 🏆 **Top 5 des produits par chiffre d’affaires**
* 📦 **Top 5 des produits les plus vendus**
* 🥧 **Contribution des produits au chiffre d’affaires**
* 📊 **Indicateurs de performance (KPI)** :

  * Total des ventes
  * Nombre de transactions
  * Moyenne des ventes

Des **filtres interactifs** permettent d’explorer les résultats par **produit** et par **année**.

---

## 🔎 Principaux résultats

L’analyse met en évidence plusieurs éléments importants :

* Une **petite proportion de produits génère une grande partie du chiffre d’affaires**.
* Certains produits sont **très demandés en volume**, mais ne génèrent pas nécessairement le chiffre d’affaires le plus élevé.
* Le chiffre d’affaires présente des **variations selon les années**, avec un **pic observé autour de 2014**.

---

## 💡 Recommandations

À partir de ces résultats, plusieurs actions peuvent être envisagées :

* Renforcer la **promotion des produits les plus rentables**
* Analyser les causes des **variations des ventes selon les années**
* Optimiser la stratégie commerciale en se concentrant sur les **produits à forte contribution**
* Améliorer les **processus de collecte et de contrôle des données**

---

## 🛠️ Outils utilisés

* **Power BI**
* **Power Query**
* **DAX**
* **Data Cleaning**
* **Data Visualization**

---

## 📷 Aperçu du tableau de bord
<img src="C:\Users\user\Desktop\PROJET Power BI/image.png" width="600">
---

## 👨‍💻 Auteur

**Mamadou Lamarana Diallo**
 Diplomé d'un **Master en Statistique et Informatique Décisionnelle**

Domaines d’intérêt :

* Data Analysis
* Business Intelligence
* Machine Learning
* Data Visualization


