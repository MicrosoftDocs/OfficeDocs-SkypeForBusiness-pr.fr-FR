---
title: Configurer le robot Ringback pour le routage direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Découvrez comment utiliser le Bot Ringback pour le routage direct afin d’éviter des silences inattendus lors de l’établi d’un appel.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827514"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="7c782-103">Configurer le robot Ringback pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="7c782-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="7c782-104">Cet article décrit le robot Ringback, que vous pouvez utiliser pour éviter des silences inattendus lorsqu’il faut plus de temps pour que les appels soient établis.</span><span class="sxs-lookup"><span data-stu-id="7c782-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="7c782-105">Le robot Ringback est disponible pour le routage direct en mode de dérivation non multimédia.</span><span class="sxs-lookup"><span data-stu-id="7c782-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="7c782-106">Parfois, les appels entrants du réseau téléphonique commuté (PSTN) vers les clients Teams peuvent prendre plus de temps que prévu.</span><span class="sxs-lookup"><span data-stu-id="7c782-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="7c782-107">Cela peut se produire pour diverses raisons.</span><span class="sxs-lookup"><span data-stu-id="7c782-107">This can occur for various reasons.</span></span> <span data-ttu-id="7c782-108">Dans ce cas, il se peut que l’appelant n’entende rien, que le client Teams ne sonne pas et que certains fournisseurs de télécommunications peuvent annuler l’appel.</span><span class="sxs-lookup"><span data-stu-id="7c782-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="7c782-109">Le Robot Ringback permet d’éviter les silences inattendus qui peuvent se produire dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="7c782-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="7c782-110">Pour les appels entrants entre les clients PSTN et Teams, le bot Ringback lit un signal audio distinct pour l’appelant pour indiquer que Teams est en train d’établir l’appel.</span><span class="sxs-lookup"><span data-stu-id="7c782-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="7c782-111">Le robot Ringback génère les premiers médias à partir du verso Teams.</span><span class="sxs-lookup"><span data-stu-id="7c782-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="7c782-112">Dans certains pays et certaines régions, l’appel peut vous être facturé lorsque les médias commencent à circuler.</span><span class="sxs-lookup"><span data-stu-id="7c782-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="7c782-113">Configurer le robot Ringback</span><span class="sxs-lookup"><span data-stu-id="7c782-113">Configure the Ringback bot</span></span>

<span data-ttu-id="7c782-114">Utilisez la cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) pour modifier une configuration de contrôleur de session (SBC) précédemment définie ou la cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) pour créer une nouvelle configuration SBC, avec le paramètre **GenerateRingingWhileLocatingUser** pour configurer le robot Ringback :</span><span class="sxs-lookup"><span data-stu-id="7c782-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="7c782-115">Pour activer le robot Ringback, définissez le paramètre **GenerateRingingWhileLocatingUser** **sur $True.**</span><span class="sxs-lookup"><span data-stu-id="7c782-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="7c782-116">Ceci est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="7c782-116">This is the default value.</span></span> 

- <span data-ttu-id="7c782-117">Pour désactiver le robot Ringback, définissez le paramètre **GenerateRingingWhileLocatingUser** **sur $False.**</span><span class="sxs-lookup"><span data-stu-id="7c782-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7c782-118">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="7c782-118">Related topics</span></span>

- [<span data-ttu-id="7c782-119">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c782-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
