---
title: 'Lync Server 2013 : Nouvelles fonctionnalités d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="1c352-102">Nouvelles fonctionnalités d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c352-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c352-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1c352-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1c352-104">L’archivage dans Lync Server 2013 permet d’archiver les types de contenu suivants :</span><span class="sxs-lookup"><span data-stu-id="1c352-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="1c352-105">Messages instantanés P2P</span><span class="sxs-lookup"><span data-stu-id="1c352-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="1c352-106">Conférences (réunions) qui sont des messages instantanés à plusieurs participants</span><span class="sxs-lookup"><span data-stu-id="1c352-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="1c352-107">Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)</span><span class="sxs-lookup"><span data-stu-id="1c352-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="1c352-108">De plus, l’archivage dans Lync Server 2013 fournit de nouvelles fonctionnalités qui améliorent l’efficacité du déploiement et des opérations.</span><span class="sxs-lookup"><span data-stu-id="1c352-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="1c352-109">Ces nouvelles fonctionnalités sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1c352-109">These new features consist of:</span></span>

  - <span data-ttu-id="1c352-110">**Colocalisation de l’archivage sur des serveurs frontaux.**    Lync Server 2013 ne possède pas de rôle serveur d’archivage distinct.</span><span class="sxs-lookup"><span data-stu-id="1c352-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="1c352-111">L’archivage est une fonctionnalité facultative disponible sur tous les serveurs frontaux d’un déploiement Enterprise Edition et sur les serveurs Standard Edition Server qui peuvent être implémentés pour un pool ou un site.</span><span class="sxs-lookup"><span data-stu-id="1c352-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="1c352-112">**Intégration de Microsoft Exchange.**    Lorsque vous déployez l’archivage, vous pouvez intégrer le stockage des données pour l’archivage avec votre espace de stockage 2013 Exchange pour tous les utilisateurs hébergés sur Exchange 2013 et disposer de leurs boîtes aux lettres sur place, de sorte que vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour archiver les données Lync.</span><span class="sxs-lookup"><span data-stu-id="1c352-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="1c352-113">Si vous n’avez pas de déploiement Exchange 2013 ou si vous préférez ne pas l’intégrer, ou si vous avez des utilisateurs de Lync 2013 qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées sur place, vous pouvez déployer des bases de données d’archivage distinctes en utilisant SQL Server to Stor. e données archivées provenant des communications Lync.</span><span class="sxs-lookup"><span data-stu-id="1c352-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="1c352-114">Vous pouvez utiliser les bases de données d’archivage Microsoft Exchange et Lync Server 2013 si vous souhaitez utiliser l’intégration de Microsoft Exchange pour certains utilisateurs, mais pas pour tous les utilisateurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1c352-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="1c352-115">Pour plus d’informations sur la conservation inaltérable, voir la section « conservation inaltérable » [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1c352-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="1c352-116">**Mise en miroir du SQL Store.**    Lorsque vous déployez l’archivage, vous pouvez activer la mise en miroir de la base de données SQL Server pour votre base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="1c352-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="1c352-117">**Archivage de tableaux blancs et de sondages.**    Le contenu des conférences archivées inclut désormais les tableaux blancs et les sondages partagés pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="1c352-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="1c352-118">Les types de contenu suivants ne sont pas archivés :</span><span class="sxs-lookup"><span data-stu-id="1c352-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="1c352-119">Transfert de fichiers d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="1c352-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="1c352-120">Audio/vidéo pour messages instantanés et conférences P2P</span><span class="sxs-lookup"><span data-stu-id="1c352-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="1c352-121">Partage d’application pour les messages instantanés et les conférences d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="1c352-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1c352-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c352-122">See Also</span></span>


[<span data-ttu-id="1c352-123">Planification de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c352-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

