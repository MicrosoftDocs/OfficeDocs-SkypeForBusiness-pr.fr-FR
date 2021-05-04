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
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129793"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="d9c3a-103">Disponibilité de l’application Approbations Teams</span><span class="sxs-lookup"><span data-stu-id="d9c3a-103">Teams Approvals app availability</span></span>

<span data-ttu-id="d9c3a-104">L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="d9c3a-105">L’application Approbations offre un moyen simple d’apporter des audits, de la conformité, de la responsabilité et des flux de travail à des approbations structurées et non structurées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![affiche l’application Approbations](media/approvals-selection.png)

<span data-ttu-id="d9c3a-107">Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![affiche l’application Approbations avec l’option épingler](media/approvalApp-pin.png)

<span data-ttu-id="d9c3a-109">La première approbation créée à partir de l’application Approbations déclenche la mise en service de la solution d’approbation dans l’environnement de service de données courant (CDS) par défaut.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="d9c3a-110">Les approbations créées à partir de l’application Approbations seront stockées dans l’environnement CDS par défaut.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="d9c3a-111">Cet article décrit la exigences et les rôles de l’application Approbations.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="d9c3a-112">Cette fonctionnalité n'a pas encore été publiée pour les utilisateurs des services Cloud de la communauté du secteur public (Cloud de la communauté du secteur public), Cloud de la communauté du secteur public High (GCCH) et Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="d9c3a-113">Autorisations et licences requises</span><span class="sxs-lookup"><span data-stu-id="d9c3a-113">Required permissions and licenses</span></span>

