---
title: 'Lync Server 2013 : présentation du processus de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd6efce509283d59c5cecc7325c35c9cf1ab371e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Vue d’ensemble du processus de sauvegarde et de restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Cette section fournit une vue d’ensemble du fonctionnement du processus de sauvegarde et de restauration pour Lync Server 2013. Vous utilisez la même procédure pour tous les serveurs Standard Edition Server et Enterprise Edition, quel que soit leur emplacement.

En règle générale, le processus de sauvegarde fonctionne comme suit :

  - Vous créez un emplacement de sauvegarde en tant que dossier partagé sur un ordinateur autonome qui ne fait partie d’aucun pool. L’emplacement de la sauvegarde est référencé dans **$Backup**.

  - De manière régulière et planifiée, vous sauvegardez toutes les bases de données Lync Server et tous les magasins de fichiers décrits dans la rubrique Configuration de la [sauvegarde et de la restauration dans Lync server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md) en suivant les procédures décrites dans la rubrique [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) le magasin central de gestion inclut tous les paramètres et configurations du serveur.

  - Chaque fois que vous exécutez une sauvegarde ultérieure, vous créez un nouveau dossier partagé et modifiez le chemin d’accès que **$Backup** référence.

En règle générale, le processus de restauration fonctionne comme suit :

  - Lorsqu’une défaillance ou une panne se produit, vous restaurez les données à l’emplacement référencé par **$Backup** sur des ordinateurs nouveaux ou nettoyés.
    
    <div>
    

    > [!IMPORTANT]  
    > Ce processus de restauration ne restaure pas les données dans un état de serveur existant. Autrement dit, ce processus nécessite que le serveur soit propre ou nouveau.

    
    </div>

  - Pour que vos informations d’utilisateur et de conférence soient récupérables au point de défaillance, vous pouvez implémenter une topologie de récupération d’urgence avec des pools frontaux couplés, comme décrit dans [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - La configuration DNS (Domain Name System), la configuration du protocole DHCP (Dynamic Host Configuration Protocol), les noms de domaine, les noms de domaine complets (FQDN), les chemins d’accès aux magasins de fichiers, etc., doivent être identiques au moment de la restauration Recule.

Si un serveur exécutant Lync Server tombe en panne, la récupération inclut les étapes suivantes :

  - Installez le système d’exploitation sur un ordinateur nouveau ou nettoyé avec le même nom de domaine complet que l’ordinateur défaillant.

  - Réinstallez les certificats.

  - Si le serveur hébergeait une base de données, installez Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2.

  - En général, si le serveur hébergeait une base de données, exécutez le générateur de topologie pour créer et installer la base de données, puis configurez les listes de contrôle d’accès (ACL).

  - En général, si le serveur hébergeait un rôle serveur, exécutez les étapes 1 à 4 de l’Assistant Déploiement de Lync Server pour installer les fichiers de configuration locaux, installer les composants de rôle serveur, assigner des certificats et démarrer les services.
    
    <div>
    

    > [!NOTE]  
    > Si le serveur hébergeait une base de données colocalisée avec le rôle serveur, l’étape 2 de l’Assistant Déploiement de Lync Server recrée la base de données.

    
    </div>

  - Si le serveur hébergeait une base de données, restaurez les données sauvegardées.

</div>

<span> </span>

</div>

</div>

</div>

