---
title: Configurer la Messagerie vocale cloud
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer la messagerie vocale Cloud pour vos utilisateurs. '
ms.openlocfilehash: 8417d8338f8ba25b9f3c92d9fc4547ed861f8b8e
ms.sourcegitcommit: 4fb1c691f0f84d47e215c9c1775da9bdba875f61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2019
ms.locfileid: "35253801"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article est destiné à l' [administrateur 365 Office](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) qui souhaite configurer la fonctionnalité de messagerie vocale Cloud pour toutes les personnes de l’entreprise.

> [!NOTE]
> La messagerie vocale Cloud prend en charge le dépôt de messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie de tiers. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Environnements Cloud uniquement: configurer la messagerie vocale Cloud

Pour les utilisateurs de Skype entreprise Online et des offres d’appels, la boîte vocale Cloud est automatiquement configurée et activée pour les utilisateurs lorsque vous attribuez une licence de **système téléphonique** et un numéro de téléphone à vos utilisateurs.
  
1. Si la fonctionnalité du système téléphonique n’est pas incluse dans votre plan, il est possible que vous deviez acheter des licences de complément de **système téléphonique** . Vous devrez également acheter une licence Exchange Online. Voir [licences de modules complémentaires Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [affecter des licences Microsoft teams](assign-teams-licenses.md)et les licences Exchange Online aux personnes de votre entreprise. Ceci fait, elles sont en mesure de recevoir des messages vocaux.
    
3. La prise en charge de la transcription de la boîte vocale a été ajoutée en mars 2017 et est activée par défaut pour tous les utilisateurs et organisations. Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.

## <a name="phone-system-with-on-premises-environments"></a>Système téléphonique avec environnements locaux

Vous trouverez ci-après des informations sur la configuration de la messagerie vocale Cloud pour travailler avec des environnements d’appels locaux.
  
1. Si la fonctionnalité du système téléphonique n’est pas incluse dans votre plan, il est possible que vous deviez acheter des licences de complément de **système téléphonique** . Vous devez également acheter une licence Exchange Online. Voir [licences de modules complémentaires Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [affecter des licences Microsoft teams](assign-teams-licenses.md)et les licences Exchange Online aux personnes de votre entreprise.
    
3. Suivez les instructions correspondant à la solution d’appels RTC sur site déployée pour vos utilisateurs. Pour la version Cloud Connector, suivez les instructions de la section configurer **les services vocaux et de messagerie vocale du système téléphonique du système** de [configuration Skype entreprise Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx). Pour [la](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)fonction d’appel RTC de Skype entreprise Server, procédez comme suit. Pour le routage direct Teams, suivez la section **configurer le numéro de téléphone et activer l’audio** et la boîte vocale d’entreprise de [configurer le routage direct](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).

4. La prise en charge de la transcription de la boîte vocale a été ajoutée en mars 2017 et est activée par défaut pour tous les utilisateurs et organisations. Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.

5. Les messages vocaux sont remis à la boîte aux lettres Exchange des utilisateurs via le protocole SMTP routé via Exchange Online Protection. Pour permettre la remise des messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre les serveurs Exchange et Exchange Online Protection. [Utiliser des connecteurs pour configurer le flux de messagerie](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

6. Pour activer les fonctionnalités de boîte vocale telles que la personnalisation des messages d’accueil et les messages vocaux visuels dans les clients Skype entreprise, il est nécessaire de se connecter à partir d’Office 365 vers la boîte aux lettres Exchange Server via les services Web Exchange. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification OAuth Exchange décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx), ou exécuter l’Assistant Exchange hybride à partir d’Exchange 2013 CU5 ou égal. Par ailleurs, vous devez configurer l’intégration et le protocole OAuth entre Skype entreprise Online et Exchange Server décrits dans [configurer l’intégration et OAuth entre Skype entreprise Online et Exchange Server](https://docs.microsoft.com/en-us/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). 

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

> [!WARNING]
> Pour les clients Skype entreprise, la désactivation de la messagerie vocale par le biais d’une politique d’appel Microsoft teams peut également désactiver le service de boîte vocale pour vos utilisateurs Skype entreprise.

La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Les messages vocaux reçus par les utilisateurs de votre organisation sont transcrits dans la région où votre client Office 365 est hébergé. La région où votre client est hébergé n’est peut-être pas la même région où se trouve l’utilisateur qui reçoit le message de la boîte vocale. Pour afficher la région où votre client est hébergé, accédez à la page de profil de l' [organisation](https://go.microsoft.com/fwlink/p/?linkid=2067339) , puis cliquez sur **afficher les détails** en regard de emplacement des **données**.

> [!IMPORTANT]
> Vous ne pouvez pas créer une nouvelle instance de stratégie pour le masquage de la transcription et de la transcription à l’aide de l’applet **de nouvelle cmdlet New-CsOnlineVoiceMailPolicy** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’applet de passe **Remove-CsOnlineVoiceMailPolicy** .

Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux. Pour afficher toutes les instances de stratégie de boîte vocale disponibles, vous pouvez utiliser l’applet de passe [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Fenêtre Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Dans la mesure où le paramètre par défaut de transcription est activé pour votre organisation, il est possible que vous souhaitiez le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour cela, exécutez:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activer le masquage de transcription pour votre organisation

Le masquage de la transcription est désactivé par défaut pour votre organisation. S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour cela, exécutez:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription de la boîte vocale est activée pour tous les utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’applet de passe [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

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

Nous disposons d’informations et d’Articles de formation pour aider vos utilisateurs à utiliser la messagerie vocale Skype entreprise. Orientez-les vers les articles suivants :

- Consultation de la [messagerie vocale et des options de Skype entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter votre messagerie vocale dans Skype entreprise, modifier le message d’accueil de votre messagerie vocale, modifier vos paramètres de boîte vocale et écouter votre messagerie vocale à différentes vitesses.

- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Planifier la migration pour Skype Entreprise Server et Exchange Server](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


