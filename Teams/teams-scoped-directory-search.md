---
title: Utiliser la recherche d’annuaire étendue Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser la recherche dans l’annuaire d’étendues de Microsoft teams pour fournir des vues personnalisées de l’annuaire.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b06e675e93dd022847fc7af202045c3ecdebe63
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341772"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Utiliser la recherche d’annuaire étendue Microsoft Teams

La fonction de recherche dans l’arborescence de Microsoft teams permet aux organisations de créer des frontières virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation. 

Microsoft teams permet aux organisations d’offrir des vues personnalisées de l’annuaire à leurs utilisateurs. Microsoft teams utilise des [stratégies de barrage des informations](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) pour prendre en charge ces affichages personnalisés. Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour lancer une discussion ou ajouter des membres à une équipe) seront définis dans l’étendue conformément aux stratégies configurées. Les utilisateurs ne seront pas en mesure de rechercher ou de découvrir les équipes lorsque la recherche avec l’étendue est en vigueur. 

> [!NOTE]
> Dans les environnements Exchange hybrides, cette fonctionnalité fonctionne uniquement avec les boîtes aux lettres Exchange Online, et non avec les boîtes aux lettres locales.

## <a name="when-should-you-use-scoped-directory-searches"></a>Quand utiliser les recherches dans l’annuaire avec une application ?

Les scénarios qui s’offrent à vous pour les recherches dans l’annuaire sont similaires aux scénarios de stratégie de carnet d’adresses. Par exemple, vous pouvez utiliser la recherche dans l’annuaire avec l’étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants. 
 
Pour plus d’informations sur l’utilisation des stratégies de carnet d’adresses, voir [stratégies de protection des informations dans Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).

> [!IMPORTANT]
> Les politiques du carnet d’adresses fournissent uniquement une séparation virtuelle des utilisateurs du point de vue du répertoire. Les utilisateurs peuvent toujours lancer des communications avec d’autres personnes en leur fournissant des adresses de messagerie complètes. Il est également important de noter que toutes les données utilisateur qui ont déjà été mises en cache avant d’appliquer les stratégies de carnet d’adresses nouvelles ou mises à jour restent disponibles pour les utilisateurs pendant 30 jours maximum.

## <a name="turn-on-scoped-directory-search"></a>Activez la recherche dans l’annuaire avec étendue

1. Utiliser des stratégies de cloisonnement des informations pour configurer votre organisation en sous-groupes virtuels. Pour plus d’informations, consultez [définir des stratégies de barrière des informations](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).

2. Dans le centre d’administration de Microsoft Teams, sélectionnez > **paramètres d’équipe** **des paramètres à l’échelle**de l’organisation.

3. Sous **recherche**, en regard de la **zone Rechercher dans l’annuaire dans teams à l’aide d’une stratégie de carnet d’adresses Exchange (ABP)**, activez le bouton **bascule.**

    ![Recherche dans l’annuaire dans l’étendue dans le centre d’administration Microsoft teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> La réplication de ce changement peut durer jusqu’à 24 heures.
