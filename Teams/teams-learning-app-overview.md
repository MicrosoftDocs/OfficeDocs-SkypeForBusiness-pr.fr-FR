---
title: Installer, gérer et attribuer des autorisations pour Microsoft Microsoft Microsoft Learning (prévisualisation privée)
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
description: Utilisez Microsoft Domaine Learning (prévisualisation privée) pour créer une plateforme centrale pour l'apprentissage où les employés peuvent partager, attribuer et apprendre des bibliothèques de contenu au sein d'une organisation.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880348"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="a5549-103">Installer, gérer et attribuer des autorisations pour Microsoft Microsoft Microsoft Learning (prévisualisation privée)</span><span class="sxs-lookup"><span data-stu-id="a5549-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="a5549-104">*Cet article contient du contenu préliminaire pour Microsoft Learning, qui est en version d'évaluation privée.*</span><span class="sxs-lookup"><span data-stu-id="a5549-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="a5549-105">Microsoft Private Learning (pré-version préliminaire privée) permet aux équipes et aux membres de votre organisation de faire de l'apprentissage une partie naturelle de leur journée.</span><span class="sxs-lookup"><span data-stu-id="a5549-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="a5549-106">L'application crée un hub central dans Teams où les employés peuvent partager, attribuer et apprendre des bibliothèques de contenu au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5549-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="a5549-107">Les administrateurs définissent des autorisations et autorisent les sources de contenu d'apprentissage pour Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="a5549-108">Le contenu d'apprentissage peut inclure LinkedIn Learning, Microsoft Learn, une formation Microsoft 365, le contenu de votre organisation stocké dans SharePoint Online et des fournisseurs tiers pris en charge par Learning Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="a5549-109">Rôles d'administrateur</span><span class="sxs-lookup"><span data-stu-id="a5549-109">Admin roles</span></span>

