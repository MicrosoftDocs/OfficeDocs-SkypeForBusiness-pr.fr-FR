---
title: Remarques sur la migration de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Pour en savoir plus sur le déploiement de votre système de salle Skype dans un environnement doté de plusieurs versions de Skype entreprise Server et de Lync Server, reportez-vous à cette rubrique.
ms.openlocfilehash: f5da7f92c7ab947d5e6d68c19823d227f8ae3ca3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234207"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="bd5e7-103">Remarques sur la migration de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="bd5e7-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="bd5e7-104">Pour en savoir plus sur le déploiement de votre système de salle Skype dans un environnement doté de plusieurs versions de Skype entreprise Server et de Lync Server, reportez-vous à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="bd5e7-105">Remarques sur la migration</span><span class="sxs-lookup"><span data-stu-id="bd5e7-105">Migration considerations</span></span>

<span data-ttu-id="bd5e7-106">Cette section fournit des recommandations si vous déployez le système de salle Skype dans un environnement multi-pool incluant différentes versions de Skype entreprise Server ou de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="bd5e7-107">Le composant réplicateur d’utilisateurs dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données SQL Server du serveur principal Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="bd5e7-108">Seul le RÉPLICATEUR d’application de bureau dans Lync Server 2013 est consciente des objets système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="bd5e7-109">Le réplicateur d’utilisateurs dans les versions précédentes de Lync Server et Office Communications Server ne détecte pas les attributs Active Directory qui désignent des objets LRS, et n’en avait, par conséquent, pas connaissance.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="bd5e7-110">Si un compte système de salle Skype tente de se connecter à Lync et effectue une découverte automatique en fonction de l’enregistrement SRV ou du système de recherche DNS A et si ces comptes pointent vers une version antérieure de Lync Server ou d’Office Communications Server, LRS recevra une réponse 404 introuvable de  le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="bd5e7-111">Le pool hérité ne sera pas en mesure de rediriger le système de salle Skype vers son pool d’hébergement 2013 Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="bd5e7-112">Vous pouvez résoudre ce problème avec les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd5e7-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="bd5e7-113">Pointez votre découverte automatique d’enregistrement SRV (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="bd5e7-114">Si la première option n’est pas possible, vous devez configurer manuellement LRS et fournir l’adresse du pool Lync Server 2013 en le configurant directement dans l’application console du système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="bd5e7-115">Si le système de salle Skype est déployé à l’extérieur du réseau d’entreprise, et qu’un serveur Edge Lync a été déployé et configuré de manière à pointer vers un pool ou un réalisateur hérité, un site serveur de bord secondaire est requis, qui pointe vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="bd5e7-116">Reportez-vous à la documentation de déploiement des serveurs Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="bd5e7-117">Interopérabilité du système de salle Skype avec un pool Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bd5e7-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="bd5e7-118">Lors de la migration, si un utilisateur qui est hébergé sur un pool Lync Server 2010 planifie une réunion et invite le compte système de salle Skype, le client de système de salle Skype dispose de fonctionnalités limitées tout en participant à la réunion.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="bd5e7-119">Lorsque le client système de salle Skype joint un appel de conférence planifiée qui a été organisé par un utilisateur hébergé sur Lync Server 2010, le système de salle Skype dispose des limitations suivantes:</span><span class="sxs-lookup"><span data-stu-id="bd5e7-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="bd5e7-120">Le système de salle Skype ne peut pas afficher la Galerie de vidéos multivues.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="bd5e7-121">Si le client système de salle Skype est le présentateur, la vidéo ne peut pas être appliquée aux participants.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="bd5e7-122">Le système de salle Skype ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence 2013 de Lync Server le permet, pour les raisons suivantes:</span><span class="sxs-lookup"><span data-stu-id="bd5e7-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="bd5e7-123">Lync Server 2010 ne prend pas en charge la résolution 1080p.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="bd5e7-124">Le système de salle Skype est toujours limité par la stratégie de conférence de l’organisateur en fonction de la résolution vidéo.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="bd5e7-125">Par conséquent, même si le pool 2010 de Lync prend en charge la résolution 720p, le système de salle Skype ne sera pas en mesure de profiter de la résolution 720p tant que la stratégie de l’organisateur ne la prend pas en charge.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="bd5e7-p105">Les clients Lync 2013 détectent la présence de LRS dans la salle de réunion, et désactivent leur micro afin d’éviter tout écho dans la salle de réunion physique. Cette fonctionnalité ne fonctionne pas pour des réunions hébergées sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="bd5e7-128">Les performances du partage de bureau sont limitées pour les réunions hébergées sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="bd5e7-129">Les utilisateurs ne seront pas en mesure de rejoindre des réunions privées hébergées sur Lync 2010 avec le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="bd5e7-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

