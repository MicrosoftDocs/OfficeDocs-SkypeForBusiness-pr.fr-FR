---
title: Désactiver la stratégie de chargement de fichiers natifs Teams
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Découvrez comment créer, définir, attribuer et ajuster la stratégie de fichiers Teams à l’aide de PowerShell.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6c7d5c89c780fa5c9286f5d7f7d2304f2e6c6220
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198526"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Désactiver la stratégie de chargement de fichiers natifs Teams

Microsoft Teams utilise OneDrive et SharePoint pour stocker et partager du contenu, mais certaines organisations et utilisateurs peuvent préférer utiliser des fournisseurs de stockage tiers.  

Si votre organisation choisit un tiers pour le stockage de contenu, vous devez désactiver le `NativeFileEntryPoints` paramètre dans la stratégie Fichiers Teams. Ce paramètre est activé par défaut, ce qui affiche l’option permettant de charger du contenu à partir de OneDrive ou SharePoint vers des conversations ou des canaux Teams.

Cet article vous aidera à créer, définir, attribuer et supprimer le paramètre à l’aide de `NativeFileEntryPoints` PowerShell.

>[!NOTE]
>Lorsque la stratégie Fichiers Teams est désactivée, les utilisateurs ne voient pas de points d’accès pour OneDrive et SharePoint dans Teams, mais la création de nouvelles équipes et de nouveaux canaux continuera à déclencher la génération de bibliothèques SharePoint correspondantes.

## <a name="prepare-to-update-the-teams-files-policy"></a>Préparer la mise à jour de la stratégie Fichiers Teams

### <a name="set-up-microsoft-powershell"></a>Configurer Microsoft PowerShell

Actuellement, cette stratégie ne peut pas être modifiée dans le Centre d’administration Teams. L’administrateur client Microsoft 365 de votre organisation devra apporter les modifications à l’aide des applets de commande PowerShell détaillées plus loin dans cet article.

Découvrez comment installer le module PowerShell Teams à l’aide de PowerShell Gallery en lisant [Installer Microsoft module PowerShell Teams](teams-powershell-install.md).

Pour installer ou télécharger le module PowerShell Teams, consultez [PowerShell Gallery pour Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Pour plus d’informations sur la configuration de PowerShell pour la gestion de Teams, consultez [Gérer Teams avec Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Autoriser les applications tierces dans teams Administration Center

Cette étape n’est pas nécessaire pour modifier la stratégie Teams Files, mais elle est nécessaire lorsque vous êtes prêt à intégrer votre fournisseur de stockage tiers dans l’expérience Teams de vos utilisateurs.

Votre administrateur client Microsoft 365 doit activer la stratégie « Autoriser les applications tierces » dans le Centre d’administration Teams.

Pour savoir comment autoriser des applications tierces ou personnalisées, consultez Gérer les paramètres des applications à l’échelle de l’organisation dans [Gérer vos applications dans le centre d’administration Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Désactiver NativeFileEntryPoints pour l’ensemble de votre locataire

La définition du `-Identity` paramètre sur `Global` applique les paramètres de stratégie à tous les utilisateurs de votre organisation.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Exemple d’applet de commande de stratégie PowerShell pour l’ensemble du locataire

Cet exemple de commande PowerShell définit le paramètre sur`NativeFileEntryPoints` pour l’ensemble `Disabled` de votre locataire.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Vérifier l’état de votre locataire  

Pour afficher l’état actuel de la stratégie Teams Files de votre locataire, utilisez l’applet de `Get-CsTeamsFilesPolicy` commande .

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Activer ou désactiver le point de chargement de fichier natif

Pour activer ou désactiver le point de chargement de fichier natif pour l’ensemble de votre locataire, définissez le paramètre sur `NativeFileEntryPoints` `Enabled` ou `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Supprimer la stratégie pour vos utilisateurs

Pour supprimer la stratégie Fichiers Teams pour vos utilisateurs, utilisez l’applet de `Remove-CsTeamsFilesPolicy` commande .

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Désactiver NativeFileEntryPoints pour des utilisateurs spécifiques

Vous pouvez également mettre à jour la stratégie Teams Files pour des utilisateurs spécifiques en créant une chaîne de stratégie Teams Files `-Identity` et en affectant la stratégie nouvellement créée aux utilisateurs.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Exemple d’applet de commande de stratégie PowerShell pour des utilisateurs spécifiques

Cet exemple de commande PowerShell crée un nouveau `CsTeamsFilesPolicy` avec le `-Identity` nommé en tant que `UserPolicy` et le `NativeFileEntryPoints` paramètre défini sur `Disabled`.

Lorsqu’un utilisateur reçoit le `CsTeamsFilesPolicy` , `-Identity UserPolicy`ses points d’entrée de fichier natifs sont désactivés.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Affecter une stratégie à l’utilisateur

Une fois que vous avez créé la nouvelle stratégie, vous pouvez affecter cette stratégie aux utilisateurs à l’aide de l’applet de `Grant-CsTeamsFilesPolicy` commande .

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Mettre à jour la stratégie

Si vous devez modifier le paramètre de la nouvelle stratégie de fichiers `UserPolicy`Teams , utilisez l’applet de `Set-CsTeamsFilePolicy` commande .

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Supprimer la stratégie pour la liste complète des utilisateurs

Pour supprimer la stratégie de tous les utilisateurs affectés à la stratégie Fichiers `UserPolicy`Teams , utilisez l’applet de `Remove-CsTeamsFilesPolicy` commande .

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Une fois que vous avez apporté des modifications à la stratégie, prévoyez jusqu’à 12 heures pour que les modifications s’affichent dans les clients Teams des utilisateurs.
