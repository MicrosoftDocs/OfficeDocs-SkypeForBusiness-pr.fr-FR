---
title: Authentification basée sur l’application dans le module PowerShell Teams
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez l’authentification basée sur l’application dans le module PowerShell Teams, utilisé pour l’administration de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89af4494a6cf20aab512c0430a6e16db622e53a2
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912643"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Authentification basée sur l’application dans le module PowerShell Teams

L’authentification basée sur l’application est désormais prise en charge dans le module PowerShell Teams en préversion avec les versions 4.7.1-preview ou ultérieures. Actuellement, ce mode d’authentification n’est pris en charge que dans les environnements commerciaux.


## <a name="cmdlets-supported"></a>Applets de commande prises en charge

Toutes les applets de commande sont désormais prises en charge, à l’exception des applets de commande mentionnées ci-dessous. 

  - New-Team
  - [Get| Défini| Nouveau| Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>Exemples

Les exemples suivants montrent comment utiliser le module PowerShell Teams avec l’authentification basée sur l’application Azure AD : 

- Se connecter à l’aide d’une empreinte numérique de certificat :

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Lorsque vous utilisez le paramètre CertificateThumbprint, le certificat doit être installé sur l’ordinateur sur lequel vous exécutez la commande. Le certificat doit être installé dans le magasin de certificats utilisateur.
  
- Se connecter à l’aide de jetons d’accès :
  
  Les jetons d’accès peuvent être récupérés via le point de terminaison login.microsoftonline.com. Il nécessite deux jetons d’accès : les ressources « MS Graph » et « API Administration client Skype et Teams ».

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>Comment cela fonctionne-t-il ?

Le module PowerShell Teams récupère le jeton basé sur l’application à l’aide de l’ID d’application, de l’ID de locataire et de l’empreinte numérique du certificat. Un rôle d’annuaire est attribué à l’objet d’application approvisionné dans Azure AD, qui est retourné dans le jeton d’accès. Le contrôle d’accès en fonction du rôle (RBAC) de la session est configuré à l’aide des informations de rôle d’annuaire disponibles dans le jeton.


## <a name="setup-application-based-authentication"></a>Configurer l’authentification basée sur l’application

Une intégration initiale est requise pour l’authentification à l’aide d’objets d’application. L’application et le principal de service sont utilisés indifféremment, mais une application est comme un objet de classe, tandis qu’un principal de service est comme une instance de la classe . Pour en savoir plus sur ces objets, consultez [Application et objets de principal de service dans Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Les exemples d’étapes de création d’applications dans Azure Ad sont mentionnés ci-dessous. Pour plus d’informations, consultez cet [article](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Inscrire l’application dans Azure AD
2. Attribuer des autorisations d’API à l’application
   - Pour \*les applets de commande -Cs, aucune autorisation d’API n’est nécessaire.
   - Pour les applets de commande Non-Cs\*, les autorisations microsoft API Graph nécessaires sont `User.Read.All`, `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, `ChannelSettings.ReadWrite.All``ChannelMember.ReadWrite.All`, , .  
3. Générer un certificat auto-signé
4. Attacher le certificat à l’application Azure AD
5. Attribuer [des rôles Azure AD](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) à l’application

Les rôles RBAC appropriés doivent être attribués à l’application. Étant donné que les applications sont approvisionnées dans Azure AD, vous pouvez utiliser n’importe lequel des rôles intégrés pris en charge.
 
