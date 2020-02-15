---
title: 'Lync Server 2013 : nouvelles fonctionnalités d’archivage'
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
ms.openlocfilehash: bf8c632fa5858eaf35464e9885e65343bc699e54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="740df-102">Nouvelles fonctionnalités d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740df-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="740df-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="740df-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="740df-104">L’archivage dans Lync Server 2013 peut archiver les types de contenu suivants :</span><span class="sxs-lookup"><span data-stu-id="740df-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="740df-105">Messages instantanés d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="740df-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="740df-106">Conférences (réunions) constituant des messages instantanés entre utilisateurs multiples</span><span class="sxs-lookup"><span data-stu-id="740df-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="740df-107">Contenu de conférence, dont le contenu téléchargé (documents, par exemple) et le contenu lié à un événement (par exemple, rejoindre ou quitter la conférence, télécharger des données partagées ou modifier la visibilité)</span><span class="sxs-lookup"><span data-stu-id="740df-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="740df-108">De plus, l’archivage dans Lync Server 2013 offre de nouvelles fonctionnalités qui améliorent l’efficacité du déploiement et des opérations.</span><span class="sxs-lookup"><span data-stu-id="740df-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="740df-109">Voici ces nouvelles options :</span><span class="sxs-lookup"><span data-stu-id="740df-109">These new features consist of:</span></span>

  - <span data-ttu-id="740df-110">**Colocalisation de l’archivage sur les serveurs frontaux.**    Lync Server 2013 ne dispose pas d’un rôle de serveur d’archivage distinct.</span><span class="sxs-lookup"><span data-stu-id="740df-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="740df-111">L’archivage est une fonctionnalité facultative disponible sur tous les serveurs frontaux dans un déploiement Enterprise Edition, ainsi que sur les serveurs Standard Edition Server qui peuvent être implémentés pour un pool ou un site.</span><span class="sxs-lookup"><span data-stu-id="740df-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="740df-112">**Intégration de Microsoft Exchange.**    Lorsque vous déployez l’archivage, vous pouvez intégrer le stockage des données pour l’archivage à votre stockage Exchange 2013 existant pour tous les utilisateurs hébergés sur Exchange 2013 et disposer de leurs boîtes aux lettres en conservation inaltérable, de sorte que vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour archiver les données Lync.</span><span class="sxs-lookup"><span data-stu-id="740df-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="740df-113">Si vous ne disposez pas d’un déploiement d’Exchange 2013 ou si vous préférez ne pas l’intégrer ou si vous avez des utilisateurs Lync 2013 qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées en conservation inaltérable, vous pouvez déployer des bases de données d’archivage distinctes à l’aide de SQL Server to Stor e données archivées à partir de Lync communications.</span><span class="sxs-lookup"><span data-stu-id="740df-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="740df-114">Vous pouvez utiliser à la fois l’intégration de Microsoft Exchange et les bases de données d’archivage Lync Server 2013 pour utiliser l’intégration de Microsoft Exchange pour certains utilisateurs, mais pas pour tous, dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="740df-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="740df-115">Pour plus d’informations sur le blocage sur place, consultez la rubrique « conservation inaltérable [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="740df-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="740df-116">**Mise en miroir du magasin SQL.**    Lorsque vous déployez l’archivage, vous pouvez activer la mise en miroir de base de données SQL Server pour votre base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="740df-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="740df-117">**Archivage des tableaux blancs et des sondages.**    Le contenu de conférence archivé inclut désormais des tableaux blancs et des sondages partagés au cours de la réunion.</span><span class="sxs-lookup"><span data-stu-id="740df-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="740df-118">Les types de contenu suivants ne sont pas archivés :</span><span class="sxs-lookup"><span data-stu-id="740df-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="740df-119">Transferts de fichiers d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="740df-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="740df-120">Audio/vidéo pour messages instantanés et conférences d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="740df-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="740df-121">Partage d’application pour messages instantanés et conférences d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="740df-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="740df-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="740df-122">See Also</span></span>


[<span data-ttu-id="740df-123">Planification de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="740df-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

