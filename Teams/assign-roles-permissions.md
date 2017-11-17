---
title: "Assigner des rôles et des autorisations dans Microsoft Teams| Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 086f054ff5af2326d106ce5c2088a50106a76462
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="2f655-103">Assigner des rôles et des autorisations dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f655-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="2f655-p101">Microsoft Teams inclut deux rôles : **Propriétaire** et **Membre**. Par défaut, un utilisateur qui crée une équipe a le statut de Propriétaire. Si une équipe est créée à partir d'un groupe existant Office 365, les autorisations sont héritées.</span><span class="sxs-lookup"><span data-stu-id="2f655-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="2f655-107">Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre :</span><span class="sxs-lookup"><span data-stu-id="2f655-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="2f655-108">Propriétaire d'équipe</span><span class="sxs-lookup"><span data-stu-id="2f655-108">Team Owner</span></span>  |<span data-ttu-id="2f655-109">Membre d'équipe</span><span class="sxs-lookup"><span data-stu-id="2f655-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2f655-110">**Créer une équipe**</span><span class="sxs-lookup"><span data-stu-id="2f655-110">**Create team**</span></span>     |<span data-ttu-id="2f655-111">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-111">Yes</span></span>        |<span data-ttu-id="2f655-112">Non</span><span class="sxs-lookup"><span data-stu-id="2f655-112">No</span></span>         |
|<span data-ttu-id="2f655-113">**Quitter une équipe**</span><span class="sxs-lookup"><span data-stu-id="2f655-113">**Leave team**</span></span>     |<span data-ttu-id="2f655-114">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-114">Yes</span></span>         |<span data-ttu-id="2f655-115">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-115">Yes</span></span>         |
|<span data-ttu-id="2f655-116">**Modifier le nom/la description d'une équipe**</span><span class="sxs-lookup"><span data-stu-id="2f655-116">**Edit team name/description**</span></span>      |<span data-ttu-id="2f655-117">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-117">Yes</span></span>         |<span data-ttu-id="2f655-118">Non</span><span class="sxs-lookup"><span data-stu-id="2f655-118">No</span></span>         |
|<span data-ttu-id="2f655-119">**Supprimer une équipe**</span><span class="sxs-lookup"><span data-stu-id="2f655-119">**Delete team**</span></span>      |<span data-ttu-id="2f655-120">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-120">Yes</span></span>         |<span data-ttu-id="2f655-121">Non</span><span class="sxs-lookup"><span data-stu-id="2f655-121">No</span></span>         |
|<span data-ttu-id="2f655-122">**Ajouter un canal**</span><span class="sxs-lookup"><span data-stu-id="2f655-122">**Add channel**</span></span>      |<span data-ttu-id="2f655-123">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-123">Yes</span></span>         |<span data-ttu-id="2f655-124">Oui*</span><span class="sxs-lookup"><span data-stu-id="2f655-124">Yes*</span></span>         |
|<span data-ttu-id="2f655-125">**Modifier le nom/la description d'un canal**</span><span class="sxs-lookup"><span data-stu-id="2f655-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="2f655-126">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-126">Yes</span></span>         |<span data-ttu-id="2f655-127">Oui*</span><span class="sxs-lookup"><span data-stu-id="2f655-127">Yes*</span></span>         |
|<span data-ttu-id="2f655-128">**Supprimer un canal**</span><span class="sxs-lookup"><span data-stu-id="2f655-128">**Delete channel**</span></span>      |<span data-ttu-id="2f655-129">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-129">Yes</span></span>         |<span data-ttu-id="2f655-130">Oui*</span><span class="sxs-lookup"><span data-stu-id="2f655-130">Yes*</span></span>         |
|<span data-ttu-id="2f655-131">**Ajouter des membres**</span><span class="sxs-lookup"><span data-stu-id="2f655-131">**Add members**</span></span>      |<span data-ttu-id="2f655-132">Oui**</span><span class="sxs-lookup"><span data-stu-id="2f655-132">Yes**</span></span>         |<span data-ttu-id="2f655-133">Non</span><span class="sxs-lookup"><span data-stu-id="2f655-133">No</span></span>         |
|<span data-ttu-id="2f655-134">**Ajouter des onglets**</span><span class="sxs-lookup"><span data-stu-id="2f655-134">**Add tabs**</span></span>      |<span data-ttu-id="2f655-135">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-135">Yes</span></span>         |<span data-ttu-id="2f655-136">Oui*</span><span class="sxs-lookup"><span data-stu-id="2f655-136">Yes*</span></span>         |
|<span data-ttu-id="2f655-137">**Ajouter des connecteurs**</span><span class="sxs-lookup"><span data-stu-id="2f655-137">**Add connectors**</span></span>      |<span data-ttu-id="2f655-138">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-138">Yes</span></span>         |<span data-ttu-id="2f655-139">Oui*</span><span class="sxs-lookup"><span data-stu-id="2f655-139">Yes*</span></span>         |
|<span data-ttu-id="2f655-140">**Ajouter des bots**</span><span class="sxs-lookup"><span data-stu-id="2f655-140">**Add bots**</span></span>      |<span data-ttu-id="2f655-141">Oui</span><span class="sxs-lookup"><span data-stu-id="2f655-141">Yes</span></span>         |<span data-ttu-id="2f655-142">Oui*</span><span class="sxs-lookup"><span data-stu-id="2f655-142">Yes*</span></span>         |
<span data-ttu-id="2f655-143">\* Ces éléments peuvent être désactivés par un propriétaire au niveau d'une équipe, auquel cas les membres n'y auront pas accès.</span><span class="sxs-lookup"><span data-stu-id="2f655-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="2f655-p102">\*\*Après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de Propriétaire. Il est également possible pour un propriétaire de rétrograder son propre statut à celui de membre.</span><span class="sxs-lookup"><span data-stu-id="2f655-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>

