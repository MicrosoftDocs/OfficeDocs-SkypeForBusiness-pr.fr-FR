---
title: Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-05_

Chaque appareil de branchement Survivable (SBA) est associé à un pool frontal, qui fait office d’agent de sauvegarde pour le SBA. Lorsque le pool frontal est mis à niveau vers Lync Server 2013, le SBA doit être désassocié du pool frontal lors de la mise à niveau du pool frontal. Après la mise à niveau du pool frontal, le SBA peut être associé au pool frontal. Cela implique la suppression de l’SBA de la topologie dans le générateur de topologie, puis l’ajout de l’SBA, là encore, au générateur de topologie. Les utilisateurs hébergés sur le SBA doivent être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie. Après l’ajout de l’SBA à la topologie, ces utilisateurs peuvent être replacés vers l’SBA.

Ces étapes sont décrites ci-dessous:

1.  Déplacez les utilisateurs de succursales hébergés sur SBA vers un autre pool frontal.

2.  Supprimez SBA de votre topologie pour dissocier le pool frontal existant en tant qu’Bureau d’enregistrement de sauvegarde.

3.  Mettez à niveau le pool frontal vers Microsoft Lync Server 2013.

4.  Ajoutez SBA dans votre topologie.

5.  Associez le nouveau pool frontal à l’SBA en tant qu’Bureau d’enregistrement de sauvegarde.

6.  Transférez les utilisateurs de succursale vers le SBA.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2010 à votre topologie](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

