---
title: Disponibilité des applications Approbations dans Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: En savoir plus sur la disponibilité des applications Approbations dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212167"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="a9be0-103">Disponibilité de l’application Approbations Teams</span><span class="sxs-lookup"><span data-stu-id="a9be0-103">Teams Approvals app availability</span></span>

<span data-ttu-id="a9be0-104">L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a9be0-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="a9be0-105">L’application Approbations offre un moyen simple d’apporter des audits, de la conformité, de la responsabilité et des flux de travail à des approbations structurées et non structurées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="a9be0-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![affiche l’application Approbations](media/approvals-selection.png)

<span data-ttu-id="a9be0-107">Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="a9be0-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![affiche l’application Approbations avec l’option épingler](media/approvalApp-pin.png)

<span data-ttu-id="a9be0-109">La première approbation créée à partir de l’application Approbations déclenche la mise en service de la solution d’approbation dans l’environnement de service de données courant (CDS) par défaut.</span><span class="sxs-lookup"><span data-stu-id="a9be0-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="a9be0-110">Les approbations créées à partir de l’application Approbations seront stockées dans l’environnement CDS par défaut.</span><span class="sxs-lookup"><span data-stu-id="a9be0-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="a9be0-111">Cet article décrit la exigences et les rôles de l’application Approbations.</span><span class="sxs-lookup"><span data-stu-id="a9be0-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="a9be0-112">Cette fonctionnalité n’a pas encore été publiée pour les utilisateurs des services Cloud de la communauté du secteur public (Cloud de la communauté du secteur public), Cloud de la communauté du secteur public High (GCCH) et Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="a9be0-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="a9be0-113">Autorisations et licences requises</span><span class="sxs-lookup"><span data-stu-id="a9be0-113">Required permissions and licenses</span></span>

