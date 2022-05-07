---
title: Chiffrement de bout en bout pour Microsoft Teams
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 03/08/2022
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Découvrez les fonctionnalités de chiffrement améliorées dans Microsoft Teams, gérez le chiffrement de bout en bout à l’aide du Centre d’administration Teams et de Microsoft PowerShell.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5865494b94c280295d13e0f99303bc76d1fc274
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249006"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls"></a>Utilisez le cryptage de bout en bout pour les appels Microsoft Teams entre particuliers.

> [!IMPORTANT]
> Le modèle de service Teams et sa prise en charge du chiffrement est susceptible d’être modifié pour améliorer l’expérience utilisateur. Par exemple, le service déconseille régulièrement des suites de chiffrement qui ne sont plus considérées comme sécurisées. Ces modifications sont apportées dans le but de maintenir la sécurité de Teams et la confiance en conception. De plus, tout le contenu d’utilisateur dans les centres de données Microsoft est chiffré. Pour plus d’informations sur les couches de chiffrement Microsoft 365, voir [Chiffrement dans Microsoft 365](/microsoft-365/compliance/encryption).

Le chiffrement de bout en bout, ou E2EE, se produit lorsque le contenu est chiffré avant d’être envoyé et déchiffré uniquement par le destinataire prévu. Avec le chiffrement de bout en bout, seuls les deux systèmes de point de terminaison sont impliqués dans le chiffrement et le déchiffrement des données d’appel. Aucun tiers, y compris Microsoft, n’a accès à la conversation déchiffrée.

Avec E2EE pour les appels individuels non programmés, seul le flux média en temps réel, c'est-à-dire les données vidéo et vocales, pour les appels individuels des équipes, est crypté de bout en bout. Les deux parties doivent activer ce paramètre pour activer le chiffrement de bout en bout. [Le chiffrement Microsoft 365](/microsoft-365/compliance/encryption) protège les conversations, le partage de fichiers, la présence et tout autre contenu dans l’appel.

Si vous n’activez pas le chiffrement de bout en bout, Teams protège toujours un appel ou une réunion à l’aide du chiffrement basé sur les normes du secteur d’activité. Les données échangées pendant les appels sont toujours sécurisées pendant le transport et au repos. Pour plus d’informations, voir [Chiffrement des médias pour Teams](teams-security-guide.md#media-encryption).

Pendant un appel chiffré de bout en bout, Teams sécurise les fonctionnalités suivantes :

- Audio

- Vidéo

- Partage d’écran

Les fonctionnalités avancées suivantes ne sont pas disponibles pendant un appel E2EE :

- Sous-titres en direct et transcription

- Transfert d’appel

- Fusion d’appels

- Parcage d'appel

- Consulter puis transférer

- Compagnon des appels et transfert d’appel vers un autre appareil

- Ajout d’un participant

- Enregistrement

Par ailleurs, si votre organisation utilise l’enregistrement de conformité, le chiffrement de bout en bout n’est pas disponible. Pour plus d’informations sur la façon dont Teams prend en charge l’enregistrement de conformité, voir [Présentation de l’enregistrement basé sur une stratégie Teams pour les appels et les réunions](teams-recording-policy.md).

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Configurer le chiffrement de bout en bout pour Microsoft Teams

Effectuez ces tâches afin que vos utilisateurs puissent passer des appels chiffrés de bout en bout.

- Activez le chiffrement de bout en bout pour votre organisation en créant une ou plusieurs stratégies qui définissent les personnes qui peuvent utiliser le chiffrement de bout en bout. Avant de commencer, veillez à ce que le rôle d’administrateur général ou Teams soit affecté à votre compte scolaire ou scolaire. Pour plus d’informations, voir [Utiliser des rôles d’administrateur Microsoft Teams pour gérer Teams](using-admin-roles.md). Lorsque vous êtes prêt à configurer E2EE, vous pouvez utiliser le Centre d’administration Teams ou Microsoft PowerShell.

- Basculez vers les appels chiffrés de bout en bout dans les paramètres Teams sur votre appareil. Chaque utilisateur doit effectuer cette tâche, mais il doit le faire sur un appareil uniquement. Teams synchronises ce paramètre sur les points de terminaison pris en charge pour chaque utilisateur. Pour obtenir des instructions, voir [Utiliser le chiffrement de bout en bout pour les appels Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Utiliser le Centre d'administration Teams pour configurer le chiffrement de bout en bout

La stratégie par défaut globale à l’échelle de l’organisation spécifie que le chiffrement de bout en bout est désactivé. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Pour activer le chiffrement de bout en bout, créez une stratégie de chiffrement ou modifiez la stratégie par défaut globale. Pour activer le chiffrement de bout en bout à l’aide du Centre d'administration Teams, effectuez ces étapes.

1. À l’aide d’un compte professionnel ou scolaire auquel le rôle d’administrateur général ou Teams a été affecté, connectez-vous au [Centre d'administration Teams](https://admin.teams.microsoft.com/).

2. Accédez à **Stratégies de chiffrement améliorées**.

3. Choisissez la stratégie par défaut ou **Ajouter** pour ajouter une nouvelle stratégie, puis nommez-la.

4. Pour activer le chiffrement de bout en bout pour vos utilisateurs, pour le **Chiffrement de bout en bout des appels**, choisissez **Remplacement d’utilisateur désactivé**, puis **Enregistrer**.

   Pour désactiver le chiffrement de bout en bout, choisissez **Désactivé**.

Une fois que vous avez terminé la configuration de la stratégie, affectez la stratégie aux utilisateurs, aux groupes ou à l’ensemble de votre client de la même façon que vous gérez d’autres stratégies Teams. Pour plus d’informations sur l’utilisation des stratégies dans Teams, voir [Gérer Teams avec des stratégies](manage-teams-with-policies.md).

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Utiliser Microsoft PowerShell pour configurer le chiffrement de bout en bout

Vous pouvez gérer les stratégies de chiffrement de bout en bout à l’aide de Microsoft PowerShell et du Centre d'administration Teams. Plusieurs cmdlets de chiffrement de bout en bout sont incluses dans le module Teams PowerShell et documentées dans la [Référence des cmdlets Microsoft Teams](/powershell/teams/?view=teams-ps&preserve-view=true). Cet article répertorie les cmdlets que vous pouvez utiliser et fournit des exemples simples de configuration. Ces configurations utilisent la stratégie globale par défaut. Votre organisation peut nécessiter une configuration de stratégie plus complexe. Des informations complètes sur ces cmdlets sont fournies dans la référence des cmdlets.

Cmdlets PowerShell de chiffrement de bout en bout :

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) renvoie des informations sur les stratégies Teams de chiffrement améliorées dans votre organisation.

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) attribue et annule l’attribution des stratégies de chiffrement améliorées existantes à un utilisateur. Utilisez `$NULL` pour annuler l’attribution de toutes les stratégies d’un utilisateur.

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) crée une stratégie Teams de chiffrement améliorée.

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) supprime une stratégie de chiffrement améliorée de votre organisation. Vous ne pouvez pas supprimer la stratégie globale par défaut.

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) met à jour les valeurs dans une stratégie Teams de chiffrement améliorée existante.

