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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944091"
---
# <a name="install-microsoft-teams-powershell"></a>Installer Microsoft teams PowerShell

Cet article explique comment installer le module Microsoft teams PowerShell à l’aide de [PowerShellGet](/powershell/scripting/gallery/installing-psget). Ces instructions fonctionnent sur les plateformes [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, MacOS et Windows.

## <a name="requirements"></a>Configuration requise

PowerShell teams fonctionne avec PowerShell 6.2.4 et versions ultérieures sur toutes les plateformes. Elle est également prise en charge dans PowerShell 5,1 sous Windows. Installez la [dernière version de PowerShell](/powershell/scripting/install/installing-powershell) disponible pour votre système d’exploitation. Teams PowerShell n’a aucune configuration requise supplémentaire lorsqu’il est exécuté sur PowerShell 6.2.4 et versions ultérieures.

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

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Répondez `Yes` ou `Yes to All` pour poursuivre l’installation.


## <a name="install-teams-powershell-public-preview"></a>Installer teams public preview

> [!NOTE]
> Si vous utilisez la version bêta publique de teams PowerShell, nous vous conseillons vivement de désinstaller le connecteur Skype entreprise online.

L’installation du module PowerShell public Preview d’teams pour tous les utilisateurs sur un système nécessite des privilèges élevés. Démarrez la session PowerShell à l’aide de l’option **exécuter en tant qu’administrateur** dans Windows ou utilisez la `sudo` commande sur MacOS ou Linux.

Si vous utilisez PowerShell 5,1, vous devez mettre à jour le module **PowerShellGet** auparavant. Après avoir effectué la mise à jour de **PowerShellGet**, fermez et rouvrez une session PowerShell avec élévation de privilèges pour vous assurer que la dernière version de **PowerShellGet** est chargée.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Pour installer Team PowerShell public Preview, exécutez la commande PowerShell ci-dessous.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>Installation de Skype entreprise Online Connector

> [!WARNING]
> Le connecteur Skype entreprise Online fait actuellement partie de Team PowerShell public preview. Après avoir déployé cette fonction dans la version GA de teams PowerShell, le connecteur Skype entreprise Online ne sera plus disponible.

Téléchargez et installez le [module PowerShell Skype entreprise](https://www.microsoft.com/download/details.aspx?id=39366), puis exécutez le code suivant dans PowerShell.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Connexion

Pour commencer à utiliser teams PowerShell, connectez-vous à l’aide de vos informations d’identification Azure.

> [!NOTE]
> Si vous utilisez la version la plus récente de la [version préliminaire public teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
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

## <a name="related-topics"></a>Sujets associés

[Gestion des équipes avec PowerShell teams](teams-powershell-managing-teams.md)

[Notes de publication teams PowerShell](teams-powershell-release-notes.md)

[Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
