---
title: Archiver ou supprimer une équipe dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Dans cet article, vous allez découvrir comment archiver ou supprimer définitivement une équipe dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97cce8577c2d3c23e097f5e3bf5d819d51a16b10
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856363"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="bc116-103">Archiver ou supprimer une équipe dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc116-103">Archive or delete a team in Microsoft Teams</span></span>

<span data-ttu-id="bc116-104">Au fil du temps, une équipe créée dans Microsoft Teams risque de ne plus être utilisée ou vous pouvez souhaiter d’archiver ou de supprimer une équipe à la fin d’un projet.</span><span class="sxs-lookup"><span data-stu-id="bc116-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="bc116-105">Si vous êtes un administrateur Microsoft Teams, suivez les étapes décrites dans cet article pour archiver ou supprimer une équipe qui n’est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="bc116-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="bc116-106">Lorsque vous archivez une équipe, toute l’activité de cette équipe cesse.</span><span class="sxs-lookup"><span data-stu-id="bc116-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="bc116-107">L’archivage d’une équipe archive également les canaux privés au sein de l’équipe et les collections de sites associées.</span><span class="sxs-lookup"><span data-stu-id="bc116-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="bc116-108">Cependant, vous pouvez toujours ajouter ou supprimer des membres et mettre à jour les rôles et vous pouvez toujours afficher toutes les activités de l'équipe dans les canaux, fichiers et conversations instantanées standard et privés.</span><span class="sxs-lookup"><span data-stu-id="bc116-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="bc116-109">Lorsque vous supprimez une équipe, l’activité d’équipe dans les canaux standard et privés (et les collections de sites associées), les fichiers et les conversations instantanées est également supprimée.</span><span class="sxs-lookup"><span data-stu-id="bc116-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc116-110">Les équipes archivées peuvent être réactivées, mais vous ne pouvez pas restaurer directement une équipe qui a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="bc116-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="bc116-111">Vous devez commencer par archiver l’équipe et retarder la suppression jusqu’à ce que vous soyez certain que vous n’avez plus besoin de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="bc116-112">Archiver une équipe</span><span class="sxs-lookup"><span data-stu-id="bc116-112">Archive a team</span></span>

<span data-ttu-id="bc116-113">Suivez ces étapes pour archiver une équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="bc116-114">Vous devez être un administrateur du service Teams pour apporter ces modifications.</span><span class="sxs-lookup"><span data-stu-id="bc116-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="bc116-115">Voir [Gérer Teams grâce aux rôles d’administrateur Teams](./using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="bc116-115">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="bc116-116">Dans le Centre d’administration, **sélectionnez Teams.**</span><span class="sxs-lookup"><span data-stu-id="bc116-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="bc116-117">Sélectionnez une équipe en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="bc116-118">Sélectionnez **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="bc116-118">Select **Archive**.</span></span> <span data-ttu-id="bc116-119">Le message suivant s’affichera.</span><span class="sxs-lookup"><span data-stu-id="bc116-119">The following message will appear.</span></span>

    ![Capture d’écran du message archive d’équipe](media/teams-archive-message.png)

4. <span data-ttu-id="bc116-121">Pour empêcher les utilisateurs de modifier le contenu du site SharePoint et de l’onglet Wiki associés à l’équipe, sélectionnez Rendre le site SharePoint en lecture seule pour les membres de **l’équipe.**</span><span class="sxs-lookup"><span data-stu-id="bc116-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="bc116-122">(Teams propriétaires pourront toujours modifier ce contenu.)</span><span class="sxs-lookup"><span data-stu-id="bc116-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="bc116-123">Sélectionnez **Archiver** pour archiver l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="bc116-124">Le statut de l’équipe passera à **Archivé**.</span><span class="sxs-lookup"><span data-stu-id="bc116-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="bc116-125">Rendre une équipe archivée active</span><span class="sxs-lookup"><span data-stu-id="bc116-125">Make an archived team active</span></span>

