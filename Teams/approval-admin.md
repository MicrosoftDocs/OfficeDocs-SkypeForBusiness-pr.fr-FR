---
title: Homologations disponibilité des applications dans teams
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
description: En savoir plus sur la disponibilité des applications approbations dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675178"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="7cf48-103">Les équipes approuvent la disponibilité des applications</span><span class="sxs-lookup"><span data-stu-id="7cf48-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="7cf48-104">L’application approbations est disponible sous la forme d’une application personnelle pour tous les utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7cf48-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="7cf48-105">L’application approbations fournit un moyen simple de mettre en place un audit, une conformité, une responsabilité et des flux de travail pour les approbations structurées et non structurées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="7cf48-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![affiche l’application approbations](media/approvals-selection.png)

<span data-ttu-id="7cf48-107">Les utilisateurs peuvent épingler l’application approbations pour l’enregistrer dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="7cf48-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![affiche l’application approbations avec l’option code confidentiel](media/approvalApp-pin.png)

<span data-ttu-id="7cf48-109">La première approbation créée à partir de l’application approbations déclenche la mise en service de la solution d’approbation dans l’environnement de CD-services communs par défaut.</span><span class="sxs-lookup"><span data-stu-id="7cf48-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="7cf48-110">Les approbations créées à partir de l’application approbations seront stockées dans l’environnement des CD par défaut.</span><span class="sxs-lookup"><span data-stu-id="7cf48-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="7cf48-111">Cet article décrit les exigences et rôles de l’application approbations.</span><span class="sxs-lookup"><span data-stu-id="7cf48-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="7cf48-112">Autorisations et licences requises</span><span class="sxs-lookup"><span data-stu-id="7cf48-112">Required permissions and licenses</span></span>

