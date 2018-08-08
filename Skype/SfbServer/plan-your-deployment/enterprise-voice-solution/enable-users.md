---
title: Activer les utilisateurs pour E9-1-1 dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires pour la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice, y compris les utilisateurs à activer et comment prendre en charge des utilisateurs itinérants.
ms.openlocfilehash: c5dbbc7904313ffc1706615f2aec506032e20074
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997193"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="ae511-103">Activer les utilisateurs pour E9-1-1 dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="ae511-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="ae511-104">Décisions nécessaires pour la stratégie d’emplacement pour un déploiement E9-1-1 dans Skype pour Business Server Enterprise Voice, y compris les utilisateurs à activer et comment prendre en charge des utilisateurs itinérants.</span><span class="sxs-lookup"><span data-stu-id="ae511-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="ae511-105">Lors de l’inscription du client, Skype pour Business Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ae511-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="ae511-106">Cette stratégie contient les paramètres qui définissent le mode d’implémentation E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ae511-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="ae511-107">Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation et si un utilisateur est invité à entrer manuellement un emplacement si le service informations d’emplacement ne sont pas automatiquement en fournir un.</span><span class="sxs-lookup"><span data-stu-id="ae511-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="ae511-108">Pour une définition complète d’une stratégie d’emplacement, voir [planifier des stratégies d’emplacement pour Skype pour Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ae511-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="ae511-109">Skype pour Business Server peut affecter une stratégie d’emplacement aux clients en fonction de sous-réseau ou aux utilisateurs selon un global par site ou stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ae511-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="ae511-110">Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="ae511-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="ae511-111">**Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**</span><span class="sxs-lookup"><span data-stu-id="ae511-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="ae511-112">Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale.</span><span class="sxs-lookup"><span data-stu-id="ae511-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="ae511-113">Toutefois, par l’affectation d’une stratégie d’emplacement à un Skype pour le site de réseau Business Server, puis ajouter des sous-réseaux au site, vous pouvez limiter la prise en charge E9-1-1 pour les emplacements sélectionnés au sein de l’entreprise et spécifier le comportement du routage E9-1-1 sur site par site.</span><span class="sxs-lookup"><span data-stu-id="ae511-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="ae511-114">**Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**</span><span class="sxs-lookup"><span data-stu-id="ae511-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="ae511-115">Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.</span><span class="sxs-lookup"><span data-stu-id="ae511-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="ae511-116">**Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="ae511-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="ae511-117">Si les utilisateurs sont affectés global, site, ou de la stratégie d’emplacement par utilisateur, ils peuvent être requis pour entrer manuellement un emplacement dans le client, si le client n’est pas situé dans un sous-réseau défini ou si aucun emplacement n’a été trouvée par le service informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ae511-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="ae511-118">Pour plus d’informations, voir [définir l’expérience utilisateur pour acquérir manuellement un emplacement dans Skype pour Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="ae511-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

