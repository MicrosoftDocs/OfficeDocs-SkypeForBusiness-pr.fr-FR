---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver le niveau d'accès par utilisateur.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f571dd461c6c783703159dfd6e9beb343612dd58
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779480"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="1adbf-103">Gérer l'accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1adbf-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="1adbf-104">Au niveau utilisateur, l’accès à Microsoft teams peut être activé ou désactivé en fonction de chaque utilisateur en attribuant ou en supprimant la licence de produit Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1adbf-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="1adbf-105">Utilisez des stratégies de messagerie gérées par le centre d’administration teams pour contrôler les fonctionnalités de messagerie et de messagerie instantanée disponibles pour les utilisateurs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="1adbf-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="1adbf-106">Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1adbf-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="1adbf-107">Pour en savoir plus, consultez [gérer les stratégies de messagerie dans teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1adbf-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="1adbf-108">Microsoft vous recommande de réactiver teams pour tous les utilisateurs d’une entreprise, de sorte que les équipes puissent être formées de manière biologique pour les projets et autres initiatives dynamiques.</span><span class="sxs-lookup"><span data-stu-id="1adbf-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="1adbf-109">Même si vous décidez de procéder au programme pilote, il est possible que les équipes puissent rester utiles pour tous les utilisateurs, mais uniquement cibler les communications destinées au groupe pilote des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1adbf-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="1adbf-110">Gérer teams via le centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1adbf-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="1adbf-111">Les licences de niveau utilisateur d’équipes sont gérées directement via les interfaces de gestion des utilisateurs du centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1adbf-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="1adbf-112">Un administrateur peut affecter des licences à de nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs possédant des comptes existants.</span><span class="sxs-lookup"><span data-stu-id="1adbf-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="1adbf-113">L’administrateur doit disposer de privilèges d’administrateur général ou de gestion des utilisateurs pour gérer les licences Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1adbf-113">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="1adbf-p104">Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1adbf-p104">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Capture d’écran de la section licences de produits dans le centre d’administration.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="1adbf-117">Une licence utilisateur d’équipes peut être désactivée à tout moment.</span><span class="sxs-lookup"><span data-stu-id="1adbf-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="1adbf-118">Lorsque la licence est désactivée, les utilisateurs qui accèdent à Microsoft teams sont empêchés et l’utilisateur ne peut plus voir teams dans le lanceur d’applications et la page d’accueil d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="1adbf-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Capture d’écran montrant les équipes sélectionnées dans la section licences de produits.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="1adbf-120">Gérer via PowerShell</span><span class="sxs-lookup"><span data-stu-id="1adbf-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1adbf-121">Le nouveau-MsolLicenseOptions activera tous les services précédemment désactivés, sauf s’ils sont explicitement identifiés dans votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="1adbf-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explicitly identified in your customized script.</span></span> <span data-ttu-id="1adbf-122">Par exemple, si vous souhaitez laisser Exchange & Sway désactivé lors de la désactivation d’équipes, vous devez l’inclure dans le script ou Exchange & Sway sera activé pour les utilisateurs que vous avez identifiés.</span><span class="sxs-lookup"><span data-stu-id="1adbf-122">As an example, if you wanted to leave both Exchange & Sway disabled while additionally disabling Teams, you'd need to include this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="1adbf-123">Pour utiliser une interface utilisateur pour gérer cette fonctionnalité, voir [outil de création de rapports et de gestion des licences Office 365-attribuer des licences en bloc](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="1adbf-123">To use a GUI to manage this functionality, see [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) for more information.</span></span>

<span data-ttu-id="1adbf-124">L’activation et la désactivation de Teams comme licence de charge de travail via PowerShell sont effectuées comme pour n'importe quelle charge de travail.</span><span class="sxs-lookup"><span data-stu-id="1adbf-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="1adbf-125">Le nom du plan de service est TEAMS1 pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1adbf-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="1adbf-126">Pour GCC, le nom du plan de service est TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="1adbf-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="1adbf-127">Dans le cas d’un nom de plan de service, le nom du plan de service est TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="1adbf-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="1adbf-128">Pour DoD, le nom du plan de service est TEAMS_DOD (voir [désactiver l’accès aux services avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) pour plus d’informations).</span><span class="sxs-lookup"><span data-stu-id="1adbf-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="1adbf-129">**Exemple :** Vous trouverez ci-dessous un exemple rapide de la manière dont vous allez désactiver teams pour tous les utilisateurs d’un type de licence particulier.</span><span class="sxs-lookup"><span data-stu-id="1adbf-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="1adbf-130">Vous devez commencer par cette opération. Ensuite, activez Microsoft Teams individuellement pour les utilisateurs devant y avoir accès à des fins de pilote.</span><span class="sxs-lookup"><span data-stu-id="1adbf-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="1adbf-131">Pour afficher les types d'abonnement dont vous disposez dans votre organisation, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1adbf-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="1adbf-132">Indiquez un nom pour votre forfait qui inclut le nom de votre organisation et le forfait pour votre établissement (par exemple ContosoSchool:ENTERPRISEPACK_STUDENT), puis exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1adbf-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="1adbf-133">Pour désactiver teams pour tous les utilisateurs disposant d’une licence active pour votre plan nommé, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1adbf-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="1adbf-135">Point de décision</span><span class="sxs-lookup"><span data-stu-id="1adbf-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="1adbf-136">Quels sont les plans de votre organisation pour l’intégration d’équipes au sein de l’Organisation ?</span><span class="sxs-lookup"><span data-stu-id="1adbf-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="1adbf-137">(Pilote ou ouvert)</span><span class="sxs-lookup"><span data-stu-id="1adbf-137">(Pilot or Open)</span></span></li></ul>         |
|![Icône représentant les étapes suivantes](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="1adbf-139">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="1adbf-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="1adbf-140">S’il s’agit d’une intégration par le biais d’un pilote fermé, décidez si vous souhaitez le faire par le biais d’une licence ou d’une communication ciblée.</span><span class="sxs-lookup"><span data-stu-id="1adbf-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="1adbf-141">En fonction de la décision, prenez des mesures pour vous assurer que seuls les utilisateurs pilotes peuvent accéder aux équipes (si nécessaire).</span><span class="sxs-lookup"><span data-stu-id="1adbf-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="1adbf-142">Documenter les recommandations relatives aux utilisateurs qui (ou non) ont accès aux équipes.</span><span class="sxs-lookup"><span data-stu-id="1adbf-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-organization-level"></a><span data-ttu-id="1adbf-143">Gérer teams au niveau de l’organisation Office 365</span><span class="sxs-lookup"><span data-stu-id="1adbf-143">Manage Teams at the Office 365 organization level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

