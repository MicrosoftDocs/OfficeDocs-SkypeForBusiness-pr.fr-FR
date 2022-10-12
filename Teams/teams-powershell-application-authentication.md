---
title: Authentification basée sur l’application dans le module Teams PowerShell
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez l’authentification basée sur l’application dans le module Teams PowerShell, utilisé pour l’administration de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8dd4b230f7f22feb574463a96d4a4447bcf0cfb0
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532494"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Authentification basée sur l’application dans le module Teams PowerShell

L’authentification basée sur l’application est désormais prise en charge dans le module Teams PowerShell pour un ensemble limité d’applets de commande en préversion avec les versions 4.7.1-preview ou ultérieures. Actuellement, ce mode d’authentification est uniquement pris en charge dans les environnements commerciaux.


## <a name="cmdlets-supported"></a>Applets de commande prises en charge

Les applets de commande ci-dessous sont déjà prises en charge, d’autres applets de commande seront déployées progressivement. 

  - Applets de commande non-CS \*(par exemple, Get-Team)
  - Get-CsTenant
  - Get-CsOnlineUser, Get-CsOnlineVoiceUser
  - \*-CsOnlineSipDomain 
  - \*-CsPhoneNumberAssignment
  - \*-CsOnlineTelephoneNumberOrder, Get-CsOnlineTelephoneNumberType, Get-CsOnlineTelephoneNumberCountry
  - \*-CsCallQueue
  - \*-CsAutoAttendant, \*-CsAutoAttendant\*
  - \*-CsOnlineVoicemailUserSettings
  - Find-CsOnlineApplicationInstance, \*-CsOnlineApplicationInstanceAssociation, Get-CsOnlineApplicationInstanceAssociationStatus
  - \*-CsOnlineSchedule, New-CsOnlineTimeRange, New-CsOnlineDateTimeRange
  - \*-CsOnlineAudioFile
  - Find-CsGroup
  - \*-CsOnlineDialInConferencingUser, \*-CsOnlineDialInConferencingServiceNumber, \*-CsOnlineDialInConferencingBridge, Get-CsOnlineDialInConferencingLanguagesSupported, Set-CsOnlineDialInConferencingUserDefaultNumber
  - \*-CsOnlineLisLocation, \*-CsOnlineLisCivicAddress, \*-CsOnlineLisWirelessAccessPoint, \*-CsOnlineLisPort, \*-CsOnlineLisSubnet, \*-CsOnlineEnhancedEmergencyServiceDisclaimer, \*-CsOnlineLisSwitch


## <a name="examples"></a>Exemples

Les exemples suivants montrent comment utiliser le module Teams PowerShell avec l’authentification basée sur l’application Azure AD : 

- Connectez-vous à l’aide d’une empreinte numérique de certificat :

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Lorsque vous utilisez le paramètre CertificateThumbprint, le certificat doit être installé sur l’ordinateur sur lequel vous exécutez la commande. Le certificat doit être installé dans le magasin de certificats utilisateur.
  
- Connectez-vous à l’aide de jetons d’accès :
  
  Les jetons d’accès peuvent être récupérés via le point de terminaison login.microsoftonline.com. Il nécessite deux jetons d’accès : les ressources « MS Graph » et « Skype et Teams Tenant Administration API ».

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
  
## <a name="how-does-it-work"></a>Comment fonctionne-t-il ?

Le module Teams PowerShell extrait le jeton basé sur l’application à l’aide de l’ID d’application, de l’ID de locataire et de l’empreinte du certificat. L’objet d’application provisionné à l’intérieur d’Azure AD est doté d’un rôle d’annuaire, qui est retourné dans le jeton d’accès. Le contrôle d’accès en fonction du rôle (RBAC) de la session est configuré à l’aide des informations de rôle d’annuaire disponibles dans le jeton.


## <a name="setup-application-based-authentication"></a>Configurer l’authentification basée sur l’application

Une intégration initiale est requise pour l’authentification à l’aide d’objets d’application. L’application et le principal de service sont utilisés indifféremment, mais une application est comme un objet de classe tandis qu’un principal de service est comme une instance de la classe. Vous pouvez en savoir plus sur ces objets sur les [objets application et principal de service dans Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Les exemples d’étapes de création d’applications dans Azure Ad sont mentionnés ci-dessous. Pour plus d’informations, reportez-vous à cet [article](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Inscrire l’application dans Azure AD
2. Attribuer des autorisations d’API à l’application
   - Pour \*les applets de commande -Cs , aucune autorisation d’API n’est nécessaire.
   - Pour les applets de commande non-Cs \*, les autorisations Microsoft API Graph nécessaires sont `User.Read.All`, , `Group.ReadWrite.All``AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All``Channel.Delete.All`, `ChannelSettings.ReadWrite.All``ChannelMember.ReadWrite.All`.  
3. Générer un certificat auto-signé
4. Attacher le certificat à l’application Azure AD
5. Attribuer des [rôles Azure AD](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) à l’application

Les rôles RBAC appropriés doivent être attribués à l’application. Étant donné que les applications sont approvisionnées dans Azure AD, vous pouvez utiliser l’un des rôles intégrés pris en charge.
 
