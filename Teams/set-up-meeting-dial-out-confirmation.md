---
title: Configurer la confirmation d’appel sortant de réunion pour vos utilisateurs dans Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer Teams pour demander une confirmation d’appel sortant pour empêcher les systèmes de messagerie vocale de se connecter aux réunions lorsque la personne appelée n’est pas en mesure de répondre à l’appel.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117092"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="b71c5-103">Configurer la confirmation d’appel sortant de réunion pour vos utilisateurs dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b71c5-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="b71c5-104">Les appels sortants et les appels m’appellent sont très utiles pour inviter des participants à participer à une réunion et pour les participants existants de participer à une réunion à l’aide d’un téléphone portable ou traditionnel.</span><span class="sxs-lookup"><span data-stu-id="b71c5-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="b71c5-105">Toutefois, lorsque la personne appelée n’est pas en mesure de répondre à l’appel et qu’elle répond par un système de messagerie vocale, le système de messagerie vocale est connecté à la réunion et les participants sont en mesure de l’écouter jusqu’à ce qu’il soit supprimé de la réunion.</span><span class="sxs-lookup"><span data-stu-id="b71c5-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="b71c5-106">Pour empêcher les systèmes de messagerie vocale de se connecter aux réunions lorsqu’un appel sortant de réunion est envoyé à un numéro de téléphone et que la personne appelée ne peut pas répondre à l’appel, vous pouvez configurer Teams pour demander à la personne appelée de participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b71c5-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="b71c5-107">Si la personne appelée ne peut pas répondre à l’appel et que l’appel est répondu par un système de messagerie vocale, le système de messagerie vocale ne sera pas connecté à la réunion, car il ne fournira pas de confirmation pour la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="b71c5-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="b71c5-108">Lorsque cette fonctionnalité est activée, les personnes qui reçoivent un appel sortant ou m’appeler doivent confirmer qu’elles veulent participer à la réunion en appuyant sur le 1 sur leur téléphone portable ou traditionnel.</span><span class="sxs-lookup"><span data-stu-id="b71c5-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="b71c5-109">Pour activer cette fonctionnalité pour toutes les réunions de votre organisation, définissez le paramètre de ```EnableDialOutJoinConfirmation``` l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur ```true``` .</span><span class="sxs-lookup"><span data-stu-id="b71c5-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="b71c5-110">Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b71c5-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="b71c5-111">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b71c5-111">Related topics</span></span>

- [<span data-ttu-id="b71c5-112">Configurer la fonctionnalité M’appeler pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b71c5-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="b71c5-113">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b71c5-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)