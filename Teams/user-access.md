---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment gérer l’accès des utilisateurs aux équipes en attribuant ou en supprimant une licence d’équipe aux utilisateurs de votre organisation.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521381"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="80f4a-103">Gérer l’accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80f4a-103">Manage user access to Teams</span></span>

<span data-ttu-id="80f4a-104">Vous pouvez gérer l’accès aux équipes au niveau utilisateur en attribuant ou en supprimant une licence de produit Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="80f4a-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="80f4a-105">Pour pouvoir utiliser Teams, chaque utilisateur de votre organisation doit disposer d’une licence Teams.</span><span class="sxs-lookup"><span data-stu-id="80f4a-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="80f4a-106">Vous pouvez affecter une licence d’équipe aux nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs possédant des comptes existants.</span><span class="sxs-lookup"><span data-stu-id="80f4a-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="80f4a-107">Par défaut, lorsque vous disposez d’un plan de gestion des licences (par exemple, Microsoft 365 entreprise E3 ou Microsoft 365 Business Premium) affecté à un utilisateur, une licence d’équipe est automatiquement affectée et l’utilisateur est activé pour Teams.</span><span class="sxs-lookup"><span data-stu-id="80f4a-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="80f4a-108">Vous pouvez désactiver ou activer les équipes pour un utilisateur en le supprimant ou en lui attribuant une licence à tout moment.</span><span class="sxs-lookup"><span data-stu-id="80f4a-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="80f4a-109">Utilisez des stratégies de messagerie gérées par le <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centre d’administration teams</a>pour contrôler les fonctionnalités de messagerie et de messagerie instantanée disponibles pour les utilisateurs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="80f4a-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="80f4a-110">Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="80f4a-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="80f4a-111">Pour en savoir plus, consultez [gérer les stratégies de messagerie dans teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="80f4a-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="80f4a-112">Vous pouvez gérer les licences d’équipes dans le centre d’administration 365 Microsoft ou en utilisant PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f4a-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="80f4a-113">Vous devez être un administrateur général ou un administrateur de gestion des utilisateurs pour gérer les licences.</span><span class="sxs-lookup"><span data-stu-id="80f4a-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="80f4a-114">Nous vous recommandons d’activer teams pour tous les utilisateurs de sorte que les équipes puissent être formées de manière biologique pour les projets et autres initiatives dynamiques.</span><span class="sxs-lookup"><span data-stu-id="80f4a-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="80f4a-115">Même si vous exécutez une version d’essai, il est possible que les équipes puissent rester opérationnelles pour tous les utilisateurs, mais uniquement cibler les communications avec le groupe pilote d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="80f4a-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="80f4a-116">Utilisation du centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="80f4a-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="80f4a-117">Les licences de niveau utilisateur d’équipes sont gérées directement via les interfaces de gestion des utilisateurs du centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80f4a-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="80f4a-118">Un administrateur peut affecter des licences à de nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs possédant des comptes existants.</span><span class="sxs-lookup"><span data-stu-id="80f4a-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="80f4a-119">L’administrateur doit disposer de privilèges d’administrateur général ou de gestion des utilisateurs pour gérer les licences Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="80f4a-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="80f4a-120">Le centre d’administration Microsoft 365 permet de gérer les licences d’équipes pour des utilisateurs individuels ou des petits groupes d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="80f4a-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="80f4a-121">Vous pouvez gérer les licences teams dans la page **licences** (pour 20 utilisateurs au maximum) ou la page **utilisateurs actifs** .</span><span class="sxs-lookup"><span data-stu-id="80f4a-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="80f4a-122">La méthode que vous choisissez dépend de la façon dont vous souhaitez gérer les licences de produits pour des utilisateurs spécifiques ou gérer des licences utilisateur pour des produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="80f4a-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="80f4a-123">Si vous avez besoin de gérer les licences d’équipes pour un grand nombre d’utilisateurs, par exemple des centaines voire des milliers d’utilisateurs, utilisez la gestion des licences [PowerShell](#using-powershell) ou par [groupe dans Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="80f4a-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="80f4a-124">Attribution d’une licence d’équipe</span><span class="sxs-lookup"><span data-stu-id="80f4a-124">Assign a Teams license</span></span>

