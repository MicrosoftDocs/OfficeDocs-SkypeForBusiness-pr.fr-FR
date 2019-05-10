---
title: Utiliser PowerShell pour contrôler l'accès invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Utilisez PowerShell pour autoriser ou bloquer l'accès invité aux équipes dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ca05e48d28986a944debe150d5dbf25129ca73c
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827668"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="f53a4-103">Utiliser PowerShell pour contrôler l'accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="f53a4-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="f53a4-104">En plus d'utiliser le Centre d'administration d'Office 365 et le portail d'Azure Active Directory, vous pouvez utiliser Windows PowerShell pour contrôler l'accès invité.</span><span class="sxs-lookup"><span data-stu-id="f53a4-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="f53a4-105">PowerShell permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f53a4-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="f53a4-106">Autoriser ou bloquer l'accès invité à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="f53a4-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="f53a4-107">Autoriser l'ajout d'invités à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="f53a4-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="f53a4-108">Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique</span><span class="sxs-lookup"><span data-stu-id="f53a4-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="f53a4-109">Pour plus d’informations, consultez la section « Utilisation de PowerShell pour contrôler l’accès invité » sous l’onglet Gestion de [l’accès invité dans Office 365 groupes](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="f53a4-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="f53a4-110">Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine.</span><span class="sxs-lookup"><span data-stu-id="f53a4-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="f53a4-111">Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="f53a4-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="f53a4-112">Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes.</span><span class="sxs-lookup"><span data-stu-id="f53a4-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="f53a4-113">Pour plus d'informations, reportez-vous à la rubrique [Autoriser/bloquer l'accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="f53a4-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="f53a4-114">Si vous souhaitez bloquer les invités dans les équipes et que vous souhaitez tout de même les autoriser à accéder aux sites SharePoint, vous pouvez utiliser les applets de commande Windows Azure Active Directory Powershell pour désactiver le paramètre AllowGuestsToAccessGroups sur l’objet de la société, en supposant que le partage externe est activé pour Sites SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f53a4-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="f53a4-115">Accès invité et l’accès externe</span><span class="sxs-lookup"><span data-stu-id="f53a4-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
