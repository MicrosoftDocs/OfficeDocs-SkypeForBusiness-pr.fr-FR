---
title: 'Lync Server 2013: topologies pour téléphones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologies pour téléphones IP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-21_

Cette section fournit une vue d’ensemble du processus de connectivité et explique les différences entre la connexion d’un téléphone IP à un réseau interne et externe.

<div>


> [!NOTE]  
> Lync Server prend en charge les téléphones IP suivants: le téléphone de bureau Aastra 6721ip, Aastra 6725ip Phone, le téléphone IP HP 4110 (téléphone pour la zone commune 4120), le numéro de téléphone IP (téléphone de bureau), le téléphone de bureau IP CX600 téléphone standard et téléphone de conférence IP Polycom CX3000. De ces téléphones, mais le Polycom CX700 peut exécuter Lync Phone Edition.



</div>

Le diagramme suivant décrit tous les composants impliqués dans la connectivité des appareils au sein de l’environnement d’entreprise.

**Topologie interne**

![3d88893e-df57-46E3-855a-a1d24589030a] (images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46E3-855a-a1d24589030a")

<div>


> [!NOTE]  
> La figure précédente est une représentation logique qui n’est pas une vue d’ensemble physique. Par exemple, les services de domaine Active Directory (AD DS) se trouvent rarement sur le même ordinateur que les composants serveur Lync. Le magasin utilisateur peut se trouver sur le serveur principal ou sur les serveurs d’archivage et de surveillance. Lync Server Management Shell, le serveur Web et les services de mise à jour font partie du rôle serveur frontal.



</div>

Le diagramme suivant fournit une vue d’ensemble des composants impliqués lorsque l’appareil se trouve en dehors du réseau d’entreprise.

**Topologie externe**

![8ce6bb8e-b89c-4C4E-ac6d-41ac6c68f6f3] (images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4C4E-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Le service Web de mise à jour d’appareil fournit un site Web interne et externe, mais seul le premier est affiché ici.<BR>L’emplacement du Bureau d’enregistrement et l’URL du service Web de mise à jour de l’appareil pour l’organisation doivent être publiés dans DNS si l’accès externe doit être activé. Par ailleurs, le serveur de périphérie doit être déployé et correctement configuré pour autoriser les communications externes entre l’appareil et l’environnement d’entreprise. Ce paramètre est omis du diagramme précédent, car le déploiement Edge n’est pas spécifique à la connectivité de l’appareil.



</div>

</div>

<span> </span>

</div>

</div>

</div>

