---
title: Remarques sur la migration de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lisez cette rubrique pour en savoir plus sur le déploiement de système d’espace Skype dans un environnement comportant plusieurs versions de Skype pour Business Server et Lync Server.
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="305f8-103">Remarques sur la migration de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="305f8-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="305f8-104">Lisez cette rubrique pour en savoir plus sur le déploiement de système d’espace Skype dans un environnement comportant plusieurs versions de Skype pour Business Server et Lync Server.</span><span class="sxs-lookup"><span data-stu-id="305f8-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="305f8-105">Remarques sur la migration</span><span class="sxs-lookup"><span data-stu-id="305f8-105">Migration considerations</span></span>

<span data-ttu-id="305f8-106">Cette section fournit des conseils si vous déployez un système de salle de Skype dans un environnement multi-pool qui inclut des versions différentes de Skype pour Business Server, Lync Server ou Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="305f8-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="305f8-107">Le composant réplicateur d’utilisateurs dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données SQL Server du serveur principal Lync Server.</span><span class="sxs-lookup"><span data-stu-id="305f8-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="305f8-108">Le réplicateur d’utilisateurs uniquement dans Lync Server 2013 est conscient des objets système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="305f8-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="305f8-109">Le réplicateur d’utilisateurs dans les versions précédentes de Lync Server et Office Communications Server ne détecte pas les attributs Active Directory qui désignent des objets LRS, et n’en avait, par conséquent, pas connaissance.</span><span class="sxs-lookup"><span data-stu-id="305f8-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="305f8-110">Si un compte système local de Skype essaie de se connecter à Lync et effectue la découverte automatique basée sur l’enregistrement SRV ou rechercher enregistrement A DNS, et si ces comptes pointent vers une version antérieure de Lync Server ou Office Communications Server, LRS recevront une réponse de 404 introuvable à partir de  le pool d’ancienne génération.</span><span class="sxs-lookup"><span data-stu-id="305f8-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="305f8-111">Le pool hérité ne pourront pas rediriger le système de salle Skype pour son pool de domicile de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="305f8-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="305f8-112">Vous pouvez résoudre ce problème avec les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="305f8-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="305f8-113">Pointez votre découverte automatique d’enregistrement SRV (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="305f8-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="305f8-114">Si la première option n’est pas possible, vous devez manuellement configurer LRS et fournir l’adresse de pool Lync Server 2013 en le configurant directement dans l’application de la console système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="305f8-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="305f8-115">Si le système de salle de Skype est déployé en dehors du réseau d’entreprise et de Lync Edge Server a été déployé et configuré pour pointer vers un pool hérité ou d’un directeur, un site de serveur de transport Edge secondaire est requis, qui pointe vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="305f8-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="305f8-116">Reportez-vous à la documentation de déploiement des serveurs Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire.</span><span class="sxs-lookup"><span data-stu-id="305f8-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="305f8-117">Salle de Skype l’interopérabilité du système avec un Pool de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="305f8-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="305f8-118">Lors de la migration, si un utilisateur qui est hébergé sur un pool Lync Server 2010 permet de planifier une réunion et invite le compte système local de Skype, le client Skype espace système sera ont des fonctionnalités limitées lors de la participation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="305f8-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="305f8-119">Lorsque le client Skype espace système joint un appel de conférence planifié qui a été organisé par un utilisateur hébergé dans Lync Server 2010, Skype espace système a les limitations suivantes en réunion :</span><span class="sxs-lookup"><span data-stu-id="305f8-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="305f8-120">Système de chambre de Skype ne peut pas afficher la Galerie vidéo multivue.</span><span class="sxs-lookup"><span data-stu-id="305f8-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="305f8-121">Si le client du système de salle de Skype est le présentateur, il ne peut pas appliquer verrouillage vidéo sur les participants.</span><span class="sxs-lookup"><span data-stu-id="305f8-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="305f8-122">Système de salle Skype ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence Lync Server 2013, autorise les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="305f8-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="305f8-123">Lync Server 2010 ne prend pas en charge la résolution de 1080p.</span><span class="sxs-lookup"><span data-stu-id="305f8-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="305f8-124">Système de chambre de Skype est toujours limitée par la stratégie de conférence de l’organisateur pour la résolution vidéo.</span><span class="sxs-lookup"><span data-stu-id="305f8-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="305f8-125">Par conséquent, même si le pool Lync 2010 prend en charge la résolution 720p, Skype espace système pas pourra bénéficier de la résolution 720p tant qu’il ne gère pas la stratégie de l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="305f8-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="305f8-p105">Les clients Lync 2013 détectent la présence de LRS dans la salle de réunion, et désactivent leur micro afin d’éviter tout écho dans la salle de réunion physique. Cette fonctionnalité ne fonctionne pas pour des réunions hébergées sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="305f8-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="305f8-128">Les performances du partage de bureau sont limitées pour les réunions hébergées sur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="305f8-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="305f8-129">Les utilisateurs ne pourront pas joindre (limitées) les conférences privées qui sont hébergés dans Lync 2010 avec système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="305f8-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

