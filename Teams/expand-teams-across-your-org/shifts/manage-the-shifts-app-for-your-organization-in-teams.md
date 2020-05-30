---
title: Gestion de l’application Shifts pour votre organisation
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416884"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="7b219-103">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b219-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b219-104">À compter du 30 juin 2020, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="7b219-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="7b219-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7b219-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="7b219-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="7b219-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="7b219-107">StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 30 juin 2020.</span><span class="sxs-lookup"><span data-stu-id="7b219-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="7b219-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="7b219-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="7b219-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="7b219-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="7b219-110">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="7b219-110">Overview of Shifts</span></span>

<span data-ttu-id="7b219-111">L’application Shifts dans Microsoft teams permet aux utilisateurs de terrain de se connecter et de se synchroniser avec eux. Il s’agit d’abord sur un appareil mobile pour une gestion rapide et efficace du temps pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="7b219-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="7b219-112">Les Shifts permettent à terrain travailleurs et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et rester en interaction.</span><span class="sxs-lookup"><span data-stu-id="7b219-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="7b219-113">Les responsables créent, mettent à jour et gèrent les plannings de Shifts pour Teams.</span><span class="sxs-lookup"><span data-stu-id="7b219-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="7b219-114">Ils peuvent envoyer des messages à une personne (« il y a un renversé sur le plancher ») ou à l’équipe entière (« le GM régional arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="7b219-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="7b219-115">Ils peuvent également envoyer des documents de stratégie, des bulletins d’actualité et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="7b219-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="7b219-116">Les employés peuvent afficher leurs Shifts à venir, peuvent voir qui est programmé pour la journée, demander à échanger ou proposer un Shift et demander du temps.</span><span class="sxs-lookup"><span data-stu-id="7b219-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="7b219-117">Il est important de savoir que les Shifts ne prennent actuellement pas en charge les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="7b219-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="7b219-118">Cela signifie que les invités ne peuvent pas être ajoutés à une équipe ou utiliser les plannings de décalage lorsque l’accès invité est activé dans Teams.</span><span class="sxs-lookup"><span data-stu-id="7b219-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="7b219-119">Disponibilité des équipes</span><span class="sxs-lookup"><span data-stu-id="7b219-119">Availability of Shifts</span></span>

<span data-ttu-id="7b219-120">Le changement est disponible dans toutes les références de l’entreprise, où teams est disponible.</span><span class="sxs-lookup"><span data-stu-id="7b219-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="7b219-121">Emplacement des données de décalage</span><span class="sxs-lookup"><span data-stu-id="7b219-121">Location of Shifts data</span></span>

