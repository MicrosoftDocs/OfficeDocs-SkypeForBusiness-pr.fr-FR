---
title: Configurer le routage direct
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
description: Apprenez à configurer le routage direct du système Microsoft Phone.
ms.openlocfilehash: 37fe6fa9355a0892720fa32d2bab30474ddaf12a
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925496"
---
# <a name="configure-direct-routing"></a>Configurer le routage direct

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du routage direct, la planification et le déploiement: [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)

Si vous ne l’avez pas encore fait, lisez [planifier le routage direct](direct-routing-plan.md) pour les prérequis et passer en revue les autres étapes que vous devez effectuer avant de configurer votre réseau de systèmes Microsoft Phone. 

Cet article décrit comment configurer le routage direct du système Microsoft Phone. Il explique en détail comment jumeler une manette de frontière de session (SBC) prise en charge et configurer les utilisateurs de Microsoft teams pour se connecter au réseau téléphonique public commuté (RTC). Pour suivre les étapes décrites dans cet article, les administrateurs doivent vous familiariser avec les applets de cmdlet PowerShell. Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Nous vous conseillons de vérifier que votre SBC a déjà été configuré comme recommandé par votre fournisseur de SBC: 

- [Documentation de déploiement AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation relative au déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation sur le déploiement des communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Vous pouvez configurer votre système Microsoft Phone et permettre aux utilisateurs d’utiliser le routage direct, puis configurer Microsoft teams en tant que client appelant préféré en exécutant les procédures suivantes: 

- [Coupler une SBC avec un système Microsoft Phone et valider le jumelage](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Activer les utilisateurs pour le service de routage direct](#enable-users-for-direct-routing-service)
- [Vérifiez que Microsoft teams est le client appelant préféré pour les utilisateurs.](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Coupler l’SBC au service de routage direct du système téléphonique 

Voici les trois principales étapes pour vous permettre de vous connecter, ou jumeler, l’interface SBC à l’interface de routage directe: 

- Se connecter au centre **d’administration de Skype entreprise Online** à l’aide de PowerShell 
- Coupler l’SBC 
- Valider le jumelage 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Se connecter à Skype entreprise Online à l’aide de PowerShell 

Vous pouvez utiliser une session PowerShell connectée au client pour jumeler l’interface SBC à l’interface de routage directe. Pour ouvrir une session PowerShell, suivez les étapes décrites dans [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer l’SBC. Pour valider les commandes, tapez ou copiez/collez les éléments suivants dans la session PowerShell, puis appuyez sur entrée: 

```
Get-Command *onlinePSTNGateway*
```

Votre commande renverra les quatre fonctions indiquées ici pour vous permettre de gérer l’SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Coupler l’SBC au client 

Pour jumeler l’SBC au client, dans la session PowerShell, entrez ce qui suit, puis appuyez sur entrée: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Nous vous recommandons vivement de définir une limite d’appels maximale dans l’SBC en utilisant les informations qui figurent dans la documentation de l’SBC. La limite déclenche une notification si l’SBC a le niveau de capacité.
  > 2. Vous pouvez uniquement jumeler l’SBC si la partie Domain de son nom de domaine complet correspond à l’un des domaines inscrits \*dans votre client, à l’exception de. onmicrosoft.com. L' \*utilisation des noms de domaine. onmicrosoft.com n’est pas prise en charge pour le nom de domaine complet SBC. Par exemple, si vous avez deux noms de domaine:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Pour le nom SBC, vous pouvez utiliser le nom sbc.contoso.com. Si vous essayez de jumeler l’SBC avec un nom SBC. contoso. ABC, le système ne vous en permettra pas, car le domaine n’est pas détenu par ce client.<br/>
  > Outre le domaine enregistré dans votre client, il est important qu’il existe un utilisateur avec ce domaine et qu’une licence E3 ou E5 lui est affectée. Si ce n’est pas le cas, vous recevez le message d’erreur suivant:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Renvoie
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Il existe d’autres options qui peuvent être définies lors du processus de jumelage. Dans l’exemple précédent, seuls les paramètres minimum requis apparaissent. 
 
Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser dans les paramètres de configuration de`New-CsOnlinePstnGateway`

|Obligatoire?|Nom|Description|Par défaut|Valeurs possibles|Type et restrictions|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Oui|FQDN|Nom de domaine complet du SBC |Aucun|Nom NoneFQDN, limiter 63 caractères|Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’appellation dans Active Directory pour les ordinateurs, domaines, sites et UO](https://support.microsoft.com/help/909264)|
|Non|MediaBypass |Paramètre réservé pour une utilisation ultérieure. Le paramètre indiqué par l’élément SBC prend en charge la dérivation multimédia et l’administrateur veut l’utiliser.|Aucun|True<br/>False|Boolean|
|Oui|SipSignallingPort |Port d’écoute utilisé pour la communication avec les services de routage directe à l’aide du protocole TLS (Transport Layer Security).|Aucun|Tout port|entre 0 et 65535 |
|Non|FailoverTimeSeconds |Lorsque la valeur est définie sur 10 (valeur par défaut), les appels sortants pour lesquels la passerelle ne répond pas dans un délai de 10 secondes sont routés vers le Trunk disponible suivant; s’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels. La valeur par défaut est 10.|0,10|Numéro|Ent|
|Non|ForwardCallHistory |Indique si les informations d’historique d’appel sont transférées par le biais de la jonction. Si cette option est activée, le Proxy RTC Office 365 envoie deux en-têtes: History-Info et expertisé. La valeur par défaut **** est false ($false). |False|True<br/>False|Boolean|
|Non|ForwardPAI|Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant. Si vous avez activé l’en-tête d’ID vie privée: il est également envoyé. La valeur par défaut **** est false ($false).|False|True<br/>False|Boolean|
|Non|SendSIPOptions |Définit si une SBC va ou non envoyer les options SIP. S’il est désactivé, l’SBC sera exclu du système de surveillance et d’alerte. Nous vous recommandons vivement d’activer les options SIP. La valeur par défaut est **true**. |True|True<br/>False|Boolean|
|Non|MaxConcurrentSessions |Utilisé par le système d’alerte. Lorsque n’importe quelle valeur est définie, le système d’alerte génère une alerte auprès de l’administrateur client lorsque le nombre de sessions simultanées est 90% ou une valeur supérieure à celle-ci. Si paramètre n’est pas défini, les alertes ne le sont pas. Toutefois, le système de surveillance rapportera le nombre de sessions simultanées toutes les 24 heures. |Valeur|Valeur<br/>1 à 100 000 ||
|Non|MediaRelayRoutingLocationOverride |Permet de sélectionner manuellement le chemin pour le média. Le routage direct affecte un centre de contenus multimédia pour le chemin multimédia en fonction de l’adresse IP publique de l’SBC. Nous cherchons toujours le plus près du centre de centres SBC. Toutefois, dans certains cas, il est possible d’attribuer une adresse IP publique de la part d’une SBC située en Europe, par exemple. Dans ce cas, nous n’utiliserons pas le chemin multimédia. Ce paramètre permet de définir manuellement la région préférée pour le trafic multimédia. Nous vous conseillons de définir ce paramètre uniquement si les journaux d’appels indiquent clairement que l’attribution automatique du centre de fichiers de média pour le chemin multimédia n’affecte pas le plus proche au centre de médias SBC. |Aucun|Codes de pays au format ISO||
|Non|Activé|Utilisé pour activer cet SBC pour les appels sortants. Peut être utilisé pour supprimer temporairement l’SBC, pendant sa mise à jour ou lors de la maintenance. |False|True<br/>False|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>Vérifier le jumelage des SBC 

Vérifiez la connexion: 
- Vérifiez si la SBC est sur la liste de SBCs couplés. 
- Valider les options SIP. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Vérifier si la SBC est sur la liste de SBCs couplés 

Une fois que vous avez couplé l’SBC, validez la présence de l’SBC dans la liste des éléments SBCs couplés en exécutant la commande suivante dans une session PowerShell distante:`Get-CSOnlinePSTNGateway`

La passerelle couplée doit apparaître dans la liste, comme illustré dans l’exemple ci-dessous, et vérifier que le paramètre *Enabled* affiche la valeur **true**. Spécifi

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Qui renvoie:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>Valider le flux d’options SIP 

Pour valider le jumelage à l’aide des options SIP sortants, utilisez l’interface de gestion des SBC et confirmez que l’SBC reçoit les réponses 200 OK à ses messages d’OPTIONS sortants.

Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages d’options SIP sortants au nom de domaine complet SBC configuré dans le champ d’en-tête de contact du message OPTIONS entrantes. 

Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion des SBC et voyez que l’SBC envoie une réponse aux messages d’OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.

## <a name="enable-users-for-direct-routing-service"></a>Activer les utilisateurs pour le service de routage direct 

Lorsque vous êtes prêt à activer les utilisateurs pour le service de routage direct, procédez comme suit: 

1. Créez un utilisateur dans Office 365 et attribuez une licence de système téléphonique. 
2. Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online. 
3. Configurez le numéro de téléphone et activez voix entreprise et boîte vocale. 
4. Configurer le routage de la voix. L’itinéraire est validé automatiquement.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Créer un utilisateur dans Office 365 et affecter la licence 

Deux options s’offrent à vous pour créer un utilisateur dans Office 365. Toutefois, nous recommandons que votre organisation sélectionne et utilise une option pour éviter les problèmes de routage: 

- Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud. Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Créer l’utilisateur directement dans le portail d’administration Office 365. Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Si votre déploiement de Skype entreprise Online co-existe avec Skype entreprise 2015 ou Lync 2010/2013 local, la seule option prise en charge consiste à créer l’utilisateur dans Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1). 

Licences requises: 

- Office 365 entreprise E3 (y compris marketing Plan2, Exchange Plan2 et Teams) + Téléphone
- Office 365 entreprise E5 (y compris marketing Plan2, Exchange Plan2, équipes et système téléphonique) 

Licences facultatives: 

- Forfait d’appels 
- Audioconférence, 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Vérifier que l’utilisateur est bien immobilier dans Skype entreprise Online 

Le routage direct nécessite que l’utilisateur soit hébergé dans Skype entreprise online. Pour cela, vous pouvez consulter le paramètre RegistrarPool. Il doit avoir une valeur dans le domaine infra.lync.com.

1. Connectez-vous à Remote PowerShell.
2. Émettez la commande suivante: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise 

Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer son numéro de téléphone et sa boîte vocale. Cette opération peut être réalisée en une seule étape. 

Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit:
 
1. Se connecter à une session PowerShell distante. 
2. Entrez la commande suivante: 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur «Beaune Low», entrez ce qui suit: 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Le numéro de téléphone utilisé doit être configuré en tant que numéro de téléphone avec l’indicatif du pays. 

  > [!NOTE]
  > Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur. 

### <a name="configure-voice-routing"></a>Configurer le routage de la voix 

Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un SBC spécifique en fonction de: 

- Modèle de nombre appelé 
- Appel de modèle de numéro + utilisateur spécifique qui effectue l’appel
 
SBCs peut être désignée comme active et Backup. Cela signifie que lorsque l’SBC configuré comme étant actif pour ce modèle de nombre, ou un modèle de nombre (utilisateur spécifique) n’est pas disponible, les appels sont dirigés vers un SBC de sauvegarde.
 
Le routage des appels se compose des éléments suivants: 
- Politique de routage de la voix-conteneur d’utilisation PSTN; peuvent être affectés à un utilisateur ou à plusieurs utilisateurs 
- Usages PSTN: conteneur des itinéraires vocaux et des utilisations PSTN; peuvent être partagés dans différentes politiques de routage vocal 
- Itinéraires vocaux: modèle numérique et ensemble de passerelles RTC en ligne à utiliser pour les appels dans lesquels le numéro de téléphone correspond au modèle 
- Passerelle RTC en ligne-pointeur vers une SBC, qui stocke également la configuration appliquée lors de l’appel via SBC, telle que l’envoi d’identité P-assertion (PAI) ou de codecs préférés. peuvent être ajoutés aux itinéraires vocaux 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Création d’une stratégie de routage de la voix avec une utilisation PSTN 

Le schéma suivant montre deux exemples de stratégies de routage de voix dans le flux d’appels.

**Flux d’appels 1 (à gauche):** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz. Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné. 

**Flux d’appels 2 (sur la droite):** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz. Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz). Si aucune des SBCs n’est disponible, l’appel est abandonné. 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.

  > [!NOTE]
  > À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés. Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft. 

Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.

Dans l’exemple ci-dessous, un itinéraire vocal est ajouté pour envoyer les appels vers tous les autres États-Unis et le numéro canadien (appels vers le modèle de numéro + 1 XXX XXX XX XX).

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé. S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.

Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.

  > [!NOTE]
  > La valeur de priorité pour l’itinéraire «Other + 1» n’a pas d’importance dans ce cas, car il n’y a qu’un seul itinéraire correspondant au modèle + 1 XXX XX XX. Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.

Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux. Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN «États-Unis et Canada».

|**Utilisation PSTN**|**Route vocale**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis uniquement|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|||||||

Tous les itinéraires sont associés à l’utilisation RTC «États-Unis et Canada» et l’utilisation RTC est associée à la politique de routage de la voix «États-Unis uniquement». Dans cet exemple, la stratégie de routage de la voix est affectée à user Spencer Low.

#### <a name="examples-of-call-routes"></a>Exemples d’itinéraires d’appels

Dans l’exemple suivant, nous montrons comment configurer des itinéraires, des utilisations RTC et des stratégies de routage, et nous affectons la stratégie à l’utilisateur.

**Étape 1:** Créez l’utilisation RTC «États-Unis et Canada».

Dans une session PowerShell distante Skype entreprise, tapez:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Vérifiez que l’utilisation a été créée en entrant: 
```
Get-CSOnlinePSTNUsage
``` 
Qui renvoie une liste de noms qui risquent d’être tronqués:
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de `(Get-CSOnlinePSTNUsage).usage` la commande PowerShell pour afficher les noms complets (sans troncature). 
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

**Étape 2:** Dans une session PowerShell dans Skype entreprise Online, créez trois itinéraires: Redmond 1, Redmond 2 et autres + 1, comme décrit dans le tableau précédent. 

Pour créer l’itinéraire «Redmond 1», entrez:

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Qui renvoie:
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
Pour créer l’itinéraire de Redmond 2, entrez:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Pour créer l’autre itinéraire + 1, entrez:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide. Vous pouvez le tester à l’aide du site Web suivant:[https://www.regexpal.com](https://www.regexpal.com)

Dans certains cas, il est nécessaire de router tous les appels vers le même SBC; Utilisez-NumberPattern ". *"

- Acheminer tous les appels vers le même SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes: 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Qui doit retourner:
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

Dans l’exemple, l’itinéraire «Other + 1» a automatiquement la priorité 4. 

**Étape 3:** Créez une stratégie de routage de la voix «États-Unis uniquement» et ajoutez-la à la politique «États-Unis et Canada».

Dans une session PowerShell dans Skype entreprise Online, tapez:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Le résultat est affiché dans cet exemple:

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Étape 4:** Accordez à l’utilisateur la politique de routage de la voix de faible utilisation par PowerShell.

- Dans une session PowerShell dans Skype entreprise Online, tapez:

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Validez l’affectation de stratégie en entrant la commande suivante:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Qui renvoie:
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Création d’une stratégie de routage de la voix avec plusieurs utilisations PSTN

La politique de routage vocale créée auparavant n’autorise que les appels vers des numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.

Dans l’exemple qui suit, vous pouvez créer la stratégie de routage téléphonique «aucune restriction». La stratégie réutilise l’utilisation RTC «États-Unis et Canada» créée dans l’exemple précédent, ainsi que la nouvelle utilisation RTC «international». 

Cela achemine tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz. Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur «Beaune Low» et aucune restriction à l’utilisateur «Jean bois».

Spencer Low – appels uniquement autorisés vers les États-Unis et le Canada. Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé. Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.

Jean bois – appels autorisés vers n’importe quel numéro. Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé. Les numéros non US seront routés par le biais de sbc2.contoso.biz et sbc5.contoso.biz.

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé. S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.

Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage «aucune restriction». 

|**Utilisation PSTN**|**Route vocale**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis uniquement|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis uniquement|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Itinéraire pour n’importe quel modèle numérique |


  > [!NOTE]
  > - L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel. Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées. L’utilisation RTC «international» doit être placée après l’utilisation RTC «États-Unis uniquement». Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande. <br/>Par exemple, pour passer de l’ordre «États-Unis et Canada» et inversement, procédez comme suit:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Le niveau de priorité des itinéraires vocaux «Other + 1» et «international» est automatiquement attribué. Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à «Redmond 1» et «Redmond 2».

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Exemple de politique de routage vocale pour les bois des utilisateurs de Jean

Les étapes à suivre pour créer une utilisation PSTN «international», un itinéraire vocal «international», «stratégie de routage vocale» n’est pas soumis à des restrictions», puis l’affecter à l’utilisateur «Jean bois» est le suivant.


1. Tout d’abord, créez l’utilisation RTC «international». Dans une session PowerShell distante dans Skype entreprise Online, entrez:

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. Ensuite, créez le nouveau message vocal «international».

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   Qui renvoie:

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. Ensuite, créez une stratégie de routage téléphonique «aucune restriction». L’utilisation RTC «Redmond 1» et «Redmond» sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro «+ 1 425 XXX XX XX» et «+ 1 206 XXX XX XX» en tant qu’appels locaux ou locaux.

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   Qui renvoie

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. Attribuez la politique de routage de la voix à l’utilisateur «Jean bois» à l’aide de la commande suivante.

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   Vérifiez ensuite le devoir à l’aide de la commande: 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   Qui renvoie:

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a>Définir Microsoft teams en tant que client appelant préféré pour les utilisateurs

Le routage direct achemine uniquement les appels vers et depuis les utilisateurs s’ils utilisent le client Teams. Si votre organisation utilise uniquement Teams, il est recommandé de définir le mode «équipes uniquement» dans la stratégie de mise à niveau. Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour plus d’informations et sélectionnez l’option appropriée: présentation de la coexistence et de la [mise à niveau de Skype entreprise et équipes](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)
