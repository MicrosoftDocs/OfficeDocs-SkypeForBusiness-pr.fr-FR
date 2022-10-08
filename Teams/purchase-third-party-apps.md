---
title: Achat d’applications tierces pour Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Découvrez comment acheter des applications tierces dans le magasin Teams à l’aide d’une carte de crédit, d’une carte de débit ou via facture.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 20abb80fed79995bd8496a04936737265503e67e
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377192"
---
# <a name="purchase-third-party-apps-for-teams"></a>Achat d’applications tierces pour Teams

Les applications Teams sont gratuites et certaines peuvent nécessiter l'achat d'abonnements à des services pour profiter de toutes les fonctionnalités et de la portée de l'application. Ces abonnements de service sont appelés offres SaaS (Software as a Service), qui sont disponibles à l’achat via [AppSource](https://appsource.microsoft.com/) et maintenant via le [Centre d’administration Microsoft Teams](https://admin.teams.microsoft.com).

La page [Gérer les applications](manage-apps.md) du Centre d’administration Microsoft Teams vous permet d’afficher et de gérer toutes les applications Teams pour votre organisation. Par exemple, vous pouvez voir l’état et les propriétés au niveau de l’organisation des applications, charger de nouvelles applications personnalisées dans l’App Store de votre organisation, bloquer ou autoriser des applications au niveau de l’organisation et gérer les paramètres d’application à l’échelle de l’organisation.

Ici, vous pouvez également acheter des licences pour les services offerts par des applications tierces pour les utilisateurs de votre organisation. La colonne **Licences** du tableau indique si une application propose un abonnement SaaS à l'achat. Les utilisateurs finaux peuvent acheter des applications à l’aide d’une carte de crédit, d’une carte de débit ou d’une facturation par facture.

:::image type="content" source="media/manage-apps-new-page.png" alt-text="Capture d’écran montrant la page Gérer les applications des licences d’achat.":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acheter des applications dans le Centre d'administration Teams

Pour acheter des applications dans le centre d'administration Teams, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**. Vous devez être un administrateur global ou un administrateur de service Teams pour accéder à la page.

1. Recherchez l’application souhaitée par son nom. Pour identifier les applications qui ont un abonnement SaaS payant, regardez dans la colonne **Licences**. Chaque application a l’une des valeurs suivantes :
    * **Achat** : l'application propose un abonnement SaaS et elle est disponible à l'achat.
    * **Acheté**: l’application propose un abonnement SaaS et vous avez acheté des licences pour celle-ci.
    * **- -**: l’application n’offre pas d’abonnement SaaS.

