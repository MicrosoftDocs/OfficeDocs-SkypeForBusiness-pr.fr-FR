---
title: Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans le générateur de topologie, effectuez les étapes suivantes pour configurer une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent.

1.  Ajoutez les bases de données miroir et les magasins de données secondaires SQL Server.

2.  Modifiez les propriétés du service de chat permanent serveur pour :
    
    1.  activer la mise en miroir pour la base de données primaire ;
    
    2.  Ajoutez le magasin SQL Server en miroir principal.
    
    3.  Activez la base de données d’envoi de journaux de SQL Server.
    
    4.  Ajoutez la banque SQL Server secondaire pour l’envoi du journal SQL Server.
    
    5.  Ajoutez le miroir SQL Server Store pour la base de données secondaire.
    
    6.  Publiez la topologie.

</div>

<span> </span>

</div>

</div>

</div>

