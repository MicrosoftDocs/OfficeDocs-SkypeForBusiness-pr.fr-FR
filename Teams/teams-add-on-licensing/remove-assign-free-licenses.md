---
title: Mettre hors service Microsoft Teams gratuit (classique) pour votre organisation
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
robots: noindex
description: Découvrez comment supprimer les licences teams gratuites (classiques) et attribuer des licences Teams payantes aux utilisateurs de votre organisation.
ms.openlocfilehash: 3015036d0656a80ac8440d2c193003cc7d67d9fc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767665"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>Mettre hors service Microsoft Teams gratuit (classique) pour votre organisation

> [!NOTE]
> Si vous êtes un utilisateur Teams Gratuit (classique), vous perdrez l’accès à Teams mi-avril 2023, sauf si votre administrateur informatique effectue les actions suivantes dans cet article.

À la mi-avril 2023, Microsoft mettra fin à la licence **Microsoft Teams gratuit (classique)**.

Cet article fournit aux administrateurs informatiques des instructions sur la façon de mettre hors service les licences **Microsoft Teams gratuit (classique)** de leur organisation et de passer à des licences Teams payantes.

Si vous ne déplacez pas les licences Teams gratuites de vos utilisateurs vers des licences Teams payantes avant la mi-avril 2023, vos utilisateurs perdront l’accès à Teams.

Pour effectuer ce processus, vous pouvez choisir l’une des deux méthodes suivantes :

