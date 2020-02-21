---
title: Connecter votre contrôleur de bordure de session (SBC) au routage direct
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
description: Apprenez à configurer le routage direct du système Microsoft Phone.
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157954"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connecter votre contrôleur de bordure de session (SBC) au routage direct 

Cet article explique comment connecter votre contrôleur de bordure de session (SBC) au routage direct du système téléphonique.  Voici la procédure à suivre pour configurer le routage direct :

- **Étape 1. Connectez votre SBC avec votre système téléphonique et validez la connexion** (cet article)
- Étape 2. [Activer les utilisateurs pour le routage direct](direct-routing-enable-users.md)
- Étape 3. [Configurer le routage des appels](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).

Pour connecter votre SBC au routage direct, vous devez effectuer les opérations suivantes : 

1. Connectez-vous au centre **d’administration de Skype entreprise Online** à l’aide de PowerShell.            
2. Connectez l’SBC au client.
3. Validez la connexion. 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Se connecter à Skype entreprise Online à l’aide de PowerShell 

Vous pouvez utiliser une session PowerShell connectée au client pour jumeler l’interface SBC à l’interface de routage directe. Pour ouvrir une session PowerShell, suivez les étapes décrites dans [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer l’SBC. Pour valider les commandes, tapez ou copiez-collez la commande suivante dans la session PowerShell, puis appuyez sur entrée : 

```PowerShell
Get-Command *onlinePSTNGateway*
```

La commande renvoie les quatre fonctions indiquées ici pour vous permettre de gérer l’SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a>Connecter l’SBC au client 

Pour connecter l’SBC au client, dans la session PowerShell, entrez ce qui suit, puis appuyez sur entrée : 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft recommande de définir une limite d’appels maximale dans l’SBC en utilisant les informations figurant dans la documentation de l’SBC. La limite déclenche une notification si l’SBC a le niveau de capacité.
  > 2. Vous pouvez uniquement jumeler l’SBC si la partie Domain de son nom de domaine complet correspond à l’un des domaines inscrits \*dans votre client, à l’exception de. onmicrosoft.com. L' \*utilisation des noms de domaine. onmicrosoft.com n’est pas prise en charge pour le nom de domaine complet SBC. Par exemple, si vous avez deux noms de domaine :<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Pour le nom SBC, vous pouvez utiliser le nom sbc.contoso.com. Si vous essayez de jumeler l’SBC avec un nom SBC. contoso. ABC, le système ne vous en permettra pas, car le domaine n’est pas détenu par ce client.<br/>
  > Outre le domaine enregistré dans votre client, il est important qu’il existe un utilisateur avec ce domaine et qu’une licence E3 ou E5 lui est affectée. Si ce n’est pas le cas, vous recevez le message d’erreur suivant :<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
Renvoie
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Il existe d’autres options qui peuvent être définies lors du processus de connexion. Dans l’exemple précédent, seuls les paramètres minimum requis apparaissent. 
 
Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser pour ```New-CsOnlinePstnGateway```définir les paramètres.

|Obligatoire?|Nom|Description|Par défaut|Valeurs possibles|Type et restrictions|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Oui|FQDN|Nom de domaine complet du SBC |Aucun|Nom NoneFQDN, limiter 63 caractères|Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’appellation dans Active Directory pour les ordinateurs, domaines, sites et UO](https://support.microsoft.com/help/909264)|
|Non|MediaBypass |Le paramètre indiqué par l’élément SBC prend en charge la dérivation multimédia et l’administrateur veut l’utiliser.|Aucun|Vrai<br/>False|Boolean|
|Oui|SipSignalingPort |Port d’écoute utilisé pour la communication avec les services de routage directe à l’aide du protocole TLS (Transport Layer Security).|Aucun|Tout port|entre 0 et 65535 |
|Non|FailoverTimeSeconds |Lorsque la valeur est définie sur 10 (valeur par défaut), les appels sortants pour lesquels la passerelle ne répond pas dans un délai de 10 secondes sont routés vers le Trunk disponible suivant ; s’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels. La valeur par défaut est 10.|0,10|Numéro|Ent|
|Non|ForwardCallHistory |Indique si les informations d’historique d’appel sont transférées par le biais de la jonction. Si cette option est activée, le Proxy RTC Office 365 envoie deux en-têtes : History-Info et expertisé. La valeur par défaut est **false** ($false). |False|Vrai<br/>False|Boolean|
|Non|ForwardPAI|Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant. Si vous avez activé l’en-tête d’ID vie privée : il est également envoyé. La valeur par défaut est **false** ($false).|False|Vrai<br/>False|Boolean|
|Non|SendSIPOptions |Définit si une SBC va ou non envoyer les options SIP. S’il est désactivé, l’SBC sera exclu du système de surveillance et d’alerte. Nous vous recommandons vivement d’activer les options SIP. La valeur par défaut est **true**. |Vrai|Vrai<br/>False|Boolean|
|Non|MaxConcurrentSessions |Utilisé par le système d’alerte. Lorsque n’importe quelle valeur est définie, le système d’alerte génère une alerte de l’administrateur client lorsque le nombre de sessions simultanées est 90% ou une valeur supérieure à celle-ci. Si le paramètre n’est pas défini, les alertes ne le sont pas. Toutefois, le système de surveillance rapportera le nombre de sessions simultanées toutes les 24 heures. |Valeur|Valeur<br/>1 à 100 000 ||
|Non|MediaRelayRoutingLocationOverride |Permet de sélectionner manuellement le chemin pour le média. Le routage direct affecte un centre de contenus multimédia pour le chemin multimédia en fonction de l’adresse IP publique de l’SBC. Nous cherchons toujours le plus près du centre de centres SBC. Toutefois, dans certains cas, une adresse IP publique de (par exemple, une plage américaine) peut être affectée à une SBC située en Europe. Dans ce cas, nous n’utiliserons pas le chemin multimédia. Ce paramètre permet de définir manuellement la région préférée pour le trafic multimédia. Microsoft recommande uniquement de définir ce paramètre si les journaux des appels indiquent clairement qu’une affectation automatique du chemin d’accès au média du datacenter n’affecte pas le plus proche du centre de médias SBC. |Aucun|Codes de pays au format ISO||
|Non|Activé|Utilisé pour activer cet SBC pour les appels sortants. Peut être utilisé pour supprimer temporairement l’SBC lors de sa mise à jour ou lors de la maintenance. |False|Vrai<br/>False|Boolean|
 
## <a name="verify-the-sbc-connection"></a>Vérifier la connexion au SBC 

Pour vérifier la connexion : 
- Vérifiez si la SBC est sur la liste de SBCs couplés. 
- Valider les options SIP. 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Vérifier si la SBC est sur la liste de SBCs couplés 

Une fois que vous avez connecté la SBC, validez la présence de l’SBC dans la liste des éléments SBCs couplés en exécutant la commande suivante dans une session PowerShell distante : 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

La passerelle couplée doit apparaître dans la liste, comme illustré dans l’exemple ci-dessous, et le paramètre **Enabled** doit afficher la valeur **true**. 


Qui renvoie :
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a>Valider le flux d’options SIP 

Pour valider le jumelage à l’aide des options SIP sortants, utilisez l’interface de gestion des SBC et confirmez que l’SBC reçoit les réponses 200 OK à ses messages d’OPTIONS sortants.

Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages d’options SIP sortants au nom de domaine complet SBC configuré dans le champ d’en-tête de contact du message OPTIONS entrantes. 

Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion des SBC et voyez que l’SBC envoie une réponse aux messages d’OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
