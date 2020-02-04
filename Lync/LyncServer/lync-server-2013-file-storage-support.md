---
title: Prise en charge du stockage des fichiers dans Lync Server 2013
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
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="6d788-102">Prise en charge du stockage des fichiers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d788-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d788-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="6d788-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6d788-104">Lync Server 2013 utilise le même magasin de fichiers pour tout le stockage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="6d788-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="6d788-105">La prise en charge du stockage de fichiers comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6d788-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="6d788-106">Un partage de fichiers sur un réseau de stockage (DAS) ou un réseau de stockage (SAN), y compris le système de fichiers DFS et sur une baie redondante de disques indépendants (RAID) pour les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="6d788-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="6d788-107">Pour plus d’informations sur la configuration requise, voir Configuration logicielle requise [pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) et la [Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="6d788-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="6d788-108">Pour plus d’informations sur le système d’exploitation DFS pour Windows Server 2008, voir le guide détaillé pour Windows Server 2008 à l' [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)adresse.</span><span class="sxs-lookup"><span data-stu-id="6d788-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="6d788-109">Un cluster partagé pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="6d788-109">A shared cluster for the file share.</span></span> <span data-ttu-id="6d788-110">Si vous utilisez un cluster partagé, vous devez utiliser des serveurs de cluster exécutant Windows Server 2008 ou Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="6d788-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="6d788-111">L’utilisation de serveurs de cluster exécutant une version antérieure de Windows peut provoquer des problèmes d’autorisation qui empêchent la disponibilité de certaines fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="6d788-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="6d788-112">Utilisez l’administrateur de cluster pour créer le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="6d788-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="6d788-113">Pour plus d’informations sur l’utilisation de l’administrateur de cluster, voir l’article de la base de connaissances Microsoft 284838, « création d’un partage de [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)fichiers de cluster de serveurs avec cluster. exe » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="6d788-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

