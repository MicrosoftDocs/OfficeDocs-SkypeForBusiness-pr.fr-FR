---
title: Utiliser PowerShell pour contrôler l'accès invité à une équipe
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment utiliser PowerShell pour autoriser ou bloquer l’accès invité à toutes les équipes ou à certaines équipes dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8a2e23f5c03420c4b0ce644a80e0733f9f69a5
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814333"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Utiliser PowerShell pour contrôler l'accès invité à une équipe
================================================

Outre l’utilisation du centre d’administration Microsoft 365 et du portail Azure Active Directory (Azure AD), vous pouvez utiliser Windows PowerShell pour contrôler l’accès invité. PowerShell permet d'effectuer les opérations suivantes :
  
- Autoriser ou bloquer l’accès invité à toutes les équipes et tous les groupes Microsoft 365

- Autoriser l’ajout d’invités à toutes les équipes et tous les groupes Microsoft 365

- Autoriser ou bloquer les utilisateurs invités d’une équipe ou d’un groupe Microsoft 365 spécifique

Pour plus d’informations, consultez la section « utiliser PowerShell pour contrôler l’accès invité » dans [gérer l’accès invité dans les groupes Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).

  
Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine. Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam. Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes. Pour plus d’informations, consultez [autoriser ou bloquer l’accès invité aux groupes Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Si vous souhaitez bloquer les invités dans Microsoft teams et que vous souhaitez quand même lui permettre d’accéder à des sites SharePoint, vous pouvez utiliser les applets de applet de cmdlet Azure AD PowerShell pour désactiver le paramètre AllowGuestsToAccessGroups sur l’objet entreprise, en partant du principe que le partage externe est activé pour les sites SharePoint.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Utiliser PowerShell pour activer ou désactiver l’accès invité

1.  Télécharger le module PowerShell Skype Entreprise Online à partir de https://www.microsoft.com/download/details.aspx?id=39366
 
2.  Connecter une session PowerShell à un point de terminaison Skype Entreprise Online.

> [!NOTE]
> Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.
>
> Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.

    ```powershell
    Import-Module -Name MicrosoftTeams
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  Vérifier votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Ensemble CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) défini sur `$True`.

    ```powershell
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
Vous pouvez désormais avoir des utilisateurs invités dans Teams pour votre organisation.


## <a name="guest-access-vs-external-access"></a>Accès invité et accès externe

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
