---
title: Module PowerShell Teams - Versions prises en charge
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez les versions prises en charge du module Teams PowerShell, utilisées pour l’administration de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 175d9785cd32d18db7eebd363d08840538baa0df
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819549"
---
# <a name="teams-powershell-module---supported-versions"></a>Module PowerShell Teams - Versions prises en charge

Les versions du module PowerShell Microsoft Teams (TPM) de la série 4.x.x ou ultérieures sont les seules versions prises en charge à l’heure actuelle. Toutes les versions antérieures sont entièrement mises hors service depuis le 15 juin 2022 & cesseront de fonctionner (billet du Centre de messages pour référence - MC350371). 

Il est recommandé de mettre à jour vers la dernière version du module Teams PowerShell.


## <a name="important-notes"></a>Remarques importantes

- Les notes de publication de toutes les versions du module Teams PowerShell sont disponibles dans les [notes de publication de Teams PowerShell](teams-powershell-release-notes.md).

- Pour mettre à jour un module PowerShell, vous devez utiliser la même méthode que celle utilisée pour installer le module. Par exemple, si vous avez utilisé Install-Module à l’origine, vous devez utiliser [Update-Module](/powershell/module/powershellget/update-module) pour obtenir la dernière version.

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Si vous effectuez une mise à jour à partir du module Teams PowerShell version 1.1.6, mettez à jour vos scripts à utiliser `Connect-MicrosoftTeams` au lieu de `New-CsOnlineSession`.

- Pendant la mise à jour, il est suggéré de ne pas utiliser TPM 4.x.x/3.x.x aux côtés des versions antérieures à 3.0.0. Par exemple, il n’est pas recommandé d’utiliser les versions 4.x.x & 2.6.0 ensemble pour différentes opérations d’administration dans la même organisation.

- Modifications associées
  - Mises à jour à Get-CsOnlineUser & Get-CsOnlineVoiceUser dans TPM 3.x.x et versions ultérieures : plus d’informations dans [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (billet du Centre de messages – MC340774).

  - Modifications apportées à l’attribution de numéros de téléphone : plus de détails dans [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (message center post – MC316139).

  - Modifications des paramètres dans Get-CsTenant : plus d’informations dans [Get-CsTenant](/powershell/module/skype/get-cstenant) (billet du centre de messages – MC365397).
  
  - Si vos scripts utilisent des applets de commande New/Set of Policy ou Configuration avec des paramètres de type PSListModifier, il est recommandé d’utiliser la dernière version (4.2.0 ou ultérieure). Message center post for reference - MC397428.

- Lors de l’utilisation de TPM 4.x.x ou version ultérieure, il est recommandé de ne pas utiliser les applets de commande déconseillées ou non prises en charge mentionnées [ci-dessous](#deprecated-cmdlets).

## <a name="deprecated-cmdlets"></a>Applets de commande déconseillées

- Certaines des applets de commande qui ont été dépréciées récemment sont répertoriées ci-dessous. Vous trouverez des détails sur la même chose dans les documentations publiques correspondantes.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint), Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- Les applets de commande qui ne sont pas prises en charge/pertinentes pour les scénarios Microsoft Teams sont répertoriées ci-dessous.
  - [Obtenir| Set]-CsUserPstnSettings
  - [Obtenir| Set| Activer| Désactiver]-CsMeetingRoom
  - [Grant| | Set| Nouveau| Remove]-CsConferencingPolicy
  - [Grant| | Set| Nouveau| Remove]-CsClientPolicy
  - [Grant| Get]-CsHostedVoicemailPolicy
  - [Grant| | Set| Nouveau| Remove]-CsMobilityPolicy
  - [Grant| Get]-CsVoiceRoutingPolicy
  - [Grant| Get]-CsBroadcastMeetingPolicy
  - [Grant| Get]-CsCloudMeetingPolicy
  - [Grant| Get]-CsGraphPolicy
  - [Grant| | Set| Nouveau| Remove]-CsExternalUserCommunicationPolicy
  - [Grant| | Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Obtenir| Set]-CsBroadcastMeetingConfiguration
  - [Obtenir| Set]-CsOAuthConfiguration
  - [Obtenir| Set]-CsMeetingConfiguration
  - [Obtenir| Set]-CsTenantHybridConfiguration
  - [Obtenir| Set]-CsPushNotificationConfiguration
  - [Obtenir| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Obtenir| Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Obtenir| Set| Inscrivez-vous| Annuler l’inscription]-CsHybridPSTNAppliance
  - [Obtenir| Set| Nouveau| Remove]-CsHybridPSTNSite
  - [Obtenir| Set]-CsHybridMediationServer
  - [Obtenir| Set| Nouveau| Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Obtenir| Set| Nouveau| Remove]-CsTeamsPinnedApp
  - [Obtenir| Set| Nouveau| Remove]-CsTenantCatalogApp
  - [Obtenir| Set| Nouveau| Remove]-CsGlobalCatalogApp
  - [Obtenir| Set| Nouveau| Remove]-CsDefaultCatalogApp
  - [Obtenir| Set| Nouveau| Remove]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Obtenir| Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>Rubriques connexes

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Informations de référence sur les applets de commande Microsoft Teams](/powershell/module/teams)

[référence de l’applet de commande Skype Entreprise](/powershell/module/skype)
