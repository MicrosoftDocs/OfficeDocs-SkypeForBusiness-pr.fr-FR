---
title: Désactiver Teams stratégie d’Télécharger fichiers natifs
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Découvrez comment créer, définir, attribuer et ajuster la stratégie Fichiers Teams à l’aide de PowerShell.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192497"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Désactiver Teams stratégie d’Télécharger fichiers natifs

Microsoft Teams utilise OneDrive et SharePoint (ODSP) pour stocker et partager du contenu, mais certaines organisations et utilisateurs peuvent préférer utiliser des fournisseurs de stockage tiers.  

Si votre organisation choisit un tiers pour le stockage de contenu, vous devez désactiver le paramètre dans la ``NativeFileEntryPoints`` stratégie Teams fichiers. Ce paramètre est activé par défaut, ce qui affiche l’option permettant de télécharger du contenu du programme ODSP vers Teams conversations ou canaux.

Cet article vous aide à créer, définir, attribuer et supprimer le paramètre à l’aide ``NativeFileEntryPoints`` de PowerShell.

>[!NOTE]
>Lorsque la stratégie Fichiers Teams est désactivée, les utilisateurs ne voient pas de points d’accès pour OneDrive et SharePoint (ODSP) dans Teams, mais la création de nouvelles équipes et canaux continuera à déclencher la génération de bibliothèques SharePoint correspondantes.

## <a name="prepare-to-update-the-teams-files-policy"></a>Préparer la mise à jour de la stratégie Teams fichiers

### <a name="set-up-microsoft-powershell"></a>Configurer Microsoft PowerShell

Pour l’instant, cette stratégie ne peut pas être modifiée dans le Teams’administration. L’administrateur de Microsoft 365 client de votre organisation devra apporter les modifications à l’aide des cmdlets PowerShell détaillées plus loin dans cet article.

Découvrez comment installer le module PowerShell Teams à l’aide de la Galerie PowerShell en lisant Installer [Microsoft Teams module PowerShell.](teams-powershell-install.md)

Pour installer ou télécharger le module PowerShell Teams, consultez la [Galerie PowerShell pour Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)

Pour plus d’informations sur la façon de configurer PowerShell Teams gestion des Teams, voir Gérer les Teams [avec Microsoft Teams PowerShell.](teams-powershell-managing-teams.md)

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Autoriser les applications tierces dans le Centre Teams’administration

Cette étape n’est pas nécessaire pour modifier la stratégie Fichiers Teams, mais elle est requise lorsque vous êtes prêt à intégrer votre fournisseur de stockage tiers à l’expérience de vos Teams utilisateurs.

Votre Microsoft 365 client doit activer la stratégie « Autoriser les applications tierces » dans le Teams d’administration.

Pour savoir comment autoriser des applications tierces ou personnalisées, voir Gérer les paramètres des applications à l’échelle de l’organisation dans Gérer vos applications dans le [Microsoft Teams d’administration.](/microsoftteams/manage-apps#manage-org-wide-app-settings)

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Désactiver NativeFileEntryPoints pour l’ensemble de votre client

La définition ``-Identity`` du paramètre ``Global`` appliquera les paramètres de stratégie à tous les utilisateurs de votre organisation.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Exemple d’cmdlet de stratégie PowerShell pour l’ensemble du client

Cet exemple de commande PowerShell définira ``NativeFileEntryPoints`` le paramètre sur pour votre client ``Disabled`` entier.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Vérifier l’état de votre client  

Pour afficher l’état actuel de la stratégie Fichiers Teams de votre client, utilisez ``Get-CsTeamsFilesPolicy`` l’cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Activer ou désactiver le point de téléchargement de fichiers natif

Pour activer ou désactiver le point de téléchargement de fichiers natif pour l’ensemble de votre client, définissez le ``NativeFileEntryPoints`` paramètre sur l’un ou ``Enabled`` l’autre. ``Disabled``

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Supprimer la stratégie pour vos utilisateurs

Pour supprimer la stratégie Teams Fichiers de vos utilisateurs, utilisez ``Remove-CsTeamsFilesPolicy`` l’cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Désactiver les nativeFileEntryPoints pour des utilisateurs spécifiques

Vous pouvez également mettre à jour la stratégie Fichiers Teams pour des utilisateurs spécifiques en créant une chaîne de stratégie Fichiers Teams et en attribuant la stratégie nouvellement créée aux ``-Identity`` utilisateurs.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Exemple d’cmdlet de stratégie PowerShell pour des utilisateurs spécifiques

Cet exemple de commande PowerShell crée une commande avec le nom en tant que et ``CsTeamsFilesPolicy`` le paramètre définie sur ``-Identity`` ``UserPolicy`` ``NativeFileEntryPoints`` ``Disabled`` .

Lorsqu’un utilisateur est affecté à l’utilisateur avec, ses points d’entrée de fichier ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` natifs sont désactivés.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Affecter une stratégie à un utilisateur

Une fois que vous avez créé la stratégie, vous pouvez affecter cette stratégie aux utilisateurs à l’aide de ``Grant-CsTeamsFilesPolicy`` l’cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Mettre à jour la stratégie

Si vous devez modifier le paramètre de la nouvelle stratégie Teams ``UserPolicy`` fichiers, utilisez ``Set-CsTeamsFilePolicy`` l’cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Supprimer la stratégie pour la liste complète des utilisateurs

Pour supprimer la stratégie de tous les utilisateurs affectés à la stratégie Teams ``UserPolicy`` Fichiers, utilisez ``Remove-CsTeamsFilesPolicy`` l’cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Une fois que vous avez apporté des modifications à la stratégie, autorisez jusqu’à 12 heures pour que les modifications s’affichent dans les clients Teams utilisateurs.