1. Lorsque vous trouvez l’application, sélectionnez **Acheter** pour accéder à l’onglet **Plans et abonnements** de la page de détails de l’application. Passez en revue les plans et les informations de tarification de l'offre SaaS pour l'application. Si vous souhaitez avoir plus d’informations, sélectionnez **En savoir plus** pour accéder à la page de l’application sur [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Des plans privés peuvent également être proposés à l'achat, qui incluent des tarifs spéciaux que votre organisation peut négocier séparément avec un développeur d'applications. Ces régimes portent l'étiquette **Plan privé** sous le nom du régime.

1. Pour vous abonner à une application, choisissez l’offre souhaitée, puis sélectionnez **Acheter**. Le flux de paiement s'ouvre directement dans le centre d'administration Teams.

1. Sélectionnez le nombre de licences utilisateur que vous souhaitez acheter.

1. Vérifiez que le compte de facturation et l’adresse du donneur d’ordre sont corrects. Si vous n’en avez pas déjà un, sélectionnez **Ajouter**. Pour plus d’informations sur les comptes de facturation, consultez [Comprendre vos comptes de facturation Microsoft](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Seul un Administration général peut ajouter un nouveau compte de facturation.

1. Vérifiez que le profil de facturation correct est sélectionné. Si vous n’en avez pas déjà un, sélectionnez **Ajouter nouveau**. Vous pouvez payer avec une carte de crédit, une carte de débit ou une [facturation par facture](#invoice-billing). Le profil de facturation vous permet également d'ajouter un numéro de bon de commande pour identifier votre commande ultérieurement. Pour plus d’informations sur les profils de facturation, consultez [Comprendre les profils de facturation](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Sélectionnez **Passer une commande**.

1. Sélectionnez **Configurer** pour activer votre abonnement sur le site web de l'éditeur. Si vous ne configurez pas votre abonnement après votre achat, vous pouvez le faire ultérieurement en sélectionnant **Gérer les abonnements**.

Une fois que vous avez acheté l’offre SaaS associée à l’application Teams, vous pouvez afficher les détails d’achat suivants sous l’onglet **Plans et abonnements** de la page de détails de l’application.

* **Date d'activation de la licence** : date d’activation de votre licence.
* **Licences** : nombre de licences que vous avez achetées.

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Capture d’écran de l’onglet Offres et tarifs dans la page des détails de l’application du Centre d’administration Teams." lightbox="media/purchase-third-party-apps-details-page.png":::

Sélectionnez **Gérer les abonnements** pour afficher et gérer les licences que vous avez achetées.

Les administrateurs généraux peuvent afficher les abonnements achetés par n’importe qui dans l’organisation, mais ils peuvent uniquement ajouter des licences supplémentaires, supprimer des licences et annuler des abonnements pour les achats effectués par n’importe qui dans leur compte de facturation. Les administrateurs de service Teams peuvent effectuer les mêmes actions pour les achats effectués par eux-mêmes.

> [!NOTE]
> Si un administrateur général souhaite gérer un abonnement acheté par un autre administrateur général, il doit se trouver dans le même compte de facturation. Vous pouvez accorder un autre accès administrateur général à un abonnement que vous avez acheté en sélectionnant l’application dans le [Centre d'administration Microsoft 365](https://admin.microsoft.com). Dans le Centre d’administration, accédez à **Afficher le profil de facturation** > **Sélectionner le compte de facturation** > **Attribuer des rôles** > **Ajouter d’autres administrateurs généraux**.

> [!IMPORTANT]
> Lorsque vous activez l'achat d'applications, cela active également les achats intégrés. Les utilisateurs peuvent voir des offres d'achat dans l'application qui sont contrôlées par le développeur de l'application pour leur application. Pour empêcher les utilisateurs d'acheter une application, vous devez bloquer l'application.

### <a name="invoice-billing"></a>Facturation

* La facturation est disponible en tant qu’option de paiement pour certaines transactions.
* Une évaluation de crédit est requise la première fois que vous utilisez la facturation, et son approbation peut prendre de 24 à 48 heures. La facturation ne sera pas disponible tant que l’évaluation de crédit n’aura pas été effectuée. Vous pouvez passer votre commande avec une carte de crédit ou réessayer ultérieurement une fois votre évaluation de crédit approuvée.
* La facturation est uniquement disponible pour les administrateurs généraux ou un administrateur disposant des autorisations d’administrateur de service Teams et d’administrateur de facturation.
* La facturation n’est pas disponible lors de l’achat d’une offre avec un essai gratuit de 30 jours.

## <a name="manage-subscriptions-in-teams-admin-center"></a>Gérer les abonnements dans le Centre d’administration Teams

Dans le Centre d’administration Teams, vous pouvez gérer les abonnements et licences d’application que vous avez achetés. Vous pouvez afficher la liste des abonnements aux applications et leurs détails et effectuer les actions suivantes :

* Modifier un plan
* Acheter ou supprimer une licence
* Mettre à jour un mode de paiement
* Annuler un abonnement
* Afficher votre facture

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="Capture d’écran des détails de l’abonnement d’une application." lightbox="media/manage-existing-subscriptions-all.png":::

Pour gérer les abonnements, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams [**Gérer les applications**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Sélectionnez l’onglet **Abonnements** pour afficher les abonnements que vous avez achetés.

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="Capture d’écran de l’option d’abonnement pour une application dans la page Gérer les applications." lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> Dans le Centre d’administration Teams, vous pouvez gérer les abonnements d’application achetés par vous ou d’autres administrateurs qui font partie du même compte de facturation. Pour afficher tous les abonnements d’application achetés pour le même locataire par d’autres administrateurs ou achetés à l’aide de comptes de facturation différents, visitez le [Centre d'administration Microsoft 365](https://admin.microsoft.com/adminportal/home#/homepage).

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Répertorier et vendre une offre SaaS pour une application Teams

Les développeurs peuvent créer des offres SaaS associées à leurs applications Teams. Ces offres sont publiées via [l’Espace partenaires](https://partner.microsoft.com) et sont disponibles à l’achat pour les organisations via [AppSource](https://appsource.microsoft.com/) et le Centre d’administration Microsoft Teams.

Pour plus d’informations pour les développeurs d’applications tierces, consultez [Créer une offre SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Articles connexes

* Vous gérez les applications pour votre organisation dans les [applications Teams au sein du centre d’administration Microsoft Teams](manage-apps.md).
* [Créer une offre SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Rôles intégrés Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Rôles d’administrateur Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
