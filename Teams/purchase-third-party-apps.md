---
title: Acheter des applications tierces pour Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Découvrez comment acheter des applications tierces auprès d’Teams magasin à l’aide d’une carte de crédit, d’une carte de débit ou d’une facturation par facture.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 33d5faec0694c666b2f392713d235cb52ef8b0e8
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190324"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acheter des applications tierces pour Teams

Teams applications sont gratuites à installer et certaines peuvent nécessiter des abonnements de service d’achat pour bénéficier des fonctionnalités et de l’étendue complètes de l’application. Ces abonnements de service sont appelés offres SaaS (Software as a Service), qui sont disponibles à l’achat via [AppSource](https://appsource.microsoft.com/) et maintenant via le centre d’administration Microsoft Teams.

La page [Gérer les applications](manage-apps.md) du centre d’administration Microsoft Teams vous permet d’afficher et de gérer toutes les applications Teams pour votre organisation. Par exemple, vous pouvez voir l’état et les propriétés des applications au niveau de l’organisation, charger de nouvelles applications personnalisées dans l’App Store de votre organisation, bloquer ou autoriser des applications au niveau de l’organisation et gérer les paramètres d’application à l’échelle de l’organisation.

Ici, vous pouvez également acheter des licences pour les services offerts par des applications tierces pour les utilisateurs de votre organisation. La colonne **Licences** du tableau indique si une application propose un abonnement SaaS à l’achat.

![Capture d’écran de la page Gérer les applications des licences d’achat.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acheter des applications dans le centre d’administration Teams

> [!IMPORTANT]
> Lorsque vous activez l’achat d’applications, il active également l’achat dans l’application. Les utilisateurs peuvent voir des offres d’achat dans l’application qui sont contrôlées par l’éditeur de logiciels indépendants pour leur application. Si vous souhaitez empêcher vos utilisateurs d’acheter une application, vous devez bloquer l’application. Pour plus d’informations sur la façon de bloquer une application, consultez [Gérer les stratégies d’application](app-policies.md) ou [découvrez comment bloquer une application au niveau de l’organisation](manage-apps.md#allow-and-block-apps).

1. Dans le volet gauche du centre d’administration Microsoft Teams, accédez à **Teams applications** > **Gérer les applications**. Vous devez être administrateur général ou administrateur de service Teams pour accéder à la page.
1. Recherchez l’application souhaitée. Pour identifier les applications qui ont un abonnement SaaS payant, consultez la colonne **Licences** . Chaque application aura l’une des valeurs suivantes :
    - **Achat** : l’application offre un abonnement SaaS et est disponible à l’achat.  
    - **Acheté** : l’application offre un abonnement SaaS et vous avez acheté des licences pour celle-ci.
    - **- -** : l’application n’offre pas d’abonnement SaaS.
1. Lorsque vous trouvez l’application, sélectionnez **Acheter** pour accéder à l’onglet **Plans et tarification** de la page de détails de l’application. Passez en revue les plans et les informations de tarification de l’offre SaaS pour l’application. Si vous avez besoin de plus d’informations, **sélectionnez En savoir plus** pour accéder à la page de l’application sur [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Les plans privés peuvent également être répertoriés à l’achat, qui incluent des tarifs spéciaux que votre organisation a précédemment négociés avec un éditeur de logiciels indépendants. Ces plans ont l’étiquette **Plan privé** sous le nom du plan.

1. Pour vous abonner à une application, choisissez le plan souhaité, puis **sélectionnez Acheter**. Le flux de sortie s’ouvre directement dans le centre d’administration Teams.

1. Sélectionnez le nombre de licences utilisateur que vous souhaitez acheter.
1. Vérifiez que le compte de facturation et l’adresse vendue sont corrects. Si vous n’en avez pas encore, ajoutez-en un nouveau en sélectionnant **Ajouter**. Pour plus d’informations sur les comptes de facturation, consultez [Comprendre les comptes de facturation](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Vous devez être administrateur général pour ajouter un nouveau compte de facturation.

1. Vérifiez que le profil de facturation correct est sélectionné. Si vous n’en avez pas encore, ajoutez-en un en sélectionnant **Ajouter nouveau**. Vous avez la possibilité de payer avec une carte de crédit, une carte de débit ou une [facturation par facture](#invoice-billing). Le profil de facturation vous permet également d’ajouter un numéro de bon de commande pour identifier votre commande ultérieurement. Pour plus d’informations sur les profils de facturation, consultez [Comprendre les profils de facturation](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).
1. Sélectionnez **Ordre des places**.
1. Sélectionnez **Configurer** pour activer votre abonnement sur le site web de l’éditeur. Si vous ne configurez pas votre abonnement après votre achat, vous pouvez le faire ultérieurement en sélectionnant **Gérer les licences**.

Une fois que vous avez acheté l’offre SaaS associée à l’application Teams, vous pouvez afficher les détails d’achat suivants sous l’onglet **Plans et tarification** de la page de détails de l’application.

- **Date d’activation de la licence** : date à laquelle votre licence a été activée. Si votre compte n’est pas encore configuré, il s’agit **d’un abonnement en attente d’activation**.
- **Licences** : nombre de licences que vous avez achetées.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Capture d’écran de l’onglet Plans et tarification de la page détails de l’application.":::

Sélectionnez **Gérer les licences** pour accéder au Centre d'administration Microsoft 365 pour afficher et gérer les licences que vous avez achetées.

Les administrateurs généraux peuvent ajouter d’autres licences, supprimer des licences et annuler des abonnements pour les achats effectués par n’importe qui dans l’organisation. Teams les administrateurs de service peuvent effectuer les mêmes actions pour les achats effectués par eux-mêmes. Toutefois, si un administrateur de service Teams a également le rôle d’administrateur de facturation, il peut gérer les achats effectués par n’importe qui dans l’organisation.

> [!NOTE]
> Si un administrateur général souhaite gérer un abonnement acheté par un autre administrateur général, il doit se trouver dans le même compte de facturation. Vous pouvez accorder à un autre administrateur général l’accès à un abonnement que vous avez acheté en sélectionnant l’application dans le Centre d'administration Microsoft 365. À partir de là, accédez à **Afficher le profil** >  de facturation **Sélectionner le compte** >  de facturation **Attribuer des rôles** > **Ajouter d’autres administrateurs généraux**.

### <a name="invoice-billing"></a>Facturation de facture

- La facturation par facture est disponible en tant qu’option de paiement pour certaines transactions.
- Une révision de crédit est requise la première fois que vous utilisez la facturation de facture, ce qui peut prendre jusqu’à 24 à 48 heures pour l’approbation. La facturation de facture n’est pas disponible tant que la vérification de crédit n’est pas terminée. Vous pouvez passer votre commande avec une carte de crédit ou réessayer ultérieurement une fois votre examen de solvabilité approuvé.
- La facturation par facture est uniquement disponible pour les administrateurs généraux ou un administrateur disposant des autorisations d’administrateur de service Teams et d’administrateur de facturation.
- La facturation de facture n’est pas disponible lors de l’achat d’un plan avec un essai gratuit de 30 jours.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Avez-vous une offre SaaS pour une application Teams que vous souhaitez répertorier et vendre dans le centre d’administration Microsoft Teams et AppSource ?

Les développeurs peuvent créer des offres SaaS associées à leurs applications Teams. Ces offres sont publiées par le biais de [l’Espace partenaires](https://partner.microsoft.com) et sont disponibles pour les organisations à acheter via [AppSource](https://appsource.microsoft.com/) et le centre d’administration Microsoft Teams.

Pour plus d’informations, les développeurs d’applications tierces peuvent accéder à [Créer une offre SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) .

## <a name="related-topics"></a>Voir aussi

- [Gérer vos applications dans le centre d’administration Microsoft Teams](manage-apps.md)
- [Créer une offre SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Rôles intégrés Azure AD](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles)
