---
title: Configurer la réponse automatique pour les Teams Android
author: KarliStites
ms.author: kastites
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
ms.custom: null
description: Découvrez comment configurer la fonctionnalité de réponse automatique pour les Salles Microsoft Teams sur Android et Teams des périphériques de téléphone vidéo avec PowerShell.
---

# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurer la réponse automatique pour les Salles Microsoft Teams sur les appareils Android Teams vidéo

Cet article vous aide à configurer la fonctionnalité de réponse automatique sur Salles Microsoft Teams appareils Android et Teams vidéo. La réponse automatique permet aux utilisateurs de votre organisation  outre des privilèges d’administration de modifier les paramètres de leur appareil pour accepter automatiquement les invitations aux réunions entrantes et accepter automatiquement les appels vidéo.

## <a name="enable-auto-answer-with-powershell"></a>Activer la réponse automatique avec PowerShell

Utilisez les attributs suivants pour activer la réponse automatique sur Salles Microsoft Teams sur les appareils Android Teams vidéo :

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Activer la réponse automatique pour les invitations aux réunions entrantes

Vous utilisez **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** pour activer la réponse automatique pour les invitations aux réunions entrantes. La réponse automatique **est désactivée** par défaut. Cette stratégie s’applique uniquement aux invitations aux réunions entrantes et ne prend pas en charge les autres types d’appels. Pour [plus d’informations sur l’let, lisez Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) .

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Définir le mode de inscription de l’appareil

Vous utilisez **Set-CsTeamsIPPhonePolicy -SignInMode** pour définir le mode de sign-in de l’appareil afin de déterminer le comportement lors de la Teams. Pour [plus d’informations sur l’let, lisez Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) .

Trois options s’offrent à vous pour le mode de inscription :

- **UserSignIn :** Permet à un utilisateur individuel Teams expérience utilisateur sur le téléphone.
- **CommonAreaPhoneSignIn :** Permet une expérience téléphonique courante sur le téléphone.
- **MeetingSignIn :** Permet une expérience de salle de réunion sur le téléphone.

Par exemple, la stratégie suivante définit le mode de inscription sur une expérience de salle de réunion.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurer les paramètres de l’appareil

Après avoir autorisé la réponse automatique, les utilisateurs  disposent d’autorisations d’administration peuvent activer la fonctionnalité dans les paramètres de leur appareil. Pour activer la fonctionnalité au niveau de l’appareil, vous devez activer automatiquement **les invitations aux réunions entrantes**. Vous pouvez également activer **l’acceptation automatique avec la vidéo**. Les deux paramètres sont éteints par défaut.

## <a name="related-topics"></a>Sujets associés

[Support Microsoft : Appels et appareils](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
