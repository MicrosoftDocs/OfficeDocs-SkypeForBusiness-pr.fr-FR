---
title: Configurer la réponse automatique pour les appareils Teams Android
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Découvrez comment configurer la fonctionnalité de réponse automatique pour Salles Microsoft Teams sur Android et Teams périphériques de téléphone vidéo avec PowerShell.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646593"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurer la réponse automatique pour Salles Microsoft Teams sur Android et Teams périphériques de téléphone vidéo

Cet article vous aidera à configurer la fonctionnalité de réponse automatique sur Salles Microsoft Teams sur Android et Teams périphériques de téléphone vidéo. La réponse automatique permet aux personnes de votre organisation disposant de privilèges d’administration de modifier leurs paramètres d’appareil pour accepter automatiquement les invitations aux réunions entrantes et accepter automatiquement les appels avec la vidéo.

## <a name="enable-auto-answer-with-powershell"></a>Activer la réponse automatique avec PowerShell

Utilisez les attributs suivants pour activer la réponse automatique sur Salles Microsoft Teams sur Android et Teams périphériques de téléphone vidéo :

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Activer la réponse automatique pour les invitations aux réunions entrantes

Vous utilisez **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** pour activer la réponse automatique pour les invitations aux réunions entrantes. La réponse automatique est **désactivée** par défaut. Cette stratégie s’applique uniquement aux invitations aux réunions entrantes et ne prend pas en charge les autres types d’appels. Pour plus d’informations sur l’applet de commande, consultez [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) .

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Définir le mode de connexion de l’appareil

Vous utilisez **Set-CsTeamsIPPhonePolicy -SignInMode** pour définir le mode de connexion de l’appareil afin de déterminer le comportement lors de la connexion à Teams. Pour plus d’informations sur l’applet de commande, consultez [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) .

Il existe trois options pour le mode de connexion :

- **UserSignIn :** Permet à un utilisateur individuel Teams expérience sur le téléphone.
- **CommonAreaPhoneSignIn :** Active une expérience téléphonique commune sur le téléphone.
- **MeetingSignIn :** Active une expérience de salle de réunion sur le téléphone.

Par exemple, la stratégie suivante définit le mode de connexion sur une expérience de salle de réunion.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurer les paramètres de l’appareil

Après avoir activé la réponse automatique, les utilisateurs disposant d’autorisations administratives peuvent activer la fonctionnalité dans leurs paramètres d’appareil. Pour activer la fonctionnalité au niveau de l’appareil, vous devez activer **l’acceptation automatique des invitations aux réunions entrantes**. Vous pouvez également activer **l’acceptation automatique avec la vidéo**. Les deux paramètres sont désactivés par défaut.

## <a name="related-topics"></a>Voir aussi

[Support Microsoft : appels et appareils](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
