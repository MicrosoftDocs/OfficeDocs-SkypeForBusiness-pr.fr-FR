---
title: Étude de cas Teams voix Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786020"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="144aa-103">Étude de cas Contoso : plan de mise à niveau de Teams</span><span class="sxs-lookup"><span data-stu-id="144aa-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="144aa-104">En souhaitant migrer Skype Entreprise vers Teams, Contoso souhaitait offrir une expérience de transition facile aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="144aa-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="144aa-105">Au lieu de basculer tout le monde vers Teams en même temps, ils ont décidé de configurer la connectivité hybride et d’utiliser la méthode des capacités superposées pour déplacer les utilisateurs vers Teams.</span><span class="sxs-lookup"><span data-stu-id="144aa-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="144aa-106">Cela permettait aux utilisateurs de Teams et de Skype Entreprise sur site de partager les informations de présence et de communication.</span><span class="sxs-lookup"><span data-stu-id="144aa-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="144aa-107">Lorsque les utilisateurs ont entré le pilote du système téléphonique, ils ont été déplacés en mode Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="144aa-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="144aa-108">Pour comprendre les concepts fondamentaux de la mise à niveau, des méthodes et des modes, Contoso lit les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="144aa-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="144aa-109">Prise en main de votre mise à niveau de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="144aa-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="144aa-110">Mise à niveau de Skype Entreprise vers Teams</span><span class="sxs-lookup"><span data-stu-id="144aa-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="144aa-111">Conseils sur la migration et l’interopérabilité</span><span class="sxs-lookup"><span data-stu-id="144aa-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="144aa-112">Contoso a également participé à la session Ignite 2019 concevant votre chemin de [Skype Entreprise à Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="144aa-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="144aa-113">Contoso a appris les sujets :</span><span class="sxs-lookup"><span data-stu-id="144aa-113">Contoso learned about:</span></span>

- <span data-ttu-id="144aa-114">Concepts fondamentaux tels que l’interopérabilité, la fédération et le comportement de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="144aa-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="144aa-115">Modes de coexistence et gestion basés sur TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="144aa-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="144aa-116">Expérience utilisateur final pour :</span><span class="sxs-lookup"><span data-stu-id="144aa-116">End user experience for:</span></span> 

  - <span data-ttu-id="144aa-117">Conversation et appel</span><span class="sxs-lookup"><span data-stu-id="144aa-117">Chat and Calling</span></span> 

  - <span data-ttu-id="144aa-118">Planification de réunions</span><span class="sxs-lookup"><span data-stu-id="144aa-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="144aa-119">Disponibilité de la fonctionnalité de collaboration dans les clients Teams</span><span class="sxs-lookup"><span data-stu-id="144aa-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="144aa-120">Pour planifier et configurer la connectivité hybride, la première étape du déplacement de leur [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) environnement local [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) vers le cloud, Contoso lit Planifier la connectivité hybride et Configurer la connectivité hybride pour comprendre comment :</span><span class="sxs-lookup"><span data-stu-id="144aa-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="144aa-121">Configurez leur service d’environnement local de manière à ce qu’il se fédérera avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="144aa-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="144aa-122">Configurer leur environnement local pour faire confiance à Office 365 et activer l’espace d’adressare SIP partagé avec Office 365</span><span class="sxs-lookup"><span data-stu-id="144aa-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="144aa-123">Activez l’espace d’adresse SIP partagé dans son client Office 365.</span><span class="sxs-lookup"><span data-stu-id="144aa-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="144aa-124">Utilisez le mode Îles pendant le pilote technique.</span><span class="sxs-lookup"><span data-stu-id="144aa-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="144aa-125">Basculez les utilisateurs en mode TeamsOnly une fois que l’utilisateur est activé pour Phone System.</span><span class="sxs-lookup"><span data-stu-id="144aa-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="144aa-126">Le mode TeamsOnly est requis pour le plan d’appels et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="144aa-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
