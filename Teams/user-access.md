---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment gérer l’accès des utilisateurs à Teams en attribuant ou en supprimant une licence Teams aux utilisateurs de votre organisation.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637726"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="c9865-103">Gérer l’accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9865-103">Manage user access to Teams</span></span>

<span data-ttu-id="c9865-104">Vous gérez l’accès à Teams au niveau de l’utilisateur en attribuant ou en supprimant une licence de produit Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c9865-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="c9865-105">Sauf pour rejoindre des réunions Teams de manière anonyme, chaque utilisateur de votre organisation doit avoir une licence Teams pour pouvoir utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="c9865-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="c9865-106">Vous pouvez attribuer une licence Teams pour les nouveaux utilisateurs lors de la création de comptes d’utilisateurs ou pour les utilisateurs ayant des comptes existants.</span><span class="sxs-lookup"><span data-stu-id="c9865-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="c9865-107">Par défaut, lorsqu’un plan de gestion des licences (par exemple, Microsoft 365 Entreprise E3 ou Microsoft 365 Business Premium) est attribué à un utilisateur, une licence Teams est attribuée automatiquement et l’utilisateur est activé pour Teams.</span><span class="sxs-lookup"><span data-stu-id="c9865-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="c9865-108">Vous pouvez désactiver ou activer Teams pour un utilisateur en supprimant ou en attribuant une licence à tout moment.</span><span class="sxs-lookup"><span data-stu-id="c9865-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="c9865-109">Utilisez les stratégies de messagerie, gérées à partir du Centre d’administration <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams,</a>pour contrôler les fonctionnalités de conversation et de messagerie de canal disponibles pour les utilisateurs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c9865-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="c9865-110">Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c9865-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="c9865-111">Pour en savoir plus, lisez [Gérer les stratégies de messagerie dans Teams.](messaging-policies-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c9865-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="c9865-112">Vous gérez les licences Teams dans le Centre d’administration Microsoft 365 ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9865-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="c9865-113">Pour gérer les licences, vous devez être administrateur global ou administrateur de gestion des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c9865-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="c9865-114">Nous vous recommandons d’activer Teams pour tous les utilisateurs afin que les équipes soient formés de manière interne pour les projets et autres initiatives dynamiques.</span><span class="sxs-lookup"><span data-stu-id="c9865-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="c9865-115">Même si vous exécutez un pilote, il peut toujours être utile de garder Teams activé pour tous les utilisateurs, mais de cibler uniquement les communications avec le groupe pilote d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c9865-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="c9865-116">Utilisation du Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9865-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="c9865-117">Les licences utilisateur Teams sont gérées directement via les interfaces de gestion des utilisateurs du Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9865-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="c9865-118">Un administrateur peut attribuer des licences aux nouveaux utilisateurs lors de la création de comptes d’utilisateurs, ou aux utilisateurs qui ont déjà des comptes.</span><span class="sxs-lookup"><span data-stu-id="c9865-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c9865-119">L’administrateur doit avoir des privilèges d’administrateur général ou d’administrateur de gestion des utilisateurs pour gérer les licences Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c9865-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="c9865-120">Le Centre d’administration Microsoft 365 permet de gérer les licences Teams pour des utilisateurs individuels ou des groupes d’utilisateurs de petite taille à la fois.</span><span class="sxs-lookup"><span data-stu-id="c9865-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="c9865-121">Vous pouvez gérer les licences Teams sur la page **Licences** (jusqu’à 20 utilisateurs à la **fois)** ou la page Utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="c9865-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="c9865-122">La méthode que vous choisissez dépend de la gestion des licences de produits pour des utilisateurs spécifiques ou de la gestion des licences utilisateur de produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c9865-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="c9865-123">Si vous devez gérer les licences Teams pour un grand nombre d’utilisateurs(par exemple, des centaines ou des milliers d’utilisateurs), utilisez [PowerShell](#using-powershell) ou des licences basées sur des groupes dans [Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="c9865-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="c9865-124">Attribuer une licence Teams</span><span class="sxs-lookup"><span data-stu-id="c9865-124">Assign a Teams license</span></span>

<span data-ttu-id="c9865-125">Les étapes diffèrent selon que vous utilisez la page Licences ou la **page** **Utilisateurs** actifs.</span><span class="sxs-lookup"><span data-stu-id="c9865-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="c9865-126">Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="c9865-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Capture d’écran de la licence Teams activée pour un utilisateur](media/assign-teams-licenses-1.png)    | ![Capture d’écran de la licence Teams activée pour un utilisateur](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="c9865-129">Supprimer une licence Teams</span><span class="sxs-lookup"><span data-stu-id="c9865-129">Remove a Teams license</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9865-130">La désactivation d’une référence SKU Teams prend environ 24 heures.</span><span class="sxs-lookup"><span data-stu-id="c9865-130">It takes about 24 hours for disabling a Teams SKU to take effect.</span></span>

<span data-ttu-id="c9865-131">Lorsque vous supprimez la licence Teams d’un utilisateur, Teams est désactivé pour cet utilisateur et il ne verra plus Teams dans le lanceur d’applications ou la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="c9865-131">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="c9865-132">Pour obtenir la procédure détaillée, voir [Désaffecter les licences des utilisateurs.](/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="c9865-132">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Capture d’écran de la licence Teams désactivée pour un utilisateur](media/remove-teams-licenses-1.png)    | ![Capture d’écran de la licence Teams désactivée pour un utilisateur](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="c9865-135">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9865-135">Using PowerShell</span></span>

<span data-ttu-id="c9865-136">Utilisez PowerShell pour gérer les licences Teams pour les utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="c9865-136">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="c9865-137">Vous activez et désactivez Teams via PowerShell de la même façon que pour toute autre licence de plan de service.</span><span class="sxs-lookup"><span data-stu-id="c9865-137">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="c9865-138">Vous aurez besoin des identificateurs des plans de service teams, qui sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c9865-138">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="c9865-139">Microsoft Teams : TEAMS1</span><span class="sxs-lookup"><span data-stu-id="c9865-139">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="c9865-140">Microsoft Teams pour le GCC : TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="c9865-140">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="c9865-141">Microsoft Teams pour DoD : TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="c9865-141">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="c9865-142">Attribuer des licences Teams en bloc</span><span class="sxs-lookup"><span data-stu-id="c9865-142">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="c9865-143">Pour obtenir la procédure détaillée, voir Attribuer des licences à des comptes [d’utilisateurs avec PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="c9865-143">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="c9865-144">Supprimer des licences Teams en bloc</span><span class="sxs-lookup"><span data-stu-id="c9865-144">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="c9865-145">Pour obtenir la procédure détaillée, voir Désactiver l’accès aux services avec [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) et Désactiver l’accès aux services lors de [l’attribution de licences utilisateur.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="c9865-145">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="c9865-146">Exemple</span><span class="sxs-lookup"><span data-stu-id="c9865-146">Example</span></span> 

<span data-ttu-id="c9865-147">Voici un exemple d’utilisation des [cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) et [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) pour désactiver Teams pour les utilisateurs qui ont un plan de licence spécifique.</span><span class="sxs-lookup"><span data-stu-id="c9865-147">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="c9865-148">Par exemple, suivez ces étapes pour désactiver d’abord Teams pour tous les utilisateurs qui ont un plan de gestion des licences particulier.</span><span class="sxs-lookup"><span data-stu-id="c9865-148">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="c9865-149">Activez ensuite Teams pour chaque utilisateur individuel qui doit avoir accès à Teams.</span><span class="sxs-lookup"><span data-stu-id="c9865-149">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9865-150">La [cmdlet New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) active tous les services précédemment désactivés, sauf s’ils sont explicitement identifiés dans votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="c9865-150">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="c9865-151">Par exemple, si vous voulez laisser Exchange et Sway désactivés tout en désactivant Teams, vous devez l’inclure dans le script, sinon Exchange et Sway seront activés pour les utilisateurs que vous avez identifiés.</span><span class="sxs-lookup"><span data-stu-id="c9865-151">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="c9865-152">Exécutez la commande suivante pour afficher tous les plans de licence disponibles dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c9865-152">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="c9865-153">Pour en savoir plus, [consultez Afficher les licences et services avec PowerShell.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="c9865-153">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="c9865-154">Exécutez les commandes suivantes, à savoir le nom de votre organisation et l’identificateur du plan de gestion des licences que vous avez récupéré à \<CompanyName:License> l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c9865-154">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="c9865-155">Par exemple, ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="c9865-155">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="c9865-156">Exécutez la commande suivante pour désactiver Teams pour tous les utilisateurs qui ont une licence active pour le plan de gestion des licences.</span><span class="sxs-lookup"><span data-stu-id="c9865-156">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="c9865-157">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c9865-157">Related topics</span></span>

- [<span data-ttu-id="c9865-158">Licences de module ajouté Teams</span><span class="sxs-lookup"><span data-stu-id="c9865-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="c9865-159">Attribuer des licences de modules add-on Teams</span><span class="sxs-lookup"><span data-stu-id="c9865-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="c9865-160">Afficher les licences et services avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9865-160">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="c9865-161">Noms de produits et identificateurs de plans de service pour la gestion des licences</span><span class="sxs-lookup"><span data-stu-id="c9865-161">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="c9865-162">Référence SKU pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="c9865-162">Education SKU reference</span></span>](sku-reference-edu.md)
