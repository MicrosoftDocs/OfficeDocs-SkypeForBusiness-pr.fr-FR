---
title: Ressources Microsoft Teams pour les administrateurs dans l’éducation
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Découverte de la procédure de licence pour Microsoft Teams dans l'éducation.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b653acbe18d2247ccbf64a523fd237ca1415414
ms.sourcegitcommit: ac811017d54a55f39ecc0e3a66a883d9e027ce68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547952"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="e4ffb-103">Attribuer des licences Microsoft Teams dans l'éducation</span><span class="sxs-lookup"><span data-stu-id="e4ffb-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="e4ffb-104">Microsoft Teams est une plateforme numérique qui centralise les conversations, le contenu et les applications.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="e4ffb-105">De par sa conception basée sur Office 365, les établissements scolaires bénéficient de l’intégration avec les applications et services Office classiques.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="e4ffb-106">Avec l'expérience unique Office 365 dans l'éducation, votre établissement peut utiliser Microsoft Teams pour créer des classes collaboratives, se connecter à des communautés d’apprentissage professionnelles et communiquer avec d’autres membres du personnel de leur établissement.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="e4ffb-107">Pour démarrer, les administrateurs informatiques doivent utiliser le Centre d’administration Microsoft 365 pour activer [Microsoft Teams pour votre établissement scolaire](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="e4ffb-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="e4ffb-108">Une fois l’opération terminée, vous devez attribuer des licences aux comptes d’utilisateurs pour que vos faculté, enseignants et étudiants puissent accéder aux services Office 365, tels que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="e4ffb-109">Vous pouvez attribuer des licences à des comptes d’utilisateurs, soit individuellement, soit automatiquement par le biais de l’appartenance à des groupes.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="e4ffb-110">Cet article vous explique comment attribuer des licences Office 365 à un individu ou un petit groupe de comptes d’utilisateurs via le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="e4ffb-111">Pour attribuer automatiquement des licences par le biais de l’appartenance à des groupes, consultez l’un des articles support suivants :</span><span class="sxs-lookup"><span data-stu-id="e4ffb-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="e4ffb-112">Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4ffb-112">Office 365 Powershell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="e4ffb-113">Gestion de licences basée sur des groupes dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="e4ffb-113">Group-based Licensing in Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="e4ffb-114">Vous pouvez attribuer des licences à des utilisateurs à partir de la page des **Licences** ou de la page des **Utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="e4ffb-115">La méthode utilisée dépend de votre souhait d’attribuer des licences de produit à des utilisateurs déterminés ou d’attribuer des licences aux utilisateurs pour des produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="e4ffb-116">Si le nouveau Centre d’administration Microsoft 365 n’est pas celui que vous utilisez, vous pouvez l’activer en sélectionnant le bouton bascule **Essayer le nouveau Centre d’administration** situé en haut de la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="e4ffb-117">Attribution de licences à des utilisateurs via la page Licences</span><span class="sxs-lookup"><span data-stu-id="e4ffb-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="e4ffb-118">Vous devez être administrateur général, administrateur de facturation, administrateur de licence ou administrateur de gestion des utilisateurs. Pour plus d'informations, consultez [À propos des rôles d'administrateur Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e4ffb-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="e4ffb-119">Lorsque vous utilisez la page **Licences** pour l'attribution de licences, vous attribuez des licences pour un produit spécifique à un maximum de 20 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="e4ffb-120">Sur la page **Licences**, une liste de tous les produits pour lesquels vous avez souscrit un abonnement s’affiche, ainsi que le nombre total de licences par produit, le nombre de licences attribuées et le nombre de licences disponibles.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="e4ffb-121">Dans le Centre d’administration, choisissez la page **Facturation** > [Licences](https://go.microsoft.com/fwlink/p/?linkid=842264).</span><span class="sxs-lookup"><span data-stu-id="e4ffb-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![Capture d’écran d'une fenêtre facturation et des options du menu.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="e4ffb-123">Sélectionnez le produit pour lequel vous voulez attribuer des licences.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="e4ffb-124">Microsoft Teams fait partie de la version gratuite Office 365 A1 pour les étudiants SKU.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![Capture d’écran de la page Licences contenant les produits disponibles auxquels attribuer des licences.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="e4ffb-126">Choisissez **Affecter des licences**.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-126">Select **Assign licenses**.</span></span>

   ![Capture d’écran de la section Utilisateurs de la page et de l’option Attribuer des licences précédée d'un signe plus.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="e4ffb-128">Dans le volet **Attribuer des licences aux utilisateurs**, commencez à taper un nom, lequel qui doit générer une liste de noms.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="e4ffb-129">Sélectionnez le nom que vous recherchez dans les résultats pour l’ajouter à la liste.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="e4ffb-130">Vous pouvez ajouter jusqu'à 20 utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-130">You can add up to 20 users at a time.</span></span>

   ![Capture d’écran de la page Attribuer des licences aux utilisateurs, avec un nom partiellement saisi, affichant les résultats de la recherche pour ce nom partiel.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="e4ffb-132">Sélectionnez **Activer ou désactiver les applications et les services** pour attribuer ou supprimer l’accès à des éléments particuliers, tels que Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="e4ffb-133">Veillez à ce que **Microsoft Teams** et **Office pour le web (éducation)** soient sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="e4ffb-134">Lorsque vous avez terminé, sélectionnez **Attribuer**, puis choisissez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="e4ffb-135">Pour modifier les applications et les services auxquels un utilisateur a accès :</span><span class="sxs-lookup"><span data-stu-id="e4ffb-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="e4ffb-136">Sélectionnez la ligne contenant l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="e4ffb-137">Dans le volet droit, sélectionnez ou désélectionnez les applications et services auxquels vous voulez octroyer ou supprimer l'accès.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="e4ffb-138">Une fois terminé, sélectionnez **Enregistrer**, puis choisissez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="e4ffb-139">Attribuer des licences à une seule personne ou à différents utilisateurs via la page Utilisateurs actifs</span><span class="sxs-lookup"><span data-stu-id="e4ffb-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="e4ffb-140">Dans le Centre d’administration, accédez à la page **Utilisateurs**  >  [Utilisateurs actifs](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="e4ffb-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Capture d’écran de l’option du menu Utilisateurs actifs dans le Centre d’administration Microsoft Office 365.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="e4ffb-142">Sélectionnez les cercles en regard un(des) nom(s) d'utilisateur(s) auquel(auxquels) vous voulez attribuer une(des) licence(s).</span><span class="sxs-lookup"><span data-stu-id="e4ffb-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![Capture d’écran de la page Utilisateurs actifs et liste des utilisateurs actifs sur cette page, dont certains utilisateurs sont sélectionnés parce qu’un cercle en regard de leur nom est rempli).](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="e4ffb-144">Dans la partie supérieure, sélectionnez **Gérer des licences de produits**.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-144">At the top select **Manage product licenses**.</span></span>

   ![Capture d’écran de l’onglet Gérer les licences de produits et d’un utilisateur en dessous, répertorié comme opérant sans licence.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="e4ffb-146">Dans le volet **Attribuer des licences de produits**, sélectionnez **Ajouter aux attributions de licence de produit existantes**  >  **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![Capture d’écran de la fenêtre Gérer les licences de produits, avec la case d’option Ajouter aux affectations de licence de produit existantes sélectionnée.](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="e4ffb-148">Dans le volet **Ajouter aux produits existants**, positionnez le bouton bascule sur **Actif**correspondant à la licence que vous voulez attribuer aux utilisateurs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="e4ffb-149">Veillez à ce que **Microsoft Teams** et **Office pour le web (éducation)** soient sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Capture d’écran Microsoft Teams et Office pour le web, éducation, sélectionné dans l’onglet Ajouter aux produits existants.](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="e4ffb-151">Par défaut, tous les services associés à cette(ces) licence(s) sont automatiquement attribués à un ou plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="e4ffb-152">Vous pouvez limiter les services mis à disposition des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="e4ffb-153">Positionnez le bouton bascule sur **Inactif** pour les services que vous ne souhaitez pas attribuer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="e4ffb-154">Dans la partie inférieure du volet, sélectionnez Ajouter > Fermer.</span><span class="sxs-lookup"><span data-stu-id="e4ffb-154">At the bottom of the pane, select Add > Close.</span></span>
