---
title: "Gérer l'accès invité dans Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: 
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 96113a828d150cd19c54d0c01d7756e5077ef37c
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="1fead-102">Gérer l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1fead-102">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="1fead-103">L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="1fead-103">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="1fead-104">Aucune licence Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="1fead-104">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="1fead-105">L'accès invité de Teams est un paramètre de niveau client et est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="1fead-105">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="1fead-106">Les administrateurs informatiques peuvent ajouter des invités au niveau du client, définir et gérer les stratégies d'utilisateurs invités et les autorisations, déterminer quels utilisateurs peuvent convier des invités et extraire des rapports sur l'activité des utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="1fead-106">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="1fead-107">Ces contrôles sont disponibles via le Centre d'administration d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fead-107">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="1fead-108">Le contenu et les activités des utilisateurs invités font l'objet de la même protection en matière de conformité et de vérification que le reste d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fead-108">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="1fead-109">Le paramètre client de l'accès invité Teams empêche uniquement les invités de se connecter.</span><span class="sxs-lookup"><span data-stu-id="1fead-109">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="1fead-110">Les propriétaires d'équipe pourront convier d'autres invités et ajouter les utilisateurs invités du répertoire existant dans leurs équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="1fead-110">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="1fead-111">Pour rappel, Teams respecte toujours les paramètres externes Azure Active Directory pour permettre ou empêcher l'ajout d'utilisateurs invités au client.</span><span class="sxs-lookup"><span data-stu-id="1fead-111">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="1fead-112">Vous pouvez également utiliser le portail Azure Active Directory pour gérer les invités et leur accès aux ressources Office 365 et Teams.</span><span class="sxs-lookup"><span data-stu-id="1fead-112">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="1fead-113">L'accès invité Teams utilise les fonctionnalités de collaboration entre entreprises (B2B) d'Azure Active Directory comme infrastructure sous-jacente pour stocker les informations relatives aux principes de sécurité telles que les propriétés d'identité, l'appartenance à un groupe et les paramètres d'authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="1fead-113">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="1fead-114">Pour en savoir plus sur Azure Active Directory B2B, reportez-vous aux rubriques [Qu'est-ce que Azure AD B2B Collaboration ?](https://go.microsoft.com/fwlink/p/?linkid=853011) et [Forums aux questions sur Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=853020).</span><span class="sxs-lookup"><span data-stu-id="1fead-114">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  