---
title: Configurer la messagerie vocale du système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
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
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 18fb66a4a16ca3fd674b2ccdd0ef15af1f6dc761
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-phone-system-voicemail"></a>Configurer la messagerie vocale du système téléphonique

Cet article est pour l' [administration d’Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) qui souhaite en paramétrer la fonctionnalité de messagerie vocale du système téléphonique pour tout le monde de l’entreprise.
  
> [!NOTE]
> Messagerie vocale du système téléphonique prend en charge les messages vocaux dépôt uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers. Comme un mécanisme de secours, messagerie vocale du système téléphonique permet de renvoyer des messages à l’aide de SMTP, ce qui signifie que les utilisateurs avec une boîte aux lettres sur un système de messagerie tiers reçoivent leurs messages vocaux avec aucun temps de fonctionnement du service de garantie ou d’autres fonctionnalités de messagerie vocale, telles que la modification les salutations et autres paramètres. 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Les environnements de cloud uniquement : configurer la messagerie vocale du système téléphonique

Pour Skype pour les utilisateurs professionnels en ligne et des Plans d’appel, messagerie vocale du système téléphonique est automatiquement défini et mis en service pour les utilisateurs une fois que vous leur attribuez une licence de **Système téléphonique** et un numéro de téléphone.
  
1. Si la fonctionnalité de système téléphonique n’est pas incluse dans votre plan, vous devrez acheter des licences supplémentaires de **Système téléphonique** . Vous devrez également acheter une licence Exchange en ligne. Reportez-vous à la section [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Attribuer ou supprimer des licences pour Office 365 pour entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [Affecter de Skype pour les professionnels et les équipes Microsoft des licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)et les licences Exchange Online pour les personnes de votre entreprise. Ceci fait, elles sont en mesure de recevoir des messages vocaux.
    
3. Prise en charge de la transcription de la messagerie vocale a été ajouté à partir de mars 2017 et est activé par défaut pour toutes les organisations et les utilisateurs. Vous pouvez désactiver la transcription de votre organisation en utilisant Windows PowerShell et en suivant les étapes ci-dessous.
    
## <a name="phone-system-with-on-premises-environments"></a>Système de téléphone avec les environnements sur site

Les informations suivantes sont sur la configuration de messagerie vocale du système téléphonique pour travailler avec les environnements d’appel de planification sur site.
  
1. Si la fonctionnalité de système téléphonique n’est pas incluse dans votre plan, vous devrez acheter des licences supplémentaires de **Système téléphonique** . Vous devez également acheter une licence Exchange en ligne. Reportez-vous à la section [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Attribuer ou supprimer des licences pour Office 365 pour entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), les [Affecter de Skype pour les professionnels et les équipes Microsoft des licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)et les licences Exchange Online pour les personnes de votre entreprise.
    
3. Suivez les instructions dans la section **Activer les utilisateurs pour le système téléphonique vocale et services de messagerie vocale** de la [Configurer de Skype pour guide du professionnel de connecteur de nuage](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Prise en charge de la transcription de la messagerie vocale a été ajouté à partir de mars 2017 et est activé par défaut pour toutes les organisations et les utilisateurs. Vous pouvez désactiver la transcription de votre organisation en utilisant Windows PowerShell et en suivant les étapes ci-dessous. 
    
5. Vous pouvez également voir [messagerie vocale du PBX d’Azure prend en charge pour Exchange Server](https://support.microsoft.com/en-us/kb/3195158) pour savoir comment configurer la remise des messages de messagerie vocale Azure pour les utilisateurs de système téléphonique qui ont une boîte aux lettres locale.
    
## <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

Transcription de la messagerie vocale est activée par défaut et le masquage des grossièretés transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; Toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) et [CsOnlineVoicemailPolicy de la subvention](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> Vous ne pouvez pas créer une nouvelle instance de stratégie pour la transcription et les transcription masquage à l’aide de l’applet de commande **New-CsOnlineVoiceMailPolicy** , et vous ne pouvez pas supprimer une instance de stratégie existant à l’aide de l’applet de commande **Remove-CsOnlineVoiceMailPolicy** .
  
Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux. Pour afficher toutes les instances de stratégie de messagerie vocale disponibles, vous pouvez utiliser l’applet de commande [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Car il est sur le paramètre par défaut de la transcription de votre organisation, vous souhaiterez peut-être désactivez-le à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Pour ce faire, exécutez la commande :
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activation de masquage de grossièretés transcription pour votre organisation

Masquage de grossièretés transcription est désactivé par défaut pour votre organisation. S’il existe des besoins de l’entreprise pour l’activer, vous pouvez activer à inconvenances de transcription de masquage à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Pour ce faire, exécutez la commande :
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription de la messagerie vocale est activée pour tous les utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .
  
Pour désactiver la transcription pour un utilisateur unique, exécutez :
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activation de masquage de grossièretés de transcription d’un utilisateur

Pour activer le masquage de grossièretés de transcription pour un utilisateur spécifique, vous pouvez affecter une stratégie pour activer le masquage de grossièretés de transcription pour un utilisateur spécifique à l’aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Pour permettre à inconvenances de transcription de masquage pour un seul utilisateur, exécutez la commande :
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées. 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous disposons des informations sur la formation et des articles pour aider vos utilisateurs à réussir avec Skype pour la messagerie vocale d’entreprise. Orientez-les vers les articles suivants :
  
- [Skype de vérifier les options de la messagerie vocale d’entreprise](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment faire pour écouter vos messages vocaux dans Skype pour entreprise, modifier votre message d’accueil vocal, modifiez vos paramètres de messagerie vocale et écouter vos messages vocaux à des vitesses différentes.
    
- [Formation Skype Entreprise 2016](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Voici les avantages du système téléphonique dans Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 