<span data-ttu-id="a9be0-114">Pour utiliser l’application Approbations, vous devez avoir une autorisation pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a9be0-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="a9be0-115">Autorisations pour créer une base de données CDS Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9be0-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="a9be0-116">Un compte sur [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a9be0-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="a9be0-117">Rôle d’administrateur dans l’environnement cible.</span><span class="sxs-lookup"><span data-stu-id="a9be0-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="a9be0-118">Licence pour une [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a9be0-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="a9be0-119">Une licence microsoft Forms est requise pour que les utilisateurs définissent de nouveaux modèles d’approbation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="a9be0-120">Stockage avec CDS</span><span class="sxs-lookup"><span data-stu-id="a9be0-120">Storage with CDS</span></span>

<span data-ttu-id="a9be0-121">Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications professionnelles et analytiques dans les CDS.</span><span class="sxs-lookup"><span data-stu-id="a9be0-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="a9be0-122">Il s'agit d'un ensemble de schémas de données standardisés et extensibles publiés par Microsoft et ses partenaires, qui permettent d'assurer la cohérence des données et de leur signification entre les applications et les processus métier.</span><span class="sxs-lookup"><span data-stu-id="a9be0-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="a9be0-123">En savoir plus sur [Modèle de données courant de Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="a9be0-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="a9be0-124">En savoir plus sur le [flux d’approbation](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="a9be0-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="a9be0-125">Les approbations créées à partir d’un modèle stockent toujours les données dans des CDS, comme leur titre, les détails, l’ID de modèle, etc.</span><span class="sxs-lookup"><span data-stu-id="a9be0-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="a9be0-126">Les réponses envoyées sur la demande d’approbation sont stockées dans Forms.</span><span class="sxs-lookup"><span data-stu-id="a9be0-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="a9be0-127">En savoir plus sur  [le stockage de données pour Microsoft Forms.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)</span><span class="sxs-lookup"><span data-stu-id="a9be0-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="a9be0-128">Si vous supprimez le modèle de formulaire sur le site Microsoft Forms, votre modèle Approbation sera supprimé et les utilisateurs ne pourront pas démarrer la demande.</span><span class="sxs-lookup"><span data-stu-id="a9be0-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="a9be0-129">Les utilisateurs obtiennent une erreur « CDB TableNotFound » lorsqu’ils essaient d’ouvrir un modèle d’approbation qui a été supprimé dans Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="a9be0-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="a9be0-130">Les modèles d’approbation sont stockés dans le centre de données Stockage (SDS), plateforme de stockage compatible utilisée en interne uniquement à l’intérieur de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9be0-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="a9be0-131">Les modèles de l’étendue de l’organisation sont stockés dans « shard client » de SDS, et les modèles d’étendue de l’équipe dans des « shard de groupe » de SDS.</span><span class="sxs-lookup"><span data-stu-id="a9be0-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="a9be0-132">Cela signifie que les modèles à l’échelle de l’organisation partagent la même durée de vie du client et les modèles d’équipe partagent la même durée de vie de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="a9be0-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="a9be0-133">Par conséquent, la suppression définitive de l’équipe supprime les modèles associés.</span><span class="sxs-lookup"><span data-stu-id="a9be0-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="a9be0-134">Autorisations de l’application Autorisations Teams</span><span class="sxs-lookup"><span data-stu-id="a9be0-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="a9be0-135">L’application Approbations Teams vous permet d’accéder aux fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9be0-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="a9be0-136">Recevoir les messages et les données que vous lui fournissez.</span><span class="sxs-lookup"><span data-stu-id="a9be0-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="a9be0-137">Vous envoyer des messages et des notifications.</span><span class="sxs-lookup"><span data-stu-id="a9be0-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="a9be0-138">Rendre les applications et les boîtes de dialogue personnelles sans en-tête fourni par Teams.</span><span class="sxs-lookup"><span data-stu-id="a9be0-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="a9be0-139">Accéder à vos informations de profil telles que votre nom, adresse e-mail, nom de votre entreprise et la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="a9be0-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="a9be0-140">Recevoir les messages et les données que les membres d’une équipe lui fournissent dans un canal.</span><span class="sxs-lookup"><span data-stu-id="a9be0-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="a9be0-141">Envoyer des messages et des notifications dans un canal.</span><span class="sxs-lookup"><span data-stu-id="a9be0-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="a9be0-142">Accédez aux informations de votre équipe :</span><span class="sxs-lookup"><span data-stu-id="a9be0-142">Access your team's information:</span></span>
  - <span data-ttu-id="a9be0-143">nom de l'équipe</span><span class="sxs-lookup"><span data-stu-id="a9be0-143">team name</span></span>
  - <span data-ttu-id="a9be0-144">liste des canaux</span><span class="sxs-lookup"><span data-stu-id="a9be0-144">channel list</span></span>
  - <span data-ttu-id="a9be0-145">liste de présence (noms et adresses de courrier des membres de l’équipe).</span><span class="sxs-lookup"><span data-stu-id="a9be0-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="a9be0-146">Utilisez les informations de l'équipe pour les contacter.</span><span class="sxs-lookup"><span data-stu-id="a9be0-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="a9be0-147">Autorisations du modèle d’approbation</span><span class="sxs-lookup"><span data-stu-id="a9be0-147">Approval Template Permissions</span></span>

- <span data-ttu-id="a9be0-148">Tous les propriétaires d’équipe peuvent créer un modèle d’approbation pour les équipes dont ils sont propriétaires.</span><span class="sxs-lookup"><span data-stu-id="a9be0-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="a9be0-149">Lorsqu’un administrateur crée un modèle pour l’ensemble de son organisation pour la première fois, il crée automatiquement une équipe Teams pour tous les administrateurs du client, y compris les administrateurs de services de l’équipe et de l’ensemble.</span><span class="sxs-lookup"><span data-stu-id="a9be0-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="a9be0-150">Ces administrateurs sont ajoutés en tant que propriétaires de l’équipe, afin qu’ils peuvent co-gérer les modèles d’organisation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="a9be0-151">Les administrateurs qui débutent dans l’organisation une fois l’équipe créée doivent être ajoutés manuellement en tant que propriétaires d’équipe afin qu’ils disposent des mêmes autorisations pour gérer les modèles à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="a9be0-152">Si un administrateur supprime l’équipe, vous avez un mois pour la restaurer dans le portail Azure Active Directory ad (AAD) afin de restaurer toutes les données associées.</span><span class="sxs-lookup"><span data-stu-id="a9be0-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="a9be0-153">Après un mois, ou si l’administrateur supprime cette équipe dans la Corbeille, vous perdrez toutes les données associées.</span><span class="sxs-lookup"><span data-stu-id="a9be0-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="a9be0-154">Gérer l'application Approbations</span><span class="sxs-lookup"><span data-stu-id="a9be0-154">Disable the Approvals app</span></span>

<span data-ttu-id="a9be0-155">L’application Approbations est disponible par défaut.</span><span class="sxs-lookup"><span data-stu-id="a9be0-155">The Approvals app is available by default.</span></span> <span data-ttu-id="a9be0-156">Vous pouvez désactiver l’application dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="a9be0-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="a9be0-157">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a9be0-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="a9be0-158">Développez **Applications Teams** et sélectionnez **Gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="a9be0-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="a9be0-159">Recherchez l’application Approbations.</span><span class="sxs-lookup"><span data-stu-id="a9be0-159">Search for the Approvals app.</span></span>

     ![affiche la navigation du Centre d’administration avec l’écran Applications Teams > Gérer les applications mis en évidence](media/manage-approval-apps.png)

  4. <span data-ttu-id="a9be0-161">Sélectionnez Approbations.</span><span class="sxs-lookup"><span data-stu-id="a9be0-161">Select Approvals.</span></span>

  5. <span data-ttu-id="a9be0-162">Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-162">Select the toggle to disable the app for your organization.</span></span>

     ![affiche les détails de l’application Approbations](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="a9be0-164">Stratégie de rétention</span><span class="sxs-lookup"><span data-stu-id="a9be0-164">Retention policy</span></span>

<span data-ttu-id="a9be0-165">Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement CDS par défaut, qui ne prend pas en charge les sauvegardes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="a9be0-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="a9be0-166">En savoir plus sur la [Sauvegarde et restauration des environnements : Plateforme Power \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="a9be0-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="a9be0-167">Les données stockées dans Forms ne sont pas supprimées  tant que les propriétaires d’équipe ne les ont pas effacées à partir de l’onglet Formulaires supprimés dans l’application web Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="a9be0-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="a9be0-168">Limites de données</span><span class="sxs-lookup"><span data-stu-id="a9be0-168">Data limitations</span></span>

<span data-ttu-id="a9be0-169">Chaque équipe peut contenir au maximum 400 modèles d’approbations, et chaque modèle peut collecter un maximum de 50 000 demandes sur la base des fonctionnalités actuelles de Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="a9be0-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="a9be0-170">Audit</span><span class="sxs-lookup"><span data-stu-id="a9be0-170">Auditing</span></span>

<span data-ttu-id="a9be0-171">L’application Approbations enregistre les événements d’audit dans le Centre de sécurité et conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9be0-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="a9be0-172">Vous pouvez afficher le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="a9be0-172">You can view the audit log.</span></span>

1. <span data-ttu-id="a9be0-173">Accédez au site de conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9be0-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="a9be0-174">Sélectionnez la section **Audit**.</span><span class="sxs-lookup"><span data-stu-id="a9be0-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="a9be0-175">Recherchez des activités sous **Activités d’approbation de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="a9be0-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="a9be0-176">Vous pouvez rechercher les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9be0-176">You can search for the following activities:</span></span>

- <span data-ttu-id="a9be0-177">Créer une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="a9be0-177">Create new approval request</span></span>

- <span data-ttu-id="a9be0-178">Afficher les détails de la demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="a9be0-178">View approval request details</span></span>

- <span data-ttu-id="a9be0-179">Demande d’approbation approuvée</span><span class="sxs-lookup"><span data-stu-id="a9be0-179">Approved approval request</span></span>

- <span data-ttu-id="a9be0-180">Demande d’approbation rejetée</span><span class="sxs-lookup"><span data-stu-id="a9be0-180">Rejected approval request</span></span>

- <span data-ttu-id="a9be0-181">Demande d’approbation annulée</span><span class="sxs-lookup"><span data-stu-id="a9be0-181">Canceled approval request</span></span>

- <span data-ttu-id="a9be0-182">Demande d’approbation partagée</span><span class="sxs-lookup"><span data-stu-id="a9be0-182">Shared approval request</span></span>

- <span data-ttu-id="a9be0-183">Fichier joint à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="a9be0-183">File attached to approval request</span></span>

- <span data-ttu-id="a9be0-184">Demande d'approbation réaffectée</span><span class="sxs-lookup"><span data-stu-id="a9be0-184">Reassigned approval request</span></span>

- <span data-ttu-id="a9be0-185">Ajout d’une signature électronique à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="a9be0-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="a9be0-186">Affichage des détails de la demande de signature électronique</span><span class="sxs-lookup"><span data-stu-id="a9be0-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="a9be0-187">Demande de signature électronique examinée</span><span class="sxs-lookup"><span data-stu-id="a9be0-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="a9be0-188">Demande de signature électronique annulée</span><span class="sxs-lookup"><span data-stu-id="a9be0-188">Canceled e-signature request</span></span>

- <span data-ttu-id="a9be0-189">Créer un modèle</span><span class="sxs-lookup"><span data-stu-id="a9be0-189">Create a new template</span></span>

- <span data-ttu-id="a9be0-190">Modifier un modèle existant</span><span class="sxs-lookup"><span data-stu-id="a9be0-190">Edit an existing template</span></span>

- <span data-ttu-id="a9be0-191">Activer/désactiver un modèle</span><span class="sxs-lookup"><span data-stu-id="a9be0-191">Enable/disable a template</span></span>

- <span data-ttu-id="a9be0-192">Modèle affichage</span><span class="sxs-lookup"><span data-stu-id="a9be0-192">Viewed template</span></span>

<span data-ttu-id="a9be0-193">Pour accéder à davantage d’approbations d’audit dans flux, activez et configurez l'audit dans l'environnement par défaut pour les entités d'approbation primaires Approbation, Demande d'approbation et Réponse d'approbation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="a9be0-194">Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements d’approbation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="a9be0-195">En savoir plus sur [Audit des données et de l’activité des utilisateurs pour des raisons de sécurité et de conformité : Plateforme Power \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="a9be0-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="a9be0-196">L’audit peut être personnalisé davantage dans le [Centre de conformité et sécurité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="a9be0-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="a9be0-197">Pour utiliser les rapports préconfigurés, connectez-vous à Conformité et sécurité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9be0-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="a9be0-198">Sélectionnez **Recherche et enquête**.</span><span class="sxs-lookup"><span data-stu-id="a9be0-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="a9be0-199">Recherchez dans le journal d’audit et sélectionnez l’onglet **Activités Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="a9be0-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="a9be0-200">En savoir plus sur [Journalisation des activités de Microsoft Dataverse et des applications pilotées par les modèles :Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="a9be0-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="a9be0-201">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a9be0-201">Security</span></span>

<span data-ttu-id="a9be0-202">À partir de l’application Approbations Teams, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations envoyées et reçues.</span><span class="sxs-lookup"><span data-stu-id="a9be0-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="a9be0-203">Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils répondent ou visualisent la demande.</span><span class="sxs-lookup"><span data-stu-id="a9be0-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="a9be0-204">Un utilisateur a le rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal sur lequel l’approbation a été créée.</span><span class="sxs-lookup"><span data-stu-id="a9be0-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="a9be0-205">Il ne peut pas agir sur la demande si ce rôle ne lui a pas été affecté lors de la création de l’approbation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="a9be0-206">Intégration de la signature électronique Approbations</span><span class="sxs-lookup"><span data-stu-id="a9be0-206">Approvals e-signature integration</span></span>

<span data-ttu-id="a9be0-207">Les approbations de signature électronique créées à partir de l’application Approbations sont stockées dans l’environnement cloud du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a9be0-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="a9be0-208">Pour plus d’informations sur le stockage autour du contrat de signature électronique, consultez la documentation de stockage du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a9be0-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="a9be0-209">Pour utiliser la fonctionnalité de signature électronique de l’application Approbations, vous devez avoir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a9be0-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="a9be0-210">Licence du fournisseur de signature électronique que vous choisissez d’utiliser.</span><span class="sxs-lookup"><span data-stu-id="a9be0-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="a9be0-211">Pour obtenir une licence pour votre organisation, vous devez vous rendre sur le site du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a9be0-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="a9be0-212">Pour la fonctionnalité de signature électronique Approbations, les partenaires de signature tiers apparaissent par défaut dans l’Teams Approbations.</span><span class="sxs-lookup"><span data-stu-id="a9be0-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="a9be0-213">Vous pouvez désactiver des fournisseurs de signature électronique spécifiques en accédant aux paramètres de l’application dans Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="a9be0-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="a9be0-214">Dans la Teams d’administration, sous **Gérer** les applications, sélectionnez l’application **Approbations,** puis **Paramètres.**</span><span class="sxs-lookup"><span data-stu-id="a9be0-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="a9be0-215">Par défaut, un bascule est placé à côté de chaque fournisseur de signature électronique (à droite).</span><span class="sxs-lookup"><span data-stu-id="a9be0-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="a9be0-216">Faites glisser le curseur vers la gauche pour désactiver un fournisseur de signature électronique spécifique.</span><span class="sxs-lookup"><span data-stu-id="a9be0-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="a9be0-217">Si un administrateur Teams désactive un fournisseur, les utilisateurs finaux ne le voient pas lors de la création d’une approbation.</span><span class="sxs-lookup"><span data-stu-id="a9be0-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="a9be0-218">Les utilisateurs finaux ne pourront pas non plus afficher les demandes de signature électronique qui ont été faites avec ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a9be0-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="a9be0-219">Les approbations de signature électronique créées à partir de l’application Approbations sont stockées dans le cloud du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a9be0-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="a9be0-220">Vous devrez donc vous rendre sur le site du fournisseur pour exporter des données relatives aux signatures électronique.</span><span class="sxs-lookup"><span data-stu-id="a9be0-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="a9be0-221">Consultez la documentation du fournisseur sur l’exportation et la rétention de ces contrats.</span><span class="sxs-lookup"><span data-stu-id="a9be0-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
