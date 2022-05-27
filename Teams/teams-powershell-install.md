---
title: Installer Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les contrôles PowerShell pour gérer Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682005"
---
# <a name="install-microsoft-teams-powershell-module"></a>Installer Microsoft Teams module PowerShell

Cet article explique comment installer le module PowerShell Microsoft Teams à l’aide de PowerShell Gallery. Le module PowerShell Microsoft Teams est pris en charge sur toutes les plateformes Windows. Mac et Linux ne sont pas pris en charge.

## <a name="requirements"></a>Conditions requises

Microsoft Teams module PowerShell nécessite PowerShell 5.1 ou version ultérieure sur toutes les plateformes. Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation.

Pour vérifier votre version de PowerShell, exécutez la commande suivante à partir d’une session PowerShell :

```powershell
$PSVersionTable.PSVersion
```

Nous vous recommandons d’utiliser l’applet de commande Install-Module pour installer le module PowerShell Microsoft Teams.

Si PowerShell Gallery (PSGallery) n’est pas configuré en tant que référentiel approuvé pour **PowerShellGet**, la première fois que vous utilisez PSGallery, le message suivant s’affiche :

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Répondez **Oui** ou **Oui à tous** pour poursuivre l’installation.

## <a name="installing-using-the-powershellgallery"></a>Installation à l’aide de PowerShellGallery

Microsoft Teams module PowerShell est actuellement pris en charge pour une utilisation avec PowerShell 5.1 sur Windows. Procédez comme suit pour installer le module :

- Mise à jour vers [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Si vous utilisez Windows 10 version 1607 ou ultérieure, PowerShell 5.1 est déjà installé.
- Installez [.NET Framework 4.7.2](/dotnet/framework/install) ou version ultérieure.
- Exécutez la commande suivante pour installer la dernière version de PowerShellGet :

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Installez le module PowerShell Teams.

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>Installation hors connexion

Dans certains environnements, il n’est pas possible de se connecter au PowerShell Gallery. Dans ce cas, suivez ces [étapes d’installation manuelle](https://aka.ms/psgallery-manualdownload).

## <a name="sign-in"></a>Connexion

Pour commencer à utiliser Microsoft Teams module PowerShell, connectez-vous avec vos informations d’identification Azure.

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>Mettre à jour Teams module PowerShell

Pour mettre à jour un module PowerShell, vous devez utiliser la même méthode que celle utilisée pour installer le module. Par exemple, si vous avez utilisé Install-Module à l’origine, vous devez utiliser [Update-Module](/powershell/module/powershellget/update-module) pour obtenir la dernière version.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue. Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de privilèges.

## <a name="uninstall-teams-powershell"></a>Désinstaller Teams PowerShell

Pour désinstaller Microsoft Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell et exécutez ce qui suit :

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>Étapes suivantes

Vous êtes maintenant prêt à gérer Microsoft Teams à l’aide de Microsoft Teams PowerShell. Pour commencer, consultez [Gestion des Teams avec Teams PowerShell](teams-powershell-managing-teams.md).

## <a name="related-topics"></a>Sujets associés

[Gestion des Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[notes de publication Teams PowerShell](teams-powershell-release-notes.md)

[référence de l’applet de commande Microsoft Teams](/powershell/teams/)

[référence de l’applet de commande Skype Entreprise](/powershell/skype/intro)
