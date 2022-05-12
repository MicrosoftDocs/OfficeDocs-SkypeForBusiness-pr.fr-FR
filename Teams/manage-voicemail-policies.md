---
title: Gérer les stratégies de messagerie vocale
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gérer les stratégies de messagerie vocale pour vos utilisateurs.
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370827"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Configuration des stratégies de messagerie vocale pour votre organisation

> [!WARNING]
> Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos utilisateurs Skype Entreprise.

Vous pouvez utiliser des stratégies de messagerie vocale pour contrôler différentes fonctionnalités liées à Messagerie vocale infonuagique.

## <a name="voicemail-organization-defaults-for-all-users"></a>Valeurs par défaut de l’organisation de messagerie vocale pour tous les utilisateurs
- La transcription de la messagerie vocale est activée.
- La traduction de transcription de la messagerie vocale est activée.
- Le masquage des vulgarités de transcription de la messagerie vocale est désactivé.
- La durée maximale d’enregistrement est définie sur cinq minutes.
- La modification des règles de réponse aux appels est activée.
- Les langues d’invite du système principal et secondaire sont définies sur null et le paramètre de langue de messagerie vocale de l’utilisateur est utilisé.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) qui est créée automatiquement ou créer et affecter des stratégies personnalisées.

## <a name="create-a-custom-voicemail-policy"></a>Créer une stratégie de messagerie vocale personnalisée

Suivez ces étapes pour créer une stratégie de messagerie vocale personnalisée.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux stratégies **VoiceVoicemail** > .
2. Sélectionnez **Ajouter**.
3. Activez ou désactivez les fonctionnalités que vous souhaitez utiliser dans votre stratégie de messagerie vocale.
4. Sélectionnez **Enregistrer**.

## <a name="edit-a-voicemail-policy"></a>Modifier une stratégie de messagerie vocale

Suivez ces étapes pour modifier une stratégie de messagerie vocale existante.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, sélectionnez **Stratégies** **VoiceVoicemail** > .
2. Cliquez en regard de la stratégie à modifier, puis **sélectionnez Modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

> [!IMPORTANT]
> Vous ne pouvez pas modifier ou supprimer les instances de stratégie préconfigurées appelées TranscriptionDisabled et TranscriptionProfanityMaskingEnabled.


## <a name="assign-a-custom-voicemail-policy-to-users"></a>Affecter une stratégie de messagerie vocale personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>Paramètres de stratégie de messagerie vocale
  
### <a name="enable-transcription"></a>Activer la transcription

Ce paramètre contrôle si le service Messagerie vocale infonuagique génère une transcipation de texte de la messagerie vocale enregistrée et l’inclut dans le message vocal. La transcription sera effectuée en fonction de la langue détectée dans la messagerie vocale enregistrée.

### <a name="transcription-translation"></a>Traduction de transcription

Ce paramètre détermine si le service Messagerie vocale infonuagique traduit la transcription de la messagerie vocale enregistrée. La traduction sera tentée dans la langue préférée du récepteur de messagerie vocale.

### <a name="transcription-profanity-masking"></a>Masquage des vulgarités de transcription

Ce paramètre détermine si le service Messagerie vocale infonuagique masque les grossièretés trouvées dans la transcription de la messagerie vocale.

### <a name="maximum-recording-duration"></a>Durée maximale d’enregistrement

La longueur maximale d’enregistrement contrôle la durée maximale d’enregistrement d’une messagerie vocale. La valeur par défaut est 5 minutes.

### <a name="call-answering-rules"></a>Règles de réponse aux appels

Ce paramètre détermine si l’utilisateur est autorisé à configurer des règles de réponse aux appels vocaux dans Microsoft Teams.

### <a name="dual-language-system-prompts"></a>Invites du système de double langage

Par défaut, les invites du système de messagerie vocale sont présentées aux appelants dans la langue sélectionnée par l’utilisateur lors de la configuration de leur messagerie vocale. Si l’entreprise exige que les invites du système de messagerie vocale soient présentées dans deux langues, une langue primaire et une langue secondaire peuvent être définies et elles peuvent ne pas être les mêmes.

### <a name="share-data-for-service-improvements"></a>Partager des données pour améliorer le service

Spécifie si les données de messagerie vocale et de transcription sont partagées avec le service pour l’entraînement et l’amélioration de la précision. Si la valeur est false, les données de messagerie vocale ne sont pas partagées, quel que soit le choix de l’utilisateur.


> [!IMPORTANT]
> Le service de messagerie vocale dans Microsoft 365 et Office 365 met en cache les stratégies de messagerie vocale et met à jour le cache toutes les 6 heures. Par conséquent, l’application des modifications de stratégie que vous apportez peut prendre jusqu’à 6 heures.

## <a name="related-articles"></a>Articles connexes

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
