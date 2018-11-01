---
title: Problèmes avec le test de l’environnement
TOCTitle: Problèmes avec le test de l’environnement
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205421(v=OCS.15)
ms:contentKeyID: 49299455
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Problèmes avec le test de l’environnement

 

_**Dernière rubrique modifiée :** 2012-09-21_

Best Practices Analyzer vous permet de vérifier que la configuration de votre environnement Lync Server 2013 est prise en charge. Dans le cadre des vérifications des services de domaine Active Directory, Best Practices Analyzer permet :

  - de vérifier la préparation de la forêt et du schéma des services de domaine Active Directory ;

  - d’identifier le nombre de domaines et de sites de services de domaine Active Directory du déploiement ;

  - de vérifier les niveaux du domaine et de la forêt ;

  - de vérifier la version du contrôleur de domaine ;

  - d’identifier le contexte d’appellation du domaine, de la configuration et du schéma ;

  - d’identifier le nombre d’utilisateurs autorisés ;

  - de vérifier où les paramètres des services de domaine Active Directory sont stockés ;

  - de vérifier les points de connexion du service pour Lync Server ;

  - d’identifier la version de la base de données.

## Résolution des problèmes avec l’environnement

Si l’environnement de test détecte des problèmes avec votre environnement, ces problèmes sont probablement causés par d’autres problèmes avec votre configuration d’Active Directory ou le niveau du logiciel exécuté sur des serveurs spécifiques. Par exemple, si Best Practices Analyzer identifie un contrôleur de domaine de votre environnement exécutant Windows Server 2000, il émettra un avertissement et vous devrez mettre à niveau ces contrôleurs de domaine vers une version prise en charge de Windows Server.