- [Utilisez le Centre d'administration Microsoft 365.](#use-microsoft-365-admin-center-to-replace-licenses)
- [Utilisez Microsoft PowerShell.](#use-microsoft-powershell-to-replace-licenses)

Si votre organisation décide de ne pas migrer vers une licence Teams payante, vous pouvez exporter le contenu de votre organisation à partir de Teams. Pour obtenir des instructions sur l’exportation de contenu Teams, consultez [Exporter du contenu avec les API d’exportation Microsoft Teams](/microsoftteams/export-teams-content).

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>Utiliser Centre d'administration Microsoft 365 pour remplacer des licences

Si peu d’utilisateurs de votre organisation ont attribué la licence **gratuite (classique) Teams**, nous vous recommandons d’utiliser la Centre d'administration Microsoft 365 pour supprimer et attribuer des licences.

### <a name="check-users-current-teams-licensing"></a>Vérifier les licences Teams actuelles des utilisateurs

1. Connectez-vous au [Centre d'administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
1. Dans le menu de gauche, accédez à **Utilisateurs** > et sélectionnez [**Utilisateurs actifs**](https://go.microsoft.com/fwlink/p/?linkid=834822) pour afficher les licences attribuées aux utilisateurs.
    1. La colonne **Licence** affiche **Microsoft Teams gratuit (classique)** en regard des utilisateurs affectés à cette licence.
1. Dans le menu de gauche, accédez à **Facturation** > et sélectionnez [**Licences**](https://go.microsoft.com/fwlink/p/?linkid=842264) pour voir si vous disposez de licences Teams payantes disponibles.
    1. Si votre organisation dispose de licences disponibles, passez directement à [Attribuer des licences Teams payantes](#assign-paid-teams-licenses) pour attribuer ces licences aux utilisateurs disposant de licences **Teams gratuites (classiques).**
1. Déterminez le nombre de licences Teams payantes que vous devez acheter, le cas échéant.

### <a name="purchase-paid-teams-licenses"></a>Acheter des licences Teams payantes

1. Dans le [Centre d'administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), accédez à **Facturation** > et sélectionnez **Acheter des services**.
1. Sélectionnez **Afficher les produits** pour afficher toutes les licences disponibles.
1. Sélectionnez le filtre **de catégorie Communication et collaboration** pour afficher les licences Teams.
1. Choisissez la licence Teams payante que vous souhaitez remplacer **Teams Gratuit (classique).**
    1. Nous vous [**recommandons la licence Teams Essentials**](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF), qui est disponible jusqu’à 300 sièges.
    1. Si vous avez besoin de plus de 300 sièges, nous vous recommandons d’acheter des [licences Microsoft 365 E1](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA).
1. Entrez le nombre de licences que vous souhaitez acheter, puis choisissez une fréquence de facturation.
1. Sélectionnez le bouton **Acheter** pour terminer le processus d’achat.

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>Acheter des licences dans la Place de marché du centre d’administration

Certains locataires ont accès à la Place de marché Centre d'administration Microsoft 365. Pour ces locataires, vous allez acheter des licences sur la Place de marché.

1. Dans le [Centre d'administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), sélectionnez **Place de marché** dans le menu de gauche.
1. Sélectionnez l’onglet **Tous les produits** .
1. Sélectionnez le filtre **de catégorie Communication et collaboration** pour afficher les licences Teams.
1. Choisissez la licence Teams payante que vous souhaitez remplacer **Teams Gratuit (classique).**
1. Entrez le nombre de licences que vous souhaitez acheter, puis choisissez une fréquence de facturation.
1. Sélectionnez le bouton **Acheter** pour terminer le processus d’achat.

### <a name="assign-paid-teams-licenses"></a>Attribuer des licences Teams payantes

1. Lorsque vous êtes prêt à remplacer les licences **Gratuites (classiques) Teams**, dans le Centre d'administration Microsoft 365, accédez à **Utilisateurs** > [**Utilisateurs actifs**](https://admin.microsoft.com/adminportal/home#/users).
1. Sélectionnez tous les utilisateurs dont la licence **Teams gratuite (classique)** est répertoriée dans la colonne **Licences** .
1. En haut du centre d’administration, sélectionnez l’option **Gérer les licences de produit** .
1. Dans le volet droit, sélectionnez **Remplacer**.
    1. Si vous sélectionnez l’option **Remplacer** , vous devez resélectionner toutes les licences que vous souhaitez attribuer à ces utilisateurs. Si vous sélectionnez uniquement la nouvelle licence Teams payante, les autres licences attribuées à ces utilisateurs seront supprimées des utilisateurs et remplacées par la licence Teams.
    1. Si vos utilisateurs ont des besoins de licences différents, effectuez ce processus par lots pour empêcher les utilisateurs de licences incorrectes.
1. Dans le volet côté trajet, choisissez la nouvelle licence Teams payante et toutes les autres licences que les utilisateurs doivent attribuer, puis sélectionnez le bouton **Enregistrer les modifications** .

## <a name="use-microsoft-powershell-to-replace-licenses"></a>Utiliser Microsoft PowerShell pour remplacer des licences

Si un grand nombre d’utilisateurs ont attribué la licence **gratuite (classique) Teams** à votre organisation, nous vous recommandons d’utiliser PowerShell pour annuler l’attribution en bloc et attribuer des licences aux utilisateurs.

Avant de pouvoir effectuer ce processus, vous devez disposer de licences Teams payantes pour les utilisateurs auxquels la licence **Teams gratuite (classique)** est attribuée. Pour acheter des licences pour ces utilisateurs, consultez [Acheter des licences Teams payantes](#purchase-paid-teams-licenses).

1. Connectez votre client Microsoft 365 au [Kit de développement logiciel (SDK) Microsoft Graph PowerShell](/powershell/microsoftgraph/get-started).
1. Ouvrez l’application de bureau Microsoft PowerShell.
1. [Définissez des autorisations d’utilisateur et d’organisation pour API Graph](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk).
1. [Supprimez les licences **Teams gratuites (classiques)** des comptes d’utilisateurs](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts).
1. [Attribuez des licences Teams payantes aux utilisateurs](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts).

Pour plus d’informations sur le processus du Kit de développement logiciel (SDK) Graph PowerShell, consultez [Utiliser le Kit de développement logiciel (SDK) Microsoft Graph PowerShell](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell).
