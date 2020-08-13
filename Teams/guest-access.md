---
title: Accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: L'accès invité dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures en leur accordant l'accès aux équipes et aux canaux.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67ddc045c04c1c3d8cb9bffa0ee15ebf71c70c2f
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656105"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="8119f-103">Accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8119f-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="8119f-104">L’accès invité vous permet d’ajouter des utilisateurs individuels situés hors de votre organisation à vos équipes et canaux dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8119f-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="8119f-105">Pour comparer l’accès externe (fédération) avec l’accès invité (et décider de celui que vous devez utiliser), lisez [Communiquer avec des utilisateurs d’autres organisations dans Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="8119f-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="8119f-106">Si vous êtes prêt à activer l’accès invité au sein de votre organisation, commencez par le [liste de vérification de l’accès invité](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="8119f-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="8119f-107">Vue d’ensemble de l’accès invité</span><span class="sxs-lookup"><span data-stu-id="8119f-107">Guest access overview</span></span>

<span data-ttu-id="8119f-108">L'accès invité permet aux équipes de votre organisation de collaborer avec des personnes extérieures à votre organisation en leur accordant l'accès aux équipes et aux canaux existants dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8119f-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="8119f-109">Toutes les personnes ayant un compte de messagerie professionnel ou de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams, avec un accès complet aux conversations, réunions et fichiers des équipes.</span><span class="sxs-lookup"><span data-stu-id="8119f-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="8119f-110">En tant qu’administrateur Teams, vous contrôlez les fonctionnalités que les invités peuvent (et ne peuvent pas) utiliser dans les équipes : consultez [Gérer l’accès invité](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="8119f-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="8119f-111">L'accès invité est un paramètre de niveau organisation dans Teams, désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="8119f-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="8119f-112">L’accès invité est soumis à Azure AD et aux limites de service Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="8119f-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8119f-113">Les utilisateurs invités suivent les paramètres de niveau organisation Teams pour le mode de mise à niveau de coexistence.</span><span class="sxs-lookup"><span data-stu-id="8119f-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="8119f-114">Il n’est pas possible de modifier cela.</span><span class="sxs-lookup"><span data-stu-id="8119f-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="8119f-115">Gestion des licences pour l’accès invité</span><span class="sxs-lookup"><span data-stu-id="8119f-115">Licensing for guest access</span></span>

<span data-ttu-id="8119f-116">L’accès invité est inclus dans tous les abonnements Microsoft 365 Business Standard, Office 365 Enterprise et Office 365 Éducation.</span><span class="sxs-lookup"><span data-stu-id="8119f-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="8119f-117">Aucune licence Microsoft 365 ou Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="8119f-117">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="8119f-118">Teams ne limite pas le nombre d’invités que vous pouvez ajouter.</span><span class="sxs-lookup"><span data-stu-id="8119f-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="8119f-119">Cependant, le nombre total d’invités pouvant être ajoutés à votre client peut être limité par les fonctionnalités payantes d’Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8119f-119">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="8119f-120">Pour plus d’informations, consultez l’article [Affectation de licences Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="8119f-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="8119f-121">Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Microsoft 365 ou Office 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation.</span><span class="sxs-lookup"><span data-stu-id="8119f-121">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="8119f-122">Pour que ces utilisateurs puissent utiliser des équipes, une offre Microsoft 365 Business Standard, Office 365 Entreprise ou Office 365 Éducation doivent leur être attribuée.</span><span class="sxs-lookup"><span data-stu-id="8119f-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="8119f-123">Qu’est-ce qu’un invité ?</span><span class="sxs-lookup"><span data-stu-id="8119f-123">Who is a guest?</span></span>

<span data-ttu-id="8119f-124">Un invité est une personne qui n'est ni un employé, ni un étudiant ni un membre de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8119f-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="8119f-125">Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8119f-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="8119f-126">Il peut par exemple s'agir de partenaires, sous-traitants, fournisseurs ou consultants.</span><span class="sxs-lookup"><span data-stu-id="8119f-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="8119f-127">Toute personne qui ne fait pas partie de votre organisation peut être ajouté en tant qu’invité dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8119f-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="8119f-128">Cela signifie que tout le monde avec un compte professionnel (autrement dit, un compte Azure Active Directory) ou un compte de messagerie consommateur (avec Outlook.com, Gmail.com ou d’autres personnes) peut participer en tant qu’invité dans Teams, avec un accès complet à des équipes et des expériences de canal.</span><span class="sxs-lookup"><span data-stu-id="8119f-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="8119f-129">Pour en savoir plus sur ce qu’un invité peut et ne peut pas faire, lisez [Autoriser l’accès invité dans Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="8119f-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="8119f-130">Sinon, consultez le tableau de [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="8119f-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="8119f-131">Finalement, tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs de Microsoft 365 ou Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8119f-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="8119f-132">Pourquoi utiliser l’accès invité?</span><span class="sxs-lookup"><span data-stu-id="8119f-132">Why use guest access?</span></span>

<span data-ttu-id="8119f-133">Grâce à l’accès invité, les organisations qui utilisent Teams peuvent fournir à leurs partenaires un accès aux équipes, documents dans les canaux, ressources, conversations et applications, tout en conservant le contrôle total de leurs propres données d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="8119f-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="8119f-134">Tous les invités dans Teams bénéficient de la même protection en matière de conformité et d’audit que les autres utilisateurs de Microsoft 365 ou Office 365, et les invités peuvent être gérés en toute sécurité dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8119f-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="8119f-135">Comprendre les limitations pour les invités</span><span class="sxs-lookup"><span data-stu-id="8119f-135">Understand the limitations for guests</span></span>

<span data-ttu-id="8119f-136">L’expérience des invités comporte des limitations de par sa conception.</span><span class="sxs-lookup"><span data-stu-id="8119f-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="8119f-137">Assurez-vous de bien comprendre l’expérience des invités de manière à ne pas essayer de résoudre un problème qui n’en est pas un.</span><span class="sxs-lookup"><span data-stu-id="8119f-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="8119f-138">Par exemple, voici une liste de certaines des fonctionnalités qui ne sont pas disponibles pour un invité dans Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="8119f-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="8119f-139">OneDrive Entreprise</span><span class="sxs-lookup"><span data-stu-id="8119f-139">OneDrive for Business</span></span>
- <span data-ttu-id="8119f-140">Recherche de personnes à l’extérieur de Teams</span><span class="sxs-lookup"><span data-stu-id="8119f-140">People search outside of Teams</span></span>
- <span data-ttu-id="8119f-141">Calendrier, réunions planifiées ou détails de la réunion</span><span class="sxs-lookup"><span data-stu-id="8119f-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="8119f-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="8119f-142">PSTN</span></span>
- <span data-ttu-id="8119f-143">Organigramme hiérarchique</span><span class="sxs-lookup"><span data-stu-id="8119f-143">Organization chart</span></span>
- <span data-ttu-id="8119f-144">Créer ou réviser une équipe</span><span class="sxs-lookup"><span data-stu-id="8119f-144">Create or revise a team</span></span>
- <span data-ttu-id="8119f-145">Rechercher une équipe</span><span class="sxs-lookup"><span data-stu-id="8119f-145">Browse for a team</span></span>
- <span data-ttu-id="8119f-146">Télécharger des fichiers dans une conversation de personne à personne</span><span class="sxs-lookup"><span data-stu-id="8119f-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="8119f-147">Pour l’instant, Teams prend uniquement en charge les types d’États 1 et 2 des utilisateurs invités [définis par Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="8119f-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="8119f-148">Pour consulter la liste complète de ce qu’un invité peut et ne peut pas faire dans Teams, voir tableau [comparaison des fonctionnalités des membres d’équipe et des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="8119f-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="8119f-149">Pour en savoir plus sur l’accès invité aux niveaux Microsoft 365 et Office 365, lisez [Ajout d’invités à des groupes Microsoft 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="8119f-149">To learn more about guest access at the Microsoft 365 and Office 365 levels, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="8119f-150">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="8119f-150">More information</span></span>

[<span data-ttu-id="8119f-151">Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur</span><span class="sxs-lookup"><span data-stu-id="8119f-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[<span data-ttu-id="8119f-152">Accès invité dans les Groupes Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8119f-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
