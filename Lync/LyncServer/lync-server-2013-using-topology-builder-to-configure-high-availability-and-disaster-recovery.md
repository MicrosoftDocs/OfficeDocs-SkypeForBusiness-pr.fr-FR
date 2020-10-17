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
ms.openlocfilehash: 21e240e8fd597f1fe8a2669df45d674be7a7bef1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508651"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans le générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.

1.  Ajoutez les bases de données miroir et les magasins SQL Server de base de données secondaire pour l’envoi de journaux.

2.  Modifiez les propriétés du service serveur de conversation permanente comme suit :
    
    1.  activer la mise en miroir pour la base de données primaire ;
    
    2.  Ajoutez le magasin SQL Server miroir principal.
    
    3.  Activez la base de données de copie des journaux SQL Server.
    
    4.  Ajoutez le magasin SQL Server secondaire de copie des journaux de transaction SQL Server.
    
    5.  Ajoutez le miroir du magasin SQL Server pour la base de données secondaire.
    
    6.  Publiez la topologie.

</div>

<span> </span>

</div>

</div>

</div>

