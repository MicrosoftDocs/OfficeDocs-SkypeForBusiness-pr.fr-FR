---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver le niveau d'accès par utilisateur.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdaa51072df7ffeeb2aeb2c66e73f07b0c0c0569
ms.sourcegitcommit: d8a68433949edfbbece628dd0e1c0ce9205ba0a0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087819"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="40221-103">Gérer l'accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40221-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="40221-104">Au niveau de l’utilisateur, l’accès à Microsoft Teams peut être activé ou désactivé sur par utilisateur à l’attribution ou la suppression de la licence de produit Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40221-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="40221-105">Actuellement, il n’existe aucune option de stratégie pour activer des équipes ou un sous-ensemble des fonctionnalités d’équipes, ou de désactiver au niveau utilisateur individuel en dehors de la gestion des licences.</span><span class="sxs-lookup"><span data-stu-id="40221-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="40221-106">Microsoft recommande que vous allumez équipes pour tous les utilisateurs d’une entreprise afin que les équipes peuvent être créées selon pour les projets et autres initiatives dynamiques.</span><span class="sxs-lookup"><span data-stu-id="40221-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="40221-107">Même si vous décidez au pilote, il peut toujours être utile de conserver les équipes activés pour tous les utilisateurs, mais uniquement cibler communications dans le groupe pilote d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="40221-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="40221-108">Gérer les équipes via le centre d’administration Office 365</span><span class="sxs-lookup"><span data-stu-id="40221-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="40221-109">Licences d’équipes au niveau utilisateur sont gérés directement via les interfaces de gestion Office 365 admin center utilisateur.</span><span class="sxs-lookup"><span data-stu-id="40221-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="40221-110">Un administrateur peut affecter des licences pour les nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou aux utilisateurs disposant de comptes existants.</span><span class="sxs-lookup"><span data-stu-id="40221-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="40221-111">L’administrateur doit disposer de privilèges d’administrateur Global de Office 365 ou administrateur de gestion des utilisateurs pour gérer les licences Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40221-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="40221-p103">Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="40221-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="40221-115">Une licence d’utilisateur équipes peut être désactivée à tout moment.</span><span class="sxs-lookup"><span data-stu-id="40221-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="40221-116">Une fois que la licence est désactivée, l’accès des utilisateurs à Microsoft Teams n’est pas autorisée et l’utilisateur ne sera plus en mesure de voir les équipes dans la page d’accueil et lancement d’application Office 365.</span><span class="sxs-lookup"><span data-stu-id="40221-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365, avec Microsoft Teams sélectionné.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="40221-118">Gérer via PowerShell</span><span class="sxs-lookup"><span data-stu-id="40221-118">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40221-119">Nouvelle MsolLicenseOptions activer tous les services qui ont été précédemment désactivées à moins qu’explictitly identitied dans votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="40221-119">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="40221-120">Par exemple, si vous souhaitez laisser les deux & Exchange balancement désactivé pendant apporte désactivation des équipes, vous devrez incluent ce dans le script ou les deux & Exchange balancement sera deviennent activé pour les utilisateurs que vous avez identifié.</span><span class="sxs-lookup"><span data-stu-id="40221-120">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="40221-121">Si vous souhaitez utilisent une interface utilisateur graphique pour gérer cette fonctionnalité, voir : [outil de gestion et de création de rapports de licence de Office 365-attribuer des licences supprimer en bloc](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="40221-121">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="40221-122">L’activation et la désactivation de Teams comme licence de charge de travail via PowerShell sont effectuées comme pour n'importe quelle charge de travail.</span><span class="sxs-lookup"><span data-stu-id="40221-122">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="40221-123">Le nom du plan de service est TEAMS1 pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40221-123">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="40221-124">Pour GCC le nom de plan de service est TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="40221-124">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="40221-125">High GCC le nom de plan de service est TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="40221-125">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="40221-126">Le nom de plan de service est DoD TEAMS_DOD (voir [désactiver l’accès aux services Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) pour plus d’informations.)</span><span class="sxs-lookup"><span data-stu-id="40221-126">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="40221-127">**Exemple :** L’exemple suivant est simplement un rapide sur la façon dont vous pouvez le désactiver équipes pour tout le monde dans un type de licence.</span><span class="sxs-lookup"><span data-stu-id="40221-127">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="40221-128">Vous devez commencer par cette opération. Ensuite, activez Microsoft Teams individuellement pour les utilisateurs devant y avoir accès à des fins de pilote.</span><span class="sxs-lookup"><span data-stu-id="40221-128">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="40221-129">Pour afficher les types d'abonnement dont vous disposez dans votre organisation, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="40221-129">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="40221-130">Indiquez un nom pour votre forfait qui inclut le nom de votre organisation et le forfait pour votre établissement (par exemple ContosoSchool:ENTERPRISEPACK_STUDENT), puis exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="40221-130">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="40221-131">Pour désactiver les équipes pour tous les utilisateurs disposant d’une licence pour votre plan nommé active, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="40221-131">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="40221-133">Point de décision</span><span class="sxs-lookup"><span data-stu-id="40221-133">Decision Point</span></span>         |<ul><li><span data-ttu-id="40221-134">Quel est le plan de votre organisation pour l’intégration des équipes au sein de l’organisation ?</span><span class="sxs-lookup"><span data-stu-id="40221-134">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="40221-135">(Pilote ou ouvrir)</span><span class="sxs-lookup"><span data-stu-id="40221-135">(Pilot or Open)</span></span></li></ul>         |
|![Icône Étapes suivantes.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="40221-137">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="40221-137">Next Steps</span></span>         |<ul><li><span data-ttu-id="40221-138">Si embarquement via un pilote fermé, décider si vous souhaitez faire par le biais de la gestion des licences ou ciblés de communication.</span><span class="sxs-lookup"><span data-stu-id="40221-138">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="40221-139">Selon la décision, procédez comme suit pour vous assurer que pilote uniquement les utilisateurs autorisés à accéder aux équipes (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="40221-139">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="40221-140">Les instructions pour les utilisateurs qui seront (ou pourront) de documents ont accès aux équipes.</span><span class="sxs-lookup"><span data-stu-id="40221-140">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="40221-141">Gérer les équipes au niveau client Office 365</span><span class="sxs-lookup"><span data-stu-id="40221-141">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

