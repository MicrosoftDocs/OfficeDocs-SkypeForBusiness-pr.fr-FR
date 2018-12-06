---
title: 'Lync Server 2013 : Conditions requises pour publier une topologie'
TOCTitle: Conditions requises pour publier une topologie
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg195733(v=OCS.15)
ms:contentKeyID: 49297926
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conditions requises pour publier une topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Cette rubrique décrit l’infrastructure et la configuration logicielle requise inhérentes à la publication d’une topologie, que vous utilisiez le Générateur de topologie ou l’interface de ligne de commande Lync Server 2013 Management Shell. Ces exigences s’ajoutent aux conditions générales requises en matière de système d’exploitation, de logiciels et d’autorisations applicables à l’ensemble des outils d’administration Lync Server 2013. Avant de publier une topologie, assurez-vous que vous répondez à toutes les caractéristiques exigées par les outils d’administration.

  - Vous devez exécuter le Générateur de topologie sur un ordinateur joint au même domaine ou à la même forêt que le déploiement Lync Server 2013 que vous créez pour mener déjà à bien les étapes de préparation des services de domaine Active Directory, ce qui vous permettra d’utiliser les outils d’administration sur cet ordinateur et de publier comme il se doit votre topologie.

  - Les ordinateurs définis dans la topologie doivent être ajoutés au domaine, à l’exception des serveurs Edge, et aux services de domaine Active Directory (AD DS). En revanche, ils n’ont pas besoin d’être en ligne au moment où vous publiez la topologie.

  - Vous devez créer le partage de fichiers du pool et le mettre à la disposition des utilisateurs distants.

  - Pour être en mesure de publier un pool de serveurs frontaux Enterprise Edition, le serveur principal SQL Server doit être joint au domaine dans lequel vous déployez les serveurs, être en ligne et configuré à l’aide des règles de pare-feu appropriées pour le mettre à la disposition des utilisateurs distants. Pour obtenir des informations sur la définition des exceptions du pare-feu, reportez-vous à [Description des exigences de pare-feu pour SQL Server avec Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Pour obtenir d’autres informations sur la configuration de SQL Server, reportez-vous à [Configuration de SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    > [!NOTE]  
    > Le serveur serveur Standard Edition dispose d’une base de données colocalisée qui acceptera la configuration publiée. Vous devez d’abord exécuter la tâche de configuration <strong>Préparer d’abord le serveur Standard Edition</strong> dans l’Assistant Déploiement de Lync Server.

## Voir aussi

#### Tâches

[Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  

#### Concepts

[Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Autres ressources

[Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

