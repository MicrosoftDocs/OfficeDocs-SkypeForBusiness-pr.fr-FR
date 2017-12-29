---
title: "Utiliser PowerShell pour contrôler l'accès invité à une équipe"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Utilisez PowerShell pour autoriser ou bloquer l'accès invité aux équipes dans Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 0e087aadced6980db80890f423e3e6e3c4b7a701
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="1fb4a-103">Utiliser PowerShell pour contrôler l'accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="1fb4a-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="1fb4a-104">En plus d'utiliser le Centre d'administration d'Office 365 et le portail d'Azure Active Directory, vous pouvez utiliser Windows PowerShell pour contrôler l'accès invité.</span><span class="sxs-lookup"><span data-stu-id="1fb4a-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="1fb4a-105">PowerShell permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fb4a-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="1fb4a-106">Autoriser ou bloquer l'accès invité à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="1fb4a-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="1fb4a-107">Autoriser l'ajout d'invités à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="1fb4a-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="1fb4a-108">Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique</span><span class="sxs-lookup"><span data-stu-id="1fb4a-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="1fb4a-109">Pour en savoir plus, consultez la section Utiliser PowerShell pour contrôler l'accès invité, dans l'onglet Gérer de l'[accès invité dans Groupes Office 365](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="1fb4a-109">For more details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="1fb4a-110">Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine.</span><span class="sxs-lookup"><span data-stu-id="1fb4a-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="1fb4a-111">Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1fb4a-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="1fb4a-112">Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes.</span><span class="sxs-lookup"><span data-stu-id="1fb4a-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="1fb4a-113">Pour plus d'informations, reportez-vous à la rubrique [Autoriser/bloquer l'accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="1fb4a-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="1fb4a-114">Si vous souhaitez bloquer l'accès invités dans Teams, mais autoriser les invités à accéder à des sites SharePoint, vous pouvez utiliser des applets de commande PowerShell Azure Active Directory pour désactiver le paramètre AllowGuestAccessToGroups sur l'objet Entreprise, en partant du principe que le partage externe est activé pour les sites SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fb4a-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

