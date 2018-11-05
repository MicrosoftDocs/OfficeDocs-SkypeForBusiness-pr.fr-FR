---
title: Meilleures pratiques de sauvegarde et restauration
TOCTitle: Meilleures pratiques de sauvegarde et restauration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202184(v=OCS.15)
ms:contentKeyID: 53095493
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Meilleures pratiques de sauvegarde et restauration

 

_**Dernière rubrique modifiée :** 2013-02-21_

Cette section comprend deux types de meilleures pratiques :

  - Meilleures pratiques de sauvegarde et restauration

  - Meilleures pratiques pour limiter l’impact d’un sinistre

## Meilleures pratiques de sauvegarde et restauration

Pour simplifier votre processus de sauvegarde et de restauration, respectez les meilleures pratiques suivantes lors de la sauvegarde ou de la restauration de vos données :

  - Effectuez des sauvegardes régulières à intervalles adéquats. Le type de sauvegarde et le planning de rotation les plus simples et les plus couramment utilisés consistent à effectuer chaque nuit une sauvegarde complète de la base de données SQL Server entière. Ainsi, si une restauration est nécessaire, le processus de restauration ne requiert qu’une sauvegarde et vous perdrez au plus une journée de données.

  - Si vous utilisez des applets de commande ou le Panneau de configuration Lync Server pour apporter des modifications de configuration, utilisez l’applet de commande **Export-CsConfiguration** pour effectuer une sauvegarde instantanée du fichier de configuration de topologie (Xds.mdf) après avoir apporté les modifications, ce qui vous évitera de perdre ces modifications si vous devez restaurer vos bases de données. Notez que cette configuration est sauvegardée au format XML et compressée dans un fichier ZIP.

  - Assurez-vous que le dossier partagé que vous envisagez d’utiliser pour la sauvegarde de Lync Server dispose d’une quantité d’espace libre suffisante pour contenir toutes les données sauvegardées.

  - Planifiez les sauvegardes lorsque l’utilisation de Lync Server est faible, afin d’améliorer les performances du serveur et l’expérience utilisateur.

  - Assurez-vous que l’emplacement de sauvegarde des données est sécurisé (nous recommandons le choix d’un emplacement distant).

  - Conservez les fichiers de sauvegarde dans un lieu accessible, au cas où vous auriez besoin de restaurer les données.

  - Planifiez et programmez des tests périodiques des processus de restauration pris en charge par votre organisation.

  - Validez vos processus de sauvegarde et de restauration à l’avance afin de vous assurer qu’ils fonctionnent comme prévu.

## Meilleures pratiques pour limiter l’impact d’un sinistre

La meilleure stratégie à adopter pour la gestion des interruptions de service désastreuses (dues à des événements ingérables tels que des pannes de courant ou de soudaines défaillances matérielles) consiste à supposer qu’elles auront lieu et à planifier en conséquence.

Si les services Lync, avec un minimum de perturbation et de panne, ont une importance critique pour votre organisation, vous devez mettre en œuvre des pools associés de serveurs frontaux, comme décrit dans [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Ainsi, en cas de sinistre affectant l’un de ces pools, un administrateur peut basculer les utilisateurs vers l’autre pool avec un minimum de temps mort.

Les plans de gestion de sinistre que vous développez dans le cadre de votre stratégie de sauvegarde et de restauration doivent prendre en compte les facteurs suivants :

  - facilité d’accès aux supports logiciels et aux mises à jour de logiciels et de microprogrammes ;

  - maintenance d’enregistrements relatifs aux matériels et aux logiciels ;

  - sauvegarde régulière des données et surveillance de l’intégrité des sauvegardes ;

  - formation du personnel en matière de récupération après incident, documentation des procédures et implémentation d’exercices de simulation de récupération après sinistre ;

  - mise à disposition de matériel de secours ou, si vous avez un contrat de niveau de service (SLA), mise en place de contrats avec des fournisseurs de matériel afin d’obtenir rapidement des pièces de remplacement ;

  - séparation des emplacements de vos fichiers journaux de transactions (fichiers .ldf) et des fichiers de base de données (fichiers .mdf).

