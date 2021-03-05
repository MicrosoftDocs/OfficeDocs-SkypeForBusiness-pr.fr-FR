---
title: Considérations relatives au mode Teams uniquement
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Les administrateurs peuvent en savoir plus sur la préparation d’une mise à niveau vers le mode Microsoft Teams uniquement dans le Centre d’administration Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460994"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="0086f-103">Considérations relatives au mode Teams uniquement</span><span class="sxs-lookup"><span data-stu-id="0086f-103">Teams Only mode considerations</span></span>

<span data-ttu-id="0086f-104">Les administrateurs des organisations Microsoft 365 ou Office 365 peuvent mettre à niveau des utilisateurs individuels ou du client entier vers le mode Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="0086f-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

<span data-ttu-id="0086f-105">La mise à niveau vers le mode Teams uniquement offre aux utilisateurs tous les avantages de Microsoft Teams, le hub pour le travail d’équipe dans Microsoft 365 ou Office 365, via une expérience client unique.</span><span class="sxs-lookup"><span data-stu-id="0086f-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="0086f-106">Les utilisateurs en mode Teams uniquement reçoivent tous les appels et conversations dans Teams, que l’expéditeur utilise Skype Entreprise ou Teams, et bénéficient de la prise en charge d’interop et de fédération.</span><span class="sxs-lookup"><span data-stu-id="0086f-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="0086f-107">Bien que des milliers de clients soient passé à la mise à niveau vers Microsoft Teams, certains éléments peuvent influencer la chronologie de mise à niveau et l’expérience utilisateur de votre organisation en cours de route.</span><span class="sxs-lookup"><span data-stu-id="0086f-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="0086f-108">Pour bénéficier de la meilleure expérience utilisateur, vérifiez que Teams répond à vos besoins en matière de collaboration et de communication, assurez-vous que votre réseau est prêt à prendre en charge Teams et implémentez votre plan de préparation des utilisateurs avant de les mettre à niveau vers Teams.</span><span class="sxs-lookup"><span data-stu-id="0086f-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0086f-109">Si vous débutez votre planification de la mise à niveau, n’oubliez pas de consulter notre guide de mise à niveau [de Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="0086f-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="0086f-110">**Considérations en coexistence**: Les organisations qui utilisent déjà Skype Entreprise Online et/ou Skype Entreprise Server peuvent présenter Teams à leur environnement à un rythme qui répond à leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="0086f-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="0086f-111">Les organisations peuvent déployer Teams de façon incrémentielle auprès d’un ensemble d’utilisateurs souhaité, et les utilisateurs qui utilisent Teams peuvent communiquer avec les utilisateurs qui utilisent Skype Entreprise et inversement.</span><span class="sxs-lookup"><span data-stu-id="0086f-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="0086f-112">Pour gérer cette expérience, les administrateurs utilisent les modes de coexistence qui définissent l’expérience client des utilisateurs finaux, le comportement de routage des conversations et appels entrants, et déterminent si les nouvelles réunions sont programmées dans Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0086f-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="0086f-113">Les utilisateurs peuvent se fédérer avec des utilisateurs d’autres organisations si l’utilisateur est mis à niveau vers **Teams uniquement**; Toutefois, la meilleure expérience est fournie lorsque les deux utilisateurs utilisent Teams.</span><span class="sxs-lookup"><span data-stu-id="0086f-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="0086f-114">Les utilisateurs qui ont été mis à niveau vers Teams uniquement peuvent toujours participer à des réunions Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0086f-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0086f-115">Pour plus d’informations sur la coexistence, reportez-vous à Comprendre la coexistence et l’interopérabilité avec Microsoft Teams et [Skype Entreprise.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="0086f-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="0086f-116">Pour plus d’informations sur Teams et Skype (grand public), consultez [Teams et l’interopérabilité de Skype.](teams-skype-interop.md)</span><span class="sxs-lookup"><span data-stu-id="0086f-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="0086f-117">**Considérations spécifiques** à l’utilisateur : Certains scénarios d’utilisateurs évoluent toujours et les administrateurs peuvent décider de différer temporairement la mise à niveau de certains utilisateurs lors de la mise à niveau d’autres utilisateurs dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="0086f-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="0086f-118">En particulier, nous travaillons toujours sur la recherche de scénarios pour les utilisateurs dont l’appareil principal est VDI.</span><span class="sxs-lookup"><span data-stu-id="0086f-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="0086f-119">Pour les annonces de site, surveillez la feuille [de route Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="0086f-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="0086f-120">Avant de passer en mode Teams uniquement, vous devez remplacer ou mettre à jour les appareils qui ne supportent pas Teams.</span><span class="sxs-lookup"><span data-stu-id="0086f-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0086f-121">**N’oubliez** pas que le déplacement vers Teams est bien plus qu’une migration technique.</span><span class="sxs-lookup"><span data-stu-id="0086f-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="0086f-122">Une mise à niveau réussie évalue la préparation technique et la préparation des utilisateurs finux.</span><span class="sxs-lookup"><span data-stu-id="0086f-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="0086f-123">Pour plus d’informations [](upgrade-framework.md) sur la planification de l’implémentation de votre mise à niveau vers Teams, voir nos conseils de mise à niveau de Skype Entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="0086f-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
