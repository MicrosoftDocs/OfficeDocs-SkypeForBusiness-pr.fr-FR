---
title: Configurer le routage de la voix pour le routage direct
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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Apprenez à configurer le routage de la voix avec le routage direct du système Microsoft Phone.
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157956"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Configurer le routage de la voix pour le routage direct

Cet article décrit comment configurer le routage vocal pour le routage direct du système téléphonique.  Pour configurer le routage direct, vous devez procéder comme suit :

- Étape 1. [Connecter l’SBC avec un système Microsoft Phone et valider la connexion](direct-routing-connect-the-sbc.md) 
- Étape 2. [Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale](direct-routing-enable-users.md)    
- **Étape 3. Configurer le routage** de la voix (cet article)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Présentation du routage vocal

Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un contrôleur de bordure de session spécifique (SBC) en fonction de : 

- Modèle de nombre appelé 
- Le modèle de numéro appelé et l’utilisateur spécifique qui effectue l’appel
 
SBCs peut être désignée comme active et Backup. Lorsque l’SBC configuré comme étant actif n’est pas disponible pour un itinéraire d’appel spécifique, l’appel est acheminé vers un SBC de sauvegarde.
 
Le routage vocal est constitué des éléments suivants : 

- **Politique de routage** de la voix : conteneur des utilisations RTC qui peuvent être attribués à un utilisateur ou à plusieurs utilisateurs. 

- **Usages PSTN** : conteneur pour les itinéraires vocaux et usages RTC, qui peuvent être partagés dans différentes politiques de routage vocal. 

- **Itinéraires vocaux** : un modèle numérique et un ensemble de passerelles RTC en ligne à utiliser pour les appels pour lesquels le numéro de téléphone correspond au modèle.

- **Passerelle RTC en ligne** : pointeur vers une SBC qui stocke également la configuration appliquée lors du passage d’un appel par le biais de l’SBC, tel que l’envoi d’identité P-assertion (PAI) ou les codecs préférés. peuvent être ajoutés aux itinéraires vocaux.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Exemple 1 : routage de la voix avec une utilisation PSTN

Le schéma suivant montre deux exemples de stratégies de routage vocal dans un flux d’appels.

**Flux d’appels 1 (à gauche) :** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz. Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné. 

**Flux d’appels 2 (sur la droite) :** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz. Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz). Si aucune des SBCs n’est disponible, l’appel est abandonné. 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.

  > [!NOTE]
  > À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés. Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft. Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.

Dans l’exemple ci-dessous, un itinéraire est ajouté à l’adresse de l’expéditeur pour les appels vers tous les autres États-Unis et le Canada (appels vers un modèle de numéro + 1 XXX XXX XX XX).

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Pour tous les autres appels :

- Si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), le routage automatique est utilisé. 
- S’il n’y a aucun résultat correspondant aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé par le biais du forfait d’appel Microsoft.
- Si l’utilisateur dispose uniquement d’un système Microsoft Phone, l’appel est abandonné, car aucune règle correspondante n’est disponible.

  > [!NOTE]
  > La valeur de priorité pour l’itinéraire « autres + 1 » n’a pas d’importance dans le cas du fait qu’il n’y a qu’un seul itinéraire qui correspond à la valeur du modèle + 1 XXX XX XX XX. Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.

Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux. Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN « États-Unis et Canada ».  Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage de la voix « États-Unis uniquement ». 

|**Utilisation PSTN**|**Route vocale**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis uniquement|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|deuxième|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|||||||


### <a name="example-1-configuration-steps"></a>Exemple 1 : étapes de configuration

L’exemple suivant montre comment :

- Créer une utilisation PSTN unique 
- Configurer trois itinéraires vocaux
- Créer une stratégie de routage de la voix
- Affectez la stratégie à user Spencer Low.

**Étape 1 :** Créer l’utilisation RTC "États-Unis et Canada"

