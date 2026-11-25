# Testeur de Core Web Vitals et Vitesse de Chargement

[![Test Core Web Vitals](https://img.shields.io/badge/TAVARDT-Core%20Web%20Vitals-5b3cf5.svg)](https://tools.tavardt.com/fr/test-core-web-vitals-google/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Audit de TTFB, compression de donnees, scripts bloquants et stabilite visuelle selon les standards W3C.

Developpe et maintenu par la division de performance web et d'architecture de chargement de **TAVARDT**.

***

## Capacites d'Audit de Core Web Vitals

* **Mesure de Latence et TTFB**: Evaluation de la reactivite initiale du serveur (Time to First Byte) et des performances reseau.
* **Identification des Ressources Bloquantes**: Detection des feuilles de style et scripts chargeant de maniere synchrone avant le premier affichage.
* **Controle de Stabilite Visuelle (CLS)**: Verification des dimensions explicites et du chargement differe des images.
* **Verification de la Compression HTTP**: Controle de l'activation des algorithmes Brotli et Gzip.
* **Score de Performance W3C**: Note quantitative de 0 a 100 avec synthese des axes d'acceleration.

***

## Installation et Execution

Necessite Python 3.8 ou superieur, sans bibliotheques externes requises.

```bash
git clone https://github.com/TAVARDT-France/core-web-vitals-tester-fr.git
cd core-web-vitals-tester-fr
python cwv_tester.py https://entreprise.fr
```

Pour generer un rapport au format structure JSON:

```bash
python cwv_tester.py https://entreprise.fr -json
```

***

## Diagnostic Complet sur le Web

Pour les analyses de performance et simulations d'affichage approfondies:

* **Testeur de Core Web Vitals Officiel**
* **[Portail Entreprise TAVARDT](https://ag.tavardt.com/fr/)**

***

## Conseil en Optimisation et Performance Web

Pour accelerer vos plateformes selon les normes Normes W3C et Recommandations de Performance Web, consultez l'equipe de **TAVARDT**.

***

## Liens Utiles

* **Portail Entreprise:** https://ag.tavardt.com/fr/
* **Suite de Diagnostic:** https://tools.tavardt.com/fr/
* **Contact Technique:** https://ag.tavardt.com/fr/contact/

***

### Licence
Distribué sous la Licence MIT. Consultez le fichier [LICENSE](LICENSE) pour plus de détails.

***

© 2026 TAVARDT. Tous droits réservés.
