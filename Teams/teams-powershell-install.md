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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768337"
---
# <a name="install-microsoft-teams-powershell"></a>Installer Microsoft Teams PowerShell

Cet article explique comment installer le module Microsoft Teams PowerShell à l'aide [de PowerShellGet.](/powershell/scripting/gallery/installing-psget) Ces instructions s'utilisent sur les plateformes [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS et Windows.

## <a name="requirements"></a>Conditions requises

Teams PowerShell requiert PowerShell 5.1 ou une plateforme supérieure sur toutes les plateformes. Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d'exploitation.

> [!NOTE]
> Pour une expérience la plus agréable possible, nous vous recommandons d'utiliser PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Installer le module Teams PowerShell

> [!NOTE]
> Pour une expérience accrue, utilisez les modules Disponibilité générale (GA) ou Prévisualisation publique, et non les deux. Ils n'ont pas l'intention de collaborer.


Utilisez les **cmdlets PowerShellGet** pour installer le module Teams PowerShell. L'installation du module pour tous les utilisateurs sur un système nécessite des privilèges élevés. Démarrez la session PowerShell à l'aide **de l'outil** Exécuter en tant qu'administrateur dans Windows ou utilisez la `sudo` commande sur macOS ou Linux :

```powershell
Install-Module MicrosoftTeams
```

Par défaut, la Galerie PowerShell (PSGallery) n'est pas configurée comme référentiel fiable **pour PowerShellGet.** La première fois que vous utilisez PSGallery, vous verrez le message suivant :

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Répondez **Oui** **ou Oui à Tous pour** poursuivre l'installation.

## <a name="sign-in"></a>Connexion

Pour commencer à travailler avec Teams PowerShell, connectez-vous avec vos informations d'identification Azure.

> [!NOTE]
> Si vous utilisez la dernière version d'aperçu [public de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n'avez pas besoin d'installer Skype Entreprise Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Se connectez à l'aide de l'authentification multifacteur et de l'authentification moderne

 Si votre compte utilise l'authentification multifacteur, utilisez les étapes de cette section.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>Mettre à jour Teams PowerShell

Pour mettre à jour Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez la commande suivante :

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Si Teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue. Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.


## <a name="uninstall-teams-powershell"></a>Désinstaller Teams PowerShell

Pour désinstaller Teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de élévation de niveau, puis exécutez l'une des commandes suivantes :

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Si Teams PowerShell a déjà été importé dans votre session PowerShell, la désinstallation du module échoue. Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de élévation de puissance.

## <a name="install-teams-powershell-public-preview"></a>Installer la prévisualisation publique de Teams PowerShell

> [!NOTE]
> Si vous utilisez la version d'aperçu public de Teams PowerShell, nous vous recommandons vivement de désinstaller Skype Entreprise Online Connector.

L'installation du module d'aperçu public Teams PowerShell pour tous les utilisateurs sur un système nécessite des privilèges élevés. Démarrez la session PowerShell à l'aide **de l'outil** Exécuter en tant qu'administrateur dans Windows ou utilisez la `sudo` commande sur macOS ou Linux.

Si vous utilisez PowerShell 5.1, vous devez mettre à jour le module **PowerShellGet** au préalable. Après avoir mis **à jour PowerShellGet,** fermez et rouvrez une session PowerShell avec élévation de charge pour vous assurer que la dernière **version de PowerShellGet** est chargée.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Pour installer la prévisualisation publique de Teams PowerShell, exécutez la commande PowerShell ci-dessous.

> [!NOTE]
> Vous pouvez trouver la dernière version d'aperçu dans la [galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou dans PowerShell en exécutant « Find-Module MicrosoftTeams -AllowPrerelease -AllVersions »

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>Étapes suivantes

Vous êtes maintenant prêt à gérer Teams à l'aide de Teams PowerShell. Consultez [Gérer les équipes avec Teams PowerShell](teams-powershell-managing-teams.md) pour commencer.

## <a name="related-topics"></a>Sujets associés

[Gestion des équipes avec Teams PowerShell](teams-powershell-managing-teams.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Référence de l'cmdlet Microsoft Teams](/powershell/teams/?view=teams-ps)

[Référence de l'cmdlet Skype Entreprise](/powershell/skype/intro?view=skype-ps)
