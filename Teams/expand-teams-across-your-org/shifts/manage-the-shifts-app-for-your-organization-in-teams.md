---
title: Gérer l’application Shifts pour votre organisation dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application Shifts dans teams pour terrain travailleurs de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 134ff131307034381b97643a2bf9a3dd7fc87a7d
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161857"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="25ade-103">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25ade-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25ade-104">À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="25ade-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="25ade-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25ade-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="25ade-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="25ade-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="25ade-107">StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019.</span><span class="sxs-lookup"><span data-stu-id="25ade-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="25ade-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="25ade-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="25ade-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="25ade-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="25ade-110">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="25ade-110">Overview of Shifts</span></span>

<span data-ttu-id="25ade-111">L’application Shifts dans Microsoft teams permet aux utilisateurs de terrain de se connecter et de se synchroniser avec eux. Il s’agit d’abord sur un appareil mobile pour une gestion rapide et efficace du temps pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="25ade-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="25ade-112">Les Shifts permettent à terrain travailleurs et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et rester en interaction.</span><span class="sxs-lookup"><span data-stu-id="25ade-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="25ade-113">Les responsables créent, mettent à jour et gèrent les plannings de Shifts pour Teams.</span><span class="sxs-lookup"><span data-stu-id="25ade-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="25ade-114">Ils peuvent envoyer des messages à une personne (« il y a un renversé sur le plancher ») ou à l’équipe entière (« le GM régional arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="25ade-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="25ade-115">Ils peuvent également envoyer des documents de stratégie, des bulletins d’actualité et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="25ade-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="25ade-116">Les employés peuvent afficher leurs Shifts à venir, peuvent voir qui est programmé pour la journée, demander à échanger ou proposer un Shift et demander du temps.</span><span class="sxs-lookup"><span data-stu-id="25ade-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="25ade-117">Il est important de savoir que les Shifts ne prennent actuellement pas en charge les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="25ade-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="25ade-118">Cela signifie que les invités ne peuvent pas être ajoutés à une équipe ou utiliser les plannings de décalage lorsque l’accès invité est activé dans Teams.</span><span class="sxs-lookup"><span data-stu-id="25ade-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="25ade-119">Disponibilité des équipes</span><span class="sxs-lookup"><span data-stu-id="25ade-119">Availability of Shifts</span></span>

<span data-ttu-id="25ade-120">Le changement est disponible dans toutes les références de l’entreprise, où teams est disponible.</span><span class="sxs-lookup"><span data-stu-id="25ade-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="25ade-121">Emplacement des données de décalage</span><span class="sxs-lookup"><span data-stu-id="25ade-121">Location of Shifts data</span></span>

<span data-ttu-id="25ade-122">Les données de décalage sont actuellement stockées dans Azure dans les centres de données en Amérique du Nord, en Europe de l’Ouest et en Asie-Pacifique.</span><span class="sxs-lookup"><span data-stu-id="25ade-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="25ade-123">Pour plus d’informations sur le stockage des données, voir [où se trouvent mes données](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="25ade-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="25ade-124">Configurer les Shifts</span><span class="sxs-lookup"><span data-stu-id="25ade-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="25ade-125">Activer ou désactiver les équipes au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="25ade-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="25ade-126">Les Shifts sont activés par défaut pour tous les utilisateurs d’équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="25ade-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="25ade-127">Vous pouvez activer ou désactiver l’application au niveau de l’organisation sur la page [gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25ade-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="25ade-128">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams** > **Manage** apps.</span><span class="sxs-lookup"><span data-stu-id="25ade-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="25ade-129">Dans la liste des applications, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="25ade-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="25ade-130">Pour désactiver les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **bloquer**.</span><span class="sxs-lookup"><span data-stu-id="25ade-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="25ade-131">Pour activer les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **allow**.</span><span class="sxs-lookup"><span data-stu-id="25ade-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="25ade-132">Activer ou désactiver les équipes pour des utilisateurs spécifiques de votre organisation</span><span class="sxs-lookup"><span data-stu-id="25ade-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="25ade-133">Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des équipes, assurez-vous que les Shifts sont activés pour votre organisation dans la page [gérer les applications](../../manage-apps.md) , puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="25ade-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="25ade-134">Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="25ade-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="25ade-135">Utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler les équipes dans teams</span><span class="sxs-lookup"><span data-stu-id="25ade-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="25ade-136">Les stratégies de configuration des applications vous permettent de personnaliser teams afin de mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="25ade-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="25ade-137">Les applications définies dans une stratégie sont épinglées à la barre&mdash;de l’application, qui se trouve sur le côté du client de bureau teams et dans la&mdash;partie inférieure des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et facilement.</span><span class="sxs-lookup"><span data-stu-id="25ade-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="25ade-138">Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez affecter à des employés terrain dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="25ade-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="25ade-139">Par défaut, la stratégie inclut les applications activités, équipes, discussions et appels.</span><span class="sxs-lookup"><span data-stu-id="25ade-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="25ade-140">Pour afficher la stratégie FirstlineWorker, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies de configuration**de l’application **teams** > .</span><span class="sxs-lookup"><span data-stu-id="25ade-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="25ade-141">![Capture d’écran de la stratégie de configuration de l’application FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FirstlineWorker dans le centre d’administration Microsoft teams")</span><span class="sxs-lookup"><span data-stu-id="25ade-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="25ade-142">Affecter la stratégie FirstlineWorker à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="25ade-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="25ade-143">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="25ade-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="25ade-144">En regard de **stratégies affectées**, choisissez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="25ade-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="25ade-145">Sous **stratégie de configuration des applications teams**, sélectionnez **FirstlineWorker**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="25ade-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="25ade-146">Affectez la stratégie de configuration de l’application FirstlineWorker aux membres des utilisateurs d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="25ade-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="25ade-147">Vous pouvez affecter la stratégie de configuration de l’application FirstlineWorker aux membres des utilisateurs d’un groupe, comme un groupe de sécurité, en vous connectant au service Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="25ade-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="25ade-148">Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="25ade-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="25ade-149">Dans cet exemple, nous affectons la stratégie d’installation de l’application FirstlineWorker à tous les membres du groupe d’équipes contoso terrain.</span><span class="sxs-lookup"><span data-stu-id="25ade-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="25ade-150">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="25ade-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="25ade-151">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="25ade-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="25ade-152">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="25ade-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="25ade-153">Affectez la stratégie de configuration de l’application FirstlineWorker à tous les membres de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="25ade-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="25ade-154">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="25ade-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25ade-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="25ade-155">Related topics</span></span>
- [<span data-ttu-id="25ade-156">Aide sur les équipes pour les travailleurs terrain</span><span class="sxs-lookup"><span data-stu-id="25ade-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
