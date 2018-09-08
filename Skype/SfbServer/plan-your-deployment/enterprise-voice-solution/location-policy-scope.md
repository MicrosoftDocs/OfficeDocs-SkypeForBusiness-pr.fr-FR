---
title: Assigner l’étendue de stratégie d’emplacement dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 28759d88be1586149b0dd482d934c5bbc89a1853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881882"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="fba8f-103">Assigner l’étendue de stratégie d’emplacement dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="fba8f-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="fba8f-104">Planification des stratégies d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fba8f-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fba8f-105">Avec les autres Skype pour les stratégies de serveur d’entreprise, les stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : globale, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fba8f-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="fba8f-106">Toutefois, l’étendue de stratégies d’emplacement de niveau utilisateur comporte un bit différemment avec d’autres Skype pour les stratégies de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="fba8f-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="fba8f-107">Non seulement les stratégies d’emplacement par utilisateur peuvent être appliqués aux objets de point de terminaison (tels que les utilisateurs et les objets contacts téléphone en zone commune), ils peuvent également s’appliquer à Skype pour les sites de réseau Business Server.</span><span class="sxs-lookup"><span data-stu-id="fba8f-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="fba8f-108">Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale).</span><span class="sxs-lookup"><span data-stu-id="fba8f-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="fba8f-109">Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="fba8f-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="fba8f-110">Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fba8f-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="fba8f-111">Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="fba8f-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fba8f-112">La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="fba8f-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

