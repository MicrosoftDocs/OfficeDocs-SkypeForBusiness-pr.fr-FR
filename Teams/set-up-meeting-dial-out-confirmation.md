---
title: Configurer une confirmation de connexion pour vos utilisateurs dans Microsoft teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Apprenez à configurer teams pour demander une confirmation de numérotation pour empêcher les systèmes de boîte vocale de se connecter aux réunions lorsque la personne appelée ne peut pas répondre à l’appel.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339472"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="05f1d-103">Configurer la confirmation pour les appels sortants de réunion pour vos utilisateurs dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="05f1d-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="05f1d-104">Les appels sortants de réunion et les appels Skype sont très utiles pour inviter les participants à rejoindre une réunion, et pour que les participants existants puissent participer à une réunion à l’aide d’un téléphone fixe ou mobile.</span><span class="sxs-lookup"><span data-stu-id="05f1d-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="05f1d-105">En revanche, lorsque la personne appelée ne peut pas répondre à l’appel et que l’appel est reçu par un système de boîte vocale, le système de boîte vocale est connecté à la réunion et les participants peuvent l’écouter jusqu’à ce qu’elle soit supprimée de la réunion.</span><span class="sxs-lookup"><span data-stu-id="05f1d-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="05f1d-106">Pour empêcher les systèmes de boîte vocale de se connecter aux réunions lorsque la numérotation d’une réunion est envoyée à un numéro de téléphone et que la personne appelée ne peut pas répondre à l’appel, vous pouvez configurer teams pour demander une confirmation de la part des personnes appelées à rejoindre la réunion.</span><span class="sxs-lookup"><span data-stu-id="05f1d-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="05f1d-107">Si la personne appelée ne peut pas répondre à l’appel et que l’appel est reçu par un système de boîte vocale, le système de messagerie vocale n’est pas connecté à la réunion, car il ne vous permet pas de le rejoindre.</span><span class="sxs-lookup"><span data-stu-id="05f1d-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="05f1d-108">Lorsque cette fonctionnalité est activée, les utilisateurs qui reçoivent un appel commuté ou qui m’appellent doivent confirmer qu’ils souhaitent participer à la réunion en appuyant sur 1 sur leur téléphone classique ou mobile.</span><span class="sxs-lookup"><span data-stu-id="05f1d-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="05f1d-109">Pour activer cette fonctionnalité pour toutes les réunions de votre organisation, définissez ```EnableDialOutJoinConfirmation``` le paramètre de l’applet de cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur ```true```.</span><span class="sxs-lookup"><span data-stu-id="05f1d-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="05f1d-110">Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="05f1d-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="05f1d-111">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="05f1d-111">Related topics</span></span>

- [<span data-ttu-id="05f1d-112">Configurer la fonctionnalité M’appeler pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="05f1d-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="05f1d-113">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="05f1d-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)