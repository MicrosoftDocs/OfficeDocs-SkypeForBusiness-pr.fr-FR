---
title: Considérations sur la migration de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lisez cette rubrique pour en savoir plus sur le déploiement de Skype Room System dans un environnement qui dispose de plusieurs versions de Skype Entreprise Server et de Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805784"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="7b47b-103">Considérations sur la migration de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="7b47b-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="7b47b-104">Lisez cette rubrique pour en savoir plus sur le déploiement de Skype Room System dans un environnement qui dispose de plusieurs versions de Skype Entreprise Server et de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b47b-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="7b47b-105">Considérations relatives à la migration</span><span class="sxs-lookup"><span data-stu-id="7b47b-105">Migration considerations</span></span>

<span data-ttu-id="7b47b-106">Cette section fournit des conseils si vous déployez Skype Room System dans un environnement multi-pool qui inclut différentes versions de Skype Entreprise Server ou de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b47b-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="7b47b-107">Le composant réplicateur d’utilisateurs (UR) dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données principale Lync Server SQL Server données.</span><span class="sxs-lookup"><span data-stu-id="7b47b-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="7b47b-108">Seule l’URL dans Lync Server 2013 connaît les objets Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7b47b-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="7b47b-109">L’UR dans les versions précédentes de Lync Server et d’Office Communications Server ne détecte pas les attributs Active Directory qui désignent les objets LRS et n’en était donc pas informé.</span><span class="sxs-lookup"><span data-stu-id="7b47b-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="7b47b-110">Si un compte Skype Room System tente de se connecter à Lync et effectue une découverte automatique basée sur l’enregistrement SRV ou la recherche d’enregistrement DNS A, et si ces comptes pointent vers une version antérieure de Lync Server ou d’Office Communications Server, LRS reçoit une réponse 404 In trouvé du pool hérité.</span><span class="sxs-lookup"><span data-stu-id="7b47b-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="7b47b-111">Le pool hérité ne pourra pas rediriger Skype Room System vers son pool d’accueil Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b47b-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="7b47b-112">Vous pouvez résoudre ce problème avec les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b47b-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="7b47b-113">Pointez votre enregistrement SRV de découverte automatique (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b47b-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="7b47b-114">Si la première option n’est pas possible, vous devez configurer manuellement LRS et fournir l’adresse du pool Lync Server 2013 en la configurant directement dans l’application console Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7b47b-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="7b47b-115">Si Skype Room System est déployé en dehors du réseau d’entreprise et qu’un serveur Edge Lync a été déployé et configuré pour pointer vers un pool ou un directeur hérité, un site serveur Edge secondaire est requis, qui pointe vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b47b-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="7b47b-116">Reportez-vous à la documentation de déploiement du serveur Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire.</span><span class="sxs-lookup"><span data-stu-id="7b47b-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="7b47b-117">Interopérabilité de Skype Room System avec un pool Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7b47b-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="7b47b-118">Lors de la migration, si un utilisateur qui est homed sur un pool Lync Server 2010 planifiera une réunion et invite le compte Skype Room System, le client Skype Room System aura des fonctionnalités limitées lors de la participation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="7b47b-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="7b47b-119">Lorsque le client Skype Room System rejoint une conférence téléphonique programmée organisée par un utilisateur sur Lync Server 2010, Skype Room System présente les limitations de réunion suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b47b-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="7b47b-120">Skype Room System ne peut pas afficher la galerie de vidéos multi-vues.</span><span class="sxs-lookup"><span data-stu-id="7b47b-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="7b47b-121">Si le client Skype Room System est le présentateur, il ne peut pas appliquer de verrouillage vidéo aux participants.</span><span class="sxs-lookup"><span data-stu-id="7b47b-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="7b47b-122">Skype Room System ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence Lync Server 2013 l’autorise, pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b47b-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="7b47b-123">Lync Server 2010 ne prend pas en charge la résolution 1080p.</span><span class="sxs-lookup"><span data-stu-id="7b47b-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="7b47b-124">Skype Room System est toujours limité par la stratégie de conférence de l’organisateur pour la résolution vidéo.</span><span class="sxs-lookup"><span data-stu-id="7b47b-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="7b47b-125">Par conséquent, même si le pool Lync 2010 prend en charge la résolution 720p, Skype Room System ne sera pas en mesure de tirer parti de la résolution 720p tant que la stratégie de l’organisateur ne la prend pas en charge.</span><span class="sxs-lookup"><span data-stu-id="7b47b-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="7b47b-126">Les clients Lync 2013 détectent la présence LRS dans la salle de réunion et se mutent automatiquement pour éviter l’écho dans la salle de réunion physique.</span><span class="sxs-lookup"><span data-stu-id="7b47b-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="7b47b-127">Cette fonctionnalité ne fonctionne pas dans les réunions hébergées sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7b47b-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="7b47b-128">Il existe des limites sur les performances de partage de bureau pour les réunions hébergées sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7b47b-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="7b47b-129">Les utilisateurs ne pourront pas participer à des réunions privées (restreintes) hébergées sur Lync 2010 avec Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7b47b-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

