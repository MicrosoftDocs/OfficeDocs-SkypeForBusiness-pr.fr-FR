---
title: Configuration du pavé de numérotation teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Apprenez-en davantage sur la configuration du pavé de numérotation dans le client teams pour permettre aux utilisateurs d’accéder à la fonctionnalité de réseau téléphonique commuté (RTC).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012415"
---
# <a name="dial-pad-configuration"></a>Configuration du pavé de numérotation

Dans le client Microsoft Teams, le pavé de numérotation permet aux utilisateurs d’accéder à la fonctionnalité de réseau téléphonique commuté (RTC). Le pavé de numérotation est disponible pour les utilisateurs disposant d’une licence de système téléphonique, à condition qu’ils soient correctement configurés. Pour afficher le pavé de numérotation, vous devez procéder comme suit :

- L’utilisateur a une licence de système téléphonique (« MCOEV ») activée
- L’utilisateur a un forfait d’appel Microsoft ou est activé pour le routage direct
- L’utilisateur est doté de la voix entreprise activée
- L’utilisateur est connecté en ligne et non dans Skype entreprise sur site
- La stratégie d’appel des équipes est activée pour l’utilisateur

Les sections suivantes décrivent comment utiliser PowerShell pour vérifier les critères. Dans la plupart des cas, vous devez examiner diverses propriétés dans la sortie de l’applet de passe Get-CsOnlineUser. Les exemples présupposent que le $user est l’adresse UPN ou la adresse SIP de l’utilisateur.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>L’utilisateur a une licence de système téléphonique (« MCOEV ») activée

Vous devez vous assurer que le plan affecté pour l’utilisateur indique l' **attribut CapabilityStatus défini sur Enabled** et que le **plan de fonctionnalités a la valeur MCOEV** (licence du système téléphonique). Vous pouvez voir MCOEV, MCOEV1, etc. Tous sont acceptables : tant que le plan de fonctionnalité commence par MCOEV.

Pour vérifier que les attributs sont correctement définis, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

La sortie ressemblera à ce qui suit. Il vous suffit de vérifier les attributs **CapabilityStatus** et de **plan de fonctionnalité** :

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>L’utilisateur a un forfait d’appel Microsoft ou est activé pour le routage direct

**Si l’utilisateur a un plan d’appel Microsoft**, vous devez vous assurer que l' **attribut CapabilityStatus est défini sur Enabled**, et que le **plan de capacité est défini sur MCOPSTN**. Vous pouvez voir MCOPSTN1, MCOPSTN2, etc. Tous sont acceptables : tant que le plan de fonctionnalité commence par MCOPSTN.

Pour vérifier les attributs, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

La sortie ressemblera à ce qui suit. Il vous suffit de vérifier les attributs **CapabilityStatus** et de **plan de fonctionnalité** :

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**Si l’utilisateur est activé pour le routage direct**, l’utilisateur doit être affecté d’une valeur non null pour OnlineVoiceRoutingPolicy. Pour vérifier l’attribut, utilisez la commande suivante :
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

La sortie doit avoir une valeur non null, par exemple :

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>L’utilisateur est doté de la voix entreprise activée

Pour vérifier si l’utilisateur est doté de la voix entreprise activée, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

Le résultat doit ressembler à ceci :

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L’utilisateur est connecté en ligne et non dans Skype entreprise sur site

Pour vous assurer que l’utilisateur est en ligne et qu’il n’est pas disponible dans Skype entreprise sur site, la RegistrarPool ne doit pas être nulle et HostingProvider doit contenir une valeur commençant par « sipfed. online ».  Pour vérifier les valeurs, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Le résultat doit ressembler à ce qui suit :

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>La stratégie d’appel des équipes est activée pour l’utilisateur

Le TeamsCallingPolicy effectif de l’utilisateur doit avoir la valeur true pour AllowPrivateCalling.  Par défaut, les utilisateurs héritent de la stratégie globale, dont la valeur par défaut est AllowPrivateCallingPolicy.

Pour obtenir le TeamsCallingPolicy d’un utilisateur et vérifier que AllowPrivateCalling est défini sur true, utilisez la commande suivante :

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

Le résultat doit ressembler à ceci :

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a>Remarques supplémentaires

-   Après avoir effectué ces modifications de configuration, vous devrez éventuellement redémarrer le client Teams.

-   Si vous avez récemment mis à jour l’un des critères ci-dessus, vous devrez peut-être patienter quelques heures avant que le client ne reçoive les nouveaux paramètres.

-   Si vous ne voyez toujours pas le pavé de numérotation, vérifiez qu’il y a une erreur de mise en service à l’aide de la commande suivante :

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    S’il s’agit de plus de 24 heures et que vous rencontrez toujours des problèmes, contactez le support technique.


