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
ms.openlocfilehash: ae1f3149ca915e2fd5a9ddf59fdb0bfad2be2ca2
ms.sourcegitcommit: a8f6b70fce1b5073f4743f7f413f7ce9fad8ead1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/10/2019
ms.locfileid: "31765148"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="3bf8a-103">Accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3bf8a-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="3bf8a-104">Vue d’ensemble de l’accès invité</span><span class="sxs-lookup"><span data-stu-id="3bf8a-104">Guest access overview</span></span>

<span data-ttu-id="3bf8a-105">L’accès Invité est l’une des fonctions les plus demandées par les clients.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="3bf8a-106">Pour vous tenir au courant de notre progression et nous faire part de vos commentaires :</span><span class="sxs-lookup"><span data-stu-id="3bf8a-106">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>

- <span data-ttu-id="3bf8a-107">Si vous rencontrez des problèmes avec l’accès invité, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3bf8a-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="3bf8a-108">Vous trouverez des informations sur les fonctionnalités à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="3bf8a-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="3bf8a-109">Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="3bf8a-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="3bf8a-110">Partagez votre expérience dans la section Commentaires ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="3bf8a-111">L’accès invité permet aux équipes de votre organisation de collaborer avec des personnes à l’extérieur de votre organisation en leur accordant l'accès aux équipes et aux canaux.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-111">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="3bf8a-112">Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see Guest access in Microsoft Teams.</span></span>

<span data-ttu-id="3bf8a-113">L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education sans demande de licence supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="3bf8a-114">Vous pouvez avoir jusqu'à 5 invités par utilisateur sous licence sur votre client.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="3bf8a-115">Pour plus d’informations sur les licences, voir [le guide de licence de collaboration Azure Active Directory B2B](https://docs.microsoft.com/fr-FR/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="3bf8a-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/fr-FR/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="3bf8a-116">L'accès invité est un paramètre de niveau client dans Microsoft Teams, désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="3bf8a-117">L’accès invité est soumis à Azure AD et aux limites de service Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="3bf8a-118">Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Office 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="3bf8a-119">Pour ces utilisateurs utilisant Teams, un abonnement Office 365 Business Premium, Office 365 Entreprise ou Office 365 éducation doivent leur être attribués.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="3bf8a-120">Qu’est-ce qu’un invité ?</span><span class="sxs-lookup"><span data-stu-id="3bf8a-120">Who is a guest?</span></span>

<span data-ttu-id="3bf8a-121">Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="3bf8a-122">Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="3bf8a-123">Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="3bf8a-124">Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="3bf8a-125">Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès complet à des équipes et des expériences de canal.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="3bf8a-126">(Vous pouvez lire les informations relatives aux restrictions d’invité dans[Autorisation de l’accès invité dans Microsoft Teams](teams-dependencies.md).) Tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs d’Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="3bf8a-127">Pourquoi utiliser l’accès invité?</span><span class="sxs-lookup"><span data-stu-id="3bf8a-127">Why use guest access?</span></span>
      
<span data-ttu-id="3bf8a-128">Grâce à l’accès invité, les organisations qui utilisent Teams peuvent fournir à leurs partenaires un accès externe aux équipes, documents dans les canaux, ressources, conversations et applications, tout en conservant le contrôle total de leurs propres données d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-128">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="3bf8a-129">Tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs d’Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="3bf8a-130">Teams est basé sur les Groupes Office 365 et offre un nouveau moyen pour accéder aux ressources partagées d'un groupe Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-130">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="3bf8a-131">Teams est la meilleure solution de conversation permanente parmi les membres d'un groupe ou d'une équipe.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="3bf8a-132">Les groupes Office 365 sont un service disponible sous la forme d'un abonnement inter-applications qui donne accès à un ensemble de ressources partagées, telles qu'un site SharePoint ou un tableau de bord Power BI, pour permettre à l'équipe de collaborer efficacement et en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="3bf8a-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="3bf8a-133">Quelle est l’accès invité et quel est l’accès externe (fédération) ?</span><span class="sxs-lookup"><span data-stu-id="3bf8a-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="3bf8a-134">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="3bf8a-134">More information</span></span>
    
[<span data-ttu-id="3bf8a-135">Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur</span><span class="sxs-lookup"><span data-stu-id="3bf8a-135">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
<span data-ttu-id="3bf8a-136">
  [Accès invité dans les Groupes Office 365](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span><span class="sxs-lookup"><span data-stu-id="3bf8a-136">[Guest access in Office 365 Groups](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span></span> 
  
|  |  |
|---------|---------|
|<span data-ttu-id="3bf8a-137">Présentation de l’accès invité</span><span class="sxs-lookup"><span data-stu-id="3bf8a-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="3bf8a-138">Présentation détaillée de l'accès invité</span><span class="sxs-lookup"><span data-stu-id="3bf8a-138">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="3bf8a-139">Ajout d'invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3bf8a-139">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