<span data-ttu-id="bc116-126">Pour réactiver une équipe archivée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bc116-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="bc116-127">Dans le Centre d’administration, **sélectionnez Teams.**</span><span class="sxs-lookup"><span data-stu-id="bc116-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="bc116-128">Sélectionnez une équipe en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="bc116-129">Sélectionnez **Désarchiver**.</span><span class="sxs-lookup"><span data-stu-id="bc116-129">Select **Unarchive**.</span></span> <span data-ttu-id="bc116-130">Le statut de l’équipe passera à **Active**.</span><span class="sxs-lookup"><span data-stu-id="bc116-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="bc116-131">Supprimer une équipe</span><span class="sxs-lookup"><span data-stu-id="bc116-131">Delete a team</span></span>

<span data-ttu-id="bc116-132">Si l’équipe ne sera pas nécessaire, vous pouvez la supprimer plutôt que de l’archiver.</span><span class="sxs-lookup"><span data-stu-id="bc116-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="bc116-133">Pour supprimer une équipe, suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="bc116-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="bc116-134">Dans le Centre d’administration, **sélectionnez Teams.**</span><span class="sxs-lookup"><span data-stu-id="bc116-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="bc116-135">Sélectionnez une équipe en cliquant sur le nom de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="bc116-136">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="bc116-136">Select **Delete**.</span></span> <span data-ttu-id="bc116-137">Un message de confirmation s’affichera.</span><span class="sxs-lookup"><span data-stu-id="bc116-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="bc116-138">Sélectionnez **Supprimer** pour supprimer définitivement l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="bc116-139">Restaurer une équipe supprimée</span><span class="sxs-lookup"><span data-stu-id="bc116-139">Restore a deleted team</span></span>

<span data-ttu-id="bc116-140">Pour restaurer une équipe supprimée, suivez ces étapes en restaurant Microsoft 365 groupe associé à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="bc116-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="bc116-141">La restauration du Microsoft 365 d’une équipe restaure le contenu de l’équipe, y compris les onglets, les canaux standard et les canaux privés et les collections de sites associées.</span><span class="sxs-lookup"><span data-stu-id="bc116-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="bc116-142">Par défaut, un groupe de Microsoft 365 supprimé est conservé pendant 30 jours.</span><span class="sxs-lookup"><span data-stu-id="bc116-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="bc116-143">Cette période de 30 jours est appelée « suppression réversible », car vous avez la possibilité de le restaurer.</span><span class="sxs-lookup"><span data-stu-id="bc116-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="bc116-144">Pour en savoir plus, voir [Restaurer un groupe supprimé.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="bc116-144">To learn more, see [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="bc116-145">Installez le module AzureADPreview</span><span class="sxs-lookup"><span data-stu-id="bc116-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="bc116-146">Ouvrez Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="bc116-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="bc116-147">Si une version antérieure du module AzureADPreview est installée ou si le module AzureAD est installé, désinstallez-le en exécutant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc116-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="bc116-148">Installez la dernière version du module AzureADPreview en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bc116-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="bc116-149">Restaurer le groupe de Microsoft 365 supprimé</span><span class="sxs-lookup"><span data-stu-id="bc116-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="bc116-150">Connectez-vous à Azure AD en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bc116-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="bc116-151">Lorsque vous y êtes invité, connectez-vous à l’aide de votre compte d’administrateur et de votre mot de passe.</span><span class="sxs-lookup"><span data-stu-id="bc116-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="bc116-152">Exécutez la liste suivante pour afficher la liste de tous les groupes de rétention supprimés de Microsoft 365 supprimés de nouveau pour une période de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="bc116-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="bc116-153">Utilisez le paramètre **-All $True** si vous avez un grand nombre de groupes.</span><span class="sxs-lookup"><span data-stu-id="bc116-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="bc116-154">Trouvez le groupe que vous voulez restaurer, puis notez l’ID.</span><span class="sxs-lookup"><span data-stu-id="bc116-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="bc116-155">Exécutez la commande suivante pour restaurer le groupe, où [id] est l’ID de groupe.</span><span class="sxs-lookup"><span data-stu-id="bc116-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="bc116-156">Exécutez la commande suivante pour vérifier que le groupe a été correctement restauré, où [id] est l’ID de groupe.</span><span class="sxs-lookup"><span data-stu-id="bc116-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="bc116-157">L’exécution du processus de restauration peut prendre jusqu’à 24 heures, après quoi l’équipe et le contenu associé à l’équipe, y compris les onglets et les canaux, s’affichent dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bc116-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>