---
title: Migrer vers un routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez les éléments nécessaires pour migrer vers un routage direct à partir d’une perspective de configuration Skype Entreprise Online et Teams.
ms.openlocfilehash: 71776c18dc6ec802c19f9dfc94c51b2b714bc210
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599749"
---
# <a name="migrate-to-direct-routing"></a>Migrer vers un routage direct

Cet article décrit les éléments nécessaires pour migrer vers un routage direct à partir d’une perspective de configuration Skype Entreprise Online et Microsoft Teams. Cet article décrit la migration à partir des éléments suivants : 
 
- Système téléphonique des forfaits d’appels (Teams et Skype Entreprise Online) 
- Système téléphonique avec connectivité PSTN en local dans Skype Entreprise Server (Skype Entreprise Online)  
- Système téléphonique la connectivité PSTN en local à l’aide de la version Cloud Connector (Skype Entreprise Online)


En plus de ces étapes de configuration, la configuration est également requise sur le contrôleur de frontière de session (SBC) pour acheminer les appels vers le nouvel itinéraire. Cet élément n’est pas abordé dans ce document. Pour plus d'informations, consultez la documentation du fournisseur du contrôleur SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>État final de l’attribution d’utilisateurs pour différentes options de connectivité PSTN 

Le tableau suivant indique l’état de fin d’un utilisateur approvisionnement pour les options de connectivité PSTN sélectionnées avec Système téléphonique. Seuls les attributs concernant la voix sont affichés.

|Attributs d’objet utilisateur |Système téléphonique avec forfaits d’appels|Système téléphonique avec une connectivité PSTN en local via Skype Entreprise Server|Système téléphonique avec une connectivité PSTN via Cloud Connector|Système téléphonique avec une connectivité PSTN par routage direct|
|---|---|---|---|---|
|Client|Skype Entreprise ou Teams |Skype Entreprise |Skype Entreprise |Teams|
|Licences|Skype Entreprise Online</br>Plan 2</br></br>MCOProfessional ou MCOSTANDARD</br></br></br>Système téléphonique (MCOEV)</br></br></br>Forfaits d’appels</br>Teams|Plan Skype Entreprise Online 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)|Plan Skype Entreprise Online 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)|Plan Skype Entreprise Online 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)</br></br>Teams|
OnPremLineURI |S/O|Le numéro de téléphone doit être synchronisé à partir du service AD local. |Le numéro de téléphone peut être géré à partir d’un service Active Directory local ou d’Azure Active Directory.|Le numéro de téléphone peut être géré à partir d’un service Active Directory local ou d’Azure Active Directory. Toutefois, si l’organisation utilise Skype Entreprise en local, le numéro doit être synchronisé à partir du service Active Directory local.|
|LineURI|Numéro de téléphone d’appel PSTN|Défini automatiquement à partir du paramètre OnPremLineURI|Défini automatiquement à partir du paramètre OnPremLineURI|Défini automatiquement à partir du paramètre OnPremLineURI|
|EnterpriseVoiceEnabled|Vrai|Vrai|Vrai|Vrai|
|HostedVoiceMail |Vrai|Vrai|Vrai|Vrai|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|A une valeur|A une valeur|A une valeur|S/O|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|A une valeur|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|Vrai|N/D|N/D|Vrai|
|TeamsCallingPolicy</br>AllowGroupCalling|Vrai|N/D|N/D|Vrai|
||||||

<sup>1</sup> Choisir le mode idéal pour TeamsUpgradePolicy dépend du scénario. Renseignez-vous sur l’expérience de la voix dans le [Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md).

Dans le cadre de cet effort, Microsoft a récemment mis à jour le « centre d’administration Microsoft Teams » (également connu sous le nom de portail moderne) pour refléter le nouveau modèle de gestion sur la base des modes de coexistence. Dans le portail moderne, la configuration de TeamsUpgradePolicy définira désormais aussi automatiquement TeamsInteropPolicy sur une valeur cohérente. Par conséquent, TeamsInteropPolicy n’est plus exposé dans l’interface utilisateur. Cependant, les administrateurs utilisant PowerShell doivent continuer à utiliser conjointement TeamsUpgradePolicy et TeamsInteropPolicy pour assurer un routage correct. Une fois la transition vers TeamsUpgradePolicy terminée, il n’est plus nécessaire de configurer TeamsInteropPolicy.

Pour plus d’informations, voir [Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migration à partir de forfaits d’appels

Pour plus d'informations sur la migration à partir de forfaits d’appels, voir :

- [Configurer des forfaits d'appels](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Utilisateur Set-CsOnlineVoice](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Nous vous recommandons de supprimer les informations d’offre de licences précédemment configurées comme suit :
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migration à partir du système téléphonique Office 365 avec une connectivité PSTN en local dans Skype Entreprise Server

Pour plus d’informations sur la migration à partir du système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server, voir :

- [Planification](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Déploiement](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Nous vous recommandons de supprimer les informations sur le routage des communications vocales précédemment configurées comme suit :

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> Si un CsVoiceRoutingPolicy global est configuré, il est recommandé de supprimer les utilisations PSTN associées à cette stratégie globale. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migration à partir du système téléphonique Office 365 avec une connectivité PSTN en local via Cloud Connector Edition 

> [!Important]
> La version Cloud Connector prendra fin le 31 juillet 2021 en même temps que Skype Entreprise Online. Une fois la mise à niveau vers Teams organisation, découvrez comment connecter votre réseau téléphonique local à Teams’aide du [routage direct.](direct-routing-landing-page.md)

Pour plus d’informations sur la migration à partir du système téléphonique avec une connectivité PSTN en local via Cloud Connector, voir :

- [Planification](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Déploiement](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuration utilisateur](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Nous vous recommandons de supprimer les informations sur le routage des communications vocales précédemment configurées comme suit :
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)