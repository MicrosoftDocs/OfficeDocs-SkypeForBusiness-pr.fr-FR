---
title: Accès invité dans Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
localization_priority: Normal
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42ec1ce60a206fa0a67f40c08db4658c0c53e543
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641190"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="5d3b8-103">Accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d3b8-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="5d3b8-104">Vue d’ensemble de l’accès invité</span><span class="sxs-lookup"><span data-stu-id="5d3b8-104">Guest access overview</span></span>

<span data-ttu-id="5d3b8-105">L’accès invité est une des fonctionnalités de clients ont demandé le plus.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="5d3b8-106">Voici comment vous pouvez suivre notre progression sur l’accès invité et donnez-nous votre avis :</span><span class="sxs-lookup"><span data-stu-id="5d3b8-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="5d3b8-107">Si vous rencontrez des problèmes avec l’accès invité, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d3b8-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="5d3b8-108">Vous trouverez des informations sur les fonctionnalités à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="5d3b8-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="5d3b8-109">Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="5d3b8-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="5d3b8-110">Partagez votre expérience dans la section Commentaires ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="5d3b8-111">Accès invité permet aux équipes de votre organisation de collaborer avec des personnes extérieures à votre organisation par leur accorder l’accès pour les équipes et les canaux sur un ou plusieurs de vos clients.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="5d3b8-112">Toute personne possédant un compte de messagerie consommateur ou de l’entreprise, comme Outlook, Gmail ou d’autres personnes, peut participer à en tant qu’invité dans les équipes avec accès total aux conversations de l’équipe, des réunions et des fichiers.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="5d3b8-113">L’accès invité est inclus avec Office 365 entreprise Premium, Office 365 pour entreprises et Office 365 éducation tous les abonnements avec aucune exigence supplémentaire pour les licences.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="5d3b8-114">Vous pouvez avoir jusqu'à 5 invités par l’utilisateur sous licence sur votre client.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="5d3b8-115">Pour plus d’informations sur les licences, consultez les [instructions de gestion des licences de collaboration Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="5d3b8-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="5d3b8-116">L'accès invité est un paramètre de niveau client dans Microsoft Teams, désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="5d3b8-117">L’accès invité est soumis à Azure AD et des limites du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="5d3b8-118">Les utilisateurs de votre organisation qui ont des plans d’abonnement Office 365 autonome uniquement, tels que Exchange Online Plan 2, ne peut pas être invités en tant qu’invités à votre organisation, car les équipes considère que ces utilisateurs appartenant à la même organisation.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="5d3b8-119">Pour les utilisateurs à utiliser des équipes, ils doivent disposer un abonnement à Office 365 entreprise Premium, Office 365 pour entreprises ou Office 365 éducation.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="5d3b8-120">Qui est invité ?</span><span class="sxs-lookup"><span data-stu-id="5d3b8-120">Who is a guest?</span></span>

<span data-ttu-id="5d3b8-121">Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="5d3b8-122">Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="5d3b8-123">Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="5d3b8-124">Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="5d3b8-125">Cela signifie que toute personne possédant un compte professionnel (c'est-à-dire un compte Azure Active Directory) ou le compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer à en tant qu’invité dans les équipes, avec un accès complet aux équipes et une expérience de canal.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="5d3b8-126">(Vous pouvez en savoir plus sur les restrictions invité dans [Autoriser l’accès invité dans les équipes Microsoft](teams-dependencies.md).) Tous les invités dans les équipes sont couverts par la même conformité et audit protection en tant que le reste d’Office 365 et peuvent être gérées de manière sécurisée dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="5d3b8-127">Pourquoi utiliser l’accès invité ?</span><span class="sxs-lookup"><span data-stu-id="5d3b8-127">Why use guest access?</span></span>
      
<span data-ttu-id="5d3b8-128">Avec l’accès invité, les organisations qui utilisent les équipes peuvent fournir un accès externe pour les équipes, des documents dans des canaux, ressources, des conversations et des applications à leurs partenaires, tout en conservant le contrôle total sur leurs propres données d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="5d3b8-129">Tous les invités dans les équipes sont couverts par la même conformité et audit protection en tant que le reste d’Office 365 et les invités peuvent être gérées de manière sécurisée dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="5d3b8-130">Les équipes repose sur les groupes d’Office 365 et fournit une nouvelle façon d’accéder aux ressources partagées d’un groupe d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="5d3b8-131">Teams est la meilleure solution de conversation permanente parmi les membres d'un groupe ou d'une équipe.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="5d3b8-132">Les groupes Office 365 sont un service disponible sous la forme d'un abonnement inter-applications qui donne accès à un ensemble de ressources partagées, telles qu'un site SharePoint ou un tableau de bord Power BI, pour permettre à l'équipe de collaborer efficacement et en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="5d3b8-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="5d3b8-133">Comment s’accès invité par rapport à l’accès externe (fédération) ?</span><span class="sxs-lookup"><span data-stu-id="5d3b8-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="5d3b8-134">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="5d3b8-134">More information</span></span>
    
[<span data-ttu-id="5d3b8-135">Ressources de support pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d3b8-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="5d3b8-136">Accès invité dans Office 365 groupes</span><span class="sxs-lookup"><span data-stu-id="5d3b8-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="5d3b8-137">Présentation de l’accès invité à</span><span class="sxs-lookup"><span data-stu-id="5d3b8-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="5d3b8-138">Examiner l’accès invité en détail</span><span class="sxs-lookup"><span data-stu-id="5d3b8-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="5d3b8-139">Ajout d’invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d3b8-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

