---
title: Configurer Microsoft 365 Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer voix au Microsoft 365 Business votre petite et moyenne entreprise ou organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534005df5161a69fd64ac94c444046508b9d7fd1
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130410"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="ae4a9-103">Configurer Microsoft 365 Business Voice</span><span class="sxs-lookup"><span data-stu-id="ae4a9-103">Set up Microsoft 365 Business Voice</span></span>

<span data-ttu-id="ae4a9-104">Business Voice est un système téléphonique complet qui peut remplacer votre fournisseur de téléphonie existant.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="ae4a9-105">Que vous débutiez dans une activité de configuration de numéros de téléphone pour la première fois ou que vous débutiez avec un fournisseur de téléphonie local hérité, les étapes de ces articles peuvent vous aider à utiliser Business Voice.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="ae4a9-106">Lorsque vous avez terminé la configuration de Voix Entreprise :</span><span class="sxs-lookup"><span data-stu-id="ae4a9-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="ae4a9-107">Vous pourrez recevoir des appels téléphoniques gratuits ou gratuits sur une ligne téléphonique principale de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="ae4a9-108">Vous pouvez même configurer un menu d'appel si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="ae4a9-109">Les utilisateurs qui utilisent Business Voice auront leurs propres numéros de téléphone à composer directement qu'ils peuvent utiliser pour effectuer et recevoir des appels téléphoniques à partir de n'importe quel appareil sur Teams installé.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="ae4a9-110">Les participants à la réunion pourront rejoindre des réunions à l'aide d'un téléphone ordinaire s'ils ne peuvent pas rejoindre une réunion à partir d'Teams client.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="ae4a9-111">Si vous avez des numéros de téléphone existants, vous pourrez continuer à les utiliser une fois qu'ils auront été déplacés vers Business Voice.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="ae4a9-112">Pour en savoir plus sur Business Voice, consultez la Microsoft 365 Business [Voice.](whats-business-voice.md)</span><span class="sxs-lookup"><span data-stu-id="ae4a9-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae4a9-113">Les informations de ces articles s'appliquent à Business Voice **avec** forfait d'appels uniquement.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="ae4a9-114">Business Voice avec forfait d’appels est disponible uniquement dans certains pays et régions.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="ae4a9-115">Avant de commencer à définir Business Voice, vérifiez la disponibilité des pays et régions pour [Business Voice](country-region-availability.md) pour voir si votre pays ou région prend en charge Business Voice avec un plan d'appel.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="ae4a9-116">Si votre client se trouve dans un pays ou une région qui ne prend pas en charge Business Voice avec forfaits d’appels, consultez l’article [Obtenir de l’aide auprès d’un revendeur ou d’un partenaire Microsoft](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="ae4a9-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="ae4a9-117">Microsoft Teams et Business Voice fonctionnent uniquement lorsque les boîtes aux lettres de vos utilisateurs se trouvent dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="ae4a9-118">Les boîtes aux lettres sur serveur Exchange local ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="ae4a9-119">Ce processus de configuration ne prend pas en charge Skype Entreprise déploiements hybrides.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="ae4a9-120">Si vous disposez d’un déploiement hybride Skype Entreprise et que vous voulez configurer l’accès à Business Voice, consultez [Configurer le système téléphonique au sein de votre organisation](../setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="ae4a9-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ae4a9-121">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ae4a9-121">Before you begin</span></span>

<span data-ttu-id="ae4a9-122">Avant de configurer Business Voice, vous devez faire quelques choses.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="ae4a9-123">Les tâches suivantes vous assurent que votre organisation est prête pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="ae4a9-124">**Achetez des licences Business Voice** et, si vous souhaitez obtenir un numéro gratuit ou passer des appels téléphoniques longue distance, crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="ae4a9-125">Pour plus d'informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?</span><span class="sxs-lookup"><span data-stu-id="ae4a9-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="ae4a9-126">**Assurez-vous que votre connexion Internet peut prendre en charge Business Voice.**</span><span class="sxs-lookup"><span data-stu-id="ae4a9-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="ae4a9-127">Pour plus d'informations, [voir Vérifier votre connexion Internet pour Business Voice.](get-ready-internet.md)</span><span class="sxs-lookup"><span data-stu-id="ae4a9-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="ae4a9-128">Configurer des Teams sur les appareils de vos utilisateurs, configurer des messages **d'accueil** de la messagerie vocale et aider vos utilisateurs à en apprendre davantage sur Teams.</span><span class="sxs-lookup"><span data-stu-id="ae4a9-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="ae4a9-129">Pour plus d'informations, [voir Comment préparer mes utilisateurs](prepare-users.md)pour Microsoft 365 Business Voice ?</span><span class="sxs-lookup"><span data-stu-id="ae4a9-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="ae4a9-130">Une fois que vous avez préparé votre organisation pour Voix Entreprise, sélectionnez **L'étape suivante : démarrer la configuration de Voix Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="ae4a9-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ae4a9-131">Étape suivante : commencer à définir Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="ae4a9-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
