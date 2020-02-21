---
title: Migration des serveurs d’archivage et de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67896576fce21eea630533a5826bbcbc53392fa0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209850"
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

Si vous avez déployé le serveur d’archivage et le serveur de surveillance dans votre Office Communications Server 2007 R2, vous pouvez déployer ces serveurs dans votre environnement Lync Server 2013 après avoir migré vos pools frontaux. Toutefois, si les fonctionnalités d’archivage et de surveillance sont critiques pour votre organisation, nous vous recommandons d’ajouter l’archivage et la surveillance à votre pool pilote avant la migration pour que la fonctionnalité soit disponible pendant le processus de migration.

Si vous voulez que les fonctionnalités d’archivage et de surveillance soient disponibles au cours de la phase de migration et de coexistence, gardez les éléments suivants à l’esprit :

  - Les données d’archivage et les données de surveillance ne sont pas déplacées vers le déploiement Lync Server 2013. Les données que vous sauvegardez avant la mise hors service de l’environnement hérité seront votre historique des activités dans Office Communications Server 2007 R2.

  - La version Office Communications Server 2007 R2 du serveur d’archivage et du serveur de surveillance ne peut être associée qu’à un pool frontal Office Communications Server 2007 R2. Dans Lync Server 2013, l’archivage et la surveillance ne sont plus des rôles serveur, mais des services intégrés au pool frontal Lync Server 2013.

  - Pendant la coexistence de vos déploiements hérités et Lync Server 2013, la version Office Communications Server 2007 R2 du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur des pools Office Communications Server 2007 R2. La version Lync Server 2013 du serveur d’archivage et du serveur de surveillance recueille des données pour les utilisateurs hébergés sur des pools Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Pendant la phase de migration, lorsque vous utilisez toujours votre serveur Edge hérité avec le nouveau pool pilote Lync Server 2013, la version Office Communications Server 2007 R2 du serveur d’archivage continue de collecter des données pour les utilisateurs hébergés sur Office Communications Server 2007 Les pools R2 et la version Lync Server 2013 du serveur d’archivage collectent des données pour les utilisateurs hébergés sur des pools Lync Server 2013.

    
    </div>

  - Si vous utilisez une solution d’archivage et de surveillance tierce en association avec le serveur d’archivage et le serveur de surveillance, demandez à votre fournisseur quand et comment vous devez intégrer la solution tierce à Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

