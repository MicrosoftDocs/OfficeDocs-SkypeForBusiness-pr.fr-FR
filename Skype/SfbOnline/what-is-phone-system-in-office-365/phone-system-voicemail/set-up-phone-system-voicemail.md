---
title: Installer la messagerie vocale du Système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer la messagerie vocale du système téléphonique (Cloud PBX) pour vos utilisateurs Skype Entreprise. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252888"
---
# <a name="set-up-phone-system-voicemail"></a>Installer la messagerie vocale du Système téléphonique

Cet article est pour l' [administrateur Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) qui souhaite installer la fonction de messagerie vocale du Système téléphonique pour tous les membres de l’entreprise.

> [!NOTE]
> La messagerie vocale du Système téléphonique prend en charge le dépôt des messages vocaux uniquement dans une boîte aux lettres Exchange et ne prend aucun système de messagerie électronique tiers en charge. Comme solution de secours, la messagerie vocale du Système téléphonique peut renvoyer les messages à l'aide du protocole SMTP, en d'autres termes, les utilisateurs disposant d'une boîte aux lettres issue d'un système de messagerie électronique tiers recevront leurs messages vocaux sans garantie d'activité du service ou de toute autre fonction de messagerie vocale, telle que la modification de leur message d'accueil et d'autres paramètres.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Environnements Cloud uniquement : installer la messagerie vocale du Système téléphonique

Pour les utilisateurs de Skype Entreprise Online et de Calling Plans, la messagerie vocale du Système téléphonique est automatiquement installée et mis en service pour les utilisateurs une fois que vous leur attribuez une licence de **Système téléphonique** et un numéro de téléphone.

1. Si la fonctionnalité Système téléphonique n’est pas incluse dans votre forfait, vous devrez peut-être acheter des licences supplémentaires **Système téléphonique**. Vous devrez peut-être également acheter une licence Exchange Online. Voir[Licences complémentaires Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Attribuer des licences Skype Entreprise et Microsoft Team](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) et les licences Exchange Online aux personnes de votre entreprise. Après cela, ils pourront recevoir des messages vocaux !


3. Le support pour la transcription de messages vocaux est disponible depuis mars 2017 et est activé par défaut pour tous les clients et utilisateurs. Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.

## <a name="phone-system-with-on-premises-environments"></a>Système téléphonique avec environnements locaux

Les informations suivantes concernent la configuration de la messagerie vocale du Système téléphonique pour fonctionner avec les Forfaits d'appels locaux.

1. Si la fonctionnalité Système téléphonique n’est pas incluse dans votre forfait, vous devrez peut-être acheter des licences supplémentaires **Système téléphonique**. Vous devez également acheter une licence Exchange Online. Voir[Licences complémentaires Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Attribuer des licences Skype Entreprise et Microsoft Team](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) et les licences Exchange Online aux personnes de votre entreprise.

3. Suivez les instructions de la section**Activer les services vocaux du Système téléphonique et de messagerie vocale pour les utilisateurs** du guide[Configuration de Skype Entreprise, version Cloud Connector](https://technet.microsoft.com/en-us/library/mt605228.aspx).

4. Le support pour la transcription de messages vocaux est disponible depuis mars 2017 et est activé par défaut pour tous les clients et utilisateurs. Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et en suivant les étapes ci-dessous.

5. Vous pouvez également consulter le [Support technique de la messagerie vocale Azure PBX pour Exchange Server](https://support.microsoft.com/en-us/kb/3195158) pour apprendre à configurer la distribution des messages vocaux Azure pour les utilisateurs du Système téléphonique ayant une boîte aux lettres locale.

## <a name="setting-voicemail-policies-in-your-organization"></a>Paramétrage des stratégies de messagerie vocale dans votre organisation

La transcription de la messagerie vocale est activée par défaut et le masquage de la transcription est désactivé par défaut pour toutes les organisations et les utilisateurs ; toutefois, vous pouvez les contrôler à l’aide des applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) et [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).

> [!IMPORTANT]
> Vous ne pouvez pas créer de nouvelle stratégie pour la transcription et son masquage à l'aide de l'applet de commande **New-CsOnlineVoiceMailPolicy** et vous ne pouvez pas supprimer de stratégie à l'aide de l'applet de commande **Remove-CsOnlineVoiceMailPolicy**.

Vous pouvez gérer les paramètres de transcription pour vos utilisateurs à l'aide des stratégies de messagerie vocale. Pour afficher toutes les stratégies disponibles concernant les messages vocaux, vous pouvez utiliser l'applet de commande [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Fenêtre Get-CsOnlineVoiceMailPolicy.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>Désactivation de la transcription pour votre organisation

Puisque le paramètre par défaut pour la transcription est activée pour votre organisation, vous voudrez peut-être le désactiver au moyen de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Pour cela, exécutez :

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Activer le masquage de transcription pour votre organisation

Le masquage de la transcription est désactivé par défaut pour votre organisation. S’il existe une exigence de l’entreprise pour l’activer, vous pouvez activer le masquage de la transcription à l’aide de [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Pour cela, exécutez :

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres organisationnels par défaut. Par exemple, si la transcription des messages vocaux est activée pour tous vos utilisateurs, vous pouvez attribuer une stratégie pour désactiver la transcription pour un utilisateur spécifique au moyen de l'applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Pour désactiver la transcription pour un utilisateur unique, exécutez :

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Activer le masquage de transcription pour un utilisateur

Pour activer le masquage de la transcription pour un utilisateur spécifique, vous pouvez attribuer une stratégie permettant d'activer le masquage de la transcription pour un utilisateur spécifique à l'aide de l’applet de commande [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).

Pour activer le masquage de la transcription pour un seul utilisateur, exécutez :

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Aidez vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous disposons d'une grande quantité d'informations et d'articles de formation qui permettront à vos utilisateurs de se servir efficacement de la messagerie vocale Skype Entreprise. Orientez-les vers les articles suivants :

- [Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8) : Cet article explique comment écouter votre messagerie vocale dans Skype Entreprise, modifier votre message d'accueil vocal et écouter vos messages vocaux à différentes vitesses.

- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Voici les avantages du système téléphonique dans Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


