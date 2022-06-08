---
title: Déployer des équipes à grande échelle pour les employés de première ligne dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déployer des équipes à grande échelle pour les employés de première ligne de votre organisation.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947227"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Déployer des équipes à grande échelle pour les employés de première ligne dans Microsoft Teams

> [!NOTE]
> Cette fonctionnalité est actuellement en préversion privée. Si vous souhaitez participer à la préversion privée, contactez-nous à [dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Présentation
 
Votre organisation peut avoir un grand nombre d’équipes que vous utilisez pour favoriser la communication et la collaboration entre votre personnel de première ligne, qui sont réparties dans différents magasins, emplacements et rôles. Actuellement, il n’existe pas de solution simple pour déployer, configurer et gérer ces équipes et ces utilisateurs à grande échelle.

Nous créons une solution pour permettre aux administrateurs de déployer et de gérer des équipes à grande échelle.

Voici une vue d’ensemble des fonctionnalités disponibles aujourd’hui pour la création et la gestion d’un grand nombre d’équipes à la fois et de ce que nous prévoyons dans un avenir proche.

||Disponible aujourd’hui |Plus tard en 2022  |
|---------|---------|---------|
|**Nombre d’équipes que vous pouvez créer par lot**|Jusqu’à 100 |Jusqu’à 500|
|**Nombre d’utilisateurs que vous pouvez ajouter par équipe**|Jusqu’à 25|Jusqu’à 25|

Le déploiement d’équipes à grande échelle vous permet d’effectuer les opérations suivantes :

- Créez des équipes à l’aide de modèles prédéfinifiés ou de vos propres modèles personnalisés.
- Ajoutez des utilisateurs aux équipes en tant que propriétaires ou membres.
- Gérez les équipes à grande échelle en ajoutant ou en supprimant des utilisateurs des équipes existantes.
- Restez informé par e-mail, y compris la saisie semi-automatique, l’état et les erreurs (le cas échéant). Les propriétaires et les membres de l’équipe sont avertis.

## <a name="how-to-deploy-teams-at-scale"></a>Comment déployer des équipes à grande échelle

> [!NOTE]
> Avant de déployer vos équipes, assurez-vous que tous les propriétaires d’équipes disposent d’une licence Teams.

Suivez ces étapes pour déployer un grand nombre d’équipes à la fois.

Vous utilisez l’applet ```New-CsBatchTeamsDeployment``` de commande pour envoyer un lot d’équipes à créer. Un ID d’orchestration est généré pour chaque lot. Vous pouvez ensuite utiliser l’applet ```Get-CsBatchTeamsDeployment``` de commande pour suivre la progression et l’état de chaque lot.

1. Installez PowerShell version 7 ou ultérieure. Pour obtenir des conseils pas à pas, consultez [l’installation de PowerShell sur Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Exécutez PowerShell en mode administrateur.
1. Exécutez ce qui suit pour désinstaller tout module Teams PowerShell précédemment installé.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Si vous recevez un message d’erreur, vous êtes déjà défini. Passez à l’étape suivante.
1. Téléchargez et installez la [dernière version du module Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Exécutez les étapes suivantes pour vous connecter à Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur.

1. Exécutez la commande suivante pour obtenir une liste des commandes dans le module Teams PowerShell.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Vérifiez cela ```New-CsBatchTeamsDeployment``` et ```Get-CsBatchTeamsDeployment``` sont répertoriés.

1. Exécutez la commande suivante pour déployer un lot d’équipes. Vous pouvez entrer jusqu’à cinq adresses e-mail dans le paramètre **UsersToNotify** .

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. Exécutez ce qui suit pour vérifier l’état du lot que vous avez envoyé.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Nous faire part de vos commentaires

Nous apprécions vos commentaires. Facilité d’utilisation, fiabilité, performances&mdash;nous accueillons tout !

Envoyez [un e-mail dscale@microsoft.com](mailto:dscale@microsoft.com) et incluez votre ID d’orchestration et votre fichier d’erreur, si vous l’avez.

## <a name="related-articles"></a>Articles connexes

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
