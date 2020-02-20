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
ms.openlocfilehash: 1cc2250020b7456515f06bcb308ca4cea4430a56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="a2bba-102">Prise en charge du stockage de fichiers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2bba-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2bba-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="a2bba-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="a2bba-104">Lync Server 2013 utilise le même magasin de fichiers pour tous les stockages de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a2bba-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="a2bba-105">La prise en charge du stockage de fichiers inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a2bba-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="a2bba-106">Un partage de fichiers sur le stockage DAS (direct Attached Storage) ou un réseau de zone de stockage (SAN), y compris le système de fichiers DFS (Distributed File System) et sur un système RAID (Redundant Array of Independent Disks) pour les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a2bba-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="a2bba-107">Pour plus d’informations sur les exigences de stockage, voir [Technical Requirements for Front End Servers, Messaging and Presence in Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) et [Hardware and Software Requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a2bba-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="a2bba-108">Pour plus d’informations sur DFS pour le système d’exploitation Windows Server 2008, voir le guide pas à pas de DFS pour Windows [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)Server 2008 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a2bba-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="a2bba-109">Un cluster partagé pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a2bba-109">A shared cluster for the file share.</span></span> <span data-ttu-id="a2bba-110">Si vous utilisez un cluster partagé, vous devez utiliser des serveurs de cluster exécutant Windows Server 2008 ou Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="a2bba-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="a2bba-111">L’utilisation de serveurs de cluster exécutant une version antérieure de Windows peut entraîner des problèmes d’autorisation qui empêchent la disponibilité de certaines fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="a2bba-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="a2bba-112">Utilisez l’administrateur de cluster pour créer les partages de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a2bba-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="a2bba-113">Pour plus d’informations sur l’utilisation de l’administrateur de cluster, consultez l’article 284838 de la base de connaissances Microsoft, « comment créer un partage de [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)fichiers de cluster de serveurs avec cluster. exe » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a2bba-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

