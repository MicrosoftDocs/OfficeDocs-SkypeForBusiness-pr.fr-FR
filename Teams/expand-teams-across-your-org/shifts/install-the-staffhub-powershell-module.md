---
title: Installer le module PowerShell Microsoft StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment installer le module Microsoft StaffHub PowerShell et vous y connecter.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246178"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

> [!IMPORTANT]
> À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Suivez les étapes décrites dans cet article pour installer le module Microsoft StaffHub PowerShell et vous y connecter. Vous en aurez besoin pour gérer StaffHub à l’aide de PowerShell et déplacer vos équipes StaffHub vers Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

1. Téléchargez le [module StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.
    > [!NOTE]
    > Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
3. Exécutez la commande suivante :

    ```
    $ENV:PSModulePath
    ```
    

4. Consultez le chemin d’accès du dossier dans la sortie et assurez-vous que tous les dossiers du chemin d’accès existent sur votre ordinateur avant de passer à l’étape suivante. Si les dossiers sont manquants, créez-les.
5. Pour pouvoir installer le module StaffHub PowerShell, procédez comme suit:

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. Exécutez la commande suivante, &lt;où&gt; Path correspond au chemin d’accès dans la sortie de l’étape 2. Par exemple, le chemin d’accès peut ressembler à C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Assurez-vous d’exécuter chaque commande séparément.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. Quittez Windows PowerShell.
8. Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur global, puis exécutez la commande suivante:

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Se connecter au module Microsoft StaffHub PowerShell

1. Exécutez la commande suivante :

    ```
    Connect-StaffHub
    ```

2. Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur général.

## <a name="related-topics"></a>Voir aussi

- [Référence PowerShell Microsoft StaffHub](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams](move-staffhub-teams-to-shifts-in-teams.md)
