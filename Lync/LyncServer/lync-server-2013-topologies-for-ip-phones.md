---
title: 'Lync Server 2013 : topologies pour téléphones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b01e4d98ced806b40cd5f092c0b8051ce86f47
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologies de téléphones IP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-21_

Cette section fournit une vue d’ensemble du processus de connexion et explique les différences qui existent entre le mode de connexion d’un téléphone IP à un réseau interne ou externe.

<div>


> [!NOTE]  
> Lync Server prend en charge les téléphones IP suivants : le téléphone de partie commune Aastra 6721ip, Aastra 6725ip téléphone, le téléphone IP HP 4110 (téléphone de partie commune), HP 4120 IP Phone (téléphone de bureau), Polycom CX600 de bureau de bureau IP, Polycom CX700 IP de bureau, Polycom CX500 IP Téléphone de partie commune et téléphone de conférence IP Polycom CX3000. Ces téléphones, à l’exception du CX700 Polycom, peuvent exécuter Lync Phone Edition.



</div>

Le diagramme suivant décrit tous les composants impliqués dans la connectivité d’appareil au sein d’un environnement d’entreprise.

**Topologie interne**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> L’illustration précédente est une représentation logique, et non une vue d’ensemble physique. Par exemple, les services de domaine Active Directory (AD DS) se trouvent rarement sur le même ordinateur que n’importe quel composant Lync Server. Le magasin d’utilisateurs peut être situé sur le serveur principal ou sur les serveurs d’archivage et de surveillance. Lync Server Management Shell, le serveur Web et les services de mise à jour font partie du rôle de serveur frontal.



</div>

Le diagramme suivant fournit une vue d’ensemble des composants impliqués lorsque l’appareil est situé à l’extérieur du réseau d’entreprise.

**Topologie externe**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> Le service web de mise à jour des appareils fournit un site web externe et interne, mais seul le site externe est indiqué ici.<BR>L’emplacement du serveur d’inscriptions et l’URL du service web de mise à jour des appareils pour l’organisation doivent être publiés dans le système DNS si l’accès externe doit être activé. Par ailleurs, le serveur Edge doit être déployé et correctement configuré afin d’autoriser les communications externes à partir de l’appareil vers l’environnement d’entreprise et vice-versa. Cela n’apparaît pas sur le diagramme précédent car le déploiement du serveur Edge n’est pas effectué en fonction de la connectivité de l’appareil.



</div>

</div>

<span> </span>

</div>

</div>

</div>