<span data-ttu-id="a5549-110">Pour configurer Contrôle Learning (prévisualisation privée), vous devez obtenir les autorisations ci-après :</span><span class="sxs-lookup"><span data-stu-id="a5549-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="a5549-111">Administrateur de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5549-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="a5549-112">Administrateur général de Microsoft 365 ou administrateur SharePoint</span><span class="sxs-lookup"><span data-stu-id="a5549-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="a5549-113">Administrateur de connaissances : il s'agit d'un nouveau rôle dans le Centre d'administration Microsoft 365 qui peut être attribué à tous les membres de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="a5549-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="a5549-114">Ce rôle gère les sources de contenu pédagogique de l'organisation via le Centre d'administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5549-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="a5549-115">L'administrateur des connaissances doit être relativement technique et avoir des informations d'identification d'administrateur SharePoint, de préférence une personne qui a une bonne connaissance de l'enseignement, de l'apprentissage, de la formation ou de l'expérience des employés au niveau de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="a5549-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="a5549-116">Gérer Contrôle Learning (prévisualisation privée) dans le Centre d'administration Teams</span><span class="sxs-lookup"><span data-stu-id="a5549-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="a5549-117">L'administrateur Teams installe Contrôle Learning (prévisualisation privée) à partir du magasin d'applications, puis applique les stratégies de configuration, de gestion et d'autorisation via le Centre d'administration Teams.</span><span class="sxs-lookup"><span data-stu-id="a5549-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="a5549-118">Gérer les paramètres pour Contrôle Learning (prévisualisation privée)</span><span class="sxs-lookup"><span data-stu-id="a5549-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="a5549-119">Vous devez être un administrateur du Centre d'administration Teams pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="a5549-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="a5549-120">Pour gérer les paramètres de Contrôle Learning, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5549-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="a5549-121">Dans le panneau de navigation gauche du Centre d'administration Teams, allez à **l'application Teams** Gérer  >  **les applications.**</span><span class="sxs-lookup"><span data-stu-id="a5549-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navigation gauche dans le Centre d'administration Teams affichant les applications Teams et la section Gérer les applications](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="a5549-123">Dans la page **Gérer les applications,** dans la zone de recherche, tapez *Apprentissage* pour rechercher l'application Teams Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Page Gérer les applications dans le Centre d'administration Teams affichant la zone de recherche](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="a5549-125">Sur la page **Apprentissage** :</span><span class="sxs-lookup"><span data-stu-id="a5549-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="a5549-126">Sous **État,** **sélectionnez Autorisé** pour activer l'application.</span><span class="sxs-lookup"><span data-stu-id="a5549-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="a5549-127">Sous **l'onglet Paramètres,** dans la section **Paramètres** des applications, allez au Centre d'administration Microsoft 365 pour configurer les sources de contenu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="a5549-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Page d'apprentissage dans le Centre d'administration Teams affichant la section Paramètres de statut et d'application](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="a5549-129">Après  avoir gérer les paramètres de l'application, accédez aux autorisations et aux stratégies de configuration pour accorder des **autorisations** aux employés qui doivent avoir accès à l'application dans le cadre de la participation de votre organisation à la prévisualisation privée.</span><span class="sxs-lookup"><span data-stu-id="a5549-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="a5549-130">Si votre organisation fait partie de l'anneau 4.0 dans le cadre du programme Teams TAP100, vous devrez peut-être suivre les opérations suivantes pour permettre aux utilisateurs approuvés de l'anneau 3.0 d'accéder à Learning Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="a5549-131">Dans le cadre de la prévisualisation privée, Learning (prévisualisation privée) est publié dans l'anneau 3.0.</span><span class="sxs-lookup"><span data-stu-id="a5549-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="a5549-132">Si votre organisation est sous l'anneau 4.0, l'application n'est pas dans l'App Store.</span><span class="sxs-lookup"><span data-stu-id="a5549-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="a5549-133">Pour tester l'application, vous devez créer une stratégie d'autorisation d'applications personnalisée, la définir sur Autoriser toutes les applications et l'affecter aux utilisateurs approuvés Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="a5549-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Page TAP-AppsPermission-Plcy affichant l'affichage Autoriser toutes les applications sélectionné](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a5549-135">Configurer des sources de contenu d'apprentissage dans le Centre d'administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5549-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a5549-136">Les administrateurs du Centre d'administration Microsoft 365, seuls ou en leur attribuant le rôle d'administrateur des connaissances à des membres sélectionnés de votre organisation, peuvent gérer les paramètres relatifs à Learning Learning (prévisualisation privée) et configurer les sources de contenu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="a5549-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="a5549-137">L'administrateur sélectionne les sources de contenu supplémentaires (par exemple, SharePoint ou les sources de fournisseurs de contenu tiers pris en charge) qui seront disponibles pour les utilisateurs de Cette formation (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="a5549-138">L'administrateur configure ensuite ces sources pour s'assurer que le contenu est disponible pour la recherche et la découverte et peut être consulté par les employés qui utilisent Contrôle Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="a5549-139">Les utilisateurs se connectent aux apprentissages non-Microsoft et LinkedIn Learning Pro dans un navigateur ou une visionneuse incorporée.</span><span class="sxs-lookup"><span data-stu-id="a5549-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="a5549-140">Cet apprentissage configuré est soumis aux conditions distinctes de licence, de confidentialité et de service entre votre organisation et le tiers, et non aux conditions générales de Cette formation (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="a5549-141">Avant de sélectionner ce type d'apprentissage, vérifiez que vous avez un contrat en place pour votre organisation et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a5549-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="a5549-142">Attribuer le rôle d'administrateur des connaissances [Facultatif]</span><span class="sxs-lookup"><span data-stu-id="a5549-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="a5549-143">Vous devez être un administrateur général Microsoft 365 pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="a5549-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="a5549-144">Pour désigner un administrateur des connaissances pour Contrôle Learning, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a5549-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="a5549-145">Dans le navigation gauche du Centre d'administration Microsoft 365, voir **Rôles.**</span><span class="sxs-lookup"><span data-stu-id="a5549-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="a5549-146">Dans la page **Rôles,** sous **l'onglet Azure AD,** sélectionnez **Administrateur des connaissances.**</span><span class="sxs-lookup"><span data-stu-id="a5549-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="a5549-147">Dans la page **Administrateur des** connaissances, dans la section **Administrateurs affectés,** sélectionnez **Ajouter,** puis ajoutez la personne que vous choisissez pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="a5549-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="a5549-148">Configurer les paramètres des sources de contenu d'apprentissage pour Learning Learning (aperçu privé)</span><span class="sxs-lookup"><span data-stu-id="a5549-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="a5549-149">Pour effectuer ces tâches, vous devez être administrateur général ou administrateur de connaissances Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5549-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="a5549-150">Pour configurer les paramètres des sources de contenu d'apprentissage dans Contrôle Learning, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a5549-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="a5549-151">Dans le panneau de navigation gauche du Centre d'administration Microsoft 365, allez dans  >  **Paramètres de l'organisation.**</span><span class="sxs-lookup"><span data-stu-id="a5549-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="a5549-152">Dans la page **Paramètres de l'organisation,** sous l'onglet **Services,** sélectionnez **Application d'apprentissage (aperçu).**</span><span class="sxs-lookup"><span data-stu-id="a5549-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Page Paramètres du Centre d'administration Microsoft 365 affichant l'application Learning répertoriée](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="a5549-154">Dans le **panneau d'aperçu de** l'application d'apprentissage, sélectionnez les sources de contenu d'apprentissage que vous voulez configurer pour l'organisation, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="a5549-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![Panneau d’apprentissage dans le Centre d’administration Microsoft 365 affichant les options de sources de contenu](media/learning-sharepoint-configure2.png)

<span data-ttu-id="a5549-156">Parmi toutes les sources d’apprentissage existantes, certaines seront activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="a5549-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="a5549-157">Elles incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a5549-157">These include:</span></span>

- <span data-ttu-id="a5549-158">LinkedIn Learning (contenu gratuit)</span><span class="sxs-lookup"><span data-stu-id="a5549-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="a5549-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="a5549-159">Microsoft Learn</span></span>
- <span data-ttu-id="a5549-160">Formation Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5549-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="a5549-161">Si votre organisation a un abonnement LinkedIn Learning Standard ou Professionnel, le référentiel de contenu sera déverrouillé pour les employés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5549-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="a5549-162">Seuls les employés autorisés pourront utiliser l’ensemble du référentiel de contenu.</span><span class="sxs-lookup"><span data-stu-id="a5549-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="a5549-163">D’autres sources doivent peut-être être activées ou configurées manuellement.</span><span class="sxs-lookup"><span data-stu-id="a5549-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="a5549-164">Les sources d’apprentissage qui ne sont pas de Microsoft sont sous licence distinctes entre votre organisation et le tiers.</span><span class="sxs-lookup"><span data-stu-id="a5549-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="a5549-165">Vous devrez vérifier que vous êtes inscrit à l’apprentissage pour vous et vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a5549-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="a5549-166">Pour activer ou désactiver une source de contenu d’apprentissage, activez la case à cocher en regard de la source.</span><span class="sxs-lookup"><span data-stu-id="a5549-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="a5549-167">Si une source est activée, une coche est visible.</span><span class="sxs-lookup"><span data-stu-id="a5549-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="a5549-168">Configurer SharePoint comme source de contenu d’apprentissage</span><span class="sxs-lookup"><span data-stu-id="a5549-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="a5549-169">Vous pouvez configurer SharePoint comme source de contenu d’apprentissage pour mettre à disposition le contenu de votre organisation dans Learning Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="a5549-170">Présentation</span><span class="sxs-lookup"><span data-stu-id="a5549-170">Overview</span></span>

<span data-ttu-id="a5549-171">L’administrateur des connaissances (ou administrateur général) fournit une URL de site à laquelle le service d’apprentissage peut créer un emplacement centralisé vide, le référentiel de contenu des applications d’apprentissage, sous la forme d’une liste SharePoint structurée.</span><span class="sxs-lookup"><span data-stu-id="a5549-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="a5549-172">Cette liste peut être utilisée par votre organisation pour contenir des liens vers des dossiers SharePoint entre entreprises contenant du contenu d’apprentissage.</span><span class="sxs-lookup"><span data-stu-id="a5549-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="a5549-173">Les administrateurs sont responsables de la collecte et de l’organisation d’une liste d’URL pour les dossiers.</span><span class="sxs-lookup"><span data-stu-id="a5549-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="a5549-174">Ces dossiers ne doivent inclure que du contenu qui peut être mis à disposition dans Nommé Learning (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="a5549-175">Contrôle Learning (aperçu privé) prend en charge les types de documents suivants :</span><span class="sxs-lookup"><span data-stu-id="a5549-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="a5549-176">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="a5549-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="a5549-177">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="a5549-177">Audio (.m4a)</span></span>
- <span data-ttu-id="a5549-178">Vidéo (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="a5549-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="a5549-179">Pour plus d'informations, consultez [la documentation SharePoint Online.](https://docs.microsoft.com/sharepoint/introductionlink)</span><span class="sxs-lookup"><span data-stu-id="a5549-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="a5549-180">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a5549-180">Permissions</span></span>

<span data-ttu-id="a5549-181">Les URL des dossiers de bibliothèque de documents peuvent être collectées à partir de n'importe quel site SharePoint de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="a5549-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="a5549-182">Cette version préliminaire (private preview) suit toutes les autorisations de contenu existantes.</span><span class="sxs-lookup"><span data-stu-id="a5549-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="a5549-183">Par conséquent, seul le contenu pour lequel un utilisateur est autorisé à accéder est accessible et accessible dans Learning (aperçu privé).</span><span class="sxs-lookup"><span data-stu-id="a5549-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="a5549-184">Tout contenu de ces dossiers pourra faire l'effet d'une recherche, mais seul le contenu auquel l'employé dispose des autorisations individuelles peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="a5549-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="a5549-185">La suppression du contenu du référentiel de votre organisation n'est pas prise en charge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="a5549-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="a5549-186">Pour supprimer le contenu accidentellement surface, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a5549-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="a5549-187">Pour restreindre l'accès à la bibliothèque de documents, sélectionnez l'option **Afficher les actions,** puis **sélectionnez Gérer l'accès.**</span><span class="sxs-lookup"><span data-stu-id="a5549-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Page Bibliothèque de documents dans SharePoint affichant l'option Afficher les actions avec l'option Gérer l'accès en surligtée.](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="a5549-189">Supprimez le document d'origine dans la bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="a5549-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="a5549-190">Pour plus d'informations, [voir Partage et autorisations dans l'expérience moderne de SharePoint.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="a5549-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="a5549-191">Service d'apprentissage</span><span class="sxs-lookup"><span data-stu-id="a5549-191">Learning Service</span></span>

<span data-ttu-id="a5549-192">Le service d'apprentissage utilise les URL des dossiers fournis pour obtenir les métadonnées de tout le contenu stocké dans ces dossiers.</span><span class="sxs-lookup"><span data-stu-id="a5549-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="a5549-193">Dans les 24 heures après avoir fournissé l'URL du dossier dans le référentiel centralisé, les employés peuvent rechercher et utiliser le contenu de votre organisation dans Cette formation (prévisualisation privée).</span><span class="sxs-lookup"><span data-stu-id="a5549-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="a5549-194">Toutes les modifications apportées au contenu, y compris les métadonnées et les autorisations mises à jour, seront également appliquées dans le service d'apprentissage dans les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="a5549-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="a5549-195">Configurer SharePoint en tant que source</span><span class="sxs-lookup"><span data-stu-id="a5549-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="a5549-196">Pour effectuer ces tâches, vous devez être un administrateur général, un administrateur SharePoint ou un administrateur de connaissances Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5549-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="a5549-197">Pour configurer SharePoint en tant que sources de contenu d'apprentissage pour Learning Learning (prévisualisation privée), suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a5549-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="a5549-198">Dans le panneau de navigation gauche du Centre d'administration Microsoft 365, allez dans  >  **Paramètres de l'organisation.**</span><span class="sxs-lookup"><span data-stu-id="a5549-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="a5549-199">Dans la page **Paramètres de l'organisation,** sous l'onglet **Services,** sélectionnez **Application d'apprentissage (aperçu).**</span><span class="sxs-lookup"><span data-stu-id="a5549-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Page Paramètres du Centre d'administration Microsoft 365 affichant Learning Dans la liste.](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="a5549-201">Dans le panneau de l'application d'apprentissage **(prévisualisation),** sous **SharePoint,** fournissez l'URL du site vers le site SharePoint où vous souhaitez que Contrôle Learning crée un référentiel centralisé.</span><span class="sxs-lookup"><span data-stu-id="a5549-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![Panneau d'apprentissage du Centre d'administration Microsoft 365 avec SharePoint sélectionné.](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="a5549-203">Une liste SharePoint est créée automatiquement dans le site SharePoint fourni.</span><span class="sxs-lookup"><span data-stu-id="a5549-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Liste SharePoint nouvellement créée dans le site SharePoint.](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="a5549-205">Dans le navigation gauche du site SharePoint, sélectionnez Référentiel de **contenu d'application** d'apprentissage pour le  >  **contenu du site.**</span><span class="sxs-lookup"><span data-stu-id="a5549-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![Liste SharePoint affichant la navigation du contenu du site et la section Référentiel de contenu d'application d'apprentissage.](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="a5549-207">Dans la page **Référentiel** de contenu d'application d'apprentissage, insérez la liste SharePoint avec des URL vers les dossiers de contenu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="a5549-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="a5549-208">Sélectionnez Nouveau pour afficher **le panneau Nouvel** élément. </span><span class="sxs-lookup"><span data-stu-id="a5549-208">Select **New** to view the **New item** panel.</span></span> 

       ![Page référentiel de contenu d'apprentissage dans SharePoint affichant l'option Nouvelle.](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="a5549-210">Dans le **panneau Nouvel élément,** dans le champ **Titre,** ajoutez le nom d'annuaire de votre choix.</span><span class="sxs-lookup"><span data-stu-id="a5549-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="a5549-211">Dans le champ **URL du** dossier, ajoutez l'URL au dossier de contenu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="a5549-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="a5549-212">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a5549-212">Select **Save**.</span></span>

       ![Panneau Nouvel élément dans SharePoint affichant les champs URL de titre et de dossier.](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="a5549-214">La page **référentiel de contenu des** applications d'apprentissage est mise à jour avec le nouveau contenu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="a5549-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Page référentiel de contenu d'apprentissage dans SharePoint affichant les informations mises à jour.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="a5549-216">Pour permettre un accès plus large au référentiel de contenu des applications d'apprentissage, un lien vers la liste sera bientôt disponible dans l'interface (prévisualisation privée) de Ces derniers, où les utilisateurs pourront demander l'accès et, finalement, vous aider à remplir la liste.</span><span class="sxs-lookup"><span data-stu-id="a5549-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="a5549-217">Les propriétaires de site et les administrateurs globaux seront requis pour accorder l'accès à la liste.</span><span class="sxs-lookup"><span data-stu-id="a5549-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="a5549-218">Access est spécifique à la liste uniquement et ne s'applique pas au site où la liste est stockée.</span><span class="sxs-lookup"><span data-stu-id="a5549-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="a5549-219">Curation de la bibliothèque de documents d'URL de dossier</span><span class="sxs-lookup"><span data-stu-id="a5549-219">Folder URL document library curation</span></span>

<span data-ttu-id="a5549-220">Les métadonnées par défaut (telles que la date de modification, créée par, le nom du document, le type de contenu et le nom de l'organisation) sont automatiquement extraites dans Le Learning (aperçu privé) par l'API Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="a5549-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="a5549-221">Pour améliorer la pertinence globale de la découverte et de la recherche du contenu, nous vous recommandons d'ajouter une **colonne Description.**</span><span class="sxs-lookup"><span data-stu-id="a5549-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="a5549-222">Pour ajouter une colonne **Description** à la page de la bibliothèque de documents, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="a5549-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="a5549-223">Dans la page **Documents,** **sélectionnez Ajouter une colonne.**</span><span class="sxs-lookup"><span data-stu-id="a5549-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="a5549-224">Sélectionnez **l'option Afficher** les actions, puis **sélectionnez Une seule ligne de texte.**</span><span class="sxs-lookup"><span data-stu-id="a5549-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Page Documents dans SharePoint affichant les options Afficher les actions avec une seule ligne de texte mise en évidence.](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="a5549-226">Dans le **panneau Créer une colonne,** dans **le** champ Nom, ajoutez un nom descriptif pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="a5549-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="a5549-227">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a5549-227">Select **Save**.</span></span>

     ![Créez un panneau de colonnes dans SharePoint affichant le nom et d'autres champs.](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="a5549-229">Dans la page **Documents,** dans la **colonne Description,** ajoutez des descriptions personnalisées pour chaque élément.</span><span class="sxs-lookup"><span data-stu-id="a5549-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="a5549-230">Si aucune description n'est fournie, Cette option fournit un message par défaut qui met en évidence le contenu provenant de votre propre bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a5549-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Page Documents dans SharePoint affichant les descriptions dans la colonne Description.](media/learning-sharepoint-curation3.png)
 
