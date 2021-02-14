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
description: 'Découvrez comment configurer la messagerie vocale cloud pour vos utilisateurs. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662209"
---
# <a name="set-up-cloud-voicemail"></a>Configurer la Messagerie vocale cloud

Cet article est pour l’administrateur Microsoft 365 ou [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) Office 365, comme décrit dans les rôles d’administrateur désireux de configurer la fonctionnalité de messagerie vocale cloud pour tous les employés de l’entreprise.

> [!NOTE]
> La messagerie vocale cloud prend en charge le dépôt de messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers. 

> [!NOTE]
> Quand un délégué répond à un appel au nom d’un délégant, les notifications ne sont pas disponibles dans la messagerie vocale cloud. Les utilisateurs peuvent recevoir des notifications d’appel manqué.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Environnements cloud uniquement : Configurer la messagerie vocale cloud pour les utilisateurs du système téléphonique en ligne

Pour les utilisateurs du système téléphonique en ligne, la messagerie vocale cloud est automatiquement mise en service pour les utilisateurs une fois que vous leur avez attribué une licence **Phone System.** 

> [!NOTE]
> Pour les utilisateurs du système téléphonique Skype Entreprise En ligne avec des numéros de téléphone locaux, vous devrez peut-être activer la messagerie vocale hébergée avec [Set-CsUser -HostedVoicemail $True.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurer la messagerie vocale cloud pour les utilisateurs Exchange Server boîte aux lettres

Les informations suivantes ont pour but de configurer la messagerie vocale cloud de façon à ce qu’elle fonctionne avec les utilisateurs qui utilisent un système téléphonique en ligne mais dont la boîte aux lettres est Exchange Server. 
  
1. Les messages vocaux sont remis à la boîte aux lettres Exchange des utilisateurs via SMTP acheminé via Exchange Online Protection. Pour permettre la remise de ces messages, assurez-vous que les connecteurs Exchange sont correctement configurés entre vos serveurs Exchange et Exchange Online Protection . [Utilisez des connecteurs pour configurer le flux de courrier.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Pour activer les fonctionnalités de messagerie vocale, telles que la personnalisation des messages d’accueil et de la messagerie vocale visuelle dans les clients Skype Entreprise, une connectivité de Microsoft 365 ou d’Office 365 à la boîte aux lettres du serveur Exchange via les services web Exchange est requise. Pour activer cette connectivité, vous devez configurer le nouveau protocole d’authentification Oauth Exchange décrit dans La configuration de l’authentification [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)entre les organisations Exchange et Exchange Online, ou exécuter l’Assistant Exchange hybride à partir d’Exchange 2013 CU5 ou version supérieure. En outre, vous devez configurer l’intégration et oauth entre Skype Entreprise Online et le serveur Exchange décrits dans Configure Integration et [OAuth entre Skype](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)Entreprise Online et Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurer la messagerie vocale cloud pour les utilisateurs de Skype Entreprise Server

Pour configurer les utilisateurs de Skype Entreprise Server pour la messagerie vocale cloud, consultez le service de messagerie vocale Cloud pour les [utilisateurs locaux.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Activation de la messagerie vocale protégée dans votre organisation

Lorsqu’un utilisateur laisse un message vocal pour un utilisateur de votre organisation, ce dernier est remis dans la boîte aux lettres de l’utilisateur sous la mesure d’une pièce jointe. En utilisant des règles de flux de courrier pour appliquer le chiffrement des messages, vous pouvez empêcher le courrier d’être transmis à d’autres destinataires. Lorsque vous activez des messages vocaux protégés, les utilisateurs peuvent écouter les messages vocaux protégés en appelant leur boîte aux lettres vocale ou en ouvrant le message dans Outlook, Outlook sur le web ou dans Outlook pour Android ou iOS. Les messages vocaux protégés ne peuvent pas être ouverts dans Skype Entreprise ou Microsoft Teams.

Pour plus d’informations sur le chiffrement des messages, voir [Chiffrement des messages.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Pour configurer une messagerie vocale protégée, vous pouvez :

1. Connectez-vous https://admin.microsoft.com à l’aide d’un compte avec des autorisations d’administrateur général.
2. Sélectionnez **Afficher tout,** puis allez dans centres **d’administration**  >  **Exchange.**
3. Dans le Centre d’administration Exchange, sélectionnez **Règles de flux de**  >  **courrier.**
4. Sélectionnez Ajouter, puis sélectionnez Appliquer le chiffrement **+** de messages **Office 365 et la protection** des droits aux messages.
5. Donnent un nom à la nouvelle règle de flux de courrier, puis sous Appliquer cette règle si **,** sélectionnez les propriétés du **message** Inclure le type de  >  **message**  >  **Messagerie vocale.** Sélectionnez **OK.**
6. Sous **Faire les choses suivantes,** sélectionnez Appliquer le chiffrement de messages Office **365** et la protection des droits au message, puis **sélectionnez-en un.** Sous **Modèle RMS,** sélectionnez **Ne pas avancer.** Sélectionnez **OK,** puis **Enregistrer.**
    > [!NOTE]
    > Si la **liste de modèles RMS** est vide, vous devez configurer le chiffrement des messages. Pour plus d’informations sur la configuration du chiffrement des messages, voir les articles suivants :
    > - [Configurer de nouvelles fonctionnalités de chiffrement de messages](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configuration et gestion des modèles pour Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Option Ne pas forwarder pour les e-mails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

> [!WARNING]
> Pour les clients Skype Entreprise, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos utilisateurs Skype Entreprise.

La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Les messages vocaux reçus par des utilisateurs de votre organisation sont transcrits dans la région où votre organisation Microsoft 365 ou Office 365 est hébergée. La région dans laquelle votre client est hébergé peut ne pas être la même que la région où se trouve l’utilisateur qui reçoit le message vocal. Pour afficher la région dans laquelle votre client est hébergé, allez sur la [page](https://go.microsoft.com/fwlink/p/?linkid=2067339) de profil de l’organisation, puis cliquez sur Afficher les **détails** en regard de **l’emplacement des données.**

> [!IMPORTANT]
> Vous ne pouvez pas créer une instance de stratégie pour la transcription et la transcription avec une utilisation de l’cmdlet **New-CsOnlineVoiceMailPolicy,** et vous ne pouvez pas supprimer une instance de stratégie existante à l’aide de l’cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Vous pouvez régler les paramètres pour vos utilisateurs qui utilisent des stratégies relatives aux messages vocaux. Pour voir toutes les stratégies de messagerie vocale disponibles, vous pouvez utiliser l’cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Fenêtre Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Étant donné que le paramètre par défaut pour la transcription est pour votre organisation, vous souhaitez peut-être le désactiver à l’aide de [Set-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798310.aspx) Pour ce faire, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activer le masquage de transcription pour votre organisation

Le masquage de la transcription est désactivé par défaut pour votre organisation. S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Pour ce faire, exécutez :

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription de messages vocaux est activée pour tous vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l’aide de l’cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)

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
> Le service de messagerie vocale dans Microsoft 365 et Office 365 met en cache les stratégies de messagerie vocale et met à jour le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Teams

Nous avons les informations suivantes pour vos utilisateurs sur la gestion de leurs paramètres de messagerie vocale ainsi que sur d’autres fonctionnalités d’appel dans Teams :

- [Gérez vos paramètres d’appel dans Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) Cet article explique comment gérer toutes les fonctionnalités d’appel Teams à l’utilisateur final. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous vous indions des informations de formation et des articles pour aider vos utilisateurs à réussir avec la messagerie vocale Skype Entreprise. Orientez-les vers les articles suivants :

- Consultez la messagerie vocale et les options de [Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)Entreprise : cet article explique comment écouter vos messages vocaux dans Skype Entreprise, modifier votre message d’accueil vocal, modifier vos paramètres de messagerie vocale et écouter vos messages vocaux à des vitesses différentes.

- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Planifier la migration pour Skype Entreprise Server et Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
