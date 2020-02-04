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
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migration des serveurs d’archivage et de surveillance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Si vous avez déployé le serveur d’archivage et le serveur de surveillance sur votre serveur Office Communications Server 2007 R2, vous pouvez déployer ces serveurs dans votre environnement Lync Server 2013 après la migration de vos pools front-end. En revanche, si la fonctionnalité d’archivage et de surveillance est essentielle pour votre organisation, il est conseillé d’y ajouter l’archivage et la surveillance de votre pool de pilotes avant de procéder à la migration.

Si vous voulez utiliser les fonctionnalités d’archivage et de surveillance pendant la phase de migration et de coexistence, gardez à l’esprit les points suivants :

  - L’archivage de données et le contrôle des données ne sont pas déplacés vers le déploiement Lync Server 2013. Les données que vous sauvegardez avant de désactiver l’environnement hérité seront votre historique d’activités dans Office Communications Server 2007 R2.

  - La version R2 d’Office Communications Server 2007 R2 du serveur d’archivage et de surveillance Server peut être associée uniquement à un pool frontal d’Office Communications Server 2007 R2. Dans Lync Server 2013, l’archivage et la surveillance ne sont plus des rôles de serveur, mais les services intégrés au pool de serveurs front end 2013 de Lync Server.

  - Pendant la période de coexistence des déploiements d’anciens et de Lync Server 2013, la version R2 d’Office Communications Server 2007 R2 du serveur d’archivage et de la surveillance du serveur collecte des données pour les utilisateurs hébergés sur des pools Office Communications Server 2007 R2. La version 2013 de Lync Server du serveur d’archivage et de surveillance du serveur de surveillance collecte des données pour les utilisateurs hébergés sur les pools 2013 du serveur Lync.
    
    <div>
    

    > [!NOTE]  
    > Pendant la phase de migration lorsque vous utilisez toujours votre serveur de périphérie antérieur avec le nouveau pool de pilotes Lync Server 2013, la version R2 d’Office Communications Server 2007 R2 du serveur d’archivage continue de rassembler les données pour les utilisateurs hébergés sur Office Communications Server 2007 Les pools R2 et la version 2013 du serveur d’archivage de Lync Server regroupent les données des utilisateurs hébergés sur les pools 2013 de Lync Server.

    
    </div>

  - Si vous utilisez une solution tierce d’archivage et de surveillance conjointement avec le serveur d’archivage et le serveur de surveillance, contactez votre revendeur sur le moment et la façon dont vous devez intégrer la solution tierce à Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

