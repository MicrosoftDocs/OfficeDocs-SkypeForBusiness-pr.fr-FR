---
title: Configurer le robot de rappel pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Découvrez comment utiliser le robot de rappel pour le routage direct afin d’éviter les silences inattendus qui peuvent se produire lors de la mise en place d’un appel.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec1500d9e7d5896d1b4cd2414355602d7400591a
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405781"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="c1495-103">Configurer le robot de rappel pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="c1495-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="c1495-104">Cet article décrit le robot de rappel, que vous pouvez utiliser pour éviter les silences inattendus qui peuvent se produire lorsque les appels sont plus longs à établir.</span><span class="sxs-lookup"><span data-stu-id="c1495-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="c1495-105">Le robot de rappel est disponible pour le routage direct en mode de contournement non multimédia.</span><span class="sxs-lookup"><span data-stu-id="c1495-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="c1495-106">Parfois, les appels entrants du réseau téléphonique public commuté (RTC) vers les clients teams peuvent prendre plus de temps que prévu.</span><span class="sxs-lookup"><span data-stu-id="c1495-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="c1495-107">Cela peut se produire pour diverses raisons.</span><span class="sxs-lookup"><span data-stu-id="c1495-107">This can occur for various reasons.</span></span> <span data-ttu-id="c1495-108">Lorsque c’est le cas, l’appelant n’entend rien, le client Teams ne sonne pas et l’appel peut être annulé par certains fournisseurs de télécommunications.</span><span class="sxs-lookup"><span data-stu-id="c1495-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="c1495-109">Le robot de rappel permet d’éviter des silences inattendus qui peuvent se produire dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="c1495-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="c1495-110">Pour les appels entrants des clients RTC aux équipes, le bot de rappel d’appel lit un signal audio distinctif pour l’appelant afin d’indiquer que les équipes sont dans le processus de création de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c1495-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="c1495-111">Le robot de rappel génère des contenus multimédias au premier plan à partir du serveur principal Teams.</span><span class="sxs-lookup"><span data-stu-id="c1495-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="c1495-112">Dans certains pays et régions, il est possible que vous deviez payer l’appel lorsque le média commence à circuler.</span><span class="sxs-lookup"><span data-stu-id="c1495-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="c1495-113">Configurer le robot de rappel</span><span class="sxs-lookup"><span data-stu-id="c1495-113">Configure the Ringback bot</span></span>

<span data-ttu-id="c1495-114">Utilisez les cmdlets [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) et [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) conjointement avec le paramètre **GenerateRingingWhileLocatingUser** pour configurer le bot de rappel.</span><span class="sxs-lookup"><span data-stu-id="c1495-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="c1495-115">Pour activer le robot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$true**.</span><span class="sxs-lookup"><span data-stu-id="c1495-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="c1495-116">Il s’agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="c1495-116">This is the default value.</span></span> 

<span data-ttu-id="c1495-117">Pour désactiver le bot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$false**.</span><span class="sxs-lookup"><span data-stu-id="c1495-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c1495-118">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c1495-118">Related topics</span></span>

- [<span data-ttu-id="c1495-119">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1495-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
