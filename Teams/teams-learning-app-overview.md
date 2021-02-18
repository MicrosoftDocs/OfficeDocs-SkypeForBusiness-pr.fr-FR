---
title: Installer, gérer et attribuer des autorisations pour l’application Teams Learning (prévisualisation privée)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Utilisez l’application Microsoft Teams Learning pour créer un hub central d’apprentissage où les employés peuvent partager, attribuer et apprendre des bibliothèques de contenu au sein d’une organisation.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285618"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="6091d-103">Installer, gérer et attribuer des autorisations pour l’application Teams Learning (prévisualisation privée)</span><span class="sxs-lookup"><span data-stu-id="6091d-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="6091d-104">*Cet article contient du contenu préliminaire pour l’application Teams Learning, qui est en version d’évaluation privée.*</span><span class="sxs-lookup"><span data-stu-id="6091d-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="6091d-105">L’application Microsoft Teams Learning (pré-version préliminaire privée) permet aux équipes et aux membres de votre organisation de faire de l’apprentissage une partie naturelle de leur journée.</span><span class="sxs-lookup"><span data-stu-id="6091d-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="6091d-106">L’application crée un hub central dans Teams dans lequel les employés peuvent partager, attribuer et apprendre des bibliothèques de contenu au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6091d-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="6091d-107">Les administrateurs définissent des autorisations et autorisent les sources de contenu d’apprentissage pour l’application.</span><span class="sxs-lookup"><span data-stu-id="6091d-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="6091d-108">Le contenu d’apprentissage peut inclure LinkedIn Learning, Microsoft Learn, une formation Microsoft 365, le contenu de votre organisation stocké dans SharePoint Online et des fournisseurs tiers pris en charge par l’application.</span><span class="sxs-lookup"><span data-stu-id="6091d-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="6091d-109">Pour configurer l’application Teams Learning (prévisualisation privée), vous devez impliquer :</span><span class="sxs-lookup"><span data-stu-id="6091d-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="6091d-110">Administrateur du Centre d’administration Teams</span><span class="sxs-lookup"><span data-stu-id="6091d-110">Teams admin center admin</span></span>
-   <span data-ttu-id="6091d-111">Administrateur du Centre d’administration Microsoft 365 (autrement dit, administrateur global)</span><span class="sxs-lookup"><span data-stu-id="6091d-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="6091d-112">Gérer l’application Teams Learning (prévisualisation privée) dans le Centre d’administration Teams</span><span class="sxs-lookup"><span data-stu-id="6091d-112">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="6091d-113">L’administrateur Teams installe l’application Teams Learning (prévisualisation privée) à partir du magasin d’applications et applique les stratégies de configuration, de gestion et d’autorisations de l’application via le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="6091d-113">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="6091d-114">Gérer l’application Teams Learning (prévisualisation privée)</span><span class="sxs-lookup"><span data-stu-id="6091d-114">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="6091d-115">Pour gérer les paramètres de l’application, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="6091d-115">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="6091d-116">Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **l’application Teams** Gérer  >  **les applications.**</span><span class="sxs-lookup"><span data-stu-id="6091d-116">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navigation gauche dans le Centre d’administration Teams affichant les applications Teams et la section Gérer les applications](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="6091d-118">Dans la page **Gérer les applications,** dans la zone de recherche, tapez *Apprentissage* pour rechercher l’application Teams Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="6091d-118">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Page Gérer les applications dans le Centre d’administration Teams affichant la zone de recherche](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="6091d-120">Sur la page **Apprentissage** :</span><span class="sxs-lookup"><span data-stu-id="6091d-120">On the **Learning** page:</span></span>
   1. <span data-ttu-id="6091d-121">Sous **État,** **sélectionnez Autorisé** pour activer l’application.</span><span class="sxs-lookup"><span data-stu-id="6091d-121">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="6091d-122">Sous **l’onglet Paramètres,** dans la section **Paramètres** des applications, allez au Centre d’administration Microsoft 365 pour configurer les sources de contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6091d-122">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Page d’apprentissage dans le Centre d’administration Teams affichant la section Paramètres de statut et d’application](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="6091d-124">Après  avoir gérer les paramètres de l’application, accédez aux autorisations et aux stratégies de configuration pour accorder des **autorisations** aux employés qui doivent avoir accès à l’application dans le cadre de la participation de votre organisation à la prévisualisation privée.</span><span class="sxs-lookup"><span data-stu-id="6091d-124">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="6091d-125">Si votre organisation fait partie de l’anneau 4.0 dans le cadre du programme Teams TAP100, vous devrez peut-être faire ce qui suit pour permettre aux utilisateurs approuvés de l’anneau 3.0 d’accéder à l’application Teams Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="6091d-125">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="6091d-126">Dans le cadre de la prévisualisation privée, l’application Teams Learning (prévisualisation privée) est publiée dans l’anneau 3.0.</span><span class="sxs-lookup"><span data-stu-id="6091d-126">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="6091d-127">Si votre organisation est sous l’anneau 4.0, l’application n’est pas dans l’App Store.</span><span class="sxs-lookup"><span data-stu-id="6091d-127">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="6091d-128">Pour tester l’application, vous devez créer une stratégie d’autorisation d’applications personnalisée, la définir sur Autoriser toutes les applications et l’affecter aux utilisateurs approuvés Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="6091d-128">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Page TAP-AppsPermission-Plcy affichant l’affichage Autoriser toutes les applications sélectionné](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6091d-130">Configurer des sources de contenu d’apprentissage dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6091d-130">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6091d-131">Les administrateurs du Centre d’administration Microsoft 365 peuvent gérer les paramètres liés à l’application Teams Learning (prévisualisation privée) et configurer les sources de contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6091d-131">The admins for the Microsoft 365 admin center can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="6091d-132">L’administrateur peut sélectionner les sources de contenu d’apprentissage supplémentaires (par exemple, SharePoint ou les sources de fournisseurs de contenu tiers pris en charge) qui seront disponibles pour les utilisateurs de l’application.</span><span class="sxs-lookup"><span data-stu-id="6091d-132">The admin can select which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of the app.</span></span> <span data-ttu-id="6091d-133">L’administrateur configure ensuite ces sources pour s’assurer que le contenu est disponible pour la recherche et la découverte et peut être consulté par les employés qui utilisent l’application.</span><span class="sxs-lookup"><span data-stu-id="6091d-133">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

