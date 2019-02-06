---
title: Migration vers le routage Direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Découvrez ce qui est nécessaire pour migrer vers routage Direct à partir d’un Skype pour Business en ligne et la perspective de configuration d’équipes.
ms.openlocfilehash: 4aeb9a2a2ba1bc8398896b2040276f08658194f5
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754470"
---
# <a name="migrating-to-direct-routing"></a>Migration vers le routage Direct

Cet article décrit ce qui est nécessaire pour migrer vers routage Direct à partir d’un Skype pour Business Online et Microsoft Teams perspective de configuration. Cet article traite de la migration à partir de la commande suivante : 
 
- Plans de système téléphonique de Office 365 avec l’appel (pour les équipes et Skype pour les entreprises en ligne) 
- Système de téléphone d’Office 365 avec une connectivité PSTN local dans Skype pour Business Server (Skype pour les entreprises en ligne)  
- Système de téléphone d’Office 365 avec une connectivité PSTN sur site à l’aide de l’édition de connecteur dans le nuage (pour Skype pour Business Online)

  
Outre ces étapes de configuration, configuration est également requis sur le contrôleur de Session en périphérie (SBC) pour acheminer les appels vers le nouvel itinéraire. Qui est en dehors de l’étendue de ce document. Pour plus d’informations, voir la documentation de votre fournisseur SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Utilisateur de mise en service d’état final des diverses options de connectivité PSTN 

Le tableau suivant indique l’état de fin d’un utilisateur mis en service pour les options de connectivité PSTN sélectionnées avec Office 365 Phone System. Seuls les attributs pertinents pour voice sont présentés.

|Attributs d’objet utilisateur |Système téléphonique avec forfaits d’appels|Téléphone système localement avec une connectivité PSTN via Skype pour Business Server|Système de téléphone localement avec une connectivité PSTN via le connecteur sur le nuage|Système de téléphone localement avec une connectivité PSTN via le routage Direct|
|---|---|---|---|---|
|Client|Skype pour les équipes ou de l’entreprise |Skype Entreprise |Skype Entreprise |Teams|
|Licences|Activité Skype en ligne</br>Plan 2</br></br>MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)</br></br></br>Offres d'appels</br>Équipes|Skype Business Online Plan 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)|Skype Business Online Plan 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Système téléphonique (MCOEV)|Skype Business Online Plan 2 (MCOProfessional ou MCOSTANDARD</br></br></br>Système téléphonique (MCOEV)</br></br>Équipes|
OnPremLineURI |N/A|Le numéro de téléphone doit être synchronisé depuis le site Active Directory. |Le numéro de téléphone peut être géré dans Active Directory de locale ou dans Azure Active Directory.|Le numéro de téléphone peut être géré dans Active Directory de locale ou dans Azure Active Directory. Toutefois, si l’organisation a Skype sur site pour les entreprises, le nombre doit être synchronisé à partir d’Active Directory local.|
|LineURI|Numéro de téléphone PSTN appelant|Définir automatiquement à partir du paramètre OnPremLineURI|Définir automatiquement à partir du paramètre OnPremLineURI|Définir automatiquement à partir du paramètre OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|A la valeur|A la valeur|A la valeur|N/A|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|A la valeur|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly ou (îles)|$Null|$Null|Îles ou TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient – Veuillez lire la Remarque ci-dessous.|Des équipes ou SfB |SfB|SfB|Équipes|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|N/A|N/A|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|N/A|N/A|True|
||||||

<sup>1</sup> Choix du mode de droite de la TeamsUpgradePolicy dépend du scénario. Veuillez lire sur l’expérience de voix dans différents modes de [Migration et interopérabilité des instructions pour les organisations](migration-interop-guidance-for-teams-with-skype.md)à l’aide d’équipes avec Skype pour les entreprises.

<sup>2</sup> Comme précédemment annoncé, TeamsInteropPolicy retirer (ciblé pour la fin de T3), et ses fonctionnalités sont consolidées dans TeamsUpgradePolicy. Interopérabilité et la migration sont gérés à l’aide du mode « coexistence » tel que déterminé par TeamsUpgradePolicy, qui est désormais disponible. Sélection du mode de l’utilisateur est déterminants de routage des conversations et les appels entrants et dans le client que l’utilisateur peut démarrer des conversations et les appels ou planifier des réunions. Tandis que TeamsInteropPolicy sera supprimé, il doit être défini en parallèle avec TeamsUpgradePolicy pendant la phaseout.  

Dans le cadre de cette initiative, Microsoft récemment mis à jour le « centre d’administration Microsoft Teams » (également appelé portail moderne) pour refléter le nouveau modèle de gestion basé sur les modes de coexistence. Dans le portail moderne, configuration TeamsUpgradePolicy vont désormais automatiquement également affecter TeamsInteropPolicy valeur cohérente, afin que TeamsInteropPolicy est n’est plus exposé dans l’interface utilisateur. Toutefois, les administrateurs à l’aide de PowerShell doit toujours définir à la fois TeamsUpgradePolicy et TeamsInteropPolicy pour garantir un routage correct. Une fois la transition vers TeamsUpgradePolicy terminée, il ne sera plus nécessaire de définir également TeamsInteropPolicy.

Pour plus d’informations, reportez-vous à la [Migration et interopérabilité des instructions pour les organisations à l’aide des équipes avec Skype pour les entreprises](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migration à partir de Plans d’appel

Pour plus d’informations sur la migration à partir de l’appel des Plans, voir :

- [Configurer des offres d'appels](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice utilisateur](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Il est recommandé de supprimer des informations de plan de gestion des licences previouslycconfigured comme suit :
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migration à partir d’Office 365 téléphone système avec une connectivité PSTN local dans Skype pour Business Server

Pour plus d’informations sur la migration à partir du système téléphonique avec une connectivité PSTN local dans Skype pour Business Server, consultez les éléments suivants :

- [Planification](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Déploiement](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Il est recommandé de supprimer précédemment configuré voix informations de routage comme suit :

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migration à partir d’Office 365 téléphone système avec une connectivité PSTN via le nuage connecteur Edition sur site 

Pour plus d’informations sur la migration à partir du système téléphonique avec une connectivité PSTN via le nuage connecteur local, voir :

- [Planification](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Déploiement](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuration utilisateur](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Il est recommandé de supprimer précédemment configuré voix informations de routage comme suit :
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>LIENS CONNEXES

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Nouvelle CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

