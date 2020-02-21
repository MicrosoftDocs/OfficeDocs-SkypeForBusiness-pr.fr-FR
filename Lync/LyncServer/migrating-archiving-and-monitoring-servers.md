---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4edd989985c4ed65027ed8d19725ec1f93c2bdc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migration des serveurs d’archivage et de surveillance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre environnement Lync Server 2010, vous pouvez déployer ces serveurs dans votre environnement Lync Server 2013 après avoir migré vos pools frontaux. Toutefois, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, vous devez ajouter l’archivage et la surveillance à votre pool de pilotes Lync Server 2013 avant de procéder à la migration afin que la fonctionnalité soit disponible pendant le processus de migration.

Si vous voulez la fonctionnalité d’archivage et de surveillance au cours du processus de migration, gardez les considérations suivantes à l’esprit :

  - Les données d’archivage et les données de surveillance ne sont pas déplacées vers le déploiement Lync Server 2013. Les données que vous sauvegardez avant de désaffecter l’environnement hérité correspondent à votre historique d’activité dans l’environnement Lync Server 2010.

  - La version Lync Server 2010 du serveur d’archivage et du serveur de surveillance ne peut être associée qu’à un pool frontal Lync Server 2010. Dans Lync Server 2013, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal Lync Server 2013.

  - Pendant la coexistence de vos déploiements hérités et Lync Server 2013, la version Lync Server 2010 du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur des pools Lync Server 2010. L’archivage et la surveillance dans Lync Server 2013 recueillent des données pour les utilisateurs hébergés sur des pools Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Pendant la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Lync Server 2013, la version Lync Server 2010 du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur les pools et l’archivage Lync Server 2010 dans Lync Server 2013 recueille des données pour les utilisateurs hébergés sur des pools Lync Server 2013.

    
    </div>

  - Si vous utilisez une solution d’archivage et de surveillance tierce en association avec l’archivage et la surveillance dans Lync Server 2013, consultez votre fournisseur quand et comment intégrer la solution tierce à Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