<span data-ttu-id="7cf48-113">Pour utiliser l’application approbations, vous devez disposer des autorisations pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7cf48-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="7cf48-114">Autorisations de création d’une base de données Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="7cf48-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="7cf48-115">Un compte sur [Flow.Microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7cf48-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="7cf48-116">Rôle d’administrateur dans l’environnement cible.</span><span class="sxs-lookup"><span data-stu-id="7cf48-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="7cf48-117">Licence pour une [automate](https://docs.microsoft.com/power-automate/get-started-approvals), une 365 ou une dynamique 365.</span><span class="sxs-lookup"><span data-stu-id="7cf48-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="7cf48-118">Stockage avec CD</span><span class="sxs-lookup"><span data-stu-id="7cf48-118">Storage with CDS</span></span>

<span data-ttu-id="7cf48-119">Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications métier et d’analyse des CD.</span><span class="sxs-lookup"><span data-stu-id="7cf48-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="7cf48-120">Il s’agit d’un ensemble de schémas de données standardisés et automatisés publiés par Microsoft et par nos partenaires, qui permettent de faire une cohérence entre les données et leur signification sur les applications et les processus métiers.</span><span class="sxs-lookup"><span data-stu-id="7cf48-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="7cf48-121">En savoir plus sur le [modèle de données commun de Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="7cf48-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="7cf48-122">En savoir plus sur le [flux de travail approbation](https://docs.microsoft.com/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="7cf48-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="7cf48-123">Autorisations de l’application équipes d’approbations</span><span class="sxs-lookup"><span data-stu-id="7cf48-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="7cf48-124">L’application équipes d’approbation vous permet d’accéder aux fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="7cf48-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="7cf48-125">Recevoir des messages et des données que vous leur fournissez ;</span><span class="sxs-lookup"><span data-stu-id="7cf48-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="7cf48-126">Vous envoyer des messages et des notifications.</span><span class="sxs-lookup"><span data-stu-id="7cf48-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="7cf48-127">Afficher des applications personnelles et des boîtes de dialogue sans en-tête fourni par Teams.</span><span class="sxs-lookup"><span data-stu-id="7cf48-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="7cf48-128">Accédez à vos informations de profil, telles que votre nom, votre adresse de messagerie, le nom de votre société et la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="7cf48-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="7cf48-129">Recevez des messages et des données que les membres de l’équipe y fournissent dans un canal.</span><span class="sxs-lookup"><span data-stu-id="7cf48-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="7cf48-130">Envoyer des messages et des notifications dans un canal.</span><span class="sxs-lookup"><span data-stu-id="7cf48-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="7cf48-131">Accédez aux informations de votre équipe :</span><span class="sxs-lookup"><span data-stu-id="7cf48-131">Access your team's information:</span></span>
  - <span data-ttu-id="7cf48-132">nom de l’équipe</span><span class="sxs-lookup"><span data-stu-id="7cf48-132">team name</span></span>
  - <span data-ttu-id="7cf48-133">liste de canaux</span><span class="sxs-lookup"><span data-stu-id="7cf48-133">channel list</span></span>
  - <span data-ttu-id="7cf48-134">liste (noms des membres de l’équipe et adresses de courrier).</span><span class="sxs-lookup"><span data-stu-id="7cf48-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="7cf48-135">Utilisez les informations de l’équipe pour les contacter.</span><span class="sxs-lookup"><span data-stu-id="7cf48-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="7cf48-136">Désactiver l’application approbations</span><span class="sxs-lookup"><span data-stu-id="7cf48-136">Disable the Approvals app</span></span>

<span data-ttu-id="7cf48-137">L’application approbations est disponible par défaut.</span><span class="sxs-lookup"><span data-stu-id="7cf48-137">The Approvals app is available by default.</span></span> <span data-ttu-id="7cf48-138">Vous pouvez désactiver l’application dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="7cf48-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="7cf48-139">Connectez-vous au centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="7cf48-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="7cf48-140">Développez **applications teams** , puis sélectionnez **gérer les applications**.</span><span class="sxs-lookup"><span data-stu-id="7cf48-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="7cf48-141">Recherchez l’application approbations.</span><span class="sxs-lookup"><span data-stu-id="7cf48-141">Search for the Approvals app.</span></span>

![affiche la navigation dans le centre d’administration avec les applications teams > gérer les applications en surbrillance](media/manage-approval-apps.png)

  4. <span data-ttu-id="7cf48-143">Sélectionnez approbations.</span><span class="sxs-lookup"><span data-stu-id="7cf48-143">Select Approvals.</span></span>

  5. <span data-ttu-id="7cf48-144">Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7cf48-144">Select the toggle to disable the app for your organization.</span></span>

![affiche les détails de l’application approbations](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="7cf48-146">Stratégie de rétention</span><span class="sxs-lookup"><span data-stu-id="7cf48-146">Retention policy</span></span>

<span data-ttu-id="7cf48-147">Les approbations créées à partir de l’application approbations sont stockées dans l’environnement des CD par défaut, qui ne prend pas en charge les sauvegardes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="7cf48-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="7cf48-148">Apprenez-en davantage sur la manière de [sauvegarder et de restaurer des environnements : \| documents Microsoft](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="7cf48-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="7cf48-149">Audit</span><span class="sxs-lookup"><span data-stu-id="7cf48-149">Auditing</span></span>

<span data-ttu-id="7cf48-150">L’application approbations enregistre les événements d’audit dans le centre de sécurité et conformité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cf48-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="7cf48-151">Vous pouvez afficher le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="7cf48-151">You can view the audit log.</span></span>

1. <span data-ttu-id="7cf48-152">Accédez au site de conformité M365.</span><span class="sxs-lookup"><span data-stu-id="7cf48-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="7cf48-153">Sélectionnez la section **audit** .</span><span class="sxs-lookup"><span data-stu-id="7cf48-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="7cf48-154">Recherchez des activités dans les **activités d’approbations de Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="7cf48-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="7cf48-155">Vous pouvez rechercher les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="7cf48-155">You can search for the following activities:</span></span>

- <span data-ttu-id="7cf48-156">Créer une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="7cf48-156">Create new approval request</span></span>

- <span data-ttu-id="7cf48-157">Afficher les détails de la demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="7cf48-157">View approval request details</span></span>

- <span data-ttu-id="7cf48-158">Demande d’approbation approuvée</span><span class="sxs-lookup"><span data-stu-id="7cf48-158">Approved approval request</span></span>

- <span data-ttu-id="7cf48-159">Demande d’approbation rejetée</span><span class="sxs-lookup"><span data-stu-id="7cf48-159">Rejected approval request</span></span>

- <span data-ttu-id="7cf48-160">Demande d’approbation annulée</span><span class="sxs-lookup"><span data-stu-id="7cf48-160">Canceled approval request</span></span>

- <span data-ttu-id="7cf48-161">Demande d’approbation partagée</span><span class="sxs-lookup"><span data-stu-id="7cf48-161">Shared approval request</span></span>

- <span data-ttu-id="7cf48-162">Fichier joint à une demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="7cf48-162">File attached to approval request</span></span>

- <span data-ttu-id="7cf48-163">Demande d’approbation réaffectée</span><span class="sxs-lookup"><span data-stu-id="7cf48-163">Reassigned approval request</span></span>

- <span data-ttu-id="7cf48-164">A ajouté une signature électronique à la demande d’approbation</span><span class="sxs-lookup"><span data-stu-id="7cf48-164">Added e-signature to approval request</span></span>

<span data-ttu-id="7cf48-165">Pour accéder à d’autres approbations d’audit au sein d’un flux, activez et configurez l’audit dans l’environnement par défaut pour l’approbation des entités d’approbation principales, la demande d’approbation et la réponse d’approbation.</span><span class="sxs-lookup"><span data-stu-id="7cf48-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="7cf48-166">Les opérations de création, de mise à jour et de suppression sont des événements pouvant être audité pour les enregistrements approbation.</span><span class="sxs-lookup"><span data-stu-id="7cf48-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="7cf48-167">En savoir plus sur [les données d’audit et l’activité des utilisateurs pour la sécurité et la conformité- \| documentation Microsoft sur la plateforme](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="7cf48-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="7cf48-168">Les contrôles peuvent être personnalisés davantage dans le [Centre de sécurité et conformité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="7cf48-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="7cf48-169">Pour utiliser les rapports préconfigurés, connectez-vous à Office 365 Security and Compliance.</span><span class="sxs-lookup"><span data-stu-id="7cf48-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="7cf48-170">Sélectionnez **rechercher & examen**.</span><span class="sxs-lookup"><span data-stu-id="7cf48-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="7cf48-171">Recherchez dans le journal d’audit et sélectionnez l’onglet **activités de Dynamics 365** .</span><span class="sxs-lookup"><span data-stu-id="7cf48-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="7cf48-172">En savoir plus sur la journalisation de l’activité des applications basées sur Microsoft Dataverse et celles basées sur le [modèle-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="7cf48-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="7cf48-173">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7cf48-173">Security</span></span>

<span data-ttu-id="7cf48-174">À partir de l’application approbation des équipes, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations qu’ils ont envoyées et reçues.</span><span class="sxs-lookup"><span data-stu-id="7cf48-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="7cf48-175">Les utilisateurs ne peuvent pas accéder aux approbations créées par d’autres personnes, sauf s’il s’agit d’un répondeur ou d’une visionneuse de la requête.</span><span class="sxs-lookup"><span data-stu-id="7cf48-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="7cf48-176">Un utilisateur aura le rôle de visionneuse d’une demande s’il fait partie d’une conversation ou d’un canal de création de l’approbation.</span><span class="sxs-lookup"><span data-stu-id="7cf48-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="7cf48-177">Ils ne seront pas en mesure d’effectuer une action sur la demande s’ils n’ont pas donné ce rôle lors de la création de l’approbation.</span><span class="sxs-lookup"><span data-stu-id="7cf48-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
