---
title: Utiliser la recherche d’annuaire étendue Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser Microsoft Teams dans l’annuaire pour fournir des affichages personnalisés de l’annuaire.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f69a4d94743e443fd20f53f5eb35d26b6d69e3b3
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046230"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Utiliser la recherche d’annuaire étendue Microsoft Teams

Microsoft Teams dans l’étendue de la recherche dans l’annuaire permet aux organisations de créer des limites virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation. 

Microsoft Teams organisations de fournir des affichages personnalisés de l’annuaire à leurs utilisateurs. Microsoft Teams utilise les [stratégies de la](/microsoft-365/compliance/information-barriers) barrière des informations pour prendre en charge ces affichages personnalisés. Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour démarrer une conversation ou pour ajouter des membres à une équipe) seront étendues en fonction des stratégies configurées. Les utilisateurs ne pourront pas rechercher ou découvrir des équipes lorsque la recherche étendue est en vigueur, mais les membres existants de ces équipes peuvent ajouter des utilisateurs, comme le permet les stratégies de barrière des informations actives.

> [!NOTE]
> Dans Exchange environnements hybrides, cette fonctionnalité fonctionne uniquement avec Exchange Online, et non avec les boîtes aux lettres locaux.

Voir aussi [Stratégies du carnet d’adresses Exchange Online.](/exchange/address-books/address-book-policies/address-book-policies)

## <a name="when-should-you-use-scoped-directory-searches"></a>Quand devez-vous utiliser des recherches dans l’annuaire dans l’étendue ?

Les scénarios qui viennent s’en tirer profit sont similaires aux scénarios de stratégies de carnet d’adresses. Par exemple, vous pouvez utiliser la recherche dans l’annuaire étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants. 
 
Pour découvrir comment utiliser les stratégies du carnet d’adresses, lisez la barrière des [informations dans Exchange Online.](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> Les stratégies de carnet d’adresses offrent une séparation virtuelle des utilisateurs du point de vue de l’annuaire. Il est également important de noter que toutes les données des utilisateurs qui avaient déjà été mises en cache avant l’application de stratégies de carnet d’adresses nouvelles ou mises à jour resteront disponibles aux utilisateurs pendant 30 jours au plus.

## <a name="turn-on-scoped-directory-search"></a>Activer la recherche dans l’annuaire étendue

1. Utilisez des stratégies de barrière des informations pour configurer votre organisation en sous-groupes virtuels. Pour plus d’informations, voir [Définir les stratégies de barrière de l’information.](/microsoft-365/compliance/information-barriers-policies)

2. Dans le Microsoft Teams d’administration, sélectionnez **Paramètres** à l’échelle de  >  **l’organisation Teams paramètres.**

3. Sous **Rechercher,** en face de la recherche dans l’étendue du répertoire Teams à l’aide d’une stratégie de carnet d’Exchange de données **(ABP),** activer le **basculement.**

    ![Recherche dans l’annuaire dans Microsoft Teams centre d’administration.](media/teams-scoped-directory-search-image1.png)

> [!IMPORTANT]
> La réplique de cette modification peut prendre quelques heures.
