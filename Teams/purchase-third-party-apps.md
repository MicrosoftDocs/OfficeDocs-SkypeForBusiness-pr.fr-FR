---
title: Acheter des applications tierces pour Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Découvrez comment acheter des applications tierces pour votre Teams dans le Microsoft Teams d’administration.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 19403d35ad2e7263ad6f0d5a2c7a2b22d4249664
ms.sourcegitcommit: c7a6079c9592c28d8b082ff92004ae4706cea76e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2021
ms.locfileid: "60600218"
---
# <a name="purchase-third-party-apps-for-teams"></a>Acheter des applications tierces pour Teams

Teams d’applications sont gratuites à installer et certaines peuvent nécessiter des abonnements de service d’achat pour que les fonctionnalités et l’étendue complètes de l’application soient remplies. Ces abonnements de service sont appelés offres SaaS (Software as a Service), qui sont disponibles à l’achat via [AppSource](https://appsource.microsoft.com/) et désormais par le biais Microsoft Teams d’administration.

La page [Gérer les](manage-apps.md) applications du Centre Microsoft Teams d’administration est l’endroit où vous affichez et gérez toutes Teams applications pour votre organisation. Par exemple, vous pouvez voir l’état au niveau de l’organisation et les propriétés des applications, télécharger de nouvelles applications personnalisées sur le magasin d’applications de votre organisation, bloquer ou autoriser des applications au niveau de l’organisation, et gérer les paramètres des applications à l’échelle de l’organisation.

Ici, vous pouvez également acheter des licences pour les services offerts par des applications tierces pour les utilisateurs de votre organisation. La **colonne Licences** du tableau indique si une application propose un abonnement SaaS à l’achat.

![Capture d’écran de la page Gérer les applications des licences d’achat.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Acheter des applications dans le centre Teams’administration

> [!IMPORTANT]
> Si vous voulez empêcher vos utilisateurs d’acheter une application via Teams app store, vous devez bloquer l’application. Pour plus d’informations sur le [](app-policies.md) blocage d’une application, voir Gérer les stratégies d’application ou découvrir comment bloquer une application au niveau [de l’organisation.](manage-apps.md#allow-and-block-apps)

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**. Vous devez être un administrateur global ou un Teams de service pour accéder à la page.
2. Recherchez l’application que vous souhaitez. Pour identifier les applications qui ont un abonnement SaaS payant, regardez dans la **colonne Licences.** Chaque application a l’une des valeurs suivantes :
    - **Achat**: L’application propose un abonnement SaaS et est disponible à l’achat.  
    - **Achat :** L’application propose un abonnement SaaS et vous avez acheté des licences pour celui-ci.
    - **- :** l’application ne propose pas d’abonnement SaaS.
3. Lorsque vous avez trouvé l’application, **cliquez** sur Acheter pour consulter l’onglet **Plans** et tarifs de la page des détails de l’application. Examinez les offres et les informations tarifaires de l’offre SaaS pour l’application. Si vous avez besoin d’informations supplémentaires, sélectionnez En savoir **plus** pour aller à la page de l’application sur [AppSource.](https://appsource.microsoft.com/)

> [!NOTE]
> Des plans privés peuvent également être répertoriés pour l’achat, qui incluent des tarifs spéciaux que votre organisation a précédemment négociations avec un isv. Sous le nom de ces plans, l’étiquette **Plan privé** s’intait.

4. Pour vous abonner à une application, choisissez l’offre de votre choix, puis sélectionnez **Acheter.** Le flux de l’argent est ouvert directement dans le centre Teams’administration.
5. Sélectionnez le nombre de licences utilisateur que vous voulez acheter.
6. Vérifiez que le compte de facturation et l’adresse de vente sont corrects. Si vous n’en avez pas, ajoutez-en un nouveau en **sélectionnant Ajouter.** Pour plus d’informations sur les comptes de facturation, voir [Comprendre les comptes de facturation.](/microsoft-365/commerce/manage-billing-accounts)

> [!NOTE]
> Vous devez être un administrateur global pour ajouter un nouveau compte de facturation.

7. Vérifiez que le profil de facturation correct est sélectionné. Si vous n’en avez pas, ajoutez-en un nouveau en **sélectionnant Ajouter nouveau.** Vous avez la possibilité de payer par carte bancaire, carte de débit ou facturation [par facture.](#invoice-billing) Le profil de facturation vous permet également d’ajouter un numéro de bon de commande pour identifier votre commande ultérieurement. Pour plus d’informations sur les profils de facturation, voir [Comprendre les profils de facturation.](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)
8. Sélectionnez **Commande.**
9. Sélectionnez **Configurer pour** activer votre abonnement sur le site web de l’éditeur. Si vous ne définissez pas votre abonnement après l’achat, vous pouvez le faire plus tard en sélectionnant **Gérer les licences.**

Après avoir acheté l’offre SaaS associée à l’application Teams, vous pouvez afficher les détails d’achat suivants sous l’onglet **Offres** et tarifs de la page des détails de l’application.

- **Date d’activation** de la licence : date à laquelle votre licence a été activée. Si votre compte n’est pas encore installé, l’activation de l’abonnement **s’affiche.**
- **Licences**: nombre de licences que vous avez achetées.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Capture d’écran de l’onglet Plans et tarifs de la page des détails de l’application.":::

Sélectionnez **Gérer les licences** pour consulter et Centre d'administration Microsoft 365 les licences que vous avez achetées.

Les administrateurs globaux peuvent ajouter des licences, supprimer des licences et annuler des abonnements pour les achats effectués par tous les membres de l’organisation. Teams de service peuvent effectuer les mêmes actions pour les achats effectués par eux-mêmes. Toutefois, si un Teams de service a également le rôle d’administrateur de facturation, il peut gérer les achats effectués par tous les membres de l’organisation.

> [!NOTE]
> Si un administrateur global souhaite gérer un abonnement acheté par un autre administrateur global, il doit se trouver sur le même compte de facturation. Vous pouvez accorder à un autre administrateur global l’accès à un abonnement que vous avez acheté en sélectionnant l’application dans le Centre d'administration Microsoft 365. À partir de là, allez à **Afficher le profil de facturation Sélectionner** le compte de  >  **facturation** Attribuer des  >    >  **rôles Ajouter d’autres administrateurs globaux.**

### <a name="invoice-billing"></a>Facturation de la facture

- La facturation de facture est disponible en tant qu’option de paiement pour certaines transactions.
- Une révision de solvabilité est requise la première fois que vous utilisez la facturation de la facture, ce qui peut prendre jusqu’à 24 à 48 heures pour l’approbation. La facturation de la facture ne sera pas disponible tant que la vérification de solvabilité n’aura pas été terminée. Vous pouvez passer votre commande avec une carte bancaire ou réessayer plus tard une fois votre révision de solvabilité approuvée.
- La facturation de facture n’est disponible que pour les administrateurs globaux ou les administrateurs qui disposent Teams’administrateur du service et de facturation.
- La facturation de facture n’est pas disponible lors de l’achat d’une offre avec une version d’essai gratuite de 30 jours.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Vous avez une offre SaaS pour une application Teams que vous voulez lister et vendre dans le centre d’administration Microsoft Teams et AppSource ?

Les développeurs peuvent créer des offres SaaS associées à Teams applications. Ces offres sont publiées via [l’Centre de](https://partner.microsoft.com) partenaires et peuvent être achetées par le biais [d’AppSource](https://appsource.microsoft.com/) et du Microsoft Teams d’administration.

Les développeurs d’applications tierces peuvent se rendre [sur l’offre SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) pour plus d’informations.

## <a name="related-topics"></a>Sujets associés

- [Gérer vos applications dans le Centre Microsoft Teams’administration](manage-apps.md)
- [Créer une offre SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD rôles intégrés](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles)