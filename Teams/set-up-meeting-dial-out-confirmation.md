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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurer la confirmation pour les appels sortants de réunion pour vos utilisateurs dans Microsoft teams

Les appels sortants de réunion et les appels Skype sont très utiles pour inviter les participants à rejoindre une réunion, et pour que les participants existants puissent participer à une réunion à l’aide d’un téléphone fixe ou mobile. En revanche, lorsque la personne appelée ne peut pas répondre à l’appel et que l’appel est reçu par un système de boîte vocale, le système de boîte vocale est connecté à la réunion et les participants peuvent l’écouter jusqu’à ce qu’elle soit supprimée de la réunion.

Pour empêcher les systèmes de boîte vocale de se connecter aux réunions lorsque la numérotation d’une réunion est envoyée à un numéro de téléphone et que la personne appelée ne peut pas répondre à l’appel, vous pouvez configurer teams pour demander une confirmation de la part des personnes appelées à rejoindre la réunion. Si la personne appelée ne peut pas répondre à l’appel et que l’appel est reçu par un système de boîte vocale, le système de messagerie vocale n’est pas connecté à la réunion, car il ne vous permet pas de le rejoindre.

Lorsque cette fonctionnalité est activée, les utilisateurs qui reçoivent un appel commuté ou qui m’appellent doivent confirmer qu’ils souhaitent participer à la réunion en appuyant sur 1 sur leur téléphone classique ou mobile.

Pour activer cette fonctionnalité pour toutes les réunions de votre organisation, définissez ```EnableDialOutJoinConfirmation``` le paramètre de l’applet de cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur ```true```. Pour cela, exécutez la commande suivante :

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Rubriques connexes

- [Configurer la fonctionnalité M’appeler pour vos utilisateurs](set-up-the-call-me-feature-for-your-users.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)