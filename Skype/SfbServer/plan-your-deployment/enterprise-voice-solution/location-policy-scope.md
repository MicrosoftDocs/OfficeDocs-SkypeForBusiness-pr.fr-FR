---
title: Affectation de l’étendue de la stratégie d’emplacement dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planification de stratégies d’emplacement pour un déploiement E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802754"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="1f857-103">Affectation de l’étendue de la stratégie d’emplacement dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1f857-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="1f857-104">Planification de stratégies d’emplacement pour un déploiement E9-1-1 dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="1f857-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="1f857-105">Comme avec d’autres stratégies serveur Skype entreprise, des stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1f857-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="1f857-106">Toutefois, l’étendue des stratégies d’emplacement utilisateur se comporte de manière légèrement différente de celle des autres stratégies serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1f857-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="1f857-107">Les stratégies d’emplacement par utilisateur ne peuvent pas seulement être appliquées aux objets de point de terminaison (par exemple, les utilisateurs et les objets de contact de zone commune), ils peuvent également être appliqués aux sites du réseau Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1f857-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="1f857-108">Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale).</span><span class="sxs-lookup"><span data-stu-id="1f857-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="1f857-109">Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="1f857-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="1f857-110">Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1f857-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="1f857-111">Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="1f857-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f857-112">La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="1f857-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

