---
title: Configurer la confirmation de rendez-vous rendez-vous pour vos utilisateurs dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer Teams pour demander une confirmation de déconnexion afin d’empêcher les systèmes de messagerie vocale de se connecter aux réunions lorsque la personne appelée ne peut pas répondre à l’appel.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271559"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurer la confirmation d’accès à la réunion pour vos utilisateurs dans Microsoft Teams

Les appels sortants de réunion et les appels m’appellent sont des moyens utiles d’inviter les participants à participer à une réunion et pour les participants existants de participer à une réunion à l’aide d’un téléphone traditionnel ou mobile. Toutefois, lorsque la personne appelée ne parvient pas à répondre à l’appel et que l’appel est répondu par un système de messagerie vocale, le système de messagerie vocale est connecté à la réunion. Les participants pourront l’écouter jusqu’à ce qu’il soit supprimé de la réunion.

Pour empêcher les systèmes de messagerie vocale de se connecter aux réunions lorsqu’un numéro de rendez-vous est envoyé à un numéro de téléphone et que la personne appelée ne peut pas répondre à l’appel, vous pouvez configurer Teams pour demander une confirmation à la personne appelée pour qu’elle rejoigne la réunion. Si la personne appelée ne peut pas répondre à l’appel et que l’appel est répondu par un système de messagerie vocale, le système de messagerie vocale ne sera pas connecté à la réunion, car il ne fournira pas de confirmation pour y participer.

Lorsque cette fonctionnalité est activée, les personnes qui reçoivent un appel sortant ou m’appellent doivent confirmer qu’elles souhaitent participer à la réunion en appuyant sur 1 sur leur téléphone traditionnel ou mobile ou en disant « OK ». La confirmation empêche le message vocal de l’utilisateur de rejoindre la réunion.

Pour activer cette fonctionnalité pour toutes les réunions de votre organisation, définissez le ```EnableDialOutJoinConfirmation``` paramètre de l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur ```true```. Pour définir ce paramètre, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Voir aussi

- [Configurer la fonctionnalité M’appeler pour vos utilisateurs](set-up-the-call-me-feature-for-your-users.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