| | |
|---------|---------|
|![Icône Ampoule.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="2f655-147">Remarque</span><span class="sxs-lookup"><span data-stu-id="2f655-147">Note</span></span>     |<span data-ttu-id="2f655-p103">Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes. Une équipe peut compter 10 propriétaires maximum.</span><span class="sxs-lookup"><span data-stu-id="2f655-p103">Owners can make other members owners in the View teams option. A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="2f655-150">Autorisations de créations d'équipes</span><span class="sxs-lookup"><span data-stu-id="2f655-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="2f655-p104">Par défaut, tous les utilisateurs disposant d'une boîte aux lettres dans Exchange Online disposent d'autorisations de créer des groupes Office 365 et par conséquent une équipe dans Microsoft Teams. Vous pouvez davantage contrôler et limiter la création d'équipes et donc de groupes Office 365 en délégant les droits de gestion et de création de groupes à un ensemble d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2f655-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="2f655-153">Si votre organisation est intéressée, les instructions ci-après présentent les tâches requises à cet effet.</span><span class="sxs-lookup"><span data-stu-id="2f655-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="2f655-154">Identifiez ou créez un groupe de sécurité (GS) d'utilisateurs qui disposeront d'autorisations déléguées pour créer des groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f655-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="2f655-p105">a.  **Action :** Configurez un groupe de sécurité dans Office 365 de manière à ajouter les utilisateurs qui peuvent créer des groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f655-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="2f655-p106">b.  Pour plus d'informations, reportez-vous au document [Créer, modifier ou supprimer un groupe de sécurité dans le centre d'administration Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="2f655-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="2f655-159">Vérifiez que le contrôle au niveau de l'entreprise permettant aux utilisateurs de créer des groupes est activé.</span><span class="sxs-lookup"><span data-stu-id="2f655-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="2f655-p107">a.  **Action :** Exécutez le script PowerShell suivant et vérifiez que le paramètre UsersPermissiontoCreateGroupsEnabled est défini sur **True.**</span><span class="sxs-lookup"><span data-stu-id="2f655-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="2f655-162">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="2f655-162">Connect-MsolService</span></span>

    <span data-ttu-id="2f655-163">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="2f655-163">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="2f655-164">b.</span><span class="sxs-lookup"><span data-stu-id="2f655-164">b.</span></span>  <span data-ttu-id="2f655-165">S'il n'est pas défini sur True, exécutez l'applet de commande Set-MsolCompanySettings **pour le définir sur True**.</span><span class="sxs-lookup"><span data-stu-id="2f655-165">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="2f655-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="2f655-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="2f655-p109">c. Pour plus d'informations, reportez-vous à la page suivante : [Gérer les utilisateurs qui peuvent créer des groupes Office 365.](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)</span><span class="sxs-lookup"><span data-stu-id="2f655-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="2f655-169">Configurez des paramètres de groupe Office 365 pour permettre uniquement au groupe de sécurité identifié disposant d'autorisations de créer des groupes.</span><span class="sxs-lookup"><span data-stu-id="2f655-169">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="2f655-p110">a.  **Action :** Créez un objet de paramètres de groupe contenant les paramètres de configuration du groupe auquel des autorisations déléguées de création de groupes seront affectées.</span><span class="sxs-lookup"><span data-stu-id="2f655-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="2f655-172">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="2f655-172">Connect-AzureAD</span></span>

    <span data-ttu-id="2f655-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="2f655-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="2f655-174">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="2f655-174">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="2f655-175">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="2f655-175">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="2f655-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span><span class="sxs-lookup"><span data-stu-id="2f655-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="2f655-177">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="2f655-177">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="2f655-p111">b. Pour plus d'informations, reportez-vous à la page suivante : [Gérer les utilisateurs qui peuvent créer des groupes Office 365.](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="2f655-p111">b. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="2f655-181">Point de décision</span><span class="sxs-lookup"><span data-stu-id="2f655-181">Decision Point</span></span>         |<span data-ttu-id="2f655-182">Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="2f655-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="2f655-184">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="2f655-184">Next Steps</span></span>         |<span data-ttu-id="2f655-185">Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.</span><span class="sxs-lookup"><span data-stu-id="2f655-185">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