<span data-ttu-id="d9c3a-114">Pour utiliser l’application Approbations, vous devez avoir une autorisation pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d9c3a-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="d9c3a-115">Autorisations pour créer une base de données CDS Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="d9c3a-116">Un compte sur [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="d9c3a-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="d9c3a-117">Rôle d’administrateur dans l’environnement cible.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="d9c3a-118">Licence pour une [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="d9c3a-119">Stockage avec CDS</span><span class="sxs-lookup"><span data-stu-id="d9c3a-119">Storage with CDS</span></span>

<span data-ttu-id="d9c3a-120">Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications professionnelles et analytiques dans les CDS.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="d9c3a-121">Il s'agit d'un ensemble de schémas de données standardisés et extensibles publiés par Microsoft et ses partenaires, qui permettent d'assurer la cohérence des données et de leur signification entre les applications et les processus métier.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="d9c3a-122">En savoir plus sur [Modèle de données courant de Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="d9c3a-123">En savoir plus sur le [flux d’approbation](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="d9c3a-124">Autorisations de l’application Autorisations Teams</span><span class="sxs-lookup"><span data-stu-id="d9c3a-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="d9c3a-125">L’application Approbations Teams vous permet d’accéder aux fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9c3a-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="d9c3a-126">Recevoir les messages et les données que vous lui fournissez.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="d9c3a-127">Vous envoyer des messages et des notifications.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="d9c3a-128">Rendre les applications et les boîtes de dialogue personnelles sans en-tête fourni par Teams.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="d9c3a-129">Accéder à vos informations de profil telles que votre nom, adresse e-mail, nom de votre entreprise et la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="d9c3a-130">Recevoir les messages et les données que les membres d’une équipe lui fournissent dans un canal.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="d9c3a-131">Envoyer des messages et des notifications dans un canal.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="d9c3a-132">Accédez aux informations de votre équipe :</span><span class="sxs-lookup"><span data-stu-id="d9c3a-132">Access your team's information:</span></span>
  - <span data-ttu-id="d9c3a-133">nom de l'équipe</span><span class="sxs-lookup"><span data-stu-id="d9c3a-133">team name</span></span>
  - <span data-ttu-id="d9c3a-134">liste des canaux</span><span class="sxs-lookup"><span data-stu-id="d9c3a-134">channel list</span></span>
  - <span data-ttu-id="d9c3a-135">liste de présence (noms et adresses de courrier des membres de l’équipe).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="d9c3a-136">Utilisez les informations de l'équipe pour les contacter.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="d9c3a-137">Gérer l'application Approbations</span><span class="sxs-lookup"><span data-stu-id="d9c3a-137">Disable the Approvals app</span></span>

<span data-ttu-id="d9c3a-138">L’application Approbations est disponible par défaut.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-138">The Approvals app is available by default.</span></span> <span data-ttu-id="d9c3a-139">Vous pouvez désactiver l’application dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="d9c3a-140">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="d9c3a-141">Développez **Applications Teams** et sélectionnez **Gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="d9c3a-142">Recherchez l’application Approbations.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-142">Search for the Approvals app.</span></span>

     ![affiche la navigation du Centre d’administration avec l’écran Applications Teams > Gérer les applications mis en évidence](media/manage-approval-apps.png)

  4. <span data-ttu-id="d9c3a-144">Sélectionnez Approbations.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-144">Select Approvals.</span></span>

  5. <span data-ttu-id="d9c3a-145">Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-145">Select the toggle to disable the app for your organization.</span></span>

     ![affiche les détails de l’application Approbations](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="d9c3a-147">Stratégie de rétention</span><span class="sxs-lookup"><span data-stu-id="d9c3a-147">Retention policy</span></span>

<span data-ttu-id="d9c3a-148">Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement CDS par défaut, qui ne prend pas en charge les sauvegardes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="d9c3a-149">En savoir plus sur la [Sauvegarde et restauration des environnements : Plateforme Power \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="d9c3a-150">Audit</span><span class="sxs-lookup"><span data-stu-id="d9c3a-150">Auditing</span></span>

<span data-ttu-id="d9c3a-151">L’application Approbations enregistre les événements d’audit dans le Centre de sécurité et conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="d9c3a-152">Vous pouvez afficher le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-152">You can view the audit log.</span></span>

1. <span data-ttu-id="d9c3a-153">Accédez au site de conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="d9c3a-154">Sélectionnez la section **Audit**.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="d9c3a-155">Recherchez des activités sous **Activités d’approbation de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="d9c3a-156">Vous pouvez rechercher les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9c3a-156">You can search for the following activities:</span></span>

- <span data-ttu-id="d9c3a-157">Créer une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="d9c3a-157">Create new approval request</span></span>

- <span data-ttu-id="d9c3a-158">Afficher les détails de la demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="d9c3a-158">View approval request details</span></span>

- <span data-ttu-id="d9c3a-159">Demande d’approbation approuvée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-159">Approved approval request</span></span>

- <span data-ttu-id="d9c3a-160">Demande d’approbation rejetée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-160">Rejected approval request</span></span>

- <span data-ttu-id="d9c3a-161">Demande d’approbation annulée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-161">Canceled approval request</span></span>

- <span data-ttu-id="d9c3a-162">Demande d’approbation partagée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-162">Shared approval request</span></span>

- <span data-ttu-id="d9c3a-163">Fichier joint à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="d9c3a-163">File attached to approval request</span></span>

- <span data-ttu-id="d9c3a-164">Demande d'approbation réaffectée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-164">Reassigned approval request</span></span>

- <span data-ttu-id="d9c3a-165">Ajout d’une signature électronique à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="d9c3a-165">Added e-signature to approval request</span></span>

- <span data-ttu-id="d9c3a-166">Affichage des détails de la demande de signature électronique</span><span class="sxs-lookup"><span data-stu-id="d9c3a-166">Viewed e-signature request details</span></span>

- <span data-ttu-id="d9c3a-167">Demande de signature électronique examinée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-167">Reviewed e-signature request</span></span>

- <span data-ttu-id="d9c3a-168">Demande de signature électronique annulée</span><span class="sxs-lookup"><span data-stu-id="d9c3a-168">Canceled e-signature request</span></span>

<span data-ttu-id="d9c3a-169">Pour accéder à davantage d’approbations d’audit dans flux, activez et configurez l'audit dans l'environnement par défaut pour les entités d'approbation primaires Approbation, Demande d'approbation et Réponse d'approbation.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-169">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="d9c3a-170">Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements d’approbation.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-170">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="d9c3a-171">En savoir plus sur [Audit des données et de l’activité des utilisateurs pour des raisons de sécurité et de conformité : Plateforme Power \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-171">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="d9c3a-172">L’audit peut être personnalisé davantage dans le [Centre de conformité et sécurité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-172">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="d9c3a-173">Pour utiliser les rapports préconfigurés, connectez-vous à Conformité et sécurité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-173">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="d9c3a-174">Sélectionnez **Recherche et enquête**.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-174">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="d9c3a-175">Recherchez dans le journal d’audit et sélectionnez l’onglet **Activités Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-175">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="d9c3a-176">En savoir plus sur [Journalisation des activités de Microsoft Dataverse et des applications pilotées par les modèles :Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-176">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="d9c3a-177">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d9c3a-177">Security</span></span>

<span data-ttu-id="d9c3a-178">À partir de l’application Approbations Teams, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations envoyées et reçues.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-178">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="d9c3a-179">Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils répondent ou visualisent la demande.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-179">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="d9c3a-180">Un utilisateur a le rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal sur lequel l’approbation a été créée.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-180">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="d9c3a-181">Il ne peut pas agir sur la demande si ce rôle ne lui a pas été affecté lors de la création de l’approbation.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-181">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="d9c3a-182">Intégration de la signature électronique Approbations</span><span class="sxs-lookup"><span data-stu-id="d9c3a-182">Approvals e-signature integration</span></span>

<span data-ttu-id="d9c3a-183">Les approbations de signature électronique créées à partir de l'application Approbations sont stockées dans l'environnement cloud du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-183">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="d9c3a-184">Pour plus d'informations sur le stockage autour du contrat de signature électronique, consultez la documentation de stockage du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-184">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="d9c3a-185">Pour utiliser la fonctionnalité de signature électronique de l'application Approbations, vous devez avoir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d9c3a-185">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="d9c3a-186">Licence du fournisseur de signature électronique que vous choisissez d'utiliser.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-186">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="d9c3a-187">Pour obtenir une licence pour votre organisation, vous devez vous rendre sur le site du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-187">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="d9c3a-188">Pour la fonctionnalité de signature électronique Approbations, les partenaires de signature tiers apparaissent par défaut dans l'Teams Approbations.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-188">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="d9c3a-189">Vous pouvez désactiver des fournisseurs de signature électronique spécifiques en accédant aux paramètres de l'application dans Teams d'administration.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-189">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="d9c3a-190">Dans le Teams d'administration, sous **Gérer** les applications, sélectionnez l'application **Approbations,** puis **Paramètres.**</span><span class="sxs-lookup"><span data-stu-id="d9c3a-190">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="d9c3a-191">Par défaut, un bascule est placé à côté de chaque fournisseur de signature électronique (à droite).</span><span class="sxs-lookup"><span data-stu-id="d9c3a-191">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="d9c3a-192">Faites glisser le curseur vers la gauche pour désactiver un fournisseur de signature électronique spécifique.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-192">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="d9c3a-193">Si un administrateur Teams désactive un fournisseur, les utilisateurs finaux ne le voient pas lors de la création d'une approbation.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-193">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="d9c3a-194">Les utilisateurs finaux ne pourront pas non plus afficher les demandes de signature électronique qui ont été faites avec ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-194">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="d9c3a-195">Les approbations de signature électronique créées à partir de l'application Approbations sont stockées dans le cloud du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-195">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="d9c3a-196">Vous devrez donc vous rendre sur le site du fournisseur pour exporter des données relatives aux signatures électronique.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-196">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="d9c3a-197">Consultez la documentation du fournisseur sur l'exportation et la rétention de ces contrats.</span><span class="sxs-lookup"><span data-stu-id="d9c3a-197">Refer to the provider's documentation about export and retention of these agreements.</span></span>
