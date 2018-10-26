---
title: Établissement d’une stratégie de sauvegarde et de restauration
TOCTitle: Établissement d’une stratégie de sauvegarde et de restauration
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202195(v=OCS.15)
ms:contentKeyID: 53095571
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Établissement d’une stratégie de sauvegarde et de restauration

 

_**Dernière rubrique modifiée :** 2013-03-26_

Avant de pouvoir développer un plan de sauvegarde et de restauration pour Lync Server, vous devez développer une stratégie en adéquation avec les objectifs de votre organisation. Pour développer une stratégie de sauvegarde et de restauration efficace, vous devrez :

  - Établir les priorités d’entreprise.

  - Identifier les besoins de sauvegarde et de restauration.

## Définition des priorités de l’entreprise

Évaluez les priorités de votre organisation. Habituellement, les principales priorités de l’entreprise qui ont des répercussions sur votre stratégie de sauvegarde et de restauration sont les suivantes :

  - Besoins de continuité de l’activité

  - Exhaustivité des données

  - Sensibilité des données

  - Besoins de portabilité

  - Contraintes budgétaires

Ces besoins de l’entreprise permettent de déterminer les contrats de niveau de service (SLA) que vous développez avec vos clients. Les contrats de niveau de service influencent considérablement votre stratégie de sauvegarde et de restauration.

## Identification des besoins de sauvegarde et de restauration

Les priorités et les contrats de niveau de service de votre entreprise déterminent les besoins de votre organisation en matière de sauvegarde et de restauration de Lync Server. Identifiez et documentez vos besoins dans les domaines suivants :

  - **Fréquence des sauvegardes**   Gardez à l’esprit que, à l’exception des pools principaux dans les relations par paire décrites dans [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md), Lync Server prend en charge le mode de récupération simple uniquement, ce qui signifie que vous restaurez la dernière sauvegarde complète. Planifiez avec soin la fréquence nécessaire de ces sauvegardes complètes. Pour plus d’informations sur les pratiques recommandées pour la fréquence de sauvegarde, voir [Meilleures pratiques de sauvegarde et restauration](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Outils de sauvegarde et de restauration**   Mentionnez qui utilisera les outils et sur quels ordinateurs. Pour plus d’informations sur les outils décrits dans la présente rubrique et les autorisations nécessaires, voir [Spécifications de sauvegarde et de restauration : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Emplacement de sauvegarde**   Déterminez si les sauvegardes sont conservées localement ou à distance, en tenant compte de leur sécurité et de leur accessibilité. Spécifiez les supports à utiliser pour les sauvegardes.

  - **Configuration matérielle et logicielle requise**   Identifiez et documentez votre configuration matérielle et logicielle spécifique, y compris le matériel de stockage des sauvegardes et de restauration de composants spécifiques, ainsi que tous les logiciels et la connectivité réseau nécessaires afin de prendre en charge la sauvegarde et la restauration. Au fur et à mesure que vous développez votre configuration matérielle et logicielle requise, gardez à l’esprit les divers scénarios de restauration ci-après.

  - **Scénarios de restauration**   Voici les de restauration pour les scénarios suivants :
    
      - Panne d’un pool Lync Server. Ce scénario requiert une nouvelle création de chaque serveur inclus dans le pool.
    
      - Panne d’un serveur Standard Edition. Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé ainsi que la restauration des bases de données.
    
      - Perte du magasin central de gestion. Au minimum, ce scénario requiert la restauration et la publication du magasin central de gestion.
    
      - Perte d’un serveur principal alors que le magasin central de gestion fonctionne toujours normalement. Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé ainsi que la restauration des bases de données.
    
      - Panne d’un serveur membre d’un pool Lync Server. Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé.
    
      - Panne d’un magasin de fichiers. Ce scénario requiert la restauration du serveur de fichiers ou du cluster de fichiers.
    
      - Panne d’une base de données d’archivage, de surveillance ou de conversation permanente. Ce scénario requiert une nouvelle création des bases de données et, si les données sont critiques pour l’organisation, une restauration des données. Les données d’archivage, de surveillance et de conversation permanente ne sont pas requises pour rendre Lync Server à nouveau opérationnel.

