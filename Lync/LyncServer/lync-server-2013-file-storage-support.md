---
title: Prise en charge du stockage des fichiers dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Prise en charge du stockage des fichiers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-16_

Lync Server 2013 utilise le même magasin de fichiers pour tout le stockage de fichiers. La prise en charge du stockage de fichiers comprend les éléments suivants:

  - Un partage de fichiers sur un réseau de stockage (DAS) ou un réseau de stockage (SAN), y compris le système de fichiers DFS et sur une baie redondante de disques indépendants (RAID) pour les magasins de fichiers. Pour plus d’informations sur la configuration requise, voir Configuration logicielle requise [pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) et configurations [matérielle et logicielle requises pour le directeur dans Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) dans le planning accompagnant. Pour plus d’informations sur le système d’exploitation DFS pour Windows Server 2008, voir le guide détaillé pour Windows Server 2008 à l' [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)adresse.

  - Un cluster partagé pour le partage de fichiers. Si vous utilisez un cluster partagé, vous devez utiliser des serveurs de cluster exécutant Windows Server 2008 ou Windows Server 2008 R2. L’utilisation de serveurs de cluster exécutant une version antérieure de Windows peut provoquer des problèmes d’autorisation qui empêchent la disponibilité de certaines fonctionnalités. Utilisez l’administrateur de cluster pour créer le partage de fichiers. Pour plus d’informations sur l’utilisation de l’administrateur de cluster, voir l’article de la base de connaissances Microsoft 284838, «création d’un partage de [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)fichiers de cluster de serveurs avec cluster. exe» à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

