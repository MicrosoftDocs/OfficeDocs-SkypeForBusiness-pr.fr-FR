---
title: Installer Microsoft teams PowerShell
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
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814463"
---
# <a name="install-microsoft-teams-powershell"></a>Installer Microsoft teams PowerShell

Cet article explique comment installer le module Microsoft teams PowerShell à l’aide de [PowerShellGet](/powershell/scripting/gallery/installing-psget). Ces instructions fonctionnent sur les plateformes [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, MacOS et Windows.

## <a name="requirements"></a>Configuration requise

Teams PowerShell nécessite PowerShell 5,1 ou une version ultérieure sur toutes les plateformes. Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation.

> [!WARNING]
> Il existe des problèmes connus dans PowerShell 7 et teams PowerShell. Pour une utilisation optimale, nous vous recommandons d’utiliser PowerShell 5,1.

## <a name="install-the-teams-powershell-module"></a>Installer le module PowerShell teams

> [!NOTE]
> Pour une utilisation optimale, utilisez les modules de disponibilité générale (GA) ou d’aperçu public. Ils ne sont pas destinés à être utilisés ensemble.


Utilisez les applets de cmdlet **PowerShellGet** pour installer le module teams PowerShell. L’installation du module pour tous les utilisateurs sur un système nécessite des privilèges élevés. Démarrez la session PowerShell à l’aide de l’option **exécuter en tant qu’administrateur** dans Windows ou utilisez la `sudo` commande sur MacOS ou Linux :

```powershell
Install-Module MicrosoftTeams
```

Par défaut, la Galerie PowerShell (PSGallery) n’est pas configurée en tant que référentiel approuvé pour **PowerShellGet**. Lorsque vous utilisez PSGallery pour la première fois, le message suivant s’affiche :

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Répondez **Yes** ou **Yes à All** pour continuer l’installation.


## <a name="install-teams-powershell-public-preview"></a>Installer teams public preview

> [!NOTE]
> Si vous utilisez la version bêta publique de teams PowerShell, nous vous conseillons vivement de désinstaller le connecteur Skype entreprise online.

L’installation du module PowerShell public Preview d’teams pour tous les utilisateurs sur un système nécessite des privilèges élevés. Démarrez la session PowerShell à l’aide de l’option **exécuter en tant qu’administrateur** dans Windows ou utilisez la `sudo` commande sur MacOS ou Linux.

Si vous utilisez PowerShell 5,1, vous devez mettre à jour le module **PowerShellGet** auparavant. Après avoir effectué la mise à jour de **PowerShellGet**, fermez et rouvrez une session PowerShell avec élévation de privilèges pour vous assurer que la dernière version de **PowerShellGet** est chargée.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Pour installer Team PowerShell public Preview, exécutez la commande PowerShell ci-dessous.

> [!NOTE]
> Pour savoir comment accéder à la version d’évaluation la plus récente dans la [Galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou dans PowerShell, exécutez « Find-module MicrosoftTeams-AllowPrerelease ».

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Installation de Skype entreprise Online Connector

> [!NOTE]
>
> Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.
> Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Connexion

Pour commencer à utiliser teams PowerShell, connectez-vous à l’aide de vos informations d’identification Azure.

> [!NOTE]
> Si vous utilisez la version la plus récente de la [version préliminaire public teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Mettre à jour PowerShell teams

Pour mettre à jour PowerShell Teams, ouvrez une nouvelle invite de commandes PowerShell avec élévation de privilèges et exécutez la commande suivante :

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Si teams PowerShell a déjà été importé dans votre session PowerShell, la mise à jour du module échoue. Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de privilèges.


## <a name="uninstall-teams-powershell"></a>Désinstaller teams PowerShell



Pour désinstaller teams PowerShell, ouvrez une nouvelle invite de commandes PowerShell avec élévation de privilèges et exécutez la commande suivante :

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Si teams PowerShell a déjà été importé dans votre session PowerShell, la désinstallation du module échoue. Fermez PowerShell et rouvrez une nouvelle session PowerShell avec élévation de privilèges.

## <a name="next-steps"></a>Étapes suivantes

Vous êtes maintenant prêt à gérer teams à l’aide de teams PowerShell. Pour commencer, voir [gestion d’équipes avec teams PowerShell](teams-powershell-managing-teams.md) .

## <a name="related-topics"></a>Voir aussi

[Gestion des équipes avec PowerShell teams](teams-powershell-managing-teams.md)

[Notes de publication teams PowerShell](teams-powershell-release-notes.md)

[Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
