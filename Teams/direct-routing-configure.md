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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Apprenez à configurer le routage direct du système Microsoft Phone pour connecter votre infrastructure de téléphonie locale à Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1c19bfcd4c220ff6b6c53d8731149eaa8b6b4b1
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031770"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="01317-103">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="01317-103">Configure Direct Routing</span></span>

<span data-ttu-id="01317-104">Le routage direct du système Microsoft Phone vous permet de connecter votre infrastructure de téléphonie locale à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01317-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="01317-105">Cet article répertorie les étapes principales requises pour connecter un contrôleur de bordure de session locale pris en charge (SBC) au routage direct et configurer les utilisateurs de teams pour se connecter au réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="01317-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="01317-106">Cet article fournit des liens vers les articles associés pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="01317-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="01317-107">Pour savoir si le routage direct est la solution adaptée à votre organisation, reportez-vous à la section [routage direct du système téléphonique](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="01317-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="01317-108">Pour plus d’informations sur les conditions préalables et la planification de votre déploiement, voir [planifier le routage direct](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="01317-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="01317-109">Vous pouvez également regarder la session suivante pour en savoir plus sur les avantages du routage direct, la planification et la façon de le déployer : le [routage directe dans Microsoft teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="01317-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="01317-110">Pour suivre les étapes décrites dans cet article, les administrateurs doivent vous familiariser avec les applets de cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01317-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="01317-111">Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="01317-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="01317-112">Avant d’effectuer les étapes décrites dans les articles suivants, Microsoft vous recommande de vérifier que votre SBC a déjà été configuré conformément aux recommandations de votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="01317-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="01317-113">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="01317-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="01317-114">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="01317-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="01317-115">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="01317-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="01317-116">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="01317-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="01317-117">Documentation sur le déploiement de switch</span><span class="sxs-lookup"><span data-stu-id="01317-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="01317-118">Pour obtenir la liste complète des commandes SBCs prises en charge, consultez la [liste des contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="01317-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="01317-119">Pour configurer le système Microsoft Phone et permettre aux utilisateurs d’utiliser le routage direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="01317-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="01317-120">**Étape 1.**</span><span class="sxs-lookup"><span data-stu-id="01317-120">**Step 1.**</span></span> [<span data-ttu-id="01317-121">Connecter l’SBC avec un système Microsoft Phone et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="01317-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="01317-122">**Étape 2.**</span><span class="sxs-lookup"><span data-stu-id="01317-122">**Step 2.**</span></span> [<span data-ttu-id="01317-123">Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="01317-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="01317-124">**Étape 3.**</span><span class="sxs-lookup"><span data-stu-id="01317-124">**Step 3.**</span></span> [<span data-ttu-id="01317-125">Configurer le routage de la voix</span><span class="sxs-lookup"><span data-stu-id="01317-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="01317-126">**Étape 4.**</span><span class="sxs-lookup"><span data-stu-id="01317-126">**Step 4.**</span></span> [<span data-ttu-id="01317-127">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="01317-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="01317-128">Si vous configurez une SBC pour plusieurs clients, vous devez également lire [configurer une SBC pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="01317-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="01317-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01317-129">Related topics</span></span>

[<span data-ttu-id="01317-130">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="01317-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="01317-131">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="01317-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

