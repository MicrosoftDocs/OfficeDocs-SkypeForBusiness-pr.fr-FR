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
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Découvrez comment configurer la messagerie vocale Cloud pour vos utilisateurs. '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031070"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article est destiné aux administrateurs Microsoft 365 ou Office 365, comme décrit dans la rubrique [à propos des rôles d’administrateur](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) qui souhaitent configurer la fonctionnalité de messagerie vocale Cloud pour toutes les personnes de l’entreprise.

> [!NOTE]
> La messagerie vocale Cloud prend en charge le dépôt de messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie de tiers. 

> [!NOTE]
> Lorsqu’un délégué répond à un appel de la part d’un déléguer, les notifications ne sont pas disponibles dans la boîte vocale Cloud. Les utilisateurs peuvent recevoir des notifications d’appels manqués.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Environnements Cloud uniquement : configurer la messagerie vocale Cloud pour les utilisateurs du système téléphonique en ligne

Pour les utilisateurs du système téléphonique en ligne, la boîte vocale Cloud est automatiquement configurée et mise en service pour les utilisateurs lorsque vous attribuez une licence de **système téléphonique** aux utilisateurs. 

> [!NOTE]
> Pour les utilisateurs du système téléphonique Skype entreprise en ligne dotés de numéros de téléphone fournis sur site, il est possible que vous deviez activer la messagerie vocale hébergée avec [Set-Csuser-HostedVoicemail $true](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps). 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configuration de la messagerie vocale Cloud pour les utilisateurs de boîtes aux lettres Exchange Server

Vous trouverez ci-après des informations sur la configuration de la messagerie vocale Cloud pour travailler avec des utilisateurs qui sont en ligne pour le système téléphonique mais disposent de leur boîte aux lettres sur Exchange Server. 
  
