---
title: Configurer le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer le routage direct de Microsoft Phone System pour connecter votre infrastructure téléphonique locale à Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701292"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="a2d73-103">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="a2d73-103">Configure Direct Routing</span></span>

<span data-ttu-id="a2d73-104">Le routage direct de Microsoft Phone System vous permet de connecter votre infrastructure téléphonique locale à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2d73-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="a2d73-105">Cet article répertorie les étapes de haut niveau requises pour connecter un contrôleur de session en ligne local pris en charge au routage direct par un contrôleur de session (SBC) et comment configurer les utilisateurs de Teams de façon à ce qu’ils utilisent le routage direct pour se connecter au réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="a2d73-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a2d73-106">Cet article est associé à des articles pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="a2d73-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="a2d73-107">Pour savoir si le routage direct est la solution adaptée à votre organisation, voir [Routage direct du](direct-routing-landing-page.md)système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="a2d73-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="a2d73-108">Pour plus d’informations sur les conditions préalables et la planification de votre déploiement, voir [Plan de routage direct.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="a2d73-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="a2d73-109">Vous pouvez également regarder la session suivante pour en savoir plus sur les avantages du routage direct, comment le planifier et comment le déployer : Routage direct [dans Microsoft Teams.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="a2d73-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="a2d73-110">Pour suivre les étapes expliquées dans cet article, les administrateurs doivent être familiarisés avec les cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2d73-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="a2d73-111">Pour plus d’informations sur l’utilisation de PowerShell, voir [Configurer votre ordinateur pour Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a2d73-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="a2d73-112">Avant d’effectuer la procédure de ces articles, Microsoft vous recommande de confirmer que votre SBC a déjà été configuré comme recommandé par votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="a2d73-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="a2d73-113">Documentation sur le déploiement de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a2d73-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a2d73-114">Documentation sur le déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="a2d73-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a2d73-115">Documentation de déploiement de Communications du ruban</span><span class="sxs-lookup"><span data-stu-id="a2d73-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a2d73-116">Documentation sur le déploiement des systèmes TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="a2d73-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="a2d73-117">Documentation sur le déploiement de metaswitch</span><span class="sxs-lookup"><span data-stu-id="a2d73-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="a2d73-118">Pour obtenir la liste complète des SBCs pris en charge, consultez la liste des contrôleurs de session [certifiés pour le routage direct.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="a2d73-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="a2d73-119">Pour configurer Microsoft Phone System et permettre aux utilisateurs d’utiliser le routage direct, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a2d73-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="a2d73-120">**Étape 1.**</span><span class="sxs-lookup"><span data-stu-id="a2d73-120">**Step 1.**</span></span> [<span data-ttu-id="a2d73-121">Connecter le SBC à Microsoft Phone System et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="a2d73-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="a2d73-122">**Étape 2.**</span><span class="sxs-lookup"><span data-stu-id="a2d73-122">**Step 2.**</span></span> [<span data-ttu-id="a2d73-123">Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="a2d73-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="a2d73-124">**Étape 3.**</span><span class="sxs-lookup"><span data-stu-id="a2d73-124">**Step 3.**</span></span> [<span data-ttu-id="a2d73-125">Configurer le routage vocal</span><span class="sxs-lookup"><span data-stu-id="a2d73-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="a2d73-126">**Étape 4.**</span><span class="sxs-lookup"><span data-stu-id="a2d73-126">**Step 4.**</span></span> [<span data-ttu-id="a2d73-127">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="a2d73-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="a2d73-128">Si vous configurez un SBC pour plusieurs locataires, vous pouvez également lire Configurer un SBC pour [plusieurs locataires.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="a2d73-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a2d73-129">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="a2d73-129">Related topics</span></span>

[<span data-ttu-id="a2d73-130">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="a2d73-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="a2d73-131">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="a2d73-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

