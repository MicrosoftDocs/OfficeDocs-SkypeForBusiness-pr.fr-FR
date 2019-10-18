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
description: Découvrez comment installer la version préliminaire du module Microsoft StaffHub PowerShell et vous y connecter.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569209"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

> [!IMPORTANT]
> À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Suivez les étapes décrites dans cet article pour installer et vous connecter à la version préliminaire du module Microsoft StaffHub PowerShell. Vous en aurez besoin pour [migrer vos équipes StaffHub vers teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>Installez la version préliminaire du module Microsoft StaffHub PowerShell.

1. Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.
    > [!NOTE]
    > Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Pour installer la version préliminaire du module StaffHub PowerShell, exécutez la commande suivante :

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. Le message d’avertissement suivant risque de s’afficher :

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    Tapez `Y`, puis cliquez sur `Enter`.
 
4. Quittez Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Se connecter au module Microsoft StaffHub PowerShell

1. Exécutez la commande suivante :

    ```
    Connect-StaffHub
    ```

2. Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur général.

## <a name="related-topics"></a>Voir aussi

- [Référence PowerShell Microsoft StaffHub](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams](move-staffhub-teams-to-shifts-in-teams.md)