Votre compte scolaire ou scolaire a besoin du rôle d’administrateur général ou Teams pour configurer le chiffrement de bout en bout.

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Activation du chiffrement de bout en bout pour l’ensemble de votre client à l’aide de la stratégie globale

Par défaut, le chiffrement de bout en bout est désactivé. Pour activer le chiffrement de bout en bout pour l'ensemble du locataire en définissant la politique globale par défaut, exécutez le cmdlet [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) comme suit.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

Où :

- `Global` signifie que vous devez définir cette configuration sur la stratégie par défaut globale à l’échelle de l’organisation.

- `DisabledUserOverride` signifie que l’E2EE est désactivé dans Teams par défaut, mais que les utilisateurs peuvent remplacer la stratégie par défaut et activer l’E2EE dans leurs paramètres Teams.

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Désactivation du chiffrement de bout en bout pour l’ensemble de votre client à l’aide de la stratégie globale

Par défaut, le chiffrement de bout en bout est désactivé. Si vous avez apporté des modifications à la stratégie globale, vous pouvez rétablir ce paramètre en exécutant le cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) comme suit.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

Où :

- `Global` signifie que vous devez définir cette configuration sur la stratégie par défaut globale à l’échelle de l’organisation.

- `Disabled` signifie que vous désactivez l’E2EE pour tout le monde et que les utilisateurs ne peuvent pas l’activer dans leurs paramètres Teams.

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>Activation du chiffrement de bout en bout pour un seul utilisateur

Pour activer le chiffrement de bout en bout pour un utilisateur, exécutez la cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) comme suit.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

Où :

- *`username`* est le nom de l’utilisateur.

- *`policyname`* est le nom que vous voulez utiliser pour la stratégie. Les noms de stratégie ne peuvent pas contenir d’espaces, par exemple, ContosoE2EEUserPolicy.

Les utilisateurs doivent encore activer les appels cryptés de bout en bout dans leurs paramètres Teams avant de pouvoir passer un appel crypté de bout en bout. Pour obtenir des instructions, voir [Utiliser le cryptage de bout en bout pour les appels Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

Par exemple :

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>Annulation de l’attribution d’une stratégie de chiffrement de bout en bout pour un seul utilisateur

Les utilisateurs ne peuvent avoir qu’une seule stratégie de chiffrement leur étant affectée à la fois. Lorsque vous annulez l’attribution d’une stratégie à un utilisateur, la stratégie par défaut globale, à l’échelle de l’organisation lui est affectée. Vous ne pouvez pas annuler l’attribution de la stratégie par défaut. Pour annuler l’attribution d’une stratégie de chiffrement de bout en bout d’un utilisateur, exécutez la cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) comme suit.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>Basculer vers le chiffrement de bout en bout sur votre appareil

Pour obtenir des instructions, voir [Utiliser le chiffrement de bout en bout pour les appels Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

## <a name="related-topics"></a>Voir aussi

[12 premières tâches pour les équipes de sécurité qui prennent en charge le travail à domicile](/microsoft-365/security/top-security-tasks-for-remote-work)

[Gérer les paramètres de réunion dans Microsoft Teams](./meeting-settings-in-teams.md)
