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
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806144"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurer la confirmation d’appel sortant de réunion pour vos utilisateurs dans Microsoft Teams

Les appels sortants et les appels d’appel de réunion sont très utiles pour inviter des participants à participer à une réunion et pour les participants existants de participer à une réunion à l’aide d’un téléphone portable ou traditionnel. Toutefois, lorsque la personne appelée n’est pas en mesure de répondre à l’appel et qu’elle répond par un système de messagerie vocale, le système de messagerie vocale est connecté à la réunion et les participants sont en mesure de l’écouter jusqu’à ce qu’il soit supprimé de la réunion.

Pour empêcher les systèmes de messagerie vocale de se connecter aux réunions lorsqu’un appel sortant de réunion est envoyé à un numéro de téléphone et que la personne appelée ne peut pas répondre à l’appel, vous pouvez configurer Teams pour demander à la personne appelée de participer à la réunion. Si la personne appelée ne peut pas répondre à l’appel et si un système de messagerie vocale répond à l’appel, le système de messagerie vocale n’est pas connecté à la réunion, car aucune confirmation ne lui est fournie pour y participer.

Lorsque cette fonctionnalité est activée, les personnes qui reçoivent un appel sortant ou m’appeler doivent confirmer qu’elles veulent participer à la réunion en appuyant sur le 1 sur leur téléphone portable ou traditionnel.

Pour activer cette fonctionnalité pour toutes les réunions de votre organisation, définissez le paramètre de ```EnableDialOutJoinConfirmation``` l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur ```true``` . Pour cela, exécutez la commande suivante :

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Sujets associés

- [Configurer la fonctionnalité M’appeler pour vos utilisateurs](set-up-the-call-me-feature-for-your-users.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)