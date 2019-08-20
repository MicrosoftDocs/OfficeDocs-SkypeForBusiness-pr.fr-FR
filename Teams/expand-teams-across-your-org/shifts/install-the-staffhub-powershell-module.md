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
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464664"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

> [!IMPORTANT]
> À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Suivez les étapes décrites dans cet article pour installer le module Microsoft StaffHub PowerShell et vous y connecter. Vous en aurez besoin pour gérer StaffHub à l’aide de PowerShell et déplacer vos équipes StaffHub vers Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

1. Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.
    > [!NOTE]
    > Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Pour installer la version stable actuelle du module StaffHub PowerShell, exécutez la commande suivante:

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    Vous pouvez exécuter cette commande uniquement si vous avez besoin d’installer la version la plus récente, qui peut avoir une plus grande instabilité par rapport à la version stable actuelle:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > Si vous recevez un message d’erreur lors de l’installation de la version la plus récente en ayant une plus grande instabilité, vous pouvez exécuter:`Install-Module PowershellGet -Force`

3. Le message d’avertissement suivant risque de s’afficher:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

Tapez `Y` , puis `Enter`cliquez sur.
 
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