<span data-ttu-id="7b219-122">Les données de décalage sont actuellement stockées dans Azure dans les centres de données en Amérique du Nord, en Europe de l’Ouest et en Asie-Pacifique.</span><span class="sxs-lookup"><span data-stu-id="7b219-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="7b219-123">Pour plus d’informations sur le stockage des données, voir [où se trouvent mes données](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="7b219-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="7b219-124">Configurer les Shifts</span><span class="sxs-lookup"><span data-stu-id="7b219-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="7b219-125">Activer ou désactiver les équipes au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="7b219-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="7b219-126">Les Shifts sont activés par défaut pour tous les utilisateurs d’équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7b219-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="7b219-127">Vous pouvez activer ou désactiver l’application au niveau de l’organisation sur la page [gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7b219-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="7b219-128">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.</span><span class="sxs-lookup"><span data-stu-id="7b219-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="7b219-129">Dans la liste des applications, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b219-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="7b219-130">Pour désactiver les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **bloquer**.</span><span class="sxs-lookup"><span data-stu-id="7b219-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="7b219-131">Pour activer les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **allow**.</span><span class="sxs-lookup"><span data-stu-id="7b219-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="7b219-132">Activer ou désactiver les équipes pour des utilisateurs spécifiques de votre organisation</span><span class="sxs-lookup"><span data-stu-id="7b219-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="7b219-133">Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des équipes, assurez-vous que les Shifts sont activés pour votre organisation dans la page [gérer les applications](../../manage-apps.md) , puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7b219-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="7b219-134">Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7b219-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="7b219-135">Utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler les équipes dans teams</span><span class="sxs-lookup"><span data-stu-id="7b219-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="7b219-136">Les stratégies de configuration des applications vous permettent de personnaliser teams afin de mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7b219-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="7b219-137">Les applications définies dans une stratégie sont épinglées à la barre de l’application &mdash; , qui se trouve sur le côté du client de bureau teams et dans la partie inférieure des clients mobiles Teams, &mdash; où les utilisateurs peuvent y accéder rapidement et facilement.</span><span class="sxs-lookup"><span data-stu-id="7b219-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="7b219-138">Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez affecter à des employés terrain dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7b219-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="7b219-139">Par défaut, la stratégie inclut les applications activités, équipes, discussions et appels.</span><span class="sxs-lookup"><span data-stu-id="7b219-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="7b219-140">Pour afficher la stratégie FirstlineWorker, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration de l’application **teams**  >  **App setup policies**.</span><span class="sxs-lookup"><span data-stu-id="7b219-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="7b219-141">![Capture d’écran de la stratégie de configuration de l’application FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FirstlineWorker dans le centre d’administration Microsoft teams")</span><span class="sxs-lookup"><span data-stu-id="7b219-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-users"></a><span data-ttu-id="7b219-142">Affecter la stratégie FirstlineWorker aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7b219-142">Assign the FirstlineWorker policy to users</span></span>

<span data-ttu-id="7b219-143">Pour affecter la stratégie de configuration de l’application FirstlineWorker à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="7b219-143">To assign the FirstlineWorker app setup policy to one user:</span></span>

1. <span data-ttu-id="7b219-144">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7b219-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="7b219-145">Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="7b219-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="7b219-146">Sous **stratégie de configuration des applications**, sélectionnez **FirstlineWorker**, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="7b219-146">Under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>

<span data-ttu-id="7b219-147">Pour affecter une stratégie à plusieurs utilisateurs à la fois :</span><span class="sxs-lookup"><span data-stu-id="7b219-147">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="7b219-148">Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.</span><span class="sxs-lookup"><span data-stu-id="7b219-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="7b219-149">Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7b219-149">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="7b219-150">Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="7b219-150">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="7b219-151">Cliquez sur **modifier les paramètres**, sous stratégie de configuration des **applications**, sélectionnez **FirstlineWorker**, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="7b219-151">Click **Edit settings**, under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>  

<span data-ttu-id="7b219-152">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b219-152">Or, you can also do the following:</span></span>

1. <span data-ttu-id="7b219-153">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration des **applications teams**  >  **Setup policies**.</span><span class="sxs-lookup"><span data-stu-id="7b219-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="7b219-154">Sélectionnez la stratégie FirstlineWorker en cliquant à gauche du nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="7b219-154">Select the FirstlineWorker policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="7b219-155">Sélectionnez **Gérer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="7b219-155">Select **Manage users**.</span></span>
4. <span data-ttu-id="7b219-156">Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="7b219-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="7b219-157">Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="7b219-157">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="7b219-158">Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="7b219-158">After you finish adding users, select **Apply**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="7b219-159">Affectez la stratégie de configuration de l’application FirstlineWorker aux membres des utilisateurs d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="7b219-159">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="7b219-160">Vous pouvez affecter la stratégie de configuration de l’application FirstlineWorker aux membres des utilisateurs d’un groupe, comme un groupe de sécurité, en vous connectant au service Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="7b219-160">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="7b219-161">Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b219-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="7b219-162">Dans cet exemple, nous affectons la stratégie d’installation de l’application FirstlineWorker à tous les membres du groupe d’équipes contoso terrain.</span><span class="sxs-lookup"><span data-stu-id="7b219-162">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="7b219-163">Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="7b219-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="7b219-164">Obtenez la GroupObjectId du groupe en particulier.</span><span class="sxs-lookup"><span data-stu-id="7b219-164">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="7b219-165">Obtenez les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="7b219-165">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="7b219-166">Affectez la stratégie de configuration de l’application FirstlineWorker à tous les membres de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="7b219-166">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="7b219-167">En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="7b219-167">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="7b219-168">Effectuer une recherche dans le journal d’audit pour les événements de décalage</span><span class="sxs-lookup"><span data-stu-id="7b219-168">Search the audit log for Shifts events</span></span>

<span data-ttu-id="7b219-169">**(version d’évaluation)**</span><span class="sxs-lookup"><span data-stu-id="7b219-169">**(in preview)**</span></span>

<span data-ttu-id="7b219-170">Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité de décalage au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7b219-170">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="7b219-171">Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit et d’afficher la liste des [activités de décalage](../../audit-log-events.md#shifts-in-teams-activities) enregistrées dans le journal d’audit, voir [effectuer des recherches dans le journal d’audit pour les événements dans teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="7b219-171">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="7b219-172">Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="7b219-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="7b219-173">Pour plus d’informations, voir [activer ou désactiver la recherche dans le journal d’audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="7b219-173">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="7b219-174">Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.</span><span class="sxs-lookup"><span data-stu-id="7b219-174">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b219-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b219-175">Related topics</span></span>

- [<span data-ttu-id="7b219-176">Aide sur les équipes pour les travailleurs terrain</span><span class="sxs-lookup"><span data-stu-id="7b219-176">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="7b219-177">Attribuer des stratégies à vos utilisateurs dans teams</span><span class="sxs-lookup"><span data-stu-id="7b219-177">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
