---
title: configuration du pavé de numérotation Teams
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
description: Découvrez comment configurer le pavé de numérotation dans le client Teams afin que les utilisateurs puissent accéder aux fonctionnalités du réseau téléphonique commuté (RTC).
ms.openlocfilehash: 7fc2622ce0fda97ce608e13d67ff786431a30aa5
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248926"
---
# <a name="dial-pad-configuration"></a>Configuration du pavé de numérotation

Dans le client Teams, le pavé de numérotation permet aux utilisateurs d’accéder à la fonctionnalité réseau téléphonique commuté (RTC). Le pavé de numérotation est disponible pour les utilisateurs disposant d’une licence Système téléphonique, à condition qu’ils soient correctement configurés. Les critères suivants sont tous requis pour que le pavé de numérotation affiche :

- L’utilisateur dispose d’une licence Système téléphonique activée (« MCOEV »)
- L’utilisateur dispose d’un plan d’appel Microsoft, d’un Operator Connect ou est activé pour le routage direct
- L’utilisateur a Voix Entreprise activé
- L’utilisateur est hébergé en ligne et non dans Skype Entreprise localement
- La stratégie d’appel Teams est activée pour l’utilisateur

Les sections suivantes décrivent comment utiliser PowerShell pour vérifier les critères. Dans la plupart des cas, vous devez examiner différentes propriétés dans la sortie de l’applet de commande Get-CsOnlineUser. Les exemples supposent que $user est l’adresse UPN ou sip de l’utilisateur.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>L’utilisateur dispose d’une licence Système téléphonique activée (« MCOEV »)

Assurez-vous que le plan affecté pour l’utilisateur affiche **l’attribut CapabilityStatus défini sur Activé** et la **fonctionnalité définie sur MCOEV** (licence Système téléphonique). Vous pouvez voir MCOEV, MCOEV1, et ainsi de suite. Tous sont acceptables, tant que la fonctionnalité commence par MCOEV.

Pour vérifier que les attributs sont correctement définis, utilisez la commande suivante :

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

La sortie se présente comme suit. Vous devez uniquement vérifier **capabilityStatus** et les attributs **capability** :

```
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```


## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>L’utilisateur dispose d’un plan d’appel Microsoft, Operator Connect OR est activé pour le routage direct

**Si l’utilisateur dispose d’un plan d’appel Microsoft**, assurez-vous que **l’attribut CapabilityStatus est activé** et que la **fonctionnalité est définie sur MCOPSTN**. Vous pouvez voir MCOPSTN1, MCOPSTN2, et ainsi de suite. Tous sont acceptables, tant que la fonctionnalité commence par MCOPSTN.

Pour vérifier les attributs, utilisez la commande suivante :

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

La sortie se présente comme suit. Vous devez uniquement vérifier **capabilityStatus** et les attributs **capability** :

```  
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```
**Si l’utilisateur est activé pour Operator Connect**, il doit avoir une valeur non Null pour TeamsCarrierEmergencyCallRoutingPolicy. Pour vérifier l’attribut, utilisez la commande suivante :
  
```
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

La sortie doit avoir une valeur non Null, par exemple :

```
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**Si l’utilisateur est activé pour le routage direct**, une valeur non Null doit lui être attribuée pour OnlineVoiceRoutingPolicy. Pour vérifier l’attribut, utilisez la commande suivante :
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

La sortie doit avoir une valeur non Null, par exemple :

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>L’utilisateur a Voix Entreprise activé

Pour vérifier si l’utilisateur a Voix Entreprise activé, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

La sortie doit ressembler à ceci :

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>L’utilisateur est hébergé en ligne et non dans Skype Entreprise localement

Pour vous assurer que l’utilisateur est hébergé en ligne et non dans Skype Entreprise local, registrarPool ne doit pas être null et hostingProvider doit contenir une valeur commençant par « sipfed.online ».  Pour vérifier les valeurs, utilisez la commande suivante :

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

La sortie doit être similaire à :

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>La stratégie d’appel Teams est activée pour l’utilisateur

AllowPrivateCalling doit avoir la valeur true pour l’application TeamsCallingPolicy effective de l’utilisateur.  Par défaut, les utilisateurs héritent de la stratégie globale, dont AllowPrivateCallingPolicy a la valeur true par défaut.

Pour obtenir TeamsCallingPolicy pour un utilisateur et vérifier que AllowPrivateCalling a la valeur true, utilisez la commande suivante :

```
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

La sortie doit ressembler à ceci :

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

-   Vous devrez peut-être redémarrer le client Teams après avoir apporté l’une de ces modifications de configuration.

-   Si vous avez récemment mis à jour l’un des critères ci-dessus, vous devrez peut-être attendre quelques heures que le client reçoive les nouveaux paramètres.

-   Si vous ne voyez toujours pas le pavé de numérotation, vérifiez s’il y a une erreur d’approvisionnement à l’aide de la commande suivante :

  ```
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

-    Si cela fait plus de 24 heures et que vous rencontrez toujours des problèmes, contactez le support technique.


