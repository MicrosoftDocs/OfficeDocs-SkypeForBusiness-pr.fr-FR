---
title: Mise en service de comptes Exchange et Skype dans Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: Consultez ces rubriques pour découvrir comment mettre en service des comptes Exchange et Skype pour Skype Room System.
ms.openlocfilehash: 685909d8a698e6520798d017156514a371c883f1
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768467"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="d3e5b-103">Mise en service de comptes Exchange et Skype dans Skype Room System</span><span class="sxs-lookup"><span data-stu-id="d3e5b-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="d3e5b-104">Consultez ces rubriques pour découvrir comment mettre en service des comptes Exchange et Skype pour Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="d3e5b-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="d3e5b-105">Microsoft teams Room est un produit différent présentant différentes dépendances et procédures de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d3e5b-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="d3e5b-106">Pour plus d’informations sur les salles de Microsoft Teams, voir la [vue d’ensemble du déploiement](room-systems-v2.md)de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3e5b-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3e5b-107">La mise en service des comptes système de salle Skype dépend du type de topologie dont dispose votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d3e5b-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="d3e5b-108">Pour en savoir plus sur les topologies Active Directory, consultez [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3e5b-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="d3e5b-109">Approvisionnement de Skype Room System échange &amp; de comptes Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="d3e5b-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="d3e5b-110">Les rubriques suivantes décrivent comment mettre en service et gérer des comptes Exchange et Skype Entreprise dans Skype Room System pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d3e5b-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="d3e5b-111">Déploiements locaux d’une forêt unique</span><span class="sxs-lookup"><span data-stu-id="d3e5b-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="d3e5b-112">Déploiements locaux de plusieurs forêts</span><span class="sxs-lookup"><span data-stu-id="d3e5b-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="d3e5b-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="d3e5b-113">Office 365</span></span>
    
- <span data-ttu-id="d3e5b-114">Déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="d3e5b-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="d3e5b-115">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d3e5b-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="d3e5b-116">Gestion des comptes Skype Room System</span><span class="sxs-lookup"><span data-stu-id="d3e5b-116">Manage Skype Room System accounts</span></span>
    

