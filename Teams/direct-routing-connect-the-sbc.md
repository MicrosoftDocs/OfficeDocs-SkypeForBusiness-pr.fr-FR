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
description: Apprenez à configurer et connecter votre SBC au routage direct du système téléphonique.
ms.openlocfilehash: 8ceb4d1811b479fbcdc0d4ca83f4dbc4672227bd
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691260"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connecter votre contrôleur de bordure de session (SBC) au routage direct

Cet article décrit la configuration d’un contrôleur de bordure de session (SBC) et la connexion au routage direct du système téléphonique.  Pour configurer le routage direct, vous devez procéder comme suit :

- **Étape 1. Connectez votre SBC avec votre système téléphonique et validez la connexion** (cet article)
- Étape 2. [Activer les utilisateurs pour le routage direct](direct-routing-enable-users.md)
- Étape 3. [Configurer le routage des appels](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Pour plus d’informations sur la procédure à suivre pour configurer le routage direct, voir [configurer le routage direct](direct-routing-configure.md).

Vous pouvez utiliser le [Centre d’administration Microsoft teams](#using-the-microsoft-teams-admin-center) ou [PowerShell](#using-powershell) pour configurer et connecter un SBC pour le routage direct.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche **Voice**, sélectionnez  >  **routage direct**de la voix, puis cliquez sur l’onglet **SBCS** .
2. Cliquez sur **Ajouter**.
3. Entrez un nom de domaine complet pour l’SBC. <br><br>Assurez-vous que la partie Domain Name du nom de domaine complet correspond à un domaine inscrit dans votre client et gardez à l’esprit que le `*.onmicrosoft.com` nom de domaine n’est pas pris en charge pour le nom de domaine de nom de domaine complet SBC. Par exemple, si vous avez deux noms de domaine `contoso.com` et `contoso.on.microsoft.com` que vous utilisez `sbc.contoso.com` le nom SBC.
4. Configurez les paramètres suivants pour SBC, en fonction des besoins de votre organisation. Pour plus d’informations sur chacun de ces paramètres, voir [paramètres de SBC](#sbc-settings).

    ![Capture d’écran de la page Ajouter un SBC dans le centre d’administration Microsoft teams](media/direct-routing-add-sbc.png)

5. Une fois que vous avez terminé, cliquez sur **Enregistrer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Pour connecter votre SBC au routage direct, vous devez effectuer les opérations suivantes :

1. [Connectez-vous à Skype entreprise Online à l’aide de PowerShell](#connect-to-skype-for-business-online-by-using-powershell).
2. [Connectez l’SBC au client](#connect-the-sbc-to-the-tenant).
3. [Vérifiez la connexion de l’SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Se connecter à Skype entreprise Online à l’aide de PowerShell

Vous pouvez utiliser une session PowerShell connectée au client pour jumeler l’interface SBC à l’interface de routage directe. Pour ouvrir une session PowerShell, suivez les étapes décrites dans [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer l’SBC. Pour vérifier les commandes, tapez ou copiez-collez la commande suivante dans la session PowerShell, puis appuyez sur entrée : 

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

### <a name="connect-the-sbc-to-the-tenant"></a>Connecter l’SBC au client

Utilisez l’applet de nouvelle applet de [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) pour connecter l’SBC au client. Dans une session PowerShell, tapez ce qui suit, puis appuyez sur entrée :

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Nous vous recommandons de définir une limite d’appels maximale dans l’SBC à l’aide d’informations qui figurent dans la documentation SBC. La limite déclenche une notification si l’SBC a le niveau de capacité.
  > 2. Vous pouvez uniquement connecter l’SBC si la partie Domain de son nom de domaine complet correspond à l’un des domaines inscrits dans votre client, à l’exception de \* . onmicrosoft.com. L’utilisation \* des noms de domaine. onmicrosoft.com n’est pas prise en charge pour le nom de domaine complet SBC. Par exemple, si vous avez deux noms de domaine, **contoso**. com et **contoso**. onmicrosoft.com, vous pouvez utiliser SBC. contoso. con pour le nom SBC. Si vous tentez de vous connecter à l’SBC avec un nom tel que SBC. contoso. ABC, le système ne vous permet pas, car le domaine n’est pas détenu par ce client.<br/>
  > Outre le domaine enregistré dans votre client, il est important de disposer d’un utilisateur avec ce domaine et d’une licence E3 ou E5 affectée. Si ce n’est pas le cas, vous recevez le message d’erreur suivant :<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Voici un exemple :

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Qui renvoie :

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

> [!NOTE]
> Cet exemple montre uniquement les paramètres obligatoires minimum. D’autres paramètres peuvent être définis à l’aide de l’applet [de nouvelle-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) au cours du processus de connexion. Pour en savoir plus, voir [paramètres de SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Vérifier la connexion au SBC

Pour vérifier la connexion :

- [Vérifiez si la SBC est sur la liste de SBCS couplés](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Valider les options SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Vérifier si la SBC est sur la liste de SBCs couplés

Une fois que vous avez connecté la SBC, utilisez l’applet de connexion [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) pour vérifier que l’SBC est présent dans la liste de SBCS couplés. Tapez la commande suivante dans une session PowerShell distante, puis appuyez sur entrée :

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

#### <a name="validate-sip-options"></a>Valider les options SIP

Pour valider le jumelage à l’aide des options SIP sortants, utilisez l’interface de gestion des SBC et confirmez que l’SBC reçoit les réponses 200 OK à ses messages d’OPTIONS sortants.

Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages d’options SIP sortants au nom de domaine complet SBC configuré dans le champ d’en-tête de contact du message OPTIONS entrantes. 

Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion des SBC et voyez que l’SBC envoie une réponse aux messages d’OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.

## <a name="sbc-settings"></a>Paramètres de SBC

Le tableau suivant répertorie les options que vous pouvez définir pour l’SBC dans le centre d’administration Microsoft teams et à l’aide de la cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) .

|Obligatoire?|Paramètre du centre d’administration Microsoft teams|Paramètre PowerShell|Description|Par défaut|Valeurs possibles|Type et restrictions|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Oui|**Ajouter un nom de domaine complet pour l’SBC**|FQDN |Aucun|Nom de domaine complet, limite de 63 caractères|, Voir la liste des caractères autorisés et interdits sur [les conventions d’appellation dans Active Directory pour les ordinateurs, domaines, sites et UO](https://support.microsoft.com/help/909264) .|
|Non|**Activé**|Activé|Permet d’activer l’SBC pour les appels sortants. Vous pouvez utiliser cette opération pour supprimer temporairement l’SBC du service lors de sa mise à jour ou de sa maintenance. |False|Vrai<br/>False|Boolean|
|Oui|**Port de signalisation SIP**|SipSignalingPort |Il s’agit du port d’écoute utilisé pour communiquer avec le routage direct via le protocole TLS (Transport Layer).|Aucun|Tout port|entre 0 et 65535 |
|Non|**Envoyer les options SIP**|SendSIPOptions |Définit si les SBC envoient des messages d’options SIP. Nous vous recommandons vivement d’activer ce paramètre. Lorsque ce paramètre est désactivé, l’SBC est exclu du système de surveillance et d’alerte.|Vrai|Vrai<br/>False|Boolean|
|Non|**Transférer l’historique des appels**|ForwardCallHistory |Indique si les informations de l’historique des appels sont transmises via le Trunk. Lorsque vous activez cette fonction, le proxy Microsoft 365 ou Office 365 envoie un en-tête de rapport historique et de référence. |False|Vrai<br/>False|Boolean|
|Non|**Forward P-assertion-Identity (PAI) en-tête**|ForwardPAI|Indique si l’en-tête PAI est transmis en même temps que l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant. Si ce paramètre est activé, l’en-tête de confidentialité : ID est également envoyé.|False|Vrai<br/>False|Boolean|
|Non|**Capacité d’appel simultanée**|MaxConcurrentSessions |Lorsque vous définissez une valeur, le système d’alerte vous avertit lorsque le nombre de sessions simultanées est de 90% ou une valeur supérieure à celle-ci. Si vous ne définissez pas de valeur, les alertes ne sont pas générées. Toutefois, le système de surveillance rapportera le nombre de sessions simultanées toutes les 24 heures. |Valeur|Valeur<br/>1 à 100 000 ||
|Non|**Code de réponse de basculement**|FailoverResponseCodes<br>|Si le routage direct reçoit tout code d’erreur SIP 4xx ou 6xx en réponse à une invitation sortante, l’appel est considéré comme complet par défaut. Sortant désigne un appel d’un client teams vers le RTC avec le flux de trafic : client teams-> le routage direct-> le réseau de téléphonie de l’SBC->). Lorsque vous spécifiez un code de réponse de basculement, cela force le routage direct à essayer un autre SBC (si un autre SBC existe dans la stratégie de routage vocale de l’utilisateur) lorsqu’il reçoit les codes spécifiés si la SBC ne peut pas faire un appel en raison de problèmes réseau ou d’autres problèmes. Pour en savoir plus, voir [basculement de codes SIP spécifiques reçus du contrôleur de bordure de session (SBC)](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Ent|
|Non|**Temps de basculement (secondes)**|FailoverTimeSeconds |Lorsque vous définissez une valeur, les appels sortants qui ne sont pas traités par la passerelle au cours de la période que vous définissez sont routés vers le Trunk disponible suivant. S’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu. La valeur par défaut est 10 secondes. Dans une organisation avec des réseaux lents et des réponses par passerelle, il est possible que les appels soient interrompus de façon inobligatoire.|0,10|Numéro|Ent|
|Non|**Pays ou région préférés pour le trafic multimédia**|MediaRelayRoutingLocationOverride |Permet de définir manuellement votre pays ou région préféré pour le trafic multimédia. Nous vous recommandons de définir cette valeur uniquement si les journaux d’appels indiquent clairement que l’affectation par défaut du centre de fichiers pour le chemin multimédia n’utilise pas le chemin le plus proche du centre de médias SBC. Par défaut, le routage direct attribue un centre de distribution en fonction de l’adresse IP publique de l’SBC et sélectionne toujours le chemin le plus proche du centre de distribution SBC. Toutefois, dans certains cas, le chemin d’accès par défaut ne sera peut-être pas le chemin optimal. Ce paramètre vous permet de définir manuellement la région préférée pour le trafic multimédia. |Aucun|Codes de pays au format ISO||
|Non|**Le SBC prend en charge PIDF/LO pour les appels d’urgence**|PidfloSupported|Spécifiez si l’SBC prend en charge l’objet d’emplacement du format de données de présence (PIDF/min) pour les appels d’urgence.||||
|Non|**Sonnerie du téléphone lors du recherche de l’utilisateur**|GenerateRingingWhileLocatingUser|Définissez si un signal audio est lu pour l’appelant pour indiquer que les équipes sont dans le processus de création de l’appel. Ce paramètre s’applique uniquement au routage direct en mode de contournement non multimédia. Parfois, les appels entrants des clients RTC aux équipes peuvent prendre plus de temps que prévu. Lorsque c’est le cas, l’appelant n’entend rien, le client Teams ne sonne pas et l’appel peut être annulé par certains fournisseurs de télécommunications. Ce paramètre permet d’éviter les silences inattendus qui peuvent se produire dans les cas suivants.|Vrai|Vrai<br/>False|Boolean|
|Non| - |MediaBypass|Ce paramètre indique si l’SBC prend en charge la dérivation multimédia et si vous voulez l’utiliser pour cet élément SBC. |Aucun|Vrai<br/>False|Boolean|

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)
