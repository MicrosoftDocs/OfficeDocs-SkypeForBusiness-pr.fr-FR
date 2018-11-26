---
title: Gérer l'offre d’évaluation de cloud commercial Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/23/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
description: Les utilisateurs Office 365 qui ne sont pas une licence de Microsoft Teams peuvent lancer une version d’évaluation de 1 an d’équipes.
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c544290c13409e3ac857e44cabf1deb56614657
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674777"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Gérer l'offre d’évaluation de cloud commercial Microsoft Teams
=======================================================

Microsoft Teams est un excellent outil de collaboration pour votre organisation. Il permet aux personnes et aux équipes de discuter, innover et partager des idées à l’aide de la puissance d’Office 365. Les équipes commerciales Cloud version d’évaluation Microsoft offre Office 365 les utilisateurs existants dans votre organisation qui ne sont pas une licence de Microsoft Teams initier une version d’évaluation de 1 an du produit. Administrateurs ont la possibilité d’activer ou désactiver cette fonctionnalité pour les utilisateurs au sein de leur organisation.

## <a name="whats-in-the-offer"></a>Nouveautés de l’offre

Les plans de service inclus dans cette offre sont les suivants :

- Foundation Exchange
- Flux pour Office 365 Plan 1
- Planificateur de Microsoft
- Équipes Microsoft (Teams1, équipes travailleur de l’information)
- Office Online
- PowerApps pour Office 365 Plan 1
- SharePoint Online Kiosk
- Balancement
- Yammer Enterprise

L’offre peut être affectée à un maximum de 500 000 utilisateurs par l’organisation. La licence d’évaluation alloue 2 Go de stockage SharePoint Online pour chaque utilisateur d’évaluation.

## <a name="who-is-eligible"></a>Qui est éligible

Les utilisateurs qui ne possèdent pas d’une licence Office 365 qui inclut les équipes peuvent lancer l’offre d’évaluation de Cloud Microsoft équipes commerciale. Par exemple, si un utilisateur a Office 365 entreprise Premium (qui inclut les équipes) et le plan de service équipes est désactivé, ils ne sont pas éligibles pour la version d’évaluation.

En outre, votre organisation n’est pas éligibles pour la version d’évaluation if : 
- Vous êtes un client de partenaire de Syndication
- Vous êtes un client de partenaire revendeur
- Vous êtes un client EDU, GOV ou GCC

En outre, si votre organisation n’est pour la Microsoft équipes commerciales Cloud d’évaluation, vous verrez pas le commutateur **aux utilisateurs d’installer les services et applications d’évaluation** .

Au niveau de l’organisation, les équipes en tant que service doit être activé (dans le centre d’administration équipes). Pour plus d’informations, voir [fonctionnalités de gestion des équipes Microsoft dans votre organisation Office 365](enable-features-office-365.md). En outre, les utilisateurs doivent être activés pour s’inscrire pour les applications et versions d’évaluation (dans le centre d’administration Office 365). Pour plus d’informations, voir [Gérer la version d’évaluation](#manage-the-trial) plus loin dans cet article.

## <a name="how-users-sign-up-for-the-trial"></a>Comment les utilisateurs s’inscrire à la version d’évaluation

Utilisateurs peuvent s’inscrire pour la version d’évaluation en vous connectant à équipes ([teams.microsoft.com](https://teams.microsoft.com)). Si éligibles, ils verront l’écran suivant pour démarrer la version d’évaluation. 

![Capture d’écran de la page de démarrage pour la version d’évaluation des équipes travailleur de l’information.](media/iw-trial-start-screen.png)

La version d’évaluation accorde une version d’évaluation d’un an dans toute l’organisation. Cette version d’évaluation rende 500 000 licences disponibles pour l’affectation. Pour chaque licence est attribuée, la version d’évaluation alloue 2 Go de stockage SharePoint Online. Utilisateurs supplémentaires au sein de votre organisation peuvent s’inscrire pour la version d’évaluation en passant par le même processus.

Toutes les versions d’évaluation de votre organisation partagent les mêmes début et les dates de fin qui correspond à la date premier utilisateur connecté pour la version d’évaluation. Par exemple, si l’utilisateur A commence à la première version d’évaluation sur 25 avril 2018, et l’utilisateur B une version d’évaluation sur 3 juin 2018, version d’évaluation de deux utilisateurs expire le 25 avril 2019.

La première personne qui a souscrit à la version d’évaluation est « propriétaire » de l’abonnement. Seulement cette personne peut gérer l’abonnement. 

## <a name="manage-the-trial"></a>Gérer la version d’évaluation

Administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux demander des applications d’évaluation et services au sein de leur organisation. Actuellement, la version d’évaluation des équipes est uniquement trial dans cette catégorie, mais elle s’applique à d’autres programmes similaires à l’avenir. 

1\. À partir du [Centre d’administration Office 365](https://portal.office.com/adminportal/home), accédez à **Services et compléments** > **utilisateur propriétaire des applications et Services**.

![Capture d’écran de la page Services et des compléments dans le centre d’administration d’Office 365.](media/iw-trial-enable-1.png)

2\. Désactivez l’option **laisser les utilisateurs installer les services et applications d’évaluation**.

![Capture d’écran de l’utilisateur appartient la page Services et applications dans le centre d’administration d’Office 365.](media/iw-trial-enable-2.png)

3\. Vous pouvez désactiver les équipes de votre organisation en accédant au portail d’administration équipes. Lorsque cette option est désactivée, les utilisateurs ne peuvent pas prétendre qu'offrent les équipes d’évaluation.

4\. Si vous avez désactivé le plan de service équipes pour un utilisateur qui dispose d’une licence éligible, que l’utilisateur n’est pas autorisé à demander une licence d’évaluation.

5\. Si un utilisateur a demandé une licence d’évaluation d’équipes, vous pouvez la supprimer en supprimant le plan de licence ou le service. 

![Capture d’écran de la page licences de produits dans le centre d’administration d’Office 365.](media/iw-trial-enable-3.png)

### <a name="upgrade-users-from-the-trial-license"></a>Mise à niveau à partir de la licence d’évaluation

Pour mettre à niveau des utilisateurs à partir de la licence d’évaluation, procédez comme suit :

1. Acheter une référence SKU qui inclut des équipes.
2. Supprimer la version d’évaluation équipes de l’utilisateur.
3. Affectez ensuite la licence récemment acquis.

Pour plus d'informations, reportez-vous à la rubrique [Licence Office 365 pour Microsoft Teams](Office-365-licensing.md).