> [!NOTE]
>  <span data-ttu-id="6091d-134">Les utilisateurs se connectent aux apprentissages non-Microsoft et LinkedIn Learning Pro dans un navigateur ou une visionneuse incorporée.</span><span class="sxs-lookup"><span data-stu-id="6091d-134">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="6091d-135">Cet apprentissage configuré est soumis aux conditions distinctes de licence, de confidentialité et de service entre votre organisation et le tiers, et non aux conditions d’apprentissage (prévisualisation).</span><span class="sxs-lookup"><span data-stu-id="6091d-135">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Learning (Preview) terms.</span></span> <span data-ttu-id="6091d-136">Avant de sélectionner cet apprentissage dans Learning (Preview), vérifiez que vous avez un contrat en place pour votre organisation et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6091d-136">Before selecting this learning in Learning (Preview), verify you have an agreement in place for your organization and users.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="6091d-137">Configurer les paramètres des sources de contenu d’apprentissage pour l’application</span><span class="sxs-lookup"><span data-stu-id="6091d-137">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="6091d-138">Ces étapes doivent être effectuées par l’administrateur Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6091d-138">These steps are to be performed by the Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="6091d-139">Dans le panneau de navigation gauche du Centre d’administration Microsoft 365, allez dans  >  **Paramètres de l’organisation.**</span><span class="sxs-lookup"><span data-stu-id="6091d-139">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="6091d-140">Dans la page **Paramètres,** dans l’onglet & des **modules,** sélectionnez **Application d’apprentissage.**</span><span class="sxs-lookup"><span data-stu-id="6091d-140">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Page Paramètres du Centre d’administration Microsoft 365 affichant l’application Learning répertoriée](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="6091d-142">Dans le **panneau Application d’apprentissage,** sélectionnez les sources de contenu d’apprentissage que vous voulez configurer pour l’organisation, puis **sélectionnez Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="6091d-142">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Panneau des applications d’apprentissage dans le Centre d’administration Microsoft 365 affichant les options de sources de contenu](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="6091d-144">Parmi toutes les sources d’apprentissage existantes, certaines seront activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="6091d-144">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="6091d-145">Elles incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6091d-145">These include:</span></span>

- <span data-ttu-id="6091d-146">LinkedIn Learning (contenu gratuit)</span><span class="sxs-lookup"><span data-stu-id="6091d-146">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="6091d-147">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="6091d-147">Microsoft Learn</span></span>
- <span data-ttu-id="6091d-148">Formation Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6091d-148">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="6091d-149">Si votre organisation a un abonnement LinkedIn Learning Standard ou Professionnel, le référentiel de contenu sera déverrouillé pour les employés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6091d-149">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="6091d-150">Seuls les employés autorisés pourront utiliser l’ensemble du référentiel de contenu.</span><span class="sxs-lookup"><span data-stu-id="6091d-150">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="6091d-151">D’autres sources doivent peut-être être activées ou configurées manuellement.</span><span class="sxs-lookup"><span data-stu-id="6091d-151">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="6091d-152">Les sources d’apprentissage qui ne sont pas de Microsoft sont sous licence distinctes entre votre organisation et le tiers.</span><span class="sxs-lookup"><span data-stu-id="6091d-152">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="6091d-153">Vous devrez vérifier que vous êtes inscrit à l’apprentissage pour vous et vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6091d-153">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="6091d-154">Pour activer ou désactiver une source de contenu d’apprentissage, activez la case à cocher en regard de la source.</span><span class="sxs-lookup"><span data-stu-id="6091d-154">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="6091d-155">Si une source est activée, une coche est visible.</span><span class="sxs-lookup"><span data-stu-id="6091d-155">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a><span data-ttu-id="6091d-156">Configurer SharePoint comme source de contenu d’apprentissage (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="6091d-156">Configure SharePoint as a learning content source (Coming Soon)</span></span>

<span data-ttu-id="6091d-157">Vous configurez SharePoint comme source de contenu d’apprentissage pour l’application Teams Learning (prévisualisation privée) dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6091d-157">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="6091d-158">Présentation</span><span class="sxs-lookup"><span data-stu-id="6091d-158">Overview</span></span>

<span data-ttu-id="6091d-159">L’administrateur fournit une URL de site dans laquelle le service d’apprentissage peut créer un référentiel de contenu d’apprentissage centralisé vide sous la forme d’une liste SharePoint structurée.</span><span class="sxs-lookup"><span data-stu-id="6091d-159">The admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="6091d-160">Cette liste peut être utilisée par l’organisation pour contenir des liens vers des dossiers SharePoint entre entreprises contenant du contenu pédagogique.</span><span class="sxs-lookup"><span data-stu-id="6091d-160">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="6091d-161">Les administrateurs sont responsables de la collecte et de l’organisation d’une liste d’URL pour les dossiers.</span><span class="sxs-lookup"><span data-stu-id="6091d-161">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="6091d-162">Ces dossiers doivent inclure uniquement le contenu qui peut être mis à disposition dans l’application Teams Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="6091d-162">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="6091d-163">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6091d-163">Permissions</span></span>

<span data-ttu-id="6091d-164">Les URL des dossiers peuvent être collectées à partir de n’importe quel site SharePoint de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6091d-164">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="6091d-165">Tout contenu de ces dossiers pourra faire l’effet d’une recherche, mais seul le contenu auquel l’employé dispose des autorisations individuelles peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="6091d-165">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="6091d-166">Service d’apprentissage</span><span class="sxs-lookup"><span data-stu-id="6091d-166">Learning Service</span></span>

<span data-ttu-id="6091d-167">Le service d’apprentissage utilise les URL des dossiers fournis pour obtenir les métadonnées de tout le contenu stocké dans ces dossiers.</span><span class="sxs-lookup"><span data-stu-id="6091d-167">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="6091d-168">Après 24 heures de fourniture de l’URL du dossier dans le référentiel centralisé, les employés peuvent rechercher et utiliser le contenu de l’entreprise au sein de l’application.</span><span class="sxs-lookup"><span data-stu-id="6091d-168">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="6091d-169">À ce stade, la suppression du contenu du référentiel n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="6091d-169">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="6091d-170">Le contenu accidentellement surface ne peut être supprimé qu’en fournissant une nouvelle URL de site SharePoint dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6091d-170">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="6091d-171">Configurer SharePoint en tant que source</span><span class="sxs-lookup"><span data-stu-id="6091d-171">Configure SharePoint as a source</span></span>

<span data-ttu-id="6091d-172">Ces étapes doivent être effectuées par l’administrateur Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6091d-172">These steps are to be performed by Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="6091d-173">Dans le panneau de navigation gauche du Centre d’administration Microsoft 365, allez dans **Paramètres.**</span><span class="sxs-lookup"><span data-stu-id="6091d-173">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="6091d-174">Dans la page **Paramètres,** dans l’onglet & des **modules,** sélectionnez **Application d’apprentissage.**</span><span class="sxs-lookup"><span data-stu-id="6091d-174">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Page Paramètres du Centre d’administration Microsoft 365 affichant l’application Learning répertoriée](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="6091d-176">Dans le **panneau Application d’apprentissage,** fournissez l’URL du site au site SharePoint où vous souhaitez que l’application crée un référentiel centralisé.</span><span class="sxs-lookup"><span data-stu-id="6091d-176">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Panneau de l’application d’apprentissage dans le Centre d’administration Microsoft 365 avec SharePoint sélectionné](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="6091d-178">Une liste SharePoint est créée automatiquement dans le site SharePoint de l’organisation fournie.</span><span class="sxs-lookup"><span data-stu-id="6091d-178">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="6091d-179">Dans le navigation gauche du site SharePoint, sélectionnez Référentiel de **contenu d’application d’apprentissage.**</span><span class="sxs-lookup"><span data-stu-id="6091d-179">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navigation gauche dans SharePoint affichant la section Référentiel de contenu d’application d’apprentissage](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="6091d-181">Dans la page **Référentiel** de contenu d’application d’apprentissage, insérez la liste SharePoint avec des URL dans les dossiers de contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6091d-181">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="6091d-182">Sélectionnez Nouveau pour afficher **le panneau Nouvel** élément. </span><span class="sxs-lookup"><span data-stu-id="6091d-182">Select **New** to view the **New item** panel.</span></span> 

   ![Page référentiel de contenu d’application d’apprentissage dans SharePoint affichant l’option Nouvelle](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="6091d-184">Dans le **panneau Nouvel élément,** dans le champ **Titre,** ajoutez le nom d’annuaire de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6091d-184">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="6091d-185">Dans le champ **URL du** dossier, ajoutez l’URL au dossier de contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6091d-185">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="6091d-186">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6091d-186">Select **Save**.</span></span>

   ![Panneau Nouvel élément dans SharePoint affichant les champs URL de titre et de dossier](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="6091d-188">La page référentiel de contenu des applications d’apprentissage est mise à jour avec le nouveau contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="6091d-188">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Page référentiel de contenu d’application d’apprentissage dans SharePoint affichant les informations mises à jour](media/learning-app-content-repository-populated.png)


 