1. Les messages vocaux sont remis à la boîte aux lettres Exchange des utilisateurs via le protocole SMTP routé via Exchange Online Protection. Pour permettre la remise des messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre les serveurs Exchange et Exchange Online Protection. [Utiliser des connecteurs pour configurer le flux de messagerie](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Pour activer les fonctionnalités de boîte vocale telles que la personnalisation des messages d’accueil et des messages vocaux visuels dans les clients Skype entreprise, la connectivité entre Microsoft 365 ou Office 365 vers la boîte aux lettres Exchange Server via les services Web Exchange est requise. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification OAuth Exchange décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), ou exécuter l’Assistant Exchange hybride à partir d’Exchange 2013 CU5 ou version ultérieure. Par ailleurs, vous devez configurer l’intégration et le protocole OAuth entre Skype entreprise Online et Exchange Server décrits dans [configurer l’intégration et OAuth entre Skype entreprise Online et Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configuration de la messagerie vocale Cloud pour les utilisateurs de Skype entreprise Server

Pour configurer les utilisateurs de Skype entreprise Server pour la boîte vocale Cloud, reportez-vous à la rubrique [planifier le service de messagerie vocale Cloud pour les utilisateurs locaux](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="enabling-protected-voicemail-in-your-organization"></a>Activation de la boîte vocale protégée au sein de votre organisation

Lorsqu’un utilisateur quitte un message vocal pour un utilisateur de votre organisation, le message vocal est remis dans la boîte aux lettres de l’utilisateur sous la forme d’une pièce jointe de message électronique. À l’aide de règles de flux de messagerie pour appliquer le chiffrement des messages, vous pouvez empêcher que les messages vocaux soient renvoyés aux autres destinataires. Lorsque vous activez la boîte vocale protégée, les utilisateurs peuvent écouter les messages vocaux protégés en les appelant dans leur boîte vocale ou en ouvrant le message dans Outlook, Outlook sur le Web ou Outlook pour Android ou iOS. Les messages vocaux protégés ne peuvent pas être ouverts dans Skype entreprise.

Pour plus d’informations sur le chiffrement des messages, voir [chiffrement](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)des messages.

Pour configurer la boîte vocale protégée, procédez comme suit :

1. Accédez à https://admin.microsoft.com , puis connectez-vous en utilisant un compte doté des autorisations d’administrateur général.
2. Sélectionnez **Afficher tout** , puis accédez à **Centre d’administration**  >  **Exchange**.
3. Dans le centre d’administration Exchange, sélectionnez règles de **flux de courrier**  >  **Rules**.
4. Cliquez **+** sur **Ajouter** , puis sélectionnez **appliquer le chiffrement des messages Office 365 et les droits de protection des messages**.
5. Attribuez un nom à la nouvelle règle de flux de courrier, puis sous **appliquer cette règle si** , sélectionnez **les propriétés du message**  >  **incluent le type de message**  >  **messagerie vocale**. Sélectionnez **OK**.
6. Sous **effectuer les opérations suivantes** , activez la case à cocher **appliquer le chiffrement et la protection des messages Office 365 au message avec** , puis sélectionnez **Sélectionner**. Sous **modèle RMS** , sélectionnez **ne pas transférer**. Sélectionnez **OK** , puis **Enregistrer**.
    > [!NOTE]
    > Si la liste de **modèles RMS** est vide, vous devez configurer le chiffrement des messages. Pour plus d’informations sur la configuration du chiffrement des messages, voir les articles suivants :
    > - [Configurer de nouvelles fonctionnalités de chiffrement de messages](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configuration et gestion des modèles pour Azure information protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Option ne pas transférer pour les messages électroniques](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

> [!WARNING]
> Pour les clients Skype entreprise, la désactivation de la messagerie vocale par le biais d’une politique d’appel Microsoft teams peut également désactiver le service de boîte vocale pour vos utilisateurs Skype entreprise.

La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Les messages vocaux reçus par les utilisateurs de votre organisation sont transcrits dans la région où est hébergé votre organisation Microsoft 365 ou Office 365. La région où votre client est hébergé n’est peut-être pas la même région où se trouve l’utilisateur qui reçoit le message de la boîte vocale. Pour afficher la région où votre client est hébergé, accédez à la page de profil de l' [organisation](https://go.microsoft.com/fwlink/p/?linkid=2067339) , puis cliquez sur **afficher les détails** en regard de emplacement des **données**.

> [!IMPORTANT]
> Vous ne pouvez pas créer une nouvelle instance de stratégie pour le masquage de la transcription et de la transcription à l’aide de l’applet **de nouvelle cmdlet New-CsOnlineVoiceMailPolicy** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’applet de passe **Remove-CsOnlineVoiceMailPolicy** .

Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux. Pour afficher toutes les instances de stratégie de boîte vocale disponibles, vous pouvez utiliser l’applet de passe [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Fenêtre Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Dans la mesure où le paramètre par défaut de transcription est activé pour votre organisation, il est possible que vous souhaitiez le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour cela, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activer le masquage de transcription pour votre organisation

Le masquage de la transcription est désactivé par défaut pour votre organisation. S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour cela, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription de la boîte vocale est activée pour tous les utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’applet de passe [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

Pour désactiver la transcription pour un utilisateur unique, exécutez :

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activer le masquage de transcription pour un utilisateur

Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Le service de boîte vocale dans Microsoft 365 et Office 365 met en cache les stratégies de boîte vocale et met à jour le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aidez vos utilisateurs à découvrir les fonctionnalités de la messagerie vocale dans teams

Les informations suivantes sont disponibles pour les utilisateurs sur la gestion de leurs paramètres de messagerie vocale ainsi que d’autres fonctions d’appel dans teams :

- [Gérer vos paramètres d’appel dans teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Cet article explique comment gérer toutes les fonctions d’appel des équipes utilisateurs finaux. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous disposons d’informations et d’Articles de formation pour aider vos utilisateurs à utiliser la messagerie vocale Skype entreprise. Orientez-les vers les articles suivants :

- Consultation de la [messagerie vocale et des options de Skype entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter votre messagerie vocale dans Skype entreprise, modifier le message d’accueil de votre messagerie vocale, modifier vos paramètres de boîte vocale et écouter votre messagerie vocale à différentes vitesses.

- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Planifier la migration pour Skype Entreprise Server et Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
