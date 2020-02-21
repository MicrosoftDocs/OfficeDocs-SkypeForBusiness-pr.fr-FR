---
title: Prise en charge du stockage de fichiers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b870aa22d9dea13e84f045af8fc6fe800fb3d55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Prise en charge du stockage de fichiers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Lync Server 2013 utilise le même magasin de fichiers pour tous les stockages de fichiers. La prise en charge du stockage de fichiers inclut les éléments suivants :

  - Un partage de fichiers sur le stockage DAS (direct Attached Storage) ou un réseau de zone de stockage (SAN), y compris le système de fichiers DFS (Distributed File System) et sur un système RAID (Redundant Array of Independent Disks) pour les magasins de fichiers. Pour plus d’informations sur les exigences de stockage, voir [Technical Requirements for Front End Servers, Messaging and Presence in Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) et [Hardware and Software Requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) dans la documentation de planification. Pour plus d’informations sur DFS pour le système d’exploitation Windows Server 2008, voir le guide pas à pas de DFS pour Windows [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)Server 2008 à l’adresse.

  - Un cluster partagé pour le partage de fichiers. Si vous utilisez un cluster partagé, vous devez utiliser des serveurs de cluster exécutant Windows Server 2008 ou Windows Server 2008 R2. L’utilisation de serveurs de cluster exécutant une version antérieure de Windows peut entraîner des problèmes d’autorisation qui empêchent la disponibilité de certaines fonctionnalités. Utilisez l’administrateur de cluster pour créer les partages de fichiers. Pour plus d’informations sur l’utilisation de l’administrateur de cluster, consultez l’article 284838 de la base de connaissances Microsoft, « comment créer un partage de [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)fichiers de cluster de serveurs avec cluster. exe » à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