<span data-ttu-id="80f4a-125">Les étapes diffèrent selon que vous utilisez la page **licences** ou **utilisateurs actifs** .</span><span class="sxs-lookup"><span data-stu-id="80f4a-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="80f4a-126">Pour obtenir des instructions détaillées, voir attribuer des [licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="80f4a-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Capture d’écran de la licence teams activée pour un utilisateur](media/assign-teams-licenses-1.png)    | ![Capture d’écran de la licence teams activée pour un utilisateur](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="80f4a-129">Supprimer une licence d’équipe</span><span class="sxs-lookup"><span data-stu-id="80f4a-129">Remove a Teams license</span></span>

<span data-ttu-id="80f4a-130">Lorsque vous supprimez une licence teams d’un utilisateur, teams est désactivé pour cet utilisateur et ne verra plus teams dans le lanceur d’applications ou sur la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="80f4a-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="80f4a-131">Pour obtenir la procédure détaillée, voir [Annuler l’attribution de licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span><span class="sxs-lookup"><span data-stu-id="80f4a-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Capture d’écran de la licence teams désactivée pour un utilisateur](media/remove-teams-licenses-1.png)    | ![Capture d’écran de la licence teams désactivée pour un utilisateur](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="80f4a-134">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="80f4a-134">Using PowerShell</span></span>

<span data-ttu-id="80f4a-135">Utiliser PowerShell pour gérer les licences teams des utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="80f4a-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="80f4a-136">Vous pouvez activer et désactiver teams via PowerShell de la même manière que pour n’importe quelle licence d’autre plan de service.</span><span class="sxs-lookup"><span data-stu-id="80f4a-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="80f4a-137">Vous aurez besoin des identificateurs pour les plans de services pour les équipes, qui sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="80f4a-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="80f4a-138">Microsoft teams : TEAMS1</span><span class="sxs-lookup"><span data-stu-id="80f4a-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="80f4a-139">Microsoft teams pour GCC : TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="80f4a-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="80f4a-140">Microsoft teams pour DoD : TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="80f4a-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="80f4a-141">Attribution de licences équipe en bloc</span><span class="sxs-lookup"><span data-stu-id="80f4a-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="80f4a-142">Pour obtenir la procédure détaillée, voir [attribuer des licences à des comptes d’utilisateurs avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="80f4a-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="80f4a-143">Supprimer des licences d’équipe en bloc</span><span class="sxs-lookup"><span data-stu-id="80f4a-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="80f4a-144">Pour obtenir la procédure détaillée, voir [désactiver l’accès aux services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) et [désactiver l’accès aux services lorsque vous attribuez des licences utilisateur](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="80f4a-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="80f4a-145">Exemple</span><span class="sxs-lookup"><span data-stu-id="80f4a-145">Example</span></span> 

<span data-ttu-id="80f4a-146">Voici un exemple d’utilisation des applets de commande [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) et [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) pour désactiver teams pour les utilisateurs disposant d’un plan de gestion des licences spécifique.</span><span class="sxs-lookup"><span data-stu-id="80f4a-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="80f4a-147">Par exemple, suivez ces étapes pour désactiver d’abord teams pour tous les utilisateurs disposant d’un plan de gestion des licences particulier.</span><span class="sxs-lookup"><span data-stu-id="80f4a-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="80f4a-148">Activez ensuite teams pour chaque utilisateur individuel qui doit avoir accès à Teams.</span><span class="sxs-lookup"><span data-stu-id="80f4a-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80f4a-149">L’applet [de action New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) active tous les services précédemment désactivés, sauf s’ils sont explicitement identifiés dans votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="80f4a-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="80f4a-150">Par exemple, si vous souhaitez que Microsoft Exchange et votre Sway soient désactivés, vous devez le faire dans le script ou Exchange et Sway seront activés pour les utilisateurs identifiés.</span><span class="sxs-lookup"><span data-stu-id="80f4a-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="80f4a-151">Exécutez la commande suivante pour afficher l’ensemble des plans de licence disponibles dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="80f4a-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="80f4a-152">Pour en savoir plus, voir [afficher des licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="80f4a-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="80f4a-153">Exécutez les commandes suivantes, où \<CompanyName:License> est le nom de votre organisation et l’identificateur correspondant au plan de gestion des licences que vous avez récupéré lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="80f4a-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="80f4a-154">Par exemple, ContosoSchool : ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="80f4a-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="80f4a-155">Exécutez la commande suivante pour désactiver teams pour tous les utilisateurs disposant d’une licence active pour le plan de gestion des licences.</span><span class="sxs-lookup"><span data-stu-id="80f4a-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="80f4a-156">Gérer teams au niveau de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="80f4a-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="80f4a-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80f4a-157">Related topics</span></span>

- [<span data-ttu-id="80f4a-158">Licences de compléments teams</span><span class="sxs-lookup"><span data-stu-id="80f4a-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="80f4a-159">Attribution de licences de complément d’équipes</span><span class="sxs-lookup"><span data-stu-id="80f4a-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="80f4a-160">Afficher les licences et services avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="80f4a-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="80f4a-161">Noms de produits et identificateurs de plans de service pour la gestion des licences</span><span class="sxs-lookup"><span data-stu-id="80f4a-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="80f4a-162">Référence SKU éducation</span><span class="sxs-lookup"><span data-stu-id="80f4a-162">Education SKU reference</span></span>](sku-reference-edu.md)