---
title: Gérer la découverte des équipes privées dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez à contrôler si les équipes privées peuvent être détectées par les utilisateurs de Microsoft teams par le biais de suggestions dans la Galerie d’équipe et les résultats de recherche.
ms.openlocfilehash: 0d068de791afd32d38b2b49ada275c6e3eced41c
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836514"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Gérer la découverte des équipes privées dans Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Les administrateurs et les propriétaires d’équipe peuvent contrôler si des équipes privées peuvent être découvertes par les utilisateurs de Microsoft teams au sein de votre organisation. Lorsqu’une équipe privée est détectable, elle apparaît dans les résultats de la recherche et est incluse dans les suggestions de la Galerie d’équipes et dans les équipes publiques de teams. Cela permet aux utilisateurs de rechercher et d’accéder facilement aux équipes privées qu’ils souhaitent rejoindre. Les utilisateurs peuvent demander à rejoindre une équipe privée, et le propriétaire d’une équipe peut ensuite approuver ou refuser la demande.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Vue d’ensemble des équipes publiques, des équipes privées et de la découverte dans teams

La plupart des organisations ont les types d’équipes suivants : équipes publiques, équipes privées détectable et équipes privées non détectablees.

![Capture d’écran de la Galerie d’équipes](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Équipes publiques

Les équipes publiques sont disponibles pour permettre à tous les utilisateurs de votre organisation de participer. Les équipes publiques sont visibles par tout le monde dans la Galerie d’équipes, et les utilisateurs peuvent rejoindre une équipe publique sans avoir besoin d’obtenir l’approbation du propriétaire de l’équipe. Par exemple, les équipes publiques incluent une équipe pour discuter des nouvelles technologiques, une équipe pour obtenir des commentaires sur vos produits et une équipe pour les personnes carpooling de travailler.

### <a name="discoverable-private-teams"></a>Équipe privée détectable

Les équipes privées détectables ne peuvent être jointes que lorsque le propriétaire de l’équipe y ajoute des utilisateurs. Lorsque vous rendez une équipe privée détectable, l’équipe est incluse dans la liste des équipes et des résultats de recherche suggérés dans la Galerie d’équipes. Utilisez les équipes privées détectables pour les projets et groupes de votre organisation que tout le monde a pris en considération et où l’accès à des conversations et des fichiers dans l’équipe doit être contrôlé. Les exemples incluent une équipe pour votre service de ressources humaines, une équipe pour tous les responsables de votre organisation et une équipe pour un responsable et leurs rapports directs.

### <a name="non-discoverable-private-teams"></a>Équipes privées non détectable

Les équipes privées non détectablees ne peuvent être jointes que lorsque le propriétaire de l’équipe y ajoute des utilisateurs. Lorsque vous rendez une équipe privée non détectable, celle-ci est masquée dans la liste des équipes suggérées et supprimées des résultats de recherche dans la Galerie d’équipes. Utilisez des équipes non détectable pour collaborer sur des sujets sensibles et hautement confidentiels. Les exemples incluent une équipe pour discuter d’une prochaine acquisition et une équipe pour discuter d’une modification apportée à la direction stratégique de votre organisation.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Définir si de nouvelles équipes privées peuvent être découvertes

Lorsque le propriétaire d’une équipe crée une équipe privée, il peut choisir de le rendre détectable en configurant le paramètre de découverte de l’équipe. Par défaut, les nouvelles équipes privées peuvent être recherchées et détectables. Si le propriétaire de l’équipe ne souhaite pas qu’elle apparaisse dans les résultats de recherche et les suggestions, le propriétaire peut désactiver le paramètre en sélectionnant l' **option modifier les paramètres** en regard de **cette équipe peut effectuer une recherche ou une découverte**.

![Capture d’écran du paramètre de découverte pour les nouvelles équipes privées](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Définir si les équipes privées existantes sont détectables

Les propriétaires d’une équipe peuvent définir le paramètre de découverte pour une équipe privée existante directement dans les paramètres de l’équipe et les administrateurs peuvent le faire à l’aide de PowerShell.

### <a name="in-team-settings"></a>Dans les paramètres d’équipe

Dans Microsoft Teams, accédez à l’équipe privée, cliquez sur **plus d’options** > **gérer l’équipe**. Dans l’onglet **paramètres** , développez **découverte d’équipe**, puis cochez ou décochez la case Activer la **détectabilité** .

![Capture d’écran du paramètre de découverte pour les équipes privées existantes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez l’applet de connexion **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** pour désactiver ou activer le paramètre de découverte pour une équipe privée existante. Voici un exemple illustrant comment rendre une équipe plus détectable :
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
Vous pouvez utiliser cette applet de cmdlet dans un script pour définir le paramètre de découverte des équipes privées existantes en bloc.

## <a name="set-whether-users-can-discover-private-teams"></a>Définir si les utilisateurs peuvent découvrir les équipes privées

En tant qu’administrateur, vous pouvez également contrôler les utilisateurs de votre organisation qui sont autorisés à découvrir des équipes privées dans les résultats de recherche et les suggestions dans Teams. Créez une stratégie à l’aide de l’applet de **[nouvelle applet de nouveau-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** , puis affectez la stratégie aux utilisateurs.
 
Définissez le paramètre **AllowPrivateTeamDiscovery** sur **true** pour autoriser les utilisateurs auxquels une stratégie est affectée pour voir les équipes privées détectables dans les résultats de recherche et les suggestions. Le fait de définir le paramètre **AllowPrivateTeamDiscovery** sur **false** entraîne la suppression de toutes les équipes privées détectable des résultats de la recherche et des suggestions pour les utilisateurs auxquels cette stratégie est affectée.

Par défaut, **AllowPrivateTeamDiscovery** est défini sur **true** pour tous les utilisateurs au sein d’une organisation.

Dans cet exemple, nous créons une stratégie nommée VendorPolicy qui empêche les utilisateurs de découvrir toutes les équipes privées découvertes, puis nous affectons la stratégie à un utilisateur nommé vendoruser1.
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> Les équipes privées qui ne sont pas détectables ne sont jamais affichées dans les résultats de recherche et les suggestions, indépendamment du paramètre de stratégie. Par exemple, si vous désactivez le paramètre de découverte pour une équipe privée, les utilisateurs ne parviennent pas à découvrir l’équipe, même si le paramètre **AllowPrivateTeamDiscovery** est défini sur **true** dans le paramètre de stratégie pour ces utilisateurs.

## <a name="related-topics"></a>Rubriques connexes
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
