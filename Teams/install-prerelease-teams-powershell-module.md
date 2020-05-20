---
title: Installer la version précommerciale du module PowerShell teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Pour installer la version préliminaire du module PowerShell teams à partir de la Galerie de tests PowerShell, procédez comme suit.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321767"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>Installer la version précommerciale du module PowerShell teams

Cet article décrit comment installer la dernière version précommerciale du module teams PowerShell à partir de la [Galerie de tests PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). Vous aurez besoin de la version préliminaire du module PowerShell teams dans les scénarios où les cmdlets de gestion d’une fonctionnalité d’équipes ne sont pas prises en charge dans la version en général disponible du module et sont uniquement disponibles dans la version préliminaire.

Pour installer la dernière version préliminaire du module PowerShell teams à partir de la Galerie de tests PowerShell, procédez comme suit.

> [!NOTE]
> N’installez pas le module PowerShell teams à partir de la Galerie de tests PowerShell côte à côte avec une version du module dans la [Galerie PowerShell publique](https://www.powershellgallery.com/packages/MicrosoftTeams/). Procédez comme suit pour désinstaller d’abord le module PowerShell teams dans la Galerie PowerShell public, puis installez la dernière version du module à partir de la Galerie de tests PowerShell.

1. Fermez toutes les sessions PowerShell existantes.
2. Démarrez une nouvelle instance du module Windows PowerShell.
3. Pour désinstaller le module teams PowerShell de la Galerie public PowerShell, exécutez la commande suivante :

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Fermez toutes les sessions PowerShell existantes.
5. Démarrez de nouveau le module Windows PowerShell, puis exécutez la commande suivante pour inscrire la Galerie de tests PowerShell en tant que source de confiance :

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Pour installer le dernier module PowerShell teams à partir de la Galerie de tests PowerShell, exécutez la commande suivante :

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Effectuer une mise à jour vers la dernière version du module PowerShell teams à partir de la Galerie de tests PowerShell

Si vous avez déjà installé le module teams PowerShell à partir de la Galerie de tests PowerShell, procédez comme suit pour effectuer une mise à jour vers la dernière version.

1. Fermez toutes les sessions PowerShell existantes.
2. Démarrez une nouvelle instance du module Windows PowerShell.
3. Exécutez la commande suivante pour mettre à jour la version actuellement installée du module PowerShell teams à partir de la Galerie de tests PowerShell :

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
