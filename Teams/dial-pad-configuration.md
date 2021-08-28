---
title: Teams configuration du pavé de numérotation
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Découvrez comment configurer le pavé de numérotation dans le client Teams pour que les utilisateurs accèdent à la fonctionnalité de réseau téléphonique commuté (PSTN).
ms.openlocfilehash: 6f67aeda059505ec5c1e78d117407f0e9703f732
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627616"
---
# <a name="dial-pad-configuration"></a>Configuration du pavé de numérotation

Dans le Teams, le pavé de numérotation permet aux utilisateurs d’accéder aux fonctionnalités de réseau téléphonique commuté (PSTN). Le pavé de numérotation est disponible pour les utilisateurs Système téléphonique licence utilisateur, à condition qu’ils soient configurés correctement. Tous les critères suivants sont requis pour que le pavé de numérotation affiche :

- Un utilisateur dispose d’une licence Système téléphonique « MCOEV »)
- L’utilisateur dispose d’un plan d’appel Microsoft ou est activé pour le routage direct
- L’utilisateur Voix Entreprise activé
- L’utilisateur est homed online et n’est pas Skype Entreprise local
- L’utilisateur a Teams stratégie d’appel activée

Les sections suivantes décrivent comment utiliser PowerShell pour vérifier les critères. Le plus souvent, vous devez examiner différentes propriétés dans la sortie de l'Get-CsOnlineUser cmdlet. Les exemples supposent $user nom d’utilisateur utilisateur (UPN) ou l’adresse SIP de l’utilisateur.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>Un utilisateur dispose d’une licence Système téléphonique « MCOEV »)

Vous devez vous assurer que le plan attribué à l’utilisateur indique l’attribut **CapabilityStatus** sur Activé et le Plan de fonctionnalité sur **MCOEV** (licence Système téléphonique données). Vous pouvez voir MCOEV, MCOEV1, etc. Tous sont acceptables, tant que le plan de fonctionnalités commence par la fonction MCOEV.

Pour vérifier que les attributs sont correctement réglés, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

La sortie ressemble à ce qui suit. Il vous suffit de vérifier les attributs **CapabilityStatus** et **le Plan** de fonctionnalités :

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>L’utilisateur dispose d’un plan d’appel Microsoft OU est activé pour le routage direct

**Si l’utilisateur** dispose d’un plan d’appels Microsoft, vous devez vous assurer que l’attribut **CapabilityStatus** est activé et que le plan de fonctionnalités est définie sur **MCOPSTN.** Vous pouvez voir MCOPSTN1, MCOPSTN2, etc. Tous sont acceptables, tant que le plan de fonctionnalités commence par MCOPSTN.

Pour vérifier les attributs, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

La sortie ressemble à ce qui suit. Il vous suffit de vérifier les attributs **CapabilityStatus** et **le Plan** de fonctionnalités :

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

**Si l’utilisateur est activé** pour l’acheminement direct, une valeur non Null doit lui être affectée pour OnlineVoiceRoutingPolicy. Pour vérifier l’attribut, utilisez la commande suivante :
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

La sortie doit avoir une valeur non Null, par exemple :

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>L’utilisateur Voix Entreprise activé

Pour vérifier si l’utilisateur Voix Entreprise activé, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

La sortie doit ressembler à ce qui s’est produit :

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L’utilisateur est homed online et n’est pas Skype Entreprise local

Pour s’assurer que l’utilisateur est homed online et non dans Skype Entreprise en local, le RegistrarPool ne doit pas être Null et HostingProvider doit contenir une valeur qui commence par « sipfed.online ».  Pour vérifier les valeurs, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

La sortie doit être similaire à :

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>L’utilisateur a Teams stratégie d’appel activée

Le site TeamsCallingPolicy de l’utilisateur doit avoir la valeur AllowPrivateCalling définie sur true.  Par défaut, les utilisateurs héritent de la stratégie globale, qui dispose de AllowPrivateCallingPolicy définie sur true par défaut.

Pour obtenir TeamsCallingPolicy pour un utilisateur et vérifier que AllowPrivateCalling est définie sur true, utilisez la commande suivante :

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

La sortie doit ressembler à ce qui s’est produit :

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

## <a name="additional-notes"></a>Notes supplémentaires

-   Vous devrez peut-être redémarrer Teams client après avoir apporté l’une de ces modifications de configuration.

-   Si vous avez récemment mis à jour l’un des critères ci-dessus, vous devrez peut-être patienter quelques heures pour que le client reçoie les nouveaux paramètres.

-   Si vous ne voyez toujours pas le pavé de numérotation, vérifiez qu’il existe une erreur de mise en service à l’aide de la commande suivante :

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    S’il y a plus de 24 heures et que vous continuez de voir des problèmes, contactez le support technique.


