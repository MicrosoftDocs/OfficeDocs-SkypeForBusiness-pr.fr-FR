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
description: Découvrez comment utiliser les contrôles PowerShell pour gérer les Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99af6bc71bdd25375f6165f1e645bf4626dd3123
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039972"
---
# <a name="install-microsoft-teams-powershell-module"></a>Installer Microsoft Teams module PowerShell

Cet article explique comment installer le module Microsoft Teams PowerShell à l’aide de la Galerie PowerShell. Le Microsoft Teams module PowerShell est pris en charge sur toutes Windows plateformes. Mac et Linux ne sont pas pris en charge.

## <a name="requirements"></a>Conditions requises

Microsoft Teams module PowerShell nécessite PowerShell 5.1 ou une plateforme supérieure sur toutes les plateformes. Installez la  [version la plus longue de PowerShell](/powershell/scripting/install/installing-powershell)  disponible pour votre système d’exploitation. 

Pour vérifier votre version de PowerShell, exécutez la commande suivante à partir d’une session PowerShell : 

```powershell
$PSVersionTable.PSVersion 
```
Nous vous recommandons d’utiliser Install-Module cmdlet pour installer Microsoft Teams module PowerShell. 
 
Si la galerie PowerShell (PSGallery) n’est pas configurée comme référentiel approuvé pour **PowerShellGet**, la première fois que vous utilisez PSGallery, vous verrez le message suivant :

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

**Répondez Oui** ou **Oui à Tous pour** poursuivre l’installation.

## <a name="installing-using-the-powershellgallery"></a>Installation à l’aide de PowerShellGallery

Microsoft Teams module PowerShell est actuellement pris en charge pour une utilisation avec PowerShell 5.1 sur Windows. Pour installer le module, suivez ces étapes : 

- Mettre à [jour Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Si vous avez la Windows 10 1607 ou une version supérieure, powerShell 5.1 est déjà installé. 
- Installez [.NET Framework 4.7.2 ou une ultérieure](/dotnet/framework/install). 
- Exécutez la commande suivante pour installer la dernière version de PowerShellGet :
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- Installez le Teams module PowerShell.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>Installation hors connexion 

Dans certains environnements, il n’est pas possible de se connecter à la galerie PowerShell. Dans ces situations, suivez ces étapes [d’installation manuelle](https://aka.ms/psgallery-manualdownload).  

## <a name="sign-in"></a>Connexion

Pour commencer à travailler avec Microsoft Teams module PowerShell, connectez-vous avec vos informations d’identification Azure.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>Mettre à Teams module PowerShell

Pour mettre à jour un module PowerShell, vous devez utiliser la même méthode que lors de l’installation du module. Par exemple, si vous utilisiez le module d’installation à l’origine, vous devez utiliser [Update-Module](/powershell/module/powershellget/update-module) pour obtenir la dernière version.  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue. Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.


## <a name="uninstall-teams-powershell"></a>Désinstaller Teams PowerShell

Pour désinstaller Microsoft Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell et exécutez les commandes suivantes : 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>Étapes suivantes 

Vous êtes maintenant prêt à gérer les Microsoft Teams à l’aide Microsoft Teams PowerShell. [Consultez Gérer Teams avec Teams PowerShell pour](teams-powershell-managing-teams.md) commencer. 

## <a name="related-topics"></a>Sujets associés

[Gestion des Teams à l’Teams PowerShell](teams-powershell-managing-teams.md)

[Teams notes de publication de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams des cmdlet](/powershell/teams/?view=teams-ps)

[Skype Entreprise des cmdlet](/powershell/skype/intro?view=skype-ps)
