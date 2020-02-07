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
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Utiliser PowerShell pour contrôler l'accès invité à une équipe
================================================

Outre l’utilisation du centre d’administration Microsoft 365 et du portail Azure Active Directory (Azure AD), vous pouvez utiliser Windows PowerShell pour contrôler l’accès invité. PowerShell permet d'effectuer les opérations suivantes :
  
- Autoriser ou bloquer l’accès invité à toutes les équipes et tous les groupes Office 365

- Autoriser les invités à être ajoutés à toutes les équipes et tous les groupes Office 365

- Autoriser ou bloquer les utilisateurs invités d'une équipe ou d'un groupe Office 365 spécifique

Pour plus d’informations, consultez la section « utiliser PowerShell pour contrôler l’accès invité » dans [gérer l’accès invité dans les groupes Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).

  
Vous pouvez également utiliser PowerShell pour autoriser ou bloquer un utilisateur invité en fonction de son domaine. Par exemple, votre entreprise, Contoso, a un partenariat avec une autre entreprise, Fabrikam. Vous pouvez ajouter Fabrikam à votre liste d'invités autorisés afin que vos utilisateurs puissent l'ajouter à leurs groupes. Pour plus d’informations, voir [autoriser ou bloquer l’accès invité aux groupes Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Si vous souhaitez bloquer les invités dans Microsoft teams et que vous souhaitez quand même leur permettre d’accéder à des sites SharePoint, vous pouvez utiliser les applets de applet PowerShell Azure AD pour désactiver le paramètre AllowGuestsToAccessGroups sur l’objet entreprise, en partant du principe que le partage externe est activé pour les sites SharePoint. .

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Utiliser PowerShell pour activer ou désactiver l’accès invité

1.  Télécharger le module PowerShell Skype Entreprise Online à partir de https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Connecter une session PowerShell à un point de terminaison Skype Entreprise Online.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Vérifier votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Ensemble CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) défini sur `$True`.

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
Vous pouvez désormais avoir des utilisateurs invités dans Teams pour votre organisation.


## <a name="guest-access-vs-external-access"></a>Accès invité et accès externe

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
