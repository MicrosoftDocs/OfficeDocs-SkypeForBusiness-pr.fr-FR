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
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420954"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="b6bb9-103">Configurer le robot de rappel pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="b6bb9-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="b6bb9-104">Cet article décrit le robot de rappel, que vous pouvez utiliser pour éviter les silences inattendus qui peuvent se produire lorsque les appels sont plus longs à établir.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="b6bb9-105">Le robot de rappel est disponible pour le routage direct en mode de contournement non multimédia.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="b6bb9-106">Parfois, les appels entrants du réseau téléphonique public commuté (RTC) vers les clients teams peuvent prendre plus de temps que prévu.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="b6bb9-107">Cela peut se produire pour diverses raisons.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-107">This can occur for various reasons.</span></span> <span data-ttu-id="b6bb9-108">Lorsque c’est le cas, l’appelant risque de n’entendre rien, le client Teams ne sonne pas et certains fournisseurs de télécommunications peuvent annuler l’appel.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="b6bb9-109">Le robot de rappel permet d’éviter des silences inattendus qui peuvent se produire dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="b6bb9-110">Pour les appels entrants des clients RTC aux équipes, le bot de rappel d’appel lit un signal audio distinctif pour l’appelant afin d’indiquer que les équipes sont dans le processus de création de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="b6bb9-111">Le robot de rappel génère des contenus multimédias au premier plan à partir du serveur principal Teams.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="b6bb9-112">Dans certains pays et régions, il est possible que vous deviez payer l’appel lorsque le média commence à circuler.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="b6bb9-113">Configurer le robot de rappel</span><span class="sxs-lookup"><span data-stu-id="b6bb9-113">Configure the Ringback bot</span></span>

<span data-ttu-id="b6bb9-114">Utilisez l’applet de commande [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) pour modifier une configuration de contrôleur de frontière de session (SBC) déjà définie ou l’applet [de commande New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) pour créer une nouvelle configuration de SBC, ainsi que le paramètre **GenerateRingingWhileLocatingUser** pour configurer le bot de rappel :</span><span class="sxs-lookup"><span data-stu-id="b6bb9-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="b6bb9-115">Pour activer le robot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$true**.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="b6bb9-116">Il s’agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-116">This is the default value.</span></span> 

- <span data-ttu-id="b6bb9-117">Pour désactiver le bot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$false**.</span><span class="sxs-lookup"><span data-stu-id="b6bb9-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b6bb9-118">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b6bb9-118">Related topics</span></span>

- [<span data-ttu-id="b6bb9-119">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6bb9-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
