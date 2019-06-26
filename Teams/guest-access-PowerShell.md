---
title: Utiliser PowerShell pour contrôler l'accès invité à une équipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
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
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35220885"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="4900f-103">Utiliser PowerShell pour contrôler l'accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="4900f-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="4900f-104">Outre l’utilisation du centre d’administration Microsoft 365 et du portail Azure Active Directory (Azure AD), vous pouvez utiliser Windows PowerShell pour contrôler l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="4900f-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="4900f-105">PowerShell permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4900f-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="4900f-106">Autoriser ou bloquer l’accès invité à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="4900f-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="4900f-107">Autoriser les invités à être ajoutés à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="4900f-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="4900f-108">Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique</span><span class="sxs-lookup"><span data-stu-id="4900f-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="4900f-109">Pour plus d’informations, consultez la section «utiliser PowerShell pour contrôler l’accès invité» dans [gérer l’accès invité dans les groupes Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="4900f-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="4900f-110">Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine.</span><span class="sxs-lookup"><span data-stu-id="4900f-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="4900f-111">Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="4900f-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="4900f-112">Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes.</span><span class="sxs-lookup"><span data-stu-id="4900f-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="4900f-113">Pour plus d’informations, voir [autoriser ou bloquer l’accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="4900f-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="4900f-114">Si vous souhaitez bloquer les invités dans Microsoft teams et que vous souhaitez quand même leur permettre d’accéder à des sites SharePoint, vous pouvez utiliser les applets de applet PowerShell Azure AD pour désactiver le paramètre AllowGuestsToAccessGroups sur l’objet entreprise, en partant du principe que le partage externe est activé pour les sites SharePoint. .</span><span class="sxs-lookup"><span data-stu-id="4900f-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="4900f-115">Accès invité et accès externe</span><span class="sxs-lookup"><span data-stu-id="4900f-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
