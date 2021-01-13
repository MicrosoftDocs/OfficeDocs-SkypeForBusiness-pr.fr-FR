---
title: Attribution d’une étendue de stratégie d’emplacement dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825524"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="cb6b5-103">Attribution d’une étendue de stratégie d’emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cb6b5-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="cb6b5-104">Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cb6b5-105">Comme avec d’autres stratégies Skype Entreprise Server, les stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="cb6b5-106">Toutefois, l’étendue des stratégies d’emplacement au niveau de l’utilisateur se comporte un peu différemment des autres stratégies Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="cb6b5-107">Non seulement les stratégies d’emplacement par utilisateur peuvent être appliquées aux objets de point de terminaison (tels que les objets contact Utilisateurs et Téléphone de partie commune), mais elles peuvent également être appliquées aux sites réseau Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="cb6b5-108">Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale).</span><span class="sxs-lookup"><span data-stu-id="cb6b5-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="cb6b5-109">Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="cb6b5-110">Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="cb6b5-111">Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb6b5-112">La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="cb6b5-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

