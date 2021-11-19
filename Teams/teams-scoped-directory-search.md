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
ms.openlocfilehash: 108a5895bf568207246ec6b1d7711e13e6c87069
ms.sourcegitcommit: 5c88a07f07f9faad294d614d507e43173efc5f46
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111984"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Utiliser la recherche d’annuaire étendue Microsoft Teams

Microsoft Teams dans l’étendue de la recherche dans l’annuaire permet aux organisations de créer des limites virtuelles qui contrôlent la façon dont les utilisateurs peuvent trouver et communiquer avec d’autres utilisateurs de leur organisation. 

Microsoft Teams organisations fournissent des affichages personnalisés de l’annuaire à leurs utilisateurs. Microsoft Teams utilise la [barrière de l’information](/microsoft-365/compliance/information-barriers) pour prendre en charge ces affichages personnalisés. Une fois les stratégies activées, les résultats renvoyés par les recherches d’autres utilisateurs (par exemple, pour démarrer une conversation ou pour ajouter des membres à une équipe) seront étendues en fonction des stratégies configurées. Les utilisateurs ne pourront pas effectuer de recherche ou découvrir d’équipes lorsque la recherche étendue est en vigueur, mais les membres existants de ces équipes peuvent ajouter des utilisateurs, comme le permet les stratégies actives de la barrière des informations.

> [!NOTE]
> Dans Exchange environnements hybrides, cette fonctionnalité fonctionne uniquement avec Exchange Online, et non avec les boîtes aux lettres locaux.

Voir aussi [Stratégies du carnet d’adresses dans Exchange Online.](/exchange/address-books/address-book-policies/address-book-policies)

## <a name="when-should-you-use-scoped-directory-searches"></a>Quand devez-vous utiliser des recherches dans l’annuaire dans l’étendue ?

Les scénarios qui viennent s’en tirer profit sont similaires aux scénarios de stratégie de carnet d’adresses. Par exemple, vous pouvez utiliser la recherche dans l’annuaire étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants. 
 
Pour découvrir comment utiliser les stratégies du carnet d’adresses, lisez la barrière des [informations dans Exchange Online.](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> Les stratégies de carnet d’adresses offrent une séparation virtuelle des utilisateurs du point de vue de l’annuaire. Il est également important de noter que toutes les données des utilisateurs qui avaient déjà été mises en cache avant l’application de stratégies de carnet d’adresses nouvelles ou mises à jour resteront disponibles aux utilisateurs pendant 30 jours.

## <a name="turn-on-scoped-directory-search"></a>Activer la recherche dans l’annuaire étendue

1. Utilisez des stratégies de barrière de l’information pour configurer votre organisation en sous-groupes virtuels. Pour plus d’informations, voir [Définir les stratégies de barrière de l’information.](/microsoft-365/compliance/information-barriers-policies)

2. Dans le Microsoft Teams d’administration, **sélectionnez** Teams  >  **Teams paramètres.**

3. Sous **Rechercher par nom,** en plus de l’étendue de la recherche dans le répertoire Teams à l’aide d’Exchange de **carnet** d’adresses de base, basculez le **désactiver.**

    ![Recherche dans l’annuaire dans l’étendue Microsoft Teams centre d’administration.](media/teams-scoped-directory-search-image1.png)

> [!IMPORTANT]
> La réplique de cette modification peut prendre quelques heures.
