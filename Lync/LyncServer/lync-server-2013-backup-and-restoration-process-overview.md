---
title: Présentation du processus de sauvegarde et de restauration Lync Server 2013
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
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Présentation du processus de sauvegarde et de restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Cette section fournit une vue d’ensemble du fonctionnement du processus de sauvegarde et de restauration pour Lync Server 2013. Vous utilisez le même processus pour tous les serveurs Standard Edition Server et les serveurs Enterprise Edition, quel que soit leur emplacement.

En règle générale, le processus de sauvegarde fonctionne comme suit :

  - Vous pouvez créer un emplacement de sauvegarde en tant que dossier partagé sur un ordinateur autonome qui ne fait pas partie d’un pool. L’emplacement de la sauvegarde est référencé dans **$Backup**.

  - D’un point de vue régulier, vous sauvegardez toutes les bases de données du serveur Lync et tous les magasins de fichiers décrits dans les [exigences de sauvegarde et de restauration de Lync server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md) en suivant les procédures décrites dans la rubrique [sauvegarde de Lync Server 2013](lync-server-2013-backing-up-lync-server.md) le centre de gestion central inclut tous les paramètres et configurations du serveur.

  - Chaque fois que vous exécutez une sauvegarde ultérieure, vous devez créer un dossier partagé et changer le chemin d’accès **$Backup** références.

En règle générale, le processus de restauration fonctionne comme suit :

  - Dans le cas d’une panne ou d’une panne, vous restaurez les données à l’emplacement référencé par **$Backup** sur des ordinateurs nouveaux ou sains.
    
    <div>
    

    > [!IMPORTANT]  
    > Ce processus de restauration ne restaure pas les données sur un État serveur existant. Autrement dit, ce processus nécessite une nouvelle installation du serveur.

    
    </div>

  - Pour permettre à l’utilisateur et aux informations de votre conférence d’être récupérable au point de défaillance, vous pouvez implémenter une topologie de récupération d’urgence avec des pools frontaux couplés, comme décrit dans la section [planification de la haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - La configuration de votre système de noms de domaine (DNS), de la configuration du protocole de configuration de l’hôte dynamique, des noms de domaine, des noms de domaine complets (FQDN), des chemins d’accès du magasin de fichiers, etc. doivent être identiques au moment de la restauration. Recule.

Si un serveur exécutant Lync Server tombe en panne, la récupération inclut les étapes suivantes :

  - Installez le système d’exploitation sur un nouvel ordinateur ou un ordinateur qui a le même nom de domaine complet que l’ordinateur en panne.

  - Réinstallez les certificats.

  - Si le serveur a hébergé une base de données, installez Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2.

  - En règle générale, si le serveur a hébergé une base de données, exécutez le générateur de topologie pour créer et installer la base de données et configurer les listes de contrôle d’accès (ACL).

  - En règle générale, si le serveur héberge un rôle serveur, exécutez les étapes 1 à 4 de l’Assistant Déploiement de Lync Server pour installer les fichiers de configuration locaux, installer les composants du rôle de serveur, attribuer des certificats et démarrer les services.
    
    <div>
    

    > [!NOTE]  
    > Si le serveur a hébergé une base de données avec le rôle serveur, l’exécution de l’étape 2 de l’Assistant Déploiement de Lync Server recrée la base de données.

    
    </div>

  - Si le serveur a hébergé une base de données, restaurez les données sauvegardées.

</div>

<span> </span>

</div>

</div>

</div>

