---
title: "Autoriser l'accès invité dans Microsoft Teams"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Gérez les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8faf2e13efb0c4c031fabea11185f1e3cdd353d1
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2017
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="6d9b3-103">Autoriser l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d9b3-103">Manage guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="6d9b3-104">Pour vous conformer aux exigences de votre organisation, vous pouvez gérer les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="6d9b3-105">Tous les niveaux d’autorisation s’appliquent à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="6d9b3-106">Chaque niveau d’autorisation contrôle l’expérience utilisateur comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="6d9b3-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="6d9b3-107">**Azure Active Directory** : l’accès invité dans Microsoft Teams repose sur la plate-forme entre entreprises (B2B) Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="6d9b3-108">Contrôle l’expérience utilisateur au niveau du répertoire, du client et de l’application.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="6d9b3-109">**Microsoft Teams** : contrôle uniquement Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="6d9b3-110">**Groupes Office 365** : contrôle l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="6d9b3-111">**SharePoint Online et OneDrive Entreprise** : contrôle l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="6d9b3-112">Ces différents niveaux d’autorisation vous donnent de la flexibilité pour configurer l’accès invité pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="6d9b3-113">Par exemple, si vous ne souhaitez pas autoriser d’utilisateurs invités dans votre organisation Microsoft Teams, il vous suffit de désactiver l’accès invité dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="6d9b3-114">Autre exemple : vous pourriez activer l’accès invité aux niveaux AAD, des équipes et des groupes, puis désactiver l’ajout d’utilisateurs invités au niveau des équipes sélectionnées qui correspondent à un ou plusieurs critères, comme par exemple une classification des données confidentielles.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="6d9b3-115">Et vous n’utilisez peut-être pas de groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="6d9b3-116">SharePoint Online et OneDrive Entreprise ont leurs propres paramètres d’accès invité qui ne reposent pas sur des groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="6d9b3-117">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="6d9b3-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="6d9b3-118">Le diagramme suivant montre comment la dépendance des autorisations de l’accès invité est octroyée et intégrée entre Azure Active Directory, Microsoft Teams et Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Diagramme des dépendances des autorisations de l’accès invité.](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a><span data-ttu-id="6d9b3-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6d9b3-120">Azure Active Directory</span></span>

<span data-ttu-id="6d9b3-121">Avec la collaboration entre entreprises (B2B) Azure AD, l’envoi d'invitations à des utilisateurs invités éventuels n’est pas restreint aux administrateurs de clients.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="6d9b3-122">Vous pouvez à la place utiliser des stratégies pour déléguer l’envoi des invitations aux utilisateurs dont les rôles les autorisent à envoyer des invitations.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="6d9b3-123">Les paramètres des invitations s’appliquent au niveau du client et contrôlent l’expérience utilisateur au niveau du répertoire, du client et de l’application.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span>


![Capture d’écran des paramètres utilisateurs dans le portail Azure Active Directory.](media/teams_dependencies_image2.png)


<span data-ttu-id="6d9b3-125">Vous pouvez définir les stratégies d’invitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d9b3-125">You can set the following parameters:</span></span>
- <span data-ttu-id="6d9b3-126">Désactiver les invitations.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-126">Turn off invitations.</span></span>
- <span data-ttu-id="6d9b3-127">Seuls les administrateurs et les utilisateurs ayant le rôle d’hôte peuvent inviter des participants.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-127">Only admins and users in the guest inviter role can invite.</span></span>
- <span data-ttu-id="6d9b3-128">Les administrateurs, le rôle d’hôte et les membres peuvent inviter des participants.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-128">Admins, the guest inviter role, and members can invite.</span></span>
- <span data-ttu-id="6d9b3-129">Tous les utilisateurs, y compris les invités, peuvent inviter des participants.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-129">All users, including guests, can invite.</span></span> <span data-ttu-id="6d9b3-130">(Il s’agit de la stratégie par défaut pour les clients.)</span><span class="sxs-lookup"><span data-stu-id="6d9b3-130">(This is the default policy for tenants.)</span></span>


##<a name="microsoft-teams"></a><span data-ttu-id="6d9b3-131">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d9b3-131">Microsoft Teams</span></span>

<span data-ttu-id="6d9b3-132">Dans Microsoft Teams, vous pouvez contrôler si l’expérience invité est activée ou désactivée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-132">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="6d9b3-133">Ce paramètre est désactivé par défaut et s’applique au niveau du client pour Microsoft Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-133">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="6d9b3-134">Vous pouvez gérer l'accès invité dans Microsoft Teams via le centre d'administration d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-134">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="6d9b3-135">Pour plus d'informations, reportez-vous à la rubrique [Activer ou désactiver l'accès invité de Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="6d9b3-135">For more details, see "Turn on or off guest access for Microsoft Teams."</span></span> 


##<a name="office-365-groups"></a><span data-ttu-id="6d9b3-136">Groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="6d9b3-136">Office 365 groups</span></span>

<span data-ttu-id="6d9b3-137">À partir des groupes Office 365, vous pouvez contrôler l’ajout d’invités et l'accès invité à tous les groupes Office 365 et Microsoft Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-137">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="6d9b3-138">Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="6d9b3-138">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="6d9b3-139">Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-139">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="6d9b3-140">Sélectionnez **Groupes Office 365**.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-140">Select **Office 365 Groups**.</span></span>
    
     ![Groupes Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="6d9b3-142">Sur la page Groupes Office 365, définissez la bascule sur **Activé** ou **Désactivé**, pour autoriser ou non les propriétaires d'équipes et de groupes en dehors de votre organisation à accéder aux groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-142">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="6d9b3-143">Définissez la bascule sur **Activé** près de l'option **Autoriser les propriétaires d'équipe à ajouter des personnes en dehors de l'organisation aux groupes**.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-143">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="6d9b3-144">Si vous définissez cette bascule sur Activé, une autre option vous permettant de contrôler si vous souhaitez autoriser ou non les propriétaires d’équipes et de groupes à ajouter des personnes externes à votre organisation aux groupes Office 365 et Microsoft Teams s’affiche.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-144">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="6d9b3-145">Définissez cette bascule sur Activé si vous souhaitez autoriser les propriétaires d'équipes et de groupes à ajouter des utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-145">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="6d9b3-146">![La capture d'écran illustre le panneau Groupes d'Office 365 avec les options activées pour permettre aux membres du groupe de l'extérieur de l'organisation d'accéder au contenu du groupe, et aux propriétaires d'ajouter au groupe des personnes externes à l'organisation.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="6d9b3-146">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="6d9b3-147">Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-147">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


##<a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="6d9b3-148">SharePoint Online et OneDrive Entreprise</span><span class="sxs-lookup"><span data-stu-id="6d9b3-148">See How SharePoint Online and OneDrive for Business interact with Teams</span></span>

<span data-ttu-id="6d9b3-149">Teams repose sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-149">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="6d9b3-150">Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6d9b3-150">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="6d9b3-151">Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**</span><span class="sxs-lookup"><span data-stu-id="6d9b3-151">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="6d9b3-152">Pour plus d'informations, reportez-vous à la rubrique [Gérer le partage externe de votre environnement SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="6d9b3-152">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="6d9b3-153">Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**</span><span class="sxs-lookup"><span data-stu-id="6d9b3-153">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="6d9b3-154">Pour plus d'informations, reportez-vous à la rubrique [Contrôler l'accès invité à Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="6d9b3-154">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="6d9b3-155">Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-155">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="6d9b3-156">Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d9b3-156">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="6d9b3-157">Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="6d9b3-157">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>