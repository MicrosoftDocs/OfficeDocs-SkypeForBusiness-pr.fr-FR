---
title: Configurer la messagerie vocale du système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: fa0783cf51b7d3b7bf29b4948994060a3d1f63a1
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182511"
---
# <a name="set-up-phone-system-voicemail"></a>Configurer la messagerie vocale du système téléphonique

Cet article est pour l' [administration d’Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) souhaite configurer la fonctionnalité de messagerie vocale système téléphonique pour tout le monde dans l’entreprise.

> [!NOTE]
> Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Environnements en nuage uniquement : configurer le système téléphonique de la messagerie vocale

Pour Skype pour les utilisateurs professionnels en ligne et des Plans de l’appel, la messagerie vocale système téléphonique est automatiquement configurée et mis en service pour les utilisateurs une fois que vous leur attribuez une licence de **Système téléphonique** et un numéro de téléphone.
  
1. If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You may also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
2. [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!
    
3. Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.

## <a name="phone-system-with-on-premises-environments"></a>Système téléphonique avec environnements locaux

Les informations suivantes concernent la configuration de la messagerie vocale du Système téléphonique pour fonctionner avec les Forfaits d'appels locaux.
  
1. If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
2. [Affecter ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)et les licences Exchange Online pour les personnes figurant dans votre entreprise.
    
3. Suivez les instructions indiquées dans la section **Activer les utilisateurs pour le système téléphonique vocale et les services de messagerie vocale** du [Configurer de Skype pour édition dans le nuage connecteur guide](https://technet.microsoft.com/library/mt605228.aspx).

4. Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.

5. Vous pouvez également consulter le [Support technique de la messagerie vocale Azure PBX pour Exchange Server](https://support.microsoft.com/kb/3195158) pour apprendre à configurer la distribution des messages vocaux Azure pour les utilisateurs du Système téléphonique ayant une boîte aux lettres locale.

6. Veuillez également lire et suivre les étapes décrites dans le document suivant : [Assistant Configuration hybride](https://docs.microsoft.com/en-us/exchange/hybrid-configuration-wizard)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

> [!IMPORTANT]
> Vous ne pouvez pas créer une nouvelle instance de stratégie pour la transcription et gratuites transcription masquage à l’aide de l’applet de commande **New-CsOnlineVoiceMailPolicy** , et vous ne pouvez pas supprimer une instance existante de stratégie à l’aide de l’applet de commande **Remove-CsOnlineVoiceMailPolicy** .

Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux. Pour afficher toutes les instances de stratégie de messagerie vocale disponibles, vous pouvez utiliser l’applet de commande [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Étant donné que le paramètre par défaut de la transcription est activé pour votre organisation, vous souhaiterez peut-être désactiver à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour ce faire, exécutez :

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activer le masquage de transcription pour votre organisation

Le masquage de la transcription est désactivé par défaut pour votre organisation. S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour ce faire, exécutez :

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription de la messagerie vocale est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

Pour désactiver la transcription pour un utilisateur unique, exécutez :

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activer le masquage de transcription pour un utilisateur

Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous disposons d’informations sur la formation et des articles pour aider vos utilisateurs à vendre Skype pour la messagerie vocale d’entreprise. Orientez-les vers les articles suivants :

- [Vérifier les Skype pour les options et de la messagerie vocale d’entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter vos messages vocaux dans Skype pour les entreprises, modifier votre message d’accueil vocal, modifier vos paramètres de messagerie vocale et écouter vos messages vocaux à différentes vitesses.

- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)


