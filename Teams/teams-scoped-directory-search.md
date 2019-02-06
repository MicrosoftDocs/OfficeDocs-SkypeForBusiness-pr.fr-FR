---
title: Utiliser la recherche d’annuaire étendue Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser recherche dans l’annuaire sur lesquelles porte Teams Microsoft pour fournir des vues personnalisées du répertoire.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a4a36de9b535d7c95f93175a97ce5266fdc37ec
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754306"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Utiliser la recherche d’annuaire étendue Microsoft Teams

Recherche dans l’annuaire étendue Microsoft Teams permet aux organisations de créer des limites virtuels qui contrôlent la façon dont les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans leur organisation. 

Microsoft Teams permet aux entreprises de fournir des vues personnalisées du répertoire à leurs utilisateurs. Teams Microsoft utilise les [stratégies de carnet d’adresses Exchange](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) pour prendre en charge ces affichages personnalisés. Une fois que les stratégies sont activées, les résultats renvoyés par la recherche pour d’autres utilisateurs (par exemple, pour lancer une conversation ou pour ajouter des membres à une équipe) seront étendus en fonction des stratégies configurées. Les utilisateurs ne sera pas en mesure de rechercher ou de découvrir les équipes lors de la recherche à étendue définie est en vigueur. 

## <a name="when-should-you-use-scoped-directory-searches"></a>Quand utiliser les recherches dans l’annuaire étendue ?

Scénarios qui tirent parti des recherches dans l’annuaire étendue définie sont similaires aux scénarios téléchargeable stratégie. Par exemple, vous souhaiterez peut-être utiliser la recherche dans l’annuaire étendue dans les situations suivantes :

- Votre organisation comporte plusieurs entreprises au sein de son client que vous souhaitez garder séparées. 
- Votre école souhaite limiter les conversations entre la faculté et les étudiants. 
 
Vous pouvez en savoir plus sur l’utilisation des stratégies de carnet d’adresses [ici](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).

> [!IMPORTANT]
> Stratégies de carnet d’adresses fournissent uniquement une séparation virtuelle d’utilisateurs du point de vue de répertoire. Les utilisateurs peuvent lancer toujours les communications avec d’autres personnes en fournissant des adresses de messagerie complète. Il est également important de noter que toutes les données utilisateur qui avaient déjà été mis en cache, avant l’application des stratégies de carnet d’adresses de nouveau ou mis à jour, reste accessibles aux utilisateurs de 30 jours.

## <a name="enable-scoped-directory-search"></a>Activer la recherche de répertoire sur lesquelles porte

1.  Stratégies de carnet d’adresses permet de configurer votre organisation en sous-groupes virtuels. Pour plus d’informations, voir [procédures de stratégies de carnet d’adresses](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).

2.  Se connecter au centre d’administration Microsoft 365, sélectionnez **centre Admin**et sélectionnez **& équipes Skype**.
 
3.  Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres à l’échelle de la société** > **paramètres équipes**.

4.  Sous **recherche**, en regard de **recherche dans l’annuaire étendue dans les équipes à l’aide d’une stratégie de carnet d’adresses Exchange (APB)**, activez la bascule **sur**. 

    ![Étendue de recherche dans le répertoire dans le centre d’administration de Microsoft Teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> Configurations hybrides (équipes avec Exchange local) ne prennent pas charge en mode de recherche à étendue définie. 

