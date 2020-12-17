---
title: Installer, gérer et affecter des autorisations pour l’application formations Teams (préversion privée)
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
description: Utilisez l’application formations de Microsoft teams pour créer un hub central permettant de partager, d’affecter et d’apprendre des bibliothèques de contenu au sein d’une organisation.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703425"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="c2903-103">Installer, gérer et affecter des autorisations pour l’application formations Teams (préversion privée)</span><span class="sxs-lookup"><span data-stu-id="c2903-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="c2903-104">*Cet article contient le contenu préliminaire de l’application formations Teams, qui est en préversion privée.*</span><span class="sxs-lookup"><span data-stu-id="c2903-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="c2903-105">L’application Microsoft teams Learning (préversion privée) donne aux équipes et aux individus de votre organisation une partie naturelle de la journée.</span><span class="sxs-lookup"><span data-stu-id="c2903-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="c2903-106">L’application crée un concentrateur central dans teams pour permettre aux employés de partager, d’affecter et d’apprendre des bibliothèques de contenu au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c2903-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="c2903-107">L’administrateur a défini les autorisations et autorise les sources de contenu d’apprentissage pour l’application.</span><span class="sxs-lookup"><span data-stu-id="c2903-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="c2903-108">Le contenu de l’apprentissage peut inclure LinkedIn Learning, Microsoft Learning, formation Microsoft 365, le contenu de votre organisation stocké dans SharePoint Online et les fournisseurs tiers pris en charge par l’application.</span><span class="sxs-lookup"><span data-stu-id="c2903-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="c2903-109">Pour configurer l’application formations d’équipe (préversion privée), vous devez faire appel aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c2903-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="c2903-110">Administrateur du centre d’administration teams</span><span class="sxs-lookup"><span data-stu-id="c2903-110">Teams admin center admin</span></span>
-   <span data-ttu-id="c2903-111">Administration du centre d’administration 365 Microsoft (c’est-à-dire un administrateur global)</span><span class="sxs-lookup"><span data-stu-id="c2903-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="c2903-112">Administrateur de connaissances (un nouveau rôle dans le centre d’administration 365 Microsoft) qui peut être attribué à n’importe quel utilisateur de l’organisation par un administrateur général (également appelé administrateur informatique ou administrateur 365).</span><span class="sxs-lookup"><span data-stu-id="c2903-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="c2903-113">Ce rôle gère les sources de contenu d’apprentissage de l’organisation par le biais du centre d’administration Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="c2903-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="c2903-114">Gérer l’application formations Teams (préversion privée) dans le centre d’administration teams</span><span class="sxs-lookup"><span data-stu-id="c2903-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="c2903-115">L’administrateur d’équipes installe l’application d’apprentissage en équipe (préversion privée) à partir de l’App Store et applique les stratégies de configuration, de gestion et d’autorisation des applications par le biais du centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="c2903-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="c2903-116">Gérer l’application formations Teams (préversion privée)</span><span class="sxs-lookup"><span data-stu-id="c2903-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="c2903-117">Pour gérer les paramètres de l’application, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c2903-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="c2903-118">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.</span><span class="sxs-lookup"><span data-stu-id="c2903-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navigation gauche dans le centre d’administration teams montrant les applications équipes et la section gérer les applications](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="c2903-120">Dans la page **gérer les applications** , dans la zone de recherche, tapez *apprendre* pour Rechercher l’application formations Teams (préversion publique).</span><span class="sxs-lookup"><span data-stu-id="c2903-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Page gérer les applications dans le centre d’administration Teams, montrant la zone de recherche](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="c2903-122">Sur la page d' **apprentissage** :</span><span class="sxs-lookup"><span data-stu-id="c2903-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="c2903-123">Sous **statut**, sélectionnez **autorisé** pour activer l’application.</span><span class="sxs-lookup"><span data-stu-id="c2903-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="c2903-124">Dans l’onglet **paramètres** , dans la section paramètres de l' **application** , accédez au centre d’administration 365 Microsoft pour configurer les sources de contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="c2903-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Page d’apprentissage dans le centre d’administration teams affichant les sections État et paramètres de l’application](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="c2903-126">Après avoir géré les paramètres de l' **application** , accédez à **autorisations et stratégies de configuration** pour octroyer des autorisations aux employés qui doivent avoir accès à l’application dans le cadre de la participation de votre organisation à la version d’évaluation privée.</span><span class="sxs-lookup"><span data-stu-id="c2903-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="c2903-127">Si votre organisation est 4,0 dans le cadre du programme TAP100 Teams, il est possible que vous deviez procéder comme suit pour permettre aux utilisateurs approuvés de sonner 3,0 d’accéder à l’application formations Teams (préversion privée).</span><span class="sxs-lookup"><span data-stu-id="c2903-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="c2903-128">Dans le cadre de la préversion privée, l’application formations Teams (préversion privée) est publiée dans la sonnerie 3,0.</span><span class="sxs-lookup"><span data-stu-id="c2903-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="c2903-129">Si votre organisation utilise l’anneau 4,0, vous ne verrez pas l’application dans l’App Store.</span><span class="sxs-lookup"><span data-stu-id="c2903-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="c2903-130">Pour tester l’application, vous devez créer une stratégie d’autorisations d’applications personnalisées, définir celle-ci pour **autoriser toutes les applications** et l’affecter à des utilisateurs approuvés de 3,0.</span><span class="sxs-lookup"><span data-stu-id="c2903-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Appuyez sur-AppsPermission-plcy avec l’option autoriser toutes les applications sélectionnée](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c2903-132">Configurer les sources de contenu d’apprentissage dans le centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2903-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="c2903-133">Les administrateurs pour le centre d’administration 365 Microsoft (par eux-mêmes ou en attribuant le rôle d’administrateur de connaissances à certaines personnes de votre organisation) peuvent gérer les paramètres liés à l’application d’apprentissage en équipe (préversion privée) et peuvent configurer les sources de contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="c2903-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="c2903-134">L’administrateur de connaissances doit être modérément technique et disposer d’informations d’identification d’administrateur SharePoint, de préférence à une personne qui est correctement reportée dans le cadre de l’éducation, de l’éducation, de la formation ou des employés de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c2903-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="c2903-135">L’administrateur sélectionne les sources de contenu de formation (par exemple, LinkedIn Learning ou SharePoint) qui seront disponibles dans l’application.</span><span class="sxs-lookup"><span data-stu-id="c2903-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="c2903-136">L’administrateur configure alors ces sources pour veiller à ce que le contenu soit disponible à des fins de recherche et de découverte et puisse être consulté par les employés qui utilisent l’application.</span><span class="sxs-lookup"><span data-stu-id="c2903-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="c2903-137">Attribuer le rôle d’administrateur de connaissances [facultatif]</span><span class="sxs-lookup"><span data-stu-id="c2903-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="c2903-138">Ces étapes doivent être effectuées par l’administrateur pour le centre d’administration 365 Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2903-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="c2903-139">Dans le volet de navigation de gauche du centre d’administration 365 de Microsoft, accédez à **rôles**.</span><span class="sxs-lookup"><span data-stu-id="c2903-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="c2903-140">Dans la page **rôles** , sous l’onglet **Azure ad** , sélectionnez **administrateur de connaissances**.</span><span class="sxs-lookup"><span data-stu-id="c2903-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="c2903-141">Dans la page **administration de connaissances** , dans la section **administrateurs attribués** , sélectionnez **Ajouter**, puis ajoutez la personne que vous choisissez pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="c2903-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="c2903-142">Configurer les paramètres des sources de contenu d’apprentissage pour l’application</span><span class="sxs-lookup"><span data-stu-id="c2903-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="c2903-143">Ces étapes doivent être effectuées par l’administrateur 365 Microsoft ou l’administrateur de connaissances.</span><span class="sxs-lookup"><span data-stu-id="c2903-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="c2903-144">Dans le volet de navigation de gauche du centre d’administration 365 Microsoft, accédez à **paramètres** de l'  >  **organisation**.</span><span class="sxs-lookup"><span data-stu-id="c2903-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="c2903-145">Dans la page **paramètres** , sous l’onglet **services & compléments** , sélectionnez application d' **apprentissage**.</span><span class="sxs-lookup"><span data-stu-id="c2903-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Page Paramètres dans le centre d’administration Microsoft 365 avec l’application d’apprentissage répertoriée](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="c2903-147">Dans le volet de l' **application formations** , sélectionnez les sources de contenu d’apprentissage que vous voulez configurer pour l’organisation, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c2903-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Panneau d’application d’apprentissage dans le centre d’administration Microsoft 365 affichant les options de sources de contenu](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="c2903-149">Parmi toutes les sources d’apprentissage qui existent, d’autres sont activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="c2903-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="c2903-150">Elles incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c2903-150">These include:</span></span>

- <span data-ttu-id="c2903-151">Formations LinkedIn (contenu gratuit)</span><span class="sxs-lookup"><span data-stu-id="c2903-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="c2903-152">Microsoft Apprenez</span><span class="sxs-lookup"><span data-stu-id="c2903-152">Microsoft Learn</span></span>
- <span data-ttu-id="c2903-153">Formation Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2903-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="c2903-154">Si votre organisation dispose d’un abonnement de type LinkedIn Learning standard ou professionnel, le référentiel de contenu sera déverrouillé pour les employés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c2903-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="c2903-155">Seuls les employés qui disposent d’une autorisation pourront utiliser l’ensemble du référentiel de contenu.</span><span class="sxs-lookup"><span data-stu-id="c2903-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="c2903-156">D’autres sources doivent être activées ou configurées manuellement.</span><span class="sxs-lookup"><span data-stu-id="c2903-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="c2903-157">Les sources d’apprentissage qui ne sont pas de Microsoft sont séparément sous licence de votre organisation et de la tierce partie.</span><span class="sxs-lookup"><span data-stu-id="c2903-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="c2903-158">Vous devez vérifier que vous vous êtes inscrit (e) pour l’apprentissage pour vous et vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c2903-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="c2903-159">Pour activer ou désactiver une source de contenu d’apprentissage, activez la case à cocher en regard de la source.</span><span class="sxs-lookup"><span data-stu-id="c2903-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="c2903-160">Si une source est activée, une coche s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c2903-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="c2903-161">Configurer SharePoint en tant que source de contenu d’apprentissage</span><span class="sxs-lookup"><span data-stu-id="c2903-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="c2903-162">Vous configurez SharePoint en tant que source de contenu d’apprentissage pour l’application formations Teams (préversion privée) dans le centre d’administration 365 Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2903-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="c2903-163">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="c2903-163">Overview</span></span>

<span data-ttu-id="c2903-164">L’administrateur de connaissances fournit une URL de site pour permettre au service d’apprentissage de créer un référentiel de contenu d’apprentissage centralisé vide sous la forme d’une liste SharePoint structurée.</span><span class="sxs-lookup"><span data-stu-id="c2903-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="c2903-165">Cette liste peut être utilisée par l’Organisation pour lier des liens vers des dossiers SharePoint interentreprises contenant du contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="c2903-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="c2903-166">Les administrateurs sont chargés de recueillir et de traiter une liste d’URL pour les dossiers.</span><span class="sxs-lookup"><span data-stu-id="c2903-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="c2903-167">Ces dossiers doivent inclure uniquement du contenu qui peut être mis à disposition de l’application formations Teams (préversion privée).</span><span class="sxs-lookup"><span data-stu-id="c2903-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="c2903-168">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c2903-168">Permissions</span></span>

<span data-ttu-id="c2903-169">Les URL de dossiers peuvent être collectées à partir de n’importe quel site SharePoint de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c2903-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="c2903-170">Tout contenu figurant dans ces dossiers pourra être utilisé dans les résultats de la recherche, mais seuls les contenus pour lesquels l’employé individuel dispose d’autorisations peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="c2903-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="c2903-171">Service d’apprentissage</span><span class="sxs-lookup"><span data-stu-id="c2903-171">Learning Service</span></span>

<span data-ttu-id="c2903-172">Le service d’apprentissage utilise les URL de dossier fournies pour obtenir les métadonnées de tout le contenu stocké dans ces dossiers.</span><span class="sxs-lookup"><span data-stu-id="c2903-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="c2903-173">Les employés peuvent rechercher et utiliser le contenu d’une entreprise dans l’application dans les 24 heures suivant la fourniture de l’URL du dossier dans le référentiel centralisé.</span><span class="sxs-lookup"><span data-stu-id="c2903-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="c2903-174">La suppression de contenu du référentiel n’est pas prise en charge à ce stade.</span><span class="sxs-lookup"><span data-stu-id="c2903-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="c2903-175">Le contenu en surface ne peut pas être supprimé en fournissant une nouvelle URL de site SharePoint dans le centre d’administration 365 Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2903-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="c2903-176">Configurer SharePoint en tant que source</span><span class="sxs-lookup"><span data-stu-id="c2903-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="c2903-177">Ces étapes doivent être effectuées par l’administrateur Microsoft 365 ou l’administrateur de connaissances.</span><span class="sxs-lookup"><span data-stu-id="c2903-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="c2903-178">Dans le volet de navigation de gauche du centre d’administration 365 de Microsoft, accédez à **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="c2903-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="c2903-179">Dans la page **paramètres** , sous l’onglet **services & compléments** , sélectionnez application d' **apprentissage**.</span><span class="sxs-lookup"><span data-stu-id="c2903-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Page Paramètres dans le centre d’administration Microsoft 365 avec l’application d’apprentissage répertoriée](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="c2903-181">Dans le volet de l' **application formations** , indiquez l’URL du site du site SharePoint sur lequel vous souhaitez que l’application crée un référentiel centralisé.</span><span class="sxs-lookup"><span data-stu-id="c2903-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Panneau de l’application formations dans le centre d’administration Microsoft 365 affichant l’option SharePoint sélectionnée](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="c2903-183">Une liste SharePoint est créée automatiquement dans le site SharePoint de l’organisation fournie.</span><span class="sxs-lookup"><span data-stu-id="c2903-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="c2903-184">Dans le volet de navigation de gauche du site SharePoint, sélectionnez formation du contenu de l' **application éducation**.</span><span class="sxs-lookup"><span data-stu-id="c2903-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navigation gauche dans SharePoint montrant la section du référentiel de contenu de l’application d’apprentissage](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="c2903-186">Dans la page du référentiel de contenu de l' **application d’apprentissage** , remplissez la liste SharePoint avec des URL vers les dossiers de contenu de formation.</span><span class="sxs-lookup"><span data-stu-id="c2903-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="c2903-187">Pour afficher le volet **nouveau** , sélectionnez **nouveau** .</span><span class="sxs-lookup"><span data-stu-id="c2903-187">Select **New** to view the **New item** panel.</span></span> 

   ![Page du référentiel de contenu de l’application d’apprentissage dans SharePoint présentant la nouvelle option](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="c2903-189">Dans le volet **nouvel élément** , dans le champ **titre** , ajoutez un nom de répertoire de votre choix.</span><span class="sxs-lookup"><span data-stu-id="c2903-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="c2903-190">Dans le champ **URL du dossier** , ajoutez l’URL du dossier contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="c2903-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="c2903-191">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c2903-191">Select **Save**.</span></span>

   ![Panneau nouvel élément dans SharePoint affichant les champs d’URL de titre et de dossier](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="c2903-193">La page du référentiel de contenu de l’application d’apprentissage est mise à jour avec le nouveau contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="c2903-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Page du référentiel de contenu de l’application d’apprentissage dans SharePoint affichant les informations mises à jour](media/learning-app-content-repository-populated.png)


 


