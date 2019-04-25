---
title: Gérer la découverte des équipes privées dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment contrôler si les équipes privées pouvant être découvert par les utilisateurs de Microsoft Teams via les suggestions dans les résultats de recherche et de la galerie de l’équipe.
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262753"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Gérer la découverte des équipes privées dans Microsoft Teams

Les propriétaires de l’équipe et les administrateurs peuvent contrôler si les équipes privées pouvant être découvert par les utilisateurs Microsoft Teams dans votre organisation. Lorsqu’une équipe privée est détectable, il s’affiche dans les résultats de recherche et est inclus dans les propositions dans la galerie de l’équipe avec des équipes publics dans les équipes. Cela facilite pour les utilisateurs à rechercher pour trouver les équipes privés qu’ils souhaitent joindre. Les utilisateurs peuvent demander à participer à une équipe privée qui un propriétaire de l’équipe puis approuver ou refuser.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Vue d’ensemble des équipes publics privés et les équipes découverte dans les équipes

La plupart des organisations ont les types suivants d’équipes - équipes publics détectables privés et les équipes-découvrable équipes privés.

![Galerie d’équipe](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Équipes publics

Équipes publics sont disponibles pour tous les utilisateurs de votre organisation à rejoindre. Les équipes publics sont visibles par tout le monde dans la galerie des équipes et les utilisateurs peuvent participer à une équipe publique sans avoir à obtenir l’approbation du propriétaire de l’équipe. Exemples d’équipes publics une équipe pour discuter des news dans une équipe pour covoiturage personnes fonctionne, une équipe pour obtenir les commentaires dogfood pour vos produits et technologie.

### <a name="discoverable-private-teams"></a>Équipes privées détectables

Détectables équipes privées ne peuvent être jointe lorsque le propriétaire de l’équipe ajoute les utilisateurs. Lorsque vous effectuez une équipe privée détectable, l’équipe est inclus dans la liste des équipes suggérées et les résultats de la recherche dans la galerie des équipes. Utilisez des équipes privées détectables pour les projets et les groupes de votre organisation tout le monde connaît et où accéder à des conversations et les fichiers de l’équipe doivent être contrôlées. Une équipe pour votre service des ressources humaines, une équipe pour tous les gestionnaires de votre organisation et exemples une équipe pour un responsable et leurs collaborateurs.

### <a name="non-discoverable-private-teams"></a>Équipes privées non-découvrable

Non-découvrable équipes privées ne peuvent être jointe lorsque le propriétaire de l’équipe ajoute les utilisateurs. Lorsque vous effectuez une équipe privée non détectables, elle a masqué dans la liste des équipes suggérées et supprimées des résultats de recherche dans la galerie des équipes. Utilisez-découvrable équipes de collaborer sur des sujets sensibles et hautement confidentielles. Une équipe pour discuter d’une acquisition à venir et exemples une équipe pour discuter de changement de direction stratégique de votre organisation.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Définir si les nouvelles équipes privées sont accessibles

Lorsqu’un propriétaire de l’équipe crée une équipe privée, ils peuvent choisir de rendre accessibles en configurant le paramètre de découverte de l’équipe. Par défaut, nouvelles équipes privées sont utilisables dans une requête et facilement identifiables. Si le propriétaire de l’équipe ne veut pas l’équipe privé s’affiche dans les résultats de recherche et les suggestions, ils peuvent désactiver le paramètre en sélectionnant **Modifier les paramètres** en regard de **cette équipe est disponible pour la recherche et facilement identifiables**.

![paramètre de découverte de nouvelles équipes privées](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Définir si les équipes privées existantes peuvent être découverts

Propriétaires de l’équipe peuvent définir le paramètre de découverte pour une équipe privée existante directement dans les paramètres de l’équipe et les administrateurs peuvent le faire à l’aide de PowerShell.

### <a name="in-team-settings"></a>Dans les paramètres d’équipe

Dans les équipes, accédez à l’équipe privée, cliquez sur **plus d’options ˙˙˙** > **l’équipe de gestion**. Sous l’onglet **paramètres** , développez la **détection de l’équipe**, puis désactivez ou activez la case à cocher **Activer la détectabilité** .

![paramètre de découverte pour les équipes privées existantes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>À l’aide de PowerShell

Pour désactiver ou activer le paramètre de découverte pour une équipe privée existante, utilisez l’applet de commande **Set-équipe** . Voici un exemple illustrant comment rendre une équipe détectable :

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
Vous pouvez utiliser cette applet de commande dans un script pour définir le paramètre de découverte des équipes privées existantes en bloc.

## <a name="set-whether-users-can-discover-private-teams"></a>Définir si les utilisateurs peuvent découvrir des équipes privées

En tant qu’administrateur, vous pouvez également contrôler les utilisateurs de votre organisation sont autorisés à découvrir des équipes privées dans les résultats de recherche et les suggestions équipes. Créer une stratégie à l’aide de l’applet de commande **New-CsTeamsChannelsPolicy** , puis affecter la stratégie aux utilisateurs.
 
Définissez le paramètre **AllowPrivateTeamDiscovery** sur **true** pour autoriser les utilisateurs auxquels la stratégie à voir détectables équipes privées dans les résultats de recherche et les suggestions. Définissant le paramètre **AllowPrivateTeamDiscovery** sur **false** supprime toutes les équipes privées accessibles à partir des résultats de recherche et des suggestions pour les utilisateurs qui sont affectés à la stratégie.

Par défaut, **AllowPrivateTeamDiscovery** est définie sur **true** pour tous les utilisateurs d’une organisation.

Dans cet exemple, nous créons une stratégie nommée VendorPolicy qui empêche les utilisateurs de la découverte des équipes privées apportées détectables, puis nous attribuer la stratégie à un utilisateur nommé vendoruser1. 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> Privée équipes qui ne sont pas accessibles ne sont jamais indiqués dans les résultats de recherche et de vos suggestions, quel que soit le paramètre de stratégie. Par exemple, si vous désactivez le paramètre de découverte pour une équipe privé, les utilisateurs ne peuvent pas détecter l’équipe, même si le paramètre **AllowPrivateTeamDiscovery** est défini sur **true** dans le paramètre de stratégie pour les utilisateurs.

## <a name="related-topics"></a>Voir aussi
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)