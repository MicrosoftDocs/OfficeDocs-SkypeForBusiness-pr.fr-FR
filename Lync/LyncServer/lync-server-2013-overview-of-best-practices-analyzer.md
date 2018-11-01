---
title: Présentation de Best Practices Analyzer
TOCTitle: Présentation de Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg591349(v=OCS.15)
ms:contentKeyID: 49298812
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation de Best Practices Analyzer

 

_**Dernière rubrique modifiée :** 2012-09-19_

Vous pouvez utiliser Best Practices Analyzer de Lync Server 2013 pour identifier et résoudre les problèmes avec votre déploiement Lync Server 2013. Best Practices Analyzer de Lync Server 2013 collecte les informations de configuration à partir des composants Lync Server 2013.

Avec le bon accès réseau, Best Practices Analyzer peut examiner les serveurs exécutant les services de domaine Active Directory, le service de messagerie unifiée Exchange Server et Lync Server 2013. Vous pouvez utiliser Best Practices Analyzer pour exécuter les tâches suivantes :

  - effectuer de manière proactive des vérifications pour contrôler que la configuration définie est conforme aux meilleures pratiques ;

  - détecter automatiquement les mises à jour nécessaires pour Lync Server 2013 ;

  - générer une liste des problèmes, par exemple les paramètres de configuration qui ne sont pas optimaux, les options non prises en charge, les mises à jour manquantes ou les pratiques que nous ne recommandons pas ;

  - contribuer à dépanner et à corriger des problèmes spécifiques.

Best Practices Analyzer offre les fonctionnalités suivantes :

  - des conditions préalables à l’installation ;

  - de la documentation en ligne sur les problèmes signalés, notamment des conseils pour le dépannage ;

  - des informations de configuration que vous pouvez enregistrer pour les consulter plus tard ;

  - une analyse de pointe du système.

Best Practices Analyzer utilise un ensemble de fichiers de configuration XML pour déterminer les informations à collecter sur votre environnement Lync Server 2013. En plus de la vérification des services de domaine Active Directory, il vérifie les sources comme le Registre du système d’exploitation Windows Server et les paramètres dans Windows Management Instrumentation (WMI).

Best Practices Analyzer compare les données qu’il rassemble et un ensemble de règles prédéfinies pour les paramètres et les configurations de déploiements Lync Server 2013.

Après la comparaison des données recueillies et des règles prédéfinies, l’outil indique les problèmes trouvés. Pour chaque problème repris, Best Practices Analyzer fournit des informations sur ce qui est trouvé dans l’environnement Lync Server 2013 analysé et la configuration recommandée. Il propose également des liens vers des informations plus détaillées sur les différents problèmes.

> [!NOTE]  
> Best Practices Analyzer de Lync Server 2013 collecte les informations de configuration uniquement à partir des composants Lync Server 2013. Vous pouvez utiliser les versions précédentes de l’outil pour analyser des environnements antérieurs. Pour plus d’informations, voir <a href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Configuration requise pour l’exécution de Best Practices Analyzer</a>.
