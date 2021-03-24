---
title: Disponibilité des applications Approbations dans Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
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
ms.openlocfilehash: 4235232a9d74b4583ecaed19b68ff87de982085c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103010"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="76ad2-103">Disponibilité de l’application Approbations Teams</span><span class="sxs-lookup"><span data-stu-id="76ad2-103">Teams Approvals app availability</span></span>

<span data-ttu-id="76ad2-104">L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76ad2-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="76ad2-105">L’application Approbations offre un moyen simple d’apporter des audits, de la conformité, de la responsabilité et des flux de travail à des approbations structurées et non structurées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="76ad2-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![affiche l’application Approbations](media/approvals-selection.png)

<span data-ttu-id="76ad2-107">Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="76ad2-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![affiche l’application Approbations avec l’option épingler](media/approvalApp-pin.png)

<span data-ttu-id="76ad2-109">La première approbation créée à partir de l’application Approbations déclenche la mise en service de la solution d’approbation dans l’environnement de service de données courant (CDS) par défaut.</span><span class="sxs-lookup"><span data-stu-id="76ad2-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="76ad2-110">Les approbations créées à partir de l’application Approbations seront stockées dans l’environnement CDS par défaut.</span><span class="sxs-lookup"><span data-stu-id="76ad2-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="76ad2-111">Cet article décrit la exigences et les rôles de l’application Approbations.</span><span class="sxs-lookup"><span data-stu-id="76ad2-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="76ad2-112">Autorisations et licences requises</span><span class="sxs-lookup"><span data-stu-id="76ad2-112">Required permissions and licenses</span></span>

<span data-ttu-id="76ad2-113">Pour utiliser l’application Approbations, vous devez avoir une autorisation pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="76ad2-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="76ad2-114">Autorisations pour créer une base de données CDS Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76ad2-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="76ad2-115">Un compte sur [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="76ad2-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="76ad2-116">Rôle d’administrateur dans l’environnement cible.</span><span class="sxs-lookup"><span data-stu-id="76ad2-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="76ad2-117">Licence pour une [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76ad2-117">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="76ad2-118">Stockage avec CDS</span><span class="sxs-lookup"><span data-stu-id="76ad2-118">Storage with CDS</span></span>

