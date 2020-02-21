---
title: Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a148b63438710c5faf599b6053dcaf4cce7d0bad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Chaque Survivable Branch Appliance (SBA) est associé à un pool de serveurs frontaux, qui sert de serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool frontal est mis à niveau vers Lync Server 2013, le SBA doit être désassocié du pool frontal pendant la mise à niveau du pool frontal. Une fois le pool frontal mis à niveau, le SBA peut être réassocié au pool frontal. Cela implique de supprimer le SBA de la topologie dans le Générateur de topologie, puis de l’ajouter à nouveau au Générateur de topologie. Les utilisateurs hébergés sur le SBA doivent être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA a été rajouté à la topologie, ces utilisateurs peuvent réintégrer le SBA.

Voici un récapitulatif de ces étapes :

1.  Déplacez les utilisateurs de succursale hébergés sur SBA vers un autre pool frontal.

2.  Supprimez SBA de votre topologie pour dissocier le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.

3.  Mettez à niveau le pool frontal vers Microsoft Lync Server 2013.

4.  Rajoutez le SBA à votre topologie.

5.  Associez le nouveau pool frontal au SBA en tant que serveur d’inscriptions de sauvegarde.

6.  Réintégrez les utilisateurs au SBA.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Ajouter le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Ajouter le site de succursale Survivable Branch Appliance Lync Server 2010 à votre topologie](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

