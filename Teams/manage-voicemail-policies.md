---
title: Gérer les stratégies de messagerie vocale
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
ms.openlocfilehash: 02df2f235512ce0aca658031fae000edc99b5ea9
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851815"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>Gérer les stratégies Messagerie vocale infonuagique pour vos utilisateurs

> [!WARNING]
> Pour Skype Entreprise clients, la désactivation de la messagerie vocale via une stratégie d’appel Microsoft Teams peut également désactiver le service de messagerie vocale pour vos utilisateurs Skype Entreprise.

Les stratégies de messagerie vocale vous permettent de configurer et d’affecter des stratégies de messagerie vocale existantes ou nouvelles à des groupes d’utilisateurs pour des fonctionnalités telles que les règles de réponse aux appels, la transcription de messagerie vocale, le masquage des grossièretés de transcription, la traduction de transcription et la langue d’invite système.

Avant de spécifier des stratégies, vous devez lire [Configurer Messagerie vocale infonuagique](set-up-phone-system-voicemail.md). Pour plus d’informations sur la gestion des paramètres pour les utilisateurs individuels, consultez [Gérer les setltings de messagerie vocale](manage-voicemail-settings.md).

Pour gérer les stratégies de messagerie vocale, vous pouvez utiliser le Centre d’administration Teams ou l’applet de commande PowerShell New-CsOnlineVoicemailPolicy. 

Les stratégies par défaut pour les utilisateurs sont les suivantes :

- La transcription de la messagerie vocale est activée.
- La traduction de transcription de messagerie vocale est activée.
- Le masquage des grossièretés de la transcription de la messagerie vocale est désactivé.
- La durée maximale de l’enregistrement est définie sur cinq minutes.
- La modification des règles de répondeur d’appel est activée.
- Les langues d’invite système primaire et secondaire sont définies sur Null et le paramètre de langue de la messagerie vocale de l’utilisateur est utilisé.
- Aucun pré- ou postamble configuré.

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) créée automatiquement ou créer et attribuer des stratégies personnalisées.

> [!IMPORTANT]
> Le service de messagerie vocale dans Microsoft 365 met en cache les stratégies de messagerie vocale et met à jour le cache toutes les 6 heures. Par conséquent, l’application des modifications de stratégie que vous apportez peut prendre jusqu’à 6 heures.

## <a name="use-teams-admin-center"></a>Utiliser le Centre d’administration Teams

### <a name="create-a-custom-voicemail-policy"></a>Créer une stratégie de messagerie vocale personnalisée

Suivez ces étapes pour créer une stratégie de messagerie vocale personnalisée.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à Stratégies **de messagerie vocale** **vocale** > .

2. Sélectionnez **Ajouter**.

3. Activez ou désactivez les fonctionnalités que vous souhaitez utiliser dans votre stratégie de messagerie vocale.

4. Sélectionnez **Enregistrer**.

### <a name="edit-a-voicemail-policy"></a>Modifier une stratégie de messagerie vocale

Suivez ces étapes pour modifier une stratégie de messagerie vocale existante.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Stratégies** > **de messagerie vocale**.

2. Cliquez en regard de la stratégie à modifier, puis sélectionnez **Modifier**.

3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

> [!IMPORTANT]
> Vous ne pouvez pas modifier ou supprimer les instances de stratégie préconfigurées appelées TranscriptionDisabled et TranscriptionProfanityMaskingEnabled.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>Affecter une stratégie de messagerie vocale personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>Utiliser PowerShell

Vous pouvez également utiliser PowerShell pour configurer et affecter des stratégies de messagerie vocale existantes ou nouvelles. Pour gérer les stratégies à l’aide de PowerShell, utilisez les applets de commande suivantes :

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>Paramètres de stratégie de messagerie vocale
  
- **Activer la transcription** : ce paramètre contrôle si le service Messagerie vocale infonuagique génère une transciption de texte de la messagerie vocale enregistrée et l’inclut dans le message vocal. La transcription est effectuée en fonction de la langue détectée dans la messagerie vocale enregistrée.

- **Traduction de transcription** : ce paramètre contrôle si le service Messagerie vocale infonuagique traduit la transcription de la messagerie vocale enregistrée. La traduction sera tentée dans la langue préférée du récepteur de messagerie vocale.

- **Masquage des grossièretés de transcription** : ce paramètre contrôle si le service Messagerie vocale infonuagique masque les grossièretés trouvées dans la transcription de la messagerie vocale.

- **Durée maximale de l’enregistrement** : la durée maximale d’enregistrement contrôle la durée maximale pendant laquelle une messagerie vocale peut être enregistrée. La valeur par défaut est de 5 minutes.

- **Règles de répondeur d’appel** : ce paramètre contrôle si l’utilisateur est autorisé à configurer des règles de réponse aux appels de messagerie vocale dans Microsoft Teams.

- **Invites système en double langue** : par défaut, les invites du système de messagerie vocale sont présentées aux appelants dans la langue sélectionnée par l’utilisateur lors de la configuration de leur messagerie vocale. Si l’entreprise exige que les invites du système de messagerie vocale soient présentées dans deux langues, une langue principale et une langue secondaire peuvent être définies et elles peuvent ne pas être identiques.

- **PréambuleAudioFile** : actuellement disponible uniquement via PowerShell. Fichier audio à lire à l’appelant avant la lecture du message d’accueil de la messagerie vocale de l’utilisateur.

- **PostambleAudioFile** : actuellement disponible uniquement via PowerShell. Fichier audio à lire à l’appelant après la lecture du message d’accueil de la messagerie vocale de l’utilisateur et avant que l’appelant soit autorisé à laisser un message vocal.

- **PréambulePostambleMandatory** : actuellement disponible uniquement via PowerShell. Est-ce que la lecture de la pré- ou de la postamble est obligatoire avant que l’appelant puisse laisser un message.

### <a name="share-data-for-service-improvements"></a>Partager des données pour améliorer le service

Spécifie si les données de messagerie vocale et de transcription sont partagées avec le service pour l’entraînement et l’amélioration de la précision. Si la valeur est false, les données de messagerie vocale ne sont pas partagées, quel que soit le choix de l’utilisateur.


## <a name="related-articles"></a>Articles connexes