<span data-ttu-id="76ad2-119">Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications professionnelles et analytiques dans les CDS.</span><span class="sxs-lookup"><span data-stu-id="76ad2-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="76ad2-120">Il s'agit d'un ensemble de schémas de données standardisés et extensibles publiés par Microsoft et ses partenaires, qui permettent d'assurer la cohérence des données et de leur signification entre les applications et les processus métier.</span><span class="sxs-lookup"><span data-stu-id="76ad2-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="76ad2-121">En savoir plus sur [Modèle de données courant de Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="76ad2-121">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="76ad2-122">En savoir plus sur le [flux d’approbation](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="76ad2-122">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="76ad2-123">Autorisations de l’application Autorisations Teams</span><span class="sxs-lookup"><span data-stu-id="76ad2-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="76ad2-124">L’application Approbations Teams vous permet d’accéder aux fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="76ad2-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="76ad2-125">Recevoir les messages et les données que vous lui fournissez.</span><span class="sxs-lookup"><span data-stu-id="76ad2-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="76ad2-126">Vous envoyer des messages et des notifications.</span><span class="sxs-lookup"><span data-stu-id="76ad2-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="76ad2-127">Rendre les applications et les boîtes de dialogue personnelles sans en-tête fourni par Teams.</span><span class="sxs-lookup"><span data-stu-id="76ad2-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="76ad2-128">Accéder à vos informations de profil telles que votre nom, adresse e-mail, nom de votre entreprise et la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="76ad2-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="76ad2-129">Recevoir les messages et les données que les membres d’une équipe lui fournissent dans un canal.</span><span class="sxs-lookup"><span data-stu-id="76ad2-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="76ad2-130">Envoyer des messages et des notifications dans un canal.</span><span class="sxs-lookup"><span data-stu-id="76ad2-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="76ad2-131">Accédez aux informations de votre équipe :</span><span class="sxs-lookup"><span data-stu-id="76ad2-131">Access your team's information:</span></span>
  - <span data-ttu-id="76ad2-132">nom de l'équipe</span><span class="sxs-lookup"><span data-stu-id="76ad2-132">team name</span></span>
  - <span data-ttu-id="76ad2-133">liste des canaux</span><span class="sxs-lookup"><span data-stu-id="76ad2-133">channel list</span></span>
  - <span data-ttu-id="76ad2-134">liste de présence (noms et adresses de courrier des membres de l’équipe).</span><span class="sxs-lookup"><span data-stu-id="76ad2-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="76ad2-135">Utilisez les informations de l'équipe pour les contacter.</span><span class="sxs-lookup"><span data-stu-id="76ad2-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="76ad2-136">Gérer l'application Approbations</span><span class="sxs-lookup"><span data-stu-id="76ad2-136">Disable the Approvals app</span></span>

<span data-ttu-id="76ad2-137">L’application Approbations est disponible par défaut.</span><span class="sxs-lookup"><span data-stu-id="76ad2-137">The Approvals app is available by default.</span></span> <span data-ttu-id="76ad2-138">Vous pouvez désactiver l’application dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="76ad2-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="76ad2-139">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76ad2-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="76ad2-140">Développez **Applications Teams** et sélectionnez **Gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="76ad2-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="76ad2-141">Recherchez l’application Approbations.</span><span class="sxs-lookup"><span data-stu-id="76ad2-141">Search for the Approvals app.</span></span>

![affiche la navigation du Centre d’administration avec l’écran Applications Teams > Gérer les applications mis en évidence](media/manage-approval-apps.png)

  4. <span data-ttu-id="76ad2-143">Sélectionnez Approbations.</span><span class="sxs-lookup"><span data-stu-id="76ad2-143">Select Approvals.</span></span>

  5. <span data-ttu-id="76ad2-144">Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="76ad2-144">Select the toggle to disable the app for your organization.</span></span>

![affiche les détails de l’application Approbations](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="76ad2-146">Stratégie de rétention</span><span class="sxs-lookup"><span data-stu-id="76ad2-146">Retention policy</span></span>

<span data-ttu-id="76ad2-147">Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement CDS par défaut, qui ne prend pas en charge les sauvegardes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="76ad2-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="76ad2-148">En savoir plus sur la [Sauvegarde et restauration des environnements : Plateforme Power \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="76ad2-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="76ad2-149">Audit</span><span class="sxs-lookup"><span data-stu-id="76ad2-149">Auditing</span></span>

<span data-ttu-id="76ad2-150">L’application Approbations enregistre les événements d’audit dans le Centre de sécurité et conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76ad2-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="76ad2-151">Vous pouvez afficher le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="76ad2-151">You can view the audit log.</span></span>

1. <span data-ttu-id="76ad2-152">Accédez au site de conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76ad2-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="76ad2-153">Sélectionnez la section **Audit**.</span><span class="sxs-lookup"><span data-stu-id="76ad2-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="76ad2-154">Recherchez des activités sous **Activités d’approbation de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="76ad2-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="76ad2-155">Vous pouvez rechercher les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="76ad2-155">You can search for the following activities:</span></span>

- <span data-ttu-id="76ad2-156">Créer une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="76ad2-156">Create new approval request</span></span>

- <span data-ttu-id="76ad2-157">Afficher les détails de la demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="76ad2-157">View approval request details</span></span>

- <span data-ttu-id="76ad2-158">Demande d’approbation approuvée</span><span class="sxs-lookup"><span data-stu-id="76ad2-158">Approved approval request</span></span>

- <span data-ttu-id="76ad2-159">Demande d’approbation rejetée</span><span class="sxs-lookup"><span data-stu-id="76ad2-159">Rejected approval request</span></span>

- <span data-ttu-id="76ad2-160">Demande d’approbation annulée</span><span class="sxs-lookup"><span data-stu-id="76ad2-160">Canceled approval request</span></span>

- <span data-ttu-id="76ad2-161">Demande d’approbation partagée</span><span class="sxs-lookup"><span data-stu-id="76ad2-161">Shared approval request</span></span>

- <span data-ttu-id="76ad2-162">Fichier joint à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="76ad2-162">File attached to approval request</span></span>

- <span data-ttu-id="76ad2-163">Demande d'approbation réaffectée</span><span class="sxs-lookup"><span data-stu-id="76ad2-163">Reassigned approval request</span></span>

- <span data-ttu-id="76ad2-164">Ajout d’une signature électronique à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="76ad2-164">Added e-signature to approval request</span></span>

<span data-ttu-id="76ad2-165">Pour accéder à davantage d’approbations d’audit dans flux, activez et configurez l'audit dans l'environnement par défaut pour les entités d'approbation primaires Approbation, Demande d'approbation et Réponse d'approbation.</span><span class="sxs-lookup"><span data-stu-id="76ad2-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="76ad2-166">Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements d’approbation.</span><span class="sxs-lookup"><span data-stu-id="76ad2-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="76ad2-167">En savoir plus sur [Audit des données et de l’activité des utilisateurs pour des raisons de sécurité et de conformité : Plateforme Power \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="76ad2-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="76ad2-168">L’audit peut être personnalisé davantage dans le [Centre de conformité et sécurité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="76ad2-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="76ad2-169">Pour utiliser les rapports préconfigurés, connectez-vous à Conformité et sécurité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76ad2-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="76ad2-170">Sélectionnez **Recherche et enquête**.</span><span class="sxs-lookup"><span data-stu-id="76ad2-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="76ad2-171">Recherchez dans le journal d’audit et sélectionnez l’onglet **Activités Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="76ad2-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="76ad2-172">En savoir plus sur [Journalisation des activités de Microsoft Dataverse et des applications pilotées par les modèles :Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="76ad2-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="76ad2-173">Sécurité</span><span class="sxs-lookup"><span data-stu-id="76ad2-173">Security</span></span>

<span data-ttu-id="76ad2-174">À partir de l’application Approbations Teams, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations envoyées et reçues.</span><span class="sxs-lookup"><span data-stu-id="76ad2-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="76ad2-175">Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils répondent ou visualisent la demande.</span><span class="sxs-lookup"><span data-stu-id="76ad2-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="76ad2-176">Un utilisateur a le rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal sur lequel l’approbation a été créée.</span><span class="sxs-lookup"><span data-stu-id="76ad2-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="76ad2-177">Il ne peut pas agir sur la demande si ce rôle ne lui a pas été affecté lors de la création de l’approbation.</span><span class="sxs-lookup"><span data-stu-id="76ad2-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>