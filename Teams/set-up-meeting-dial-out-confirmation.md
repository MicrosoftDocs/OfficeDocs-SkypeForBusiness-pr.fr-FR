---
title: Configurer la confirmation d’appel sortant de réunion pour vos utilisateurs dans Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer des Teams pour demander une confirmation d’appel sortant afin d’empêcher les systèmes de messagerie vocale de se connecter à des réunions lorsque la personne appelée n’est pas en mesure de répondre à l’appel.
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae670cec7adcca3dada49a3dcda0ae11f3d1b7b7
ms.sourcegitcommit: 70bba31b0ca4615a3c6a90f42d3568450ea51b82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2021
ms.locfileid: "61327252"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurer la confirmation d’appel sortant de réunion pour vos utilisateurs dans Microsoft Teams

Les appels sortants et les appels d’appel de réunion sont utiles pour inviter des participants à participer à une réunion et pour les participants existants de participer à une réunion à l’aide d’un téléphone portable ou traditionnel. Toutefois, lorsque la personne appelée ne peut pas répondre à l’appel et que le système de messagerie vocale répond à l’appel, le système est connecté à la réunion. Les participants pourront l’écouter jusqu’à sa suppression de la réunion.

Pour empêcher les systèmes de messagerie vocale de se connecter aux réunions lorsqu’un appel sortant de réunion est envoyé à un numéro de téléphone et que la personne appelée ne peut pas répondre à l’appel, vous pouvez configurer les Teams pour demander à la personne appelée de participer à la réunion. Si la personne appelée ne peut pas répondre à l’appel et que l’appel est répondu par un système de messagerie vocale, le système de messagerie vocale ne sera pas connecté à la réunion, car il ne fournira pas de confirmation pour la rejoindre.

Lorsque cette fonctionnalité est activée, les personnes qui reçoivent un appel sortant ou m’appeler doivent confirmer qu’elles souhaitent participer à la réunion en appuyant sur le 1 sur leur téléphone portable ou traditionnel ou en disant « OK ».

Pour activer cette fonctionnalité pour toutes les réunions de votre organisation, définissez le paramètre de ```EnableDialOutJoinConfirmation``` l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur ```true``` . Pour définir ce paramètre, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Rubriques connexes

- [Configurer la fonctionnalité M’appeler pour vos utilisateurs](set-up-the-call-me-feature-for-your-users.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
