---
title: Guide de démarrage rapide - Configuration des forfaits d’appels
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guide de démarrage rapide pour la configuration des plans d’appel dans Microsoft Teams afin de rendre un ensemble d’utilisateurs opérationnel.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799764"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="6a8a1-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="6a8a1-104">Ce guide vous aide à rendre un ensemble d’utilisateurs opérationnel afin qu’ils peuvent découvrir les forfaits d’appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="6a8a1-105">Lire l’annonce des plans d’appel dans Teams du 12 décembre 2017 : [Intelligent Communications passe](https://aka.ms/ipyqus) à l’étape suivante avec les appels dans Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="6a8a1-106">Nous vous recommandons, en parallèle de ce guide de démarrage rapide, de lire Phone System avec les [forfaits](calling-plan-landing-page.md) d’appels et [FastTrack](https://aka.ms/cloudvoice) pour planifier et conduire un déploiement réussi.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="6a8a1-107">En ajoutant des forfaits d’appels, une fonctionnalité de Microsoft 365 et Office 365 optimisée par Skype Entreprise, vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques vers ou depuis des lignes fixes et des téléphones mobiles via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Capture d’écran montrant la page Contacts dans Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="6a8a1-109">Conditions préalables à l’activation de **l’onglet** Appels dans Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="6a8a1-110">Pour activer l’onglet **Appels** dans Teams, les utilisateurs doivent avoir des appels en tête-à-tête activés dans Teams et utiliser un client Teams qui prend en charge les appels 1:1 Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="6a8a1-111">Pour découvrir comment gérer les appels en tête-à-tête dans Teams, [lisez Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="6a8a1-112">Pour connaître les clients qui supportent les appels, consultez les [limites et les spécifications de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="6a8a1-113">Pour l’instant, la messagerie vocale ne sera pas disponible dans l’onglet Appels, sauf si l’utilisateur est activé pour les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="6a8a1-114">Conditions préalables à l’activation **du pavé de numérotation** dans Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="6a8a1-115">Pour activer **l’onglet** Pavé de numérotation dans Teams et permettre à vos utilisateurs d’effectuer et de recevoir des appels PSTN, vous devez mettre en service les utilisateurs pour les forfaits téléphoniques et les plans d’appel.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="6a8a1-116">Pour découvrir comment configurer des forfaits d’appels, lisez [Configurer les forfaits d’appels.](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="6a8a1-117">De plus, pour les utilisateurs de Teams uniquement, vous devez vous assurer que la stratégie « Autoriser les appels privés » est activée dans la stratégie d’appel teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="6a8a1-118">Pour [plus d’informations, voir Gérer Teams lors de](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) la transition vers le nouveau Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="6a8a1-119">Vous pouvez également utiliser le routage direct pour permettre à vos utilisateurs d’effectuer et de recevoir des appels RSTN.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="6a8a1-120">Pour découvrir comment configurer le routage direct, lisez [Configurer le routage direct.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="6a8a1-121">Utilisation de TeamsUpgradePolicy pour contrôler la place des appels</span><span class="sxs-lookup"><span data-stu-id="6a8a1-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="6a8a1-122">Pour contrôler l’accès aux appels entrants (et aux conversations) dans Teams ou Skype Entreprise, les administrateurs utilisent TeamsUpgradePolicy, en utilisant le Centre d’administration [Microsoft Teams](https://aka.ms/teamsadmincenter) ou une session de Windows PowerShell distante avec les cmdlets [Skype](https://docs.microsoft.com/powershell/module/skype) Entreprise.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="6a8a1-123">La configuration par défaut de TeamsUpgradePolicy est le mode Islands, qui est conçu pour garantir que les flux de travail d’entreprise existants ne soient pas interrompus pendant un déploiement Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="6a8a1-124">Par défaut, les appels VoIP, PSTN et fédérés vers vos utilisateurs continueront d’être acheminés vers Skype Entreprise jusqu’à ce que vous actualisiez la stratégie pour activer les appels entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="6a8a1-125">Lorsque les destinataires sont en mode îles :</span><span class="sxs-lookup"><span data-stu-id="6a8a1-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="6a8a1-126">Les appels VOIP entrants provenant de Skype Entreprise arrivent toujours dans le client Skype Entreprise du destinataire.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="6a8a1-127">Les appels VOIP entrants en provenance de Teams arrivent dans Teams, si l’expéditeur et le destinataire *se trouvent dans le même client.*</span><span class="sxs-lookup"><span data-stu-id="6a8a1-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="6a8a1-128">Les appels VOIP fédérés entrants (quel que soit l’origine du client) et les appels PSTN arrivent toujours dans le client Skype Entreprise du destinataire.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="6a8a1-129">Pour vous assurer que les appels VOIP et PSTN entrants arrivent toujours dans le client Teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (c’est-à-dire, affectez-lui l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="6a8a1-130">Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, consultez les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec [Skype Entreprise.](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="6a8a1-131">**NOTES**</span><span class="sxs-lookup"><span data-stu-id="6a8a1-131">**NOTES**</span></span>
 - <span data-ttu-id="6a8a1-132">Les téléphones IP Skype Entreprise recevront des appels, même si l’utilisateur est en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="6a8a1-133">Les utilisateurs qui ont été mis en service avec des licences Système téléphonique et Forfaits d’appels pour une utilisation avec Skype Entreprise Online (par exemple, une valeur de OnlineVoiceRoutingPolicy) verront l’onglet Appels activé dans Teams et pourront passer des appels RSTN sortants de Teams sans que les administrateurs n’ont à prendre d’action administrative.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="6a8a1-134">Comment configurer les utilisateurs pour recevoir tous les appels VOIP et PSTN entrants dans Teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="6a8a1-135">Pour vous assurer que les utilisateurs reçoivent tous les appels VOIP et PSTN entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le Centre d’administration Microsoft Teams, ou utilisez la session de Windows PowerShell distante Skype Entreprise pour mettre à jour TeamsUpgradePolicy comme suit :</span><span class="sxs-lookup"><span data-stu-id="6a8a1-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="6a8a1-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a8a1-136">See also</span></span>
[<span data-ttu-id="6a8a1-137">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="6a8a1-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="6a8a1-138">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="6a8a1-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="6a8a1-139">Système téléphonique avec Forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="6a8a1-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="6a8a1-140">Référence de l’cmdlet Skype Entreprise PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a8a1-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

