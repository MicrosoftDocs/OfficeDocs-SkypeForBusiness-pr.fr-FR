---
title: "Gérer l'accès des utilisateurs à Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment activer ou désactiver le niveau d'accès par utilisateur."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 79dbf55d14b1866a30b5396bb5668a28df95946a
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="fe578-103">Gérer l'accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe578-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="fe578-104">Au niveau utilisateur, l'accès à Microsoft Teams peut être activé ou désactivé par utilisateur en affectant ou en supprimant la licence du produit Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fe578-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="fe578-105">Actuellement, hormis l'affection ou la suppression de licence, il n'existe aucune option de stratégie, ni sous-ensemble de fonctionnalités, permettant d'activer ou de désactiver Microsoft Teams de manière individuelle.</span><span class="sxs-lookup"><span data-stu-id="fe578-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>

| | |
|---------|---------|
|![Icône Note.](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="fe578-107">Remarque</span><span class="sxs-lookup"><span data-stu-id="fe578-107">Note</span></span> |<span data-ttu-id="fe578-p101">Microsoft recommande d'activer Microsoft Teams pour tous les utilisateurs dans l'entreprise de manière à pouvoir créer des équipes organiques pour des projets et autres initiatives dynamiques. Même dans le cas de groupes pilote, il peut toujours être utile d'activer Microsoft Teams pour tous les utilisateurs, tout en ciblant uniquement les communications au groupe pilote d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fe578-p101">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives. Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span> |

<span data-ttu-id="fe578-p102">Les licences Microsoft Teams de niveau utilisateur sont directement gérées via les interfaces de gestion utilisateur du centre d'administration Office 365. Un administrateur peut affecter des licences aux nouveaux utilisateurs lors de la création de comptes utilisateur ou à des utilisateurs disposant déjà d'un compte. L'administrateur doit disposer de droits d'administrateur général Office 365 ou d'administrateur de gestion des utilisateurs pour gérer les licences Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fe578-p102">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces. An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts. The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="fe578-p103">Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fe578-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="fe578-p104">Une licence Microsoft Teams peut être désactivée à tout moment. Une fois la licence désactivée, les utilisateurs ne pourront plus accéder à Microsoft Teams ni afficher le produit dans le lanceur d'applications et la page d'accueil d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe578-p104">A Microsoft Teams user license can be disabled at any time. Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365, avec Microsoft Teams sélectionné.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="fe578-p105">Outre le centre d'administration Office 365, les administrateurs d'Office 365 peuvent également utiliser PowerShell Office 365 pour affecter et supprimer des licences. Pour affecter une licence à un utilisateur, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="fe578-p105">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses. To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="fe578-121">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span><span class="sxs-lookup"><span data-stu-id="fe578-121">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="fe578-122">Dans l'exemple suivant, une licence du plan de gestion des licences litwareinc:ENTERPRISEPACK (Office 365 Entreprise E3) est affectée à l'utilisateur sans licence belindan@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fe578-122">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="fe578-123">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="fe578-123">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="fe578-124">Pour obtenir plus de détails et d'exemples, reportez-vous à la page [*Attribuer des licences à des comptes d'utilisateurs avec Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span><span class="sxs-lookup"><span data-stu-id="fe578-124">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="fe578-125">Pour supprimer une licence d'un compte utilisateur existant, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="fe578-125">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="fe578-126">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span><span class="sxs-lookup"><span data-stu-id="fe578-126">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="fe578-127">Dans l'exemple suivant, la licence litwareinc:ENTERPRISEPACK (Office 365 Entreprise E3) est supprimée pour le compte d'utilisateur BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fe578-127">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="fe578-128">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="fe578-128">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="fe578-129">Pour obtenir plus de détails et d'exemples, reportez-vous à la page [*Licence Office 365 et Windows PowerShell : Suppression d'une licence*](https://go.microsoft.com/fwlink/?linkid=855756).</span><span class="sxs-lookup"><span data-stu-id="fe578-129">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="fe578-131">Point de décision</span><span class="sxs-lookup"><span data-stu-id="fe578-131">Decision Point</span></span>         |<ul><li><span data-ttu-id="fe578-p106">Que prévoit votre organisation pour intégrer Microsoft Teams ?  (Groupe pilote ou licence ouvert)</span><span class="sxs-lookup"><span data-stu-id="fe578-p106">What is your organization’s plan for Microsoft Teams onboarding across the organization?  (Pilot or Open)</span></span></li></ul>         |
|![Icône Étapes suivantes.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="fe578-135">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="fe578-135">Next Steps</span></span>         |<ul><li><span data-ttu-id="fe578-136">Si l'intégration est effectuée via un projet pilote fermé, choisissez entre l'affectation de licence ou une communication ciblée.</span><span class="sxs-lookup"><span data-stu-id="fe578-136">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="fe578-137">En fonction de votre décision, prenez les mesures qui s'imposent pour garantir que seuls les utilisateurs du groupe pilote sont autorisés à accéder à Microsoft Teams (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="fe578-137">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="fe578-138">Indiquez les directives suivant lesquelles les utilisateurs auront accès ou non à Microsoft Teams ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fe578-138">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
