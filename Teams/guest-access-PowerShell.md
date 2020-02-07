---
title: Utiliser PowerShell pour contrôler l'accès invité à une équipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Utilisez PowerShell pour autoriser ou bloquer l'accès invité aux équipes dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c91d64973c97ce358741874ba45c1d6338915264
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834024"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="f21ef-103">Utiliser PowerShell pour contrôler l'accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="f21ef-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="f21ef-104">Outre l’utilisation du centre d’administration Microsoft 365 et du portail Azure Active Directory (Azure AD), vous pouvez utiliser Windows PowerShell pour contrôler l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="f21ef-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="f21ef-105">PowerShell permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f21ef-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="f21ef-106">Autoriser ou bloquer l’accès invité à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="f21ef-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="f21ef-107">Autoriser les invités à être ajoutés à toutes les équipes et tous les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="f21ef-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="f21ef-108">Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique</span><span class="sxs-lookup"><span data-stu-id="f21ef-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="f21ef-109">Pour plus d’informations, consultez la section « utiliser PowerShell pour contrôler l’accès invité » dans [gérer l’accès invité dans les groupes Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="f21ef-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>

  
<span data-ttu-id="f21ef-110">Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine.</span><span class="sxs-lookup"><span data-stu-id="f21ef-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="f21ef-111">Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="f21ef-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="f21ef-112">Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes.</span><span class="sxs-lookup"><span data-stu-id="f21ef-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="f21ef-113">Pour plus d’informations, voir [autoriser ou bloquer l’accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="f21ef-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="f21ef-114">Si vous souhaitez bloquer les invités dans Microsoft teams et que vous souhaitez quand même leur permettre d’accéder à des sites SharePoint, vous pouvez utiliser les applets de applet PowerShell Azure AD pour désactiver le paramètre AllowGuestsToAccessGroups sur l’objet entreprise, en partant du principe que le partage externe est activé pour les sites SharePoint. .</span><span class="sxs-lookup"><span data-stu-id="f21ef-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="f21ef-115">Utiliser PowerShell pour activer ou désactiver l’accès invité</span><span class="sxs-lookup"><span data-stu-id="f21ef-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="f21ef-116">Télécharger le module PowerShell Skype Entreprise Online à partir de https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="f21ef-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="f21ef-117">Connecter une session PowerShell à un point de terminaison Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="f21ef-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="f21ef-118">Vérifier votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Ensemble CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) défini sur `$True`.</span><span class="sxs-lookup"><span data-stu-id="f21ef-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```PowerShell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="f21ef-119">Vous pouvez désormais avoir des utilisateurs invités dans Teams pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f21ef-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="f21ef-120">Accès invité et accès externe</span><span class="sxs-lookup"><span data-stu-id="f21ef-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
