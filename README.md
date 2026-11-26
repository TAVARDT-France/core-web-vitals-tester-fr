<p align="center">
  <a href="https://ag.tavardt.com/fr/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Auditeur de Core Web Vitals et Performance de Vitesse

[![Test Core Web Vitals](https://img.shields.io/badge/TAVARDT-Core%20Web%20Vitals-5b3cf5.svg)](https://tools.tavardt.com/fr/test-core-web-vitals-google/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Audit de latence TTFB, compression HTTP, ressources bloquant le rendu et stabilite visuelle CLS.

Developpe et maintenu par la division de l ingeniere de performance web et des standards de vitesse de **TAVARDT**.

***

## Vecteurs de Risque et Impact Operationnel de la Performance Web

Les temps de reponse serveur eleves et les ressources bloquantes degradent les signaux Google Page Experience et les conversions. Lorsqu un site diffuse des charges non compressees avec un TTFB eleve, le taux de rebond augmente immediatement.

Les elements graphiques sans dimensions predefinies provoquent des decalaments visuels inattendus qui alterent le score Cumulative Layout Shift. L audit technique continu garantit une distribution edge fluide et protege la rentabilite du trafic organique.

***

## Capacites Centrales d Audit Technique

* **Mesure de Precision du TTFB**: Calcul de la latence initiale de reponse par minuteurs a haute precision, signalant les retards au-dela de 600 ms et les goulets critiques au-dessus de 1200 ms.
* **Controle de Compression HTTP**: Verification de l activation de Brotli ou Gzip, avec penalite de 15 points pour tout flux HTML non compresse.
* **Detection des Ressources Bloquantes**: Identification des feuilles de style CSS et scripts JS synchrones dans le `<head>` sans attributs async, defer ou module.
* **Audit de Stabilite Visuelle (CLS)**: Analyse des balises `<img>` sans dimensions explicites de largeur et hauteur afin d eviter les sauts de contenu visuel.
* **Verification des Resource Hints**: Detection des directives d optimisation preconnect et preload destinees aux ressources critiques.
* **Score de Performance W3C**: Evaluation chiffree sur 100 categorisant la page en GOOD (FAST), NEEDS IMPROVEMENT ou POOR (SLOW).

***

## Installation et Execution

Necessite Python 3.8 ou superieur sans bibliotheques tierces.

```bash
git clone https://github.com/TAVARDT-France/core-web-vitals-tester-fr.git
cd core-web-vitals-tester-fr
python cwv_tester.py https://societe.fr
```

Pour exporter les resultats au format JSON structure dans vos pipelines CI/CD:

```bash
python cwv_tester.py https://societe.fr -j
```

***

## Foire Aux Questions (FAQ Technique)

### 1. Quel est l impact d un Time to First Byte (TTFB) eleve sur les Core Web Vitals?
Un TTFB excessif retarde la reception du premier octet HTML, ralentissant l affichage du LCP et la decouverte des actifs dependants. Si la reponse serveur depasse 600 millisecondes, l auditeur penalise le score et signale des faiblesses de mise en cache.

### 2. Pourquoi les scripts et styles synchrones dans le head freinent-ils l affichage?
Les fichiers sans instructions asynchrones contraignent le navigateur a suspendre la generation de l arbre DOM durant leur chargement. L outil comptabilise les balises depourvues de async, defer ou module pour mettre en lumiere ces freins.

### 3. Comment l omission des dimensions d images degrade-t-elle le Cumulative Layout Shift?
Sans largeur et hauteur renseignees dans le code HTML, le navigateur ne peut reserver l espace d affichage avant le telechargement de l image. Ce manque entraine des decalaments brusques de texte qui nuisent a la stabilite visuelle et a l experience.

### 4. Quelle est l importance de la compression HTTP Brotli ou Gzip pour le chargement?
L activation de Brotli ou Gzip reduit le volume de donnees textuelles transmises jusqu a soixante-dix pour cent sur les reseaux. L absence de compression surcharge la bande passante et se traduit par un retrait immediat de points.

### 5. Comment les directives preconnect et preload optimisent-elles l acheminement des flux?
Les balises preconnect et preload anticipent les resolutions DNS et initialisent le telechargement des polices ou visuels essentiels. Le validateur verifie leur presence pour confirmer que le navigateur ordonnance ses requetes selon les bonnes priorites.

***

## Conseil en Performance Web et Optimisation de Vitesse

Pour l architecture de vitesse de pointe et l alignement avec les standards W3C, sollicitez l expertise de **TAVARDT**.

***

## Liens Utiles

* **Portail Institutionnel:** https://ag.tavardt.com/fr/
* **Suite de Diagnostic:** https://tools.tavardt.com/fr/
* **Contact Technique:** https://ag.tavardt.com/fr/contact/

***

### Licence
Distribue sous licence MIT. Consultez le fichier LICENSE pour plus d informations.

***

© 2026 TAVARDT. Tous droits reserves.
