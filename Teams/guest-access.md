---
title: "Accès invité dans Microsoft Teams"
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 318acad5b5f86b99640653a425e0a1841316ee3e
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="fe2c6-103">Accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe2c6-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="fe2c6-104">L’accès invité est une nouvelle fonction dans Teams.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="fe2c6-105">C’est l’une des fonctions les plus demandées par les clients.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="fe2c6-106">Nous y travaillons toujours, pour améliorer ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="fe2c6-107">Pour vous tenir au courant de notre progression et nous faire part de vos commentaires :</span><span class="sxs-lookup"><span data-stu-id="fe2c6-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="fe2c6-108">Si vous rencontrez des problèmes avec l’accès invité, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fe2c6-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="fe2c6-109">Vous trouverez des informations sur les fonctionnalités à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="fe2c6-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="fe2c6-110">Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="fe2c6-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="fe2c6-111">Partagez votre expérience dans la section Commentaires ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="fe2c6-112">L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="fe2c6-113">L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="fe2c6-114">Aucune licence Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-114">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="fe2c6-115">L'accès invité est un paramètre de niveau client dans Microsoft Teams, désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>


<span data-ttu-id="fe2c6-116">Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-116">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="fe2c6-117">Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-117">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="fe2c6-118">Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-118">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="fe2c6-119">Seuls les utilisateurs disposant d'une adresse de messagerie correspondant à un compte scolaire ou professionnel Azure Active Directory ou Office 365 peuvent être ajoutés en tant qu'utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-119">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
       

<span data-ttu-id="fe2c6-120">Les organisations qui utilisent Teams peuvent fournir à leurs partenaires un accès externe aux équipes, documents dans les canaux, ressources, conversations et applications, tout en conservant le contrôle total de leurs propres données d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-120">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>

<span data-ttu-id="fe2c6-121">Teams est basé sur les groupes Office 365 et offre un nouveau moyen pour accéder aux ressources partagées d'un groupe Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-121">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="fe2c6-122">Teams est la meilleure solution de conversation permanente parmi les membres d'un groupe ou d'une équipe.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-122">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="fe2c6-123">Les groupes Office 365 sont un service disponible sous la forme d'un abonnement inter-applications qui donne accès à un ensemble de ressources partagées, telles qu'un site SharePoint ou un tableau de bord Power BI, pour permettre à l'équipe de collaborer efficacement et en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="fe2c6-123">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="fe2c6-124">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="fe2c6-124">More information</span></span>

 
  
    
  [<span data-ttu-id="fe2c6-125">Ressources de support pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe2c6-125">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="fe2c6-126">Présentation détaillée de l'accès invité</span><span class="sxs-lookup"><span data-stu-id="fe2c6-126">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="fe2c6-127">Activation de l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe2c6-127">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="fe2c6-128">Ajout d'invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe2c6-128">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

