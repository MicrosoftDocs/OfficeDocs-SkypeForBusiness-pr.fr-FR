---
title: Autoriser l'accès invité dans Microsoft Teams
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Gérez les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4fe71b4126a5fb9024de78b696383c0e2f65307
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531869"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="8c090-103">Autoriser l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c090-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="8c090-104">Pour vous conformer aux exigences de votre organisation, vous pouvez gérer les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.</span><span class="sxs-lookup"><span data-stu-id="8c090-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="8c090-105">Tous les niveaux d’autorisation s’appliquent à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c090-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="8c090-106">Chaque niveau d’autorisation contrôle l’expérience utilisateur comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="8c090-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="8c090-107">**Azure Active Directory** : l’accès invité dans Microsoft Teams repose sur la plate-forme entre entreprises (B2B) Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8c090-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="8c090-108">Contrôle l’expérience utilisateur au niveau du répertoire, du client et de l’application.</span><span class="sxs-lookup"><span data-stu-id="8c090-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="8c090-109">**Microsoft Teams** : contrôle uniquement Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="8c090-110">**Groupes Office 365** : contrôle l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="8c090-111">**SharePoint Online et OneDrive Entreprise** : contrôle l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="8c090-112">Ces différents niveaux d’autorisation vous donnent de la flexibilité pour configurer l’accès invité pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c090-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="8c090-113">Par exemple, si vous ne souhaitez pas autoriser d’utilisateurs invités dans votre organisation Microsoft Teams, il vous suffit de désactiver l’accès invité dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="8c090-114">Autre exemple : vous pourriez activer l’accès invité aux niveaux AAD, des équipes et des groupes, puis désactiver l’ajout d’utilisateurs invités au niveau des équipes sélectionnées qui correspondent à un ou plusieurs critères, comme par exemple une classification des données confidentielles.</span><span class="sxs-lookup"><span data-stu-id="8c090-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="8c090-115">Et vous n’utilisez peut-être pas de groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c090-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="8c090-116">SharePoint Online et OneDrive Entreprise ont leurs propres paramètres d’accès invité qui ne reposent pas sur des groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c090-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="8c090-117">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="8c090-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="8c090-118">Le diagramme suivant montre comment la dépendance des autorisations de l’accès invité est octroyée et intégrée entre Azure Active Directory, Microsoft Teams et Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c090-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Diagramme des dépendances des autorisations de l’accès invité.](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="8c090-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c090-120">Azure Active Directory</span></span>

<span data-ttu-id="8c090-121">Avec la collaboration entre entreprises (B2B) Azure AD, l’envoi d'invitations à des utilisateurs invités éventuels n’est pas restreint aux administrateurs de clients.</span><span class="sxs-lookup"><span data-stu-id="8c090-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="8c090-122">Vous pouvez à la place utiliser des stratégies pour déléguer l’envoi des invitations aux utilisateurs dont les rôles les autorisent à envoyer des invitations.</span><span class="sxs-lookup"><span data-stu-id="8c090-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="8c090-123">Les paramètres des invitations s’appliquent au niveau du client et contrôlent l’expérience utilisateur au niveau du répertoire, du client et de l’application.</span><span class="sxs-lookup"><span data-stu-id="8c090-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="8c090-124">Au minimum pour prendre en charge les visiteurs, **les membres peuvent inviter** doit être définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8c090-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Capture d’écran des paramètres utilisateurs dans le portail Azure Active Directory.](media/teams_dependencies_image2.png)

<span data-ttu-id="8c090-126">Azure AD inclut les paramètres suivants pour configurer des utilisateurs externes :</span><span class="sxs-lookup"><span data-stu-id="8c090-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="8c090-127">**Les autorisations utilisateur invité sont limitées**: **Oui** signifie que les invités n’autorisé pour certaines tâches de répertoire, énumérer tels que les utilisateurs, groupes ou autres ressources de répertoire.</span><span class="sxs-lookup"><span data-stu-id="8c090-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="8c090-128">En outre, les invités ne peuvent pas être attribuées aux rôles d’administration dans votre répertoire.</span><span class="sxs-lookup"><span data-stu-id="8c090-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="8c090-129">**No** signifie que les invités ont le même accès aux données dont les utilisateurs classiques dans votre répertoire de l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="8c090-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="8c090-130">**Administrateurs et aux utilisateurs dans le rôle d’émetteur de l’invitation invité peuvent inviter**: **Oui** signifie que les administrateurs et aux utilisateurs dans le rôle « Émetteur de l’invitation invité » sera en mesure d’invités au client.</span><span class="sxs-lookup"><span data-stu-id="8c090-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="8c090-131">**No** signifie Administrateurs et les utilisateurs ne peuvent pas invités au client.</span><span class="sxs-lookup"><span data-stu-id="8c090-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="8c090-132">**Les membres peuvent inviter**: **Oui** signifie que non-admin membres de votre annuaire peuvent invités à collaborer sur des ressources sécurisées par votre Azure AD, tels que les sites SharePoint ou ressources Azure.</span><span class="sxs-lookup"><span data-stu-id="8c090-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="8c090-133">**No** signifie que seuls les administrateurs peuvent inviter invités dans votre répertoire.</span><span class="sxs-lookup"><span data-stu-id="8c090-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="8c090-134">**Les invités peuvent inviter**: **Oui** signifie que les invités dans votre répertoire peuvent eux-mêmes inviter autre invité à collaborer sur des ressources sécurisées par votre Azure AD, tels que les sites SharePoint ou ressources Azure.</span><span class="sxs-lookup"><span data-stu-id="8c090-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="8c090-135">**No** signifie que les invités ne peut pas inviter d’autres invités pour collaborer avec votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c090-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="8c090-136">Vous pouvez également gérer les domaines peuvent être invités à votre client en tant qu’invités.</span><span class="sxs-lookup"><span data-stu-id="8c090-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="8c090-137">Voir [Autoriser/bloquer l’accès invité à des groupes d’Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="8c090-137">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="8c090-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c090-138">Microsoft Teams</span></span>
<span data-ttu-id="8c090-139">Dans Microsoft Teams, vous pouvez contrôler si l’expérience invité est activée ou désactivée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c090-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="8c090-140">Ce paramètre est désactivé par défaut et s’applique au niveau du client pour Microsoft Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="8c090-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="8c090-141">Vous pouvez gérer l'accès invité dans Microsoft Teams via le centre d'administration d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c090-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="8c090-142">Pour plus d'informations, reportez-vous à la rubrique [Activer ou désactiver l'accès invité de Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="8c090-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="8c090-143">Groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="8c090-143">Office 365 Groups</span></span>

<span data-ttu-id="8c090-144">À partir des groupes Office 365, vous pouvez contrôler l’ajout d’invités et l'accès invité à tous les groupes Office 365 et Microsoft Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c090-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="8c090-145">Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="8c090-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="8c090-146">Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.</span><span class="sxs-lookup"><span data-stu-id="8c090-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="8c090-147">Sélectionnez **Groupes Office 365**.</span><span class="sxs-lookup"><span data-stu-id="8c090-147">Select **Office 365 Groups**.</span></span>
    
     ![Groupes Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="8c090-149">Sur la page Groupes Office 365, définissez la bascule sur **Activé** ou **Désactivé**, pour autoriser ou non les propriétaires d'équipes et de groupes en dehors de votre organisation à accéder aux groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c090-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="8c090-150">Définissez la bascule sur **Activé** près de l'option **Autoriser les propriétaires d'équipe à ajouter des personnes en dehors de l'organisation aux groupes**.</span><span class="sxs-lookup"><span data-stu-id="8c090-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="8c090-151">Si vous définissez cette bascule sur Activé, une autre option vous permettant de contrôler si vous souhaitez autoriser ou non les propriétaires d’équipes et de groupes à ajouter des personnes externes à votre organisation aux groupes Office 365 et Microsoft Teams s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8c090-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="8c090-152">Définissez cette bascule sur Activé si vous souhaitez autoriser les propriétaires d'équipes et de groupes à ajouter des utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="8c090-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> 
 
   ![La capture d'écran illustre le panneau Groupes d'Office 365 avec les options activées pour permettre aux membres du groupe de l'extérieur de l'organisation d'accéder au contenu du groupe, et aux propriétaires d'ajouter au groupe des personnes externes à l'organisation.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




<span data-ttu-id="8c090-154">Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="8c090-155">SharePoint Online et OneDrive Entreprise</span><span class="sxs-lookup"><span data-stu-id="8c090-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="8c090-156">Teams repose sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations.</span><span class="sxs-lookup"><span data-stu-id="8c090-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="8c090-157">Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="8c090-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="8c090-158">Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**</span><span class="sxs-lookup"><span data-stu-id="8c090-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="8c090-159">Pour plus d'informations, reportez-vous à la rubrique [Gérer le partage externe de votre environnement SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span><span class="sxs-lookup"><span data-stu-id="8c090-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span></span>
    
  
- <span data-ttu-id="8c090-160">Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**</span><span class="sxs-lookup"><span data-stu-id="8c090-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="8c090-161">Pour plus d'informations, reportez-vous à la rubrique [Contrôler l'accès invité à Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="8c090-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="8c090-162">Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="8c090-163">Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c090-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="8c090-164">Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="8c090-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
