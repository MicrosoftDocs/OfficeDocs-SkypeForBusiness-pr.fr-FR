---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786020"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="5f228-103">Étude de cas contoso : plan de mise à niveau des équipes</span><span class="sxs-lookup"><span data-stu-id="5f228-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="5f228-104">Dans la décision de migrer de Skype entreprise vers Teams, contoso voulait offrir une interface de transition facile pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="5f228-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="5f228-105">Au lieu de basculer tous les membres vers teams en même temps, ils ont décidé de configurer une connectivité hybride et de recourir à la méthode de superposition pour déplacer des utilisateurs vers Teams.</span><span class="sxs-lookup"><span data-stu-id="5f228-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="5f228-106">Cela permettait aux utilisateurs de Microsoft teams et de Skype entreprise local de partager leur présence et de communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="5f228-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="5f228-107">Lorsque les utilisateurs ont entré le pilote pour le système téléphonique, ils ont été déplacés vers le mode équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="5f228-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="5f228-108">Pour comprendre les concepts fondamentaux liés à la mise à niveau, aux méthodes et aux modes, Contoso a lu les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="5f228-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="5f228-109">Prise en main de votre mise à niveau de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f228-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="5f228-110">Mise à niveau de Skype Entreprise vers Teams</span><span class="sxs-lookup"><span data-stu-id="5f228-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="5f228-111">Recommandations en matière de migration et d’interopérabilité</span><span class="sxs-lookup"><span data-stu-id="5f228-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="5f228-112">Contoso a également participé à la session d’enflammer 2019 [qui concevait votre chemin entre Skype entreprise et teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="5f228-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="5f228-113">Contoso a appris ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="5f228-113">Contoso learned about:</span></span>

- <span data-ttu-id="5f228-114">Concepts de base, tels que le comportement d’interopérabilité, de Fédération et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="5f228-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="5f228-115">Modes et gestion de coexistence basés sur TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="5f228-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="5f228-116">Utilisation de l’utilisateur final pour :</span><span class="sxs-lookup"><span data-stu-id="5f228-116">End user experience for:</span></span> 

  - <span data-ttu-id="5f228-117">Discussions et appels</span><span class="sxs-lookup"><span data-stu-id="5f228-117">Chat and Calling</span></span> 

  - <span data-ttu-id="5f228-118">Planification de réunions</span><span class="sxs-lookup"><span data-stu-id="5f228-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="5f228-119">Disponibilité des fonctionnalités de collaboration dans les clients teams</span><span class="sxs-lookup"><span data-stu-id="5f228-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="5f228-120">Pour planifier et configurer une connectivité hybride, vous devez commencer par déplacer son environnement local vers le Cloud, contoso lire le [plan de connexion hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) et [configurer une connectivité hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) pour comprendre comment :</span><span class="sxs-lookup"><span data-stu-id="5f228-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="5f228-121">Configurez son service d’environnement local pour qu’il se fédérer avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f228-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="5f228-122">Configurer son environnement local pour faire confiance à Office 365 et activer l’espace d’adressage SIP partagé avec Office 365</span><span class="sxs-lookup"><span data-stu-id="5f228-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="5f228-123">Activez l’espace d’adressage SIP partagé dans le client Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f228-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="5f228-124">Utiliser le mode insulaire lors du pilotage technique.</span><span class="sxs-lookup"><span data-stu-id="5f228-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="5f228-125">Basculer les utilisateurs vers le mode TeamsOnly une fois l’utilisateur activé pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="5f228-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="5f228-126">Le mode TeamsOnly est requis pour le plan d’appel et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="5f228-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
