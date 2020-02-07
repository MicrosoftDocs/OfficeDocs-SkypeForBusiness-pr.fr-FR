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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75ed6840b409f391b87759e2004c0f1ea475ce69
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827562"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

> [!IMPORTANT]
> À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Suivez les étapes décrites dans cet article pour installer le module Microsoft StaffHub PowerShell et vous y connecter. Vous en aurez besoin pour [migrer vos équipes StaffHub vers teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

1. Téléchargez le [module StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub).
2. Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.
    > [!NOTE]
    > Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).
3. Exécutez la commande suivante :

    ```PowerShell
    $ENV:PSModulePath
    ```
4. Consultez le chemin d’accès du dossier dans la sortie et assurez-vous que tous les dossiers du chemin d’accès existent sur votre ordinateur avant de passer à l’étape suivante. Si les dossiers sont manquants, créez-les.
5. Pour pouvoir installer le module StaffHub PowerShell, procédez comme suit :

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. Exécutez la commande suivante, &lt;où&gt; Path correspond au chemin d’accès dans la sortie de l’étape 3. Par exemple, le chemin d’accès peut ressembler à C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Assurez-vous d’exécuter chaque commande séparément.

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Quittez Windows PowerShell.
8. Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur global, puis exécutez la commande suivante :

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Se connecter au module Microsoft StaffHub PowerShell

1. Exécutez la commande suivante :

    ```PowerShell
    Connect-StaffHub
    ```

2. Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur général.

## <a name="related-topics"></a>Rubriques connexes

- [Référence PowerShell Microsoft StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams](move-staffhub-teams-to-shifts-in-teams.md)