Dans une session PowerShell distante Skype entreprise, tapez :

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Vérifiez que l’utilisation a été créée en entrant : 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
Qui renvoie une liste de noms qui risquent d’être tronqués :
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
L’exemple ci-dessous montre le résultat de l’exécution `(Get-CSOnlinePSTNUsage).usage` de la commande PowerShell pour afficher les noms complets (pas tronqués) :

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Étape 2 :** Dans une session PowerShell dans Skype entreprise Online, créez trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme indiqué dans le tableau précédent.

Pour créer l’itinéraire « Redmond 1 », entrez :

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Qui renvoie :
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Pour créer l’itinéraire de Redmond 2, entrez :

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Pour créer l’autre itinéraire + 1, entrez :

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide. Vous pouvez le tester à l’aide du site Web suivant :[https://www.regexpal.com](https://www.regexpal.com)

Dans certains cas, il est nécessaire de router tous les appels vers le même SBC ; use-NumberPattern ". *"

Acheminez tous les appels vers le même SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes :

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Qui doit retourner :
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4. 

**Étape 3 :** Créez une stratégie de routage de la voix « États-Unis uniquement » et ajoutez-la à la politique « États-Unis et Canada ».

Dans une session PowerShell dans Skype entreprise Online, tapez :

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Le résultat est affiché dans cet exemple :

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Étape 4 :** À l’aide de PowerShell, accordez la stratégie de routage vocale à l’utilisateur Spencer Low :

Dans une session PowerShell dans Skype entreprise Online, tapez :

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Validez l’affectation de stratégie en entrant la commande suivante :

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

La commande renvoie ce qui suit :
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Exemple 2 : routage de la voix avec plusieurs utilisations RTC

La politique de routage vocale créée dans l’exemple 1 autorise uniquement les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.

Dans l’exemple qui suit, vous pouvez créer la stratégie de routage téléphonique « aucune restriction ». La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation RTC « international ».  Cette stratégie route tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz. 

Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur Beaune Low et la stratégie no restrictions à l’utilisateur Jean Martin de sorte que le routage se déroule comme suit :

- Beaune : politique de niveau faible-américaine uniquement.  Les appels ne sont admis qu’aux États-Unis et au Canada. Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé. Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.

- Jean bois-politique internationale.  Les appels sont autorisés à n’importe quel numéro. Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé. Les numéros non US seront routés à l’aide de sbc2.contoso.biz et sbc5.contoso.biz.

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé. S’il n’y a aucun résultat correspondant aux modèles de chiffres dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide d’un forfait d’appel Microsoft.  Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ». 

|**Utilisation PSTN**|**Route vocale**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis uniquement|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|deuxième|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Itinéraire pour n’importe quel modèle numérique |


  > [!NOTE]
  > - L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel. Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées. L’utilisation RTC « international » doit être placée après l’utilisation RTC « États-Unis uniquement ». Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande. <br/>Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué. Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».


### <a name="example-2-configuration-steps"></a>Exemple 2 : étapes de configuration

L’exemple suivant montre comment :

- Créer une nouvelle utilisation RTC appelée international
- Créer un nouvel itinéraire vocal appelé international
- Création d’une stratégie de routage de la voix sans restrictions
- Affecter la politique aux bois des utilisateurs Jean


**Étape 1**: créer une utilisation PSTN internationale. 

Dans une session PowerShell distante dans Skype entreprise Online, entrez :

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Étape 2**: créer le nouvel itinéraire vocal « international »

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Qui renvoie :

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Étape 3**: créer une stratégie de routage téléphonique « aucune restriction ». 

L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prenez note de l’ordre des utilisations RTC :

  a. Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit le routage défini dans utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée. C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.

  b. S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage. Entrez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Qui renvoie :

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

**Étape 4**: affectez la stratégie de routage téléphonique à l’utilisateur « Jean bois » à l’aide de la commande suivante.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

Vérifiez ensuite le devoir à l’aide de la commande : 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Qui renvoie :

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.



## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
