---
title: Activation des utilisateurs pour E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires pour la stratégie de l’emplacement d’un déploiement E9-1-1 dans Skype de Voix Entreprise Server Business, y compris les utilisateurs à activer et à la prise en charge des utilisateurs itinérants.
ms.openlocfilehash: 966344f2cfc7a964c9dda0898b4ba99c42e03193
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server-2015"></a><span data-ttu-id="0e4d9-103">Activation des utilisateurs pour E9-1-1 dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e4d9-103">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e4d9-104">Décisions nécessaires pour la stratégie de l’emplacement d’un déploiement E9-1-1 dans Skype de Voix Entreprise Server Business, y compris les utilisateurs à activer et à la prise en charge des utilisateurs itinérants.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="0e4d9-105">Lors de l’inscription du client, Skype pour Business Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs disposant d’une Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="0e4d9-106">Cette stratégie contient les paramètres qui définissent le mode d’implémentation de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="0e4d9-107">Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation et de secours ou non un utilisateur est tenu d’entrer manuellement un emplacement si le service d’informations d’emplacement n’est pas automatiquement à en fournir une.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="0e4d9-108">Pour une définition complète d’une stratégie d’emplacement, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e4d9-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server 2015](location-policies.md).</span></span>
  
<span data-ttu-id="0e4d9-109">Skype pour Business Server peut affecter une stratégie emplacement aux clients basés sur un sous-réseau ou à des utilisateurs basées sur global, par site, ou la stratégie de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="0e4d9-110">Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="0e4d9-111">**Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**</span><span class="sxs-lookup"><span data-stu-id="0e4d9-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="0e4d9-112">Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="0e4d9-113">Toutefois, par l’affectation d’une stratégie de l’emplacement d’un Skype pour un site de réseau de serveur d’entreprise, puis ajouter des sous-réseaux au site, vous pouvez limiter la prise en charge de E9-1-1 pour les emplacements sélectionnés au sein de l’entreprise et spécifier le comportement de routage E9-1-1 sur une base site par site.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="0e4d9-114">**Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**</span><span class="sxs-lookup"><span data-stu-id="0e4d9-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="0e4d9-115">Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="0e4d9-116">**Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="0e4d9-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="0e4d9-117">Si les utilisateurs sont affectés à une commande globale, de site, ou de la stratégie d’emplacement par utilisateur, ils peuvent être requis pour entrer manuellement un emplacement dans le client si le client n’est pas situé dans un sous-réseau défini ou si aucun emplacement n’a été trouvée par le service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="0e4d9-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="0e4d9-118">Pour plus d’informations, consultez [définir l’expérience utilisateur pour l’acquisition d’un emplacement dans Skype pour Business Server 2015 manuellement](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="0e4d9-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server 2015](manually-acquiring-a-location.md).</span></span>
    

