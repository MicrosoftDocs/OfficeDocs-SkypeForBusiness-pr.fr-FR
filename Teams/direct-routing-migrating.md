---
title: Migrer vers un routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Découvrez ce qui est nécessaire pour migrer vers le routage direct à partir d’un point de vue de la configuration d’équipes et de Skype entreprise online.
ms.openlocfilehash: 49980a0364e729fc41e6fe716de336a8a28f85bb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759007"
---
# <a name="migrate-to-direct-routing"></a>Migrer vers un routage direct

Cet article décrit les éléments nécessaires à la migration vers le routage direct à partir d’une perspective de configuration de Skype entreprise Online et Microsoft Teams. Cet article décrit la migration des éléments suivants: 
 
- Système téléphonique Office 365 avec des plans d’appels (pour les équipes et Skype entreprise Online) 
- Système téléphonique Office 365 avec connectivité PSTN locale dans Skype entreprise Server (pour Skype entreprise Online)  
- Système téléphonique Office 365 avec connectivité PSTN locale à l’aide de la version Cloud Connector (pour Skype entreprise Online)

  
Outre ces étapes de configuration, la configuration est également requise sur le contrôleur de bordure de session (SBC) pour acheminer les appels vers le nouvel itinéraire. Hors de l’objectif de ce document. Pour plus d’informations, consultez la documentation de votre fournisseur de SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>État de fin de la mise en service des utilisateurs pour différentes options de connectivité PSTN 

Le tableau suivant indique l’état final d’un utilisateur configuré pour les options de connectivité PSTN sélectionnées avec le système téléphonique Office 365. Seuls les attributs appropriés pour la voix apparaissent.

|Attributs d’objet utilisateur |Système téléphonique avec forfaits d’appels|Système téléphonique avec connectivité PSTN locale via Skype entreprise Server|Système téléphonique avec connectivité PSTN locale via Cloud Connector|Système téléphonique avec connectivité PSTN locale via le routage direct|
|---|---|---|---|---|
|Client|Skype entreprise ou équipes |Skype Entreprise |Skype Entreprise |Teams|
|Autorise|Skype entreprise Online</br>Plan 2</br></br>MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)</br></br></br>Offres d'appels</br>Équipes|Plan 2 de Skype entreprise Online (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)|Plan 2 de Skype entreprise Online (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)|Skype Business Online plan 2 (MCOProfessional ou MCOSTANDARD</br></br></br>Système téléphonique (MCOEV)</br></br>Équipes|
OnPremLineURI |S/O|Le numéro de téléphone doit être synchronisé à partir de la publicité locale. |Le numéro de téléphone peut être géré dans l’environnement Active Directory local ou dans Azure Active Directory.|Le numéro de téléphone peut être géré dans l’environnement Active Directory local ou dans Azure Active Directory. Toutefois, si l’organisation a Skype entreprise locale, le numéro doit être synchronisé à partir de l’Active Directory local.|
|LineURI|Numéro de téléphone d’appel RTC|Définie automatiquement à partir du paramètre OnPremLineURI|Définie automatiquement à partir du paramètre OnPremLineURI|Définie automatiquement à partir du paramètre OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|A une valeur|A une valeur|A une valeur|S/O|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|A une valeur|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly ou îles|$Null|$Null|Îles ou TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient-veuillez lire la remarque ci-dessous.|Teams ou marketing |Marketing|Marketing|Équipes|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|N/A|N/A|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|N/A|N/A|True|
||||||

<sup>1</sup> Le choix du mode approprié du TeamsUpgradePolicy dépend du scénario. Pour plus d’informations sur l’utilisation des fonctionnalités vocales, consultez les différents modes de [migration et d’interopérabilité pour les organisations qui utilisent des équipes dans Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Comme précédemment annoncé, TeamsInteropPolicy sera supprimé (ciblé pour la fin du 3e trimestre) et ses fonctionnalités sont consolidées dans TeamsUpgradePolicy. L’interopérabilité et la migration seront gérées à l’aide du «mode coexistence» déterminé par TeamsUpgradePolicy, qui est désormais disponible. Le fait de sélectionner le mode de l’utilisateur régit à la fois le routage des appels entrants et des discussions, et le client qui peut lancer les discussions et les appels ou planifier des réunions. Tandis que TeamsInteropPolicy sera supprimé, il doit toujours être défini en parallèle avec TeamsUpgradePolicy pendant Phaseout.  

Dans le cadre de cette tâche, Microsoft a récemment mis à jour le «centre d’administration Microsoft Teams» (également appelé portail moderne) pour refléter le nouveau modèle de gestion en fonction des modes de coexistence. Dans le portail moderne, la configuration de TeamsUpgradePolicy définit désormais automatiquement TeamsInteropPolicy sur une valeur cohérente, donc TeamsInteropPolicy n’est plus exposé dans l’interface utilisateur. En revanche, les administrateurs qui utilisent PowerShell doivent toujours définir à la fois TeamsUpgradePolicy et TeamsInteropPolicy pour s’assurer que le routage est approprié. Après la transition vers TeamsUpgradePolicy, il n’est plus nécessaire de définir TeamsInteropPolicy.

Pour plus d’informations, reportez-vous à la rubrique [instructions de migration et d’interopérabilité pour les organisations qui utilisent des équipes dans Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migration des offres d’appels

Pour plus d’informations sur la migration de forfaits d’appels, voir:

- [Configurer des forfaits d'appels](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Utilisateur Set-CsOnlineVoice](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Nous vous recommandons de supprimer les informations de plan de gestion des licences précédemment configurées comme suit:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migration à partir d’un système téléphonique Office 365 avec connectivité PSTN locale dans Skype entreprise Server

Pour plus d’informations sur la migration à partir d’un système téléphonique avec la connectivité PSTN locale dans Skype entreprise Server, voir les rubriques suivantes:

- [Planification](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Déploiement](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Nous vous conseillons de supprimer les informations de routage vocal précédemment configurées comme suit:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migration à partir d’un système téléphonique Office 365 avec une connectivité PSTN locale via la version Cloud Connector 

Pour plus d’informations sur la migration à partir d’un système téléphonique avec la connectivité PSTN locale via Cloud Connector, voir les rubriques suivantes:

- [Planification](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Déploiement](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuration utilisateur](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Nous vous conseillons de supprimer les informations de routage vocal précédemment configurées comme suit:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>LIENS CONNEXES

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Nouveau-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

