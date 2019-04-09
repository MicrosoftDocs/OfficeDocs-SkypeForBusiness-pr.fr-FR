---
title: Installez le module StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment installer et se connecter au module Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555131"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module Microsoft StaffHub PowerShell

> [!IMPORTANT]
> Effet 2019, octobre 1, Microsoft StaffHub sera être retirée. Nous créons StaffHub fonctionnalités dans Microsoft Teams. Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps. StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019. Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes. Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).  

Utilisez les étapes décrites dans cet article pour installer et se connecter au module Microsoft StaffHub PowerShell. Vous aurez besoin pour gérer les StaffHub à l’aide de PowerShell et atteindre vos équipes StaffHub Teams Microsoft.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module Microsoft StaffHub PowerShell

1. Télécharger le [module StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Ouvrez Windows PowerShell 3.0 ou version ultérieure en tant qu’administrateur. Pour ce faire, cliquez sur **Démarrer**, tapez **Windows PowerShell**, avec le bouton droit de **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
3. Exécutez la commande suivante :

    ```
    $ENV:PSModulePath
    ```

4. Vérifiez le chemin d’accès du dossier dans la sortie et vous assurer que tous les dossiers dans le chemin d’accès existent sur votre ordinateur avant de passer à l’étape suivante. Si des dossiers sont manquants, les créer.
5. Exécutez la commande suivante, où &lt;chemin d’accès&gt; est le chemin d’accès dans la sortie de l’étape 2. Par exemple, le chemin d’accès peut ressembler à C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Se connecter au module Microsoft StaffHub PowerShell

1. Exécutez la commande suivante :

    ```
    Connect-StaffHub
    ```

2. Lorsque vous y êtes invité, ouvrez une session tant qu’un administrateur global.

## <a name="related-topics"></a>Rubriques connexes

- [Référence Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams](move-staffhub-teams-to-shifts-in-teams.md)
