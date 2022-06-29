---
title: Connecter votre contrôleur de frontière de session (SBC) au routage direct
ms.reviewer: fillipse
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
description: Découvrez comment configurer et connecter votre SBC au routage direct du système téléphonique Teams.
ms.openlocfilehash: e33f9538fdf69696e0a87da84dc5aec8e8d304af
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241103"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Connecter votre contrôleur de frontière de session (SBC) au routage direct

Cet article explique comment configurer un contrôleur de frontière de session (SBC) et le connecter au routage direct.  Il s’agit de l’étape 1 des étapes suivantes pour configurer le routage direct :

- **Étape 1. Connecter votre SBC avec le système téléphonique et valider la connexion** (cet article)
- Étape 2. [Activer les utilisateurs pour le routage direct](direct-routing-enable-users.md)
- Étape 3. [Configurer le routage des appels](direct-routing-voice-routing.md)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md)

Pour plus d’informations sur toutes les étapes nécessaires à la configuration du routage direct, consultez [Configurer le routage direct](direct-routing-configure.md).

Vous pouvez utiliser le [Centre d’administration Microsoft Teams](#using-the-microsoft-teams-admin-center) ou [PowerShell](#using-powershell) pour configurer et connecter un SBC au routage direct.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez à **Voice** > **Direct Routing**, puis cliquez sur l’onglet **SBC** .

2. Cliquez sur **Ajouter**.

3. Entrez un nom de domaine complet pour le SBC. <br><br>Assurez-vous que la partie nom de domaine du nom de domaine complet correspond à un domaine inscrit dans votre locataire et gardez à l’esprit que le `*.onmicrosoft.com` nom de domaine n’est pas pris en charge pour le nom de domaine FQDN SBC. Par exemple, si vous avez deux noms de domaine et `contoso.onmicrosoft.com`, `contoso.com` utilisez-le `sbc.contoso.com` comme nom SBC. Si vous utilisez un sous-domaine, assurez-vous que ce sous-domaine est également inscrit dans votre locataire. Par exemple, si vous souhaitez utiliser `sbc.service.contoso.com`, `service.contoso.com` vous devez être inscrit.

4. Configurez les paramètres suivants pour le SBC, en fonction des besoins de votre organisation. Pour plus d’informations sur chacun de ces paramètres, consultez [les paramètres SBC](#sbc-settings).

    ![Capture d’écran de la page Ajouter SBC dans le Centre d’administration Microsoft Teams.](media/direct-routing-add-sbc.png)

5. Une fois que vous avez terminé, cliquez sur **Enregistrer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Pour connecter votre SBC au routage direct, vous devez :

1. [Connectez-vous à Skype Entreprise Online à l’aide de PowerShell](#connect-to-skype-for-business-online-by-using-powershell).

2. [Connectez le SBC au locataire](#connect-the-sbc-to-the-tenant).

3. [Vérifiez la connexion SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Se connecter à Skype Entreprise Online à l’aide de PowerShell

Pour associer le SBC à l’interface de routage direct, utilisez une session PowerShell connectée au locataire. Pour ouvrir une session PowerShell, suivez les étapes décrites dans [Configurer votre ordinateur pour Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer le SBC. Pour vérifier les commandes, tapez ou copiez et collez la commande suivante dans la session PowerShell, puis appuyez sur Entrée : 

```PowerShell
Get-Command *onlinePSTNGateway*
```

La commande retourne les quatre fonctions affichées ici qui vous permettent de gérer le SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Connecter le SBC au locataire

Pour connecter le SBC au locataire, utilisez l’applet de commande [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . Dans une session PowerShell, tapez ce qui suit, puis appuyez sur Entrée :

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Nous vous recommandons de définir une limite maximale d’appels dans le SBC à l’aide des informations disponibles dans la documentation SBC. La limite déclenche une notification si le SBC est au niveau de la capacité.
  > 2. Vous ne pouvez connecter le SBC que si la partie domaine de son nom de domaine complet correspond à l’un des domaines enregistrés dans votre locataire, à l’exception \*de .onmicrosoft.com. L’utilisation \*de .onmicrosoft.com noms de domaine n’est pas prise en charge pour le nom de domaine complet SBC. Par exemple, si vous avez deux noms de domaine, **contoso.com** et **contoso.onmicrosoft.com**, vous pouvez utiliser sbc.contoso.com pour le nom SBC. Si vous essayez de connecter le SBC avec un nom tel que sbc.contoso.abc, le système ne vous le permet pas, car le domaine n’appartient pas à ce locataire.<br/>
  > Outre le domaine inscrit dans votre locataire, il est important qu’un utilisateur dispose de ce domaine et d’une licence E3 ou E5 affectée. Si ce n’est pas le cas, vous recevrez l’erreur suivante :<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. Plusieurs adresses IP mappées avec le même nom de domaine complet côté SBC ne sont pas prises en charge.

Voici un exemple :

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Qui retourne :

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
> Cet exemple montre uniquement les paramètres minimaux requis. Vous pouvez définir d’autres paramètres avec l’applet de commande [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) pendant le processus de connexion. Pour plus d’informations, consultez [les paramètres SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Vérifier la connexion SBC

Pour vérifier la connexion :

- [Vérifiez si le SBC figure dans la liste des SBC jumelés](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Validez les options SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Vérifier si le SBC figure dans la liste des SBC jumelés

Après avoir connecté le SBC, utilisez l’applet de commande [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) pour vérifier que le SBC est présent dans la liste des SBC jumelés. Tapez ce qui suit dans une session PowerShell distante, puis appuyez sur Entrée :

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

La passerelle jumelée doit apparaître dans la liste, comme indiqué dans l’exemple ci-dessous, et le paramètre **Activé** doit afficher la valeur **True**.

Qui retourne :

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

Pour valider le jumelage à l’aide des options SIP sortantes, utilisez l’interface de gestion SBC et vérifiez que le SBC reçoit 200 réponses OK à ses messages OPTIONS sortants.

Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages SIP Options sortants au nom de domaine complet SBC configuré dans le champ d’en-tête Contact du message OPTIONS entrant. 

Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion SBC et vérifiez que le SBC envoie une réponse aux messages OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.

## <a name="sbc-settings"></a>Paramètres SBC

Ce tableau répertorie les options que vous pouvez définir pour le SBC dans le Centre d’administration Microsoft Teams et à l’aide de l’applet de commande [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) .

|Obligatoire?|Paramètre du Centre d’administration Teams|Paramètre PowerShell|Description|Par défaut|Valeurs possibles|Type et restrictions|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Oui|**Ajouter un nom de domaine complet pour le SBC**|FQDN |Aucun|Nom du nom de domaine complet, limite de 63 caractères|Chaîne, consultez la liste des caractères autorisés et non autorisés dans les conventions d’affectation de noms [dans Active Directory pour les ordinateurs, les domaines, les sites et les unités d’organisation](https://support.microsoft.com/help/909264)|
|Non|**Activé**|Activé|Permet d’activer le SBC pour les appels sortants. Vous pouvez l’utiliser pour supprimer temporairement le SBC du service pendant sa mise à jour ou pendant la maintenance. |False|Vrai<br/>False|Boolean|
|Oui|**Port de signalisation SIP**|SipSignalingPort |Il s’agit du port d’écoute utilisé pour communiquer avec le routage direct à l’aide du protocole TLS (Transport Layer).|Aucun|N’importe quel port|0 à 65535 |
|Non|**Envoyer des options SIP**|SendSIPOptions |Définit si le SBC enverra des messages d’options SIP. Nous vous recommandons vivement d’activer ce paramètre. Lorsque ce paramètre est désactivé, le SBC est exclu du système de surveillance et d’alerte.|Vrai|Vrai<br/>False|Boolean|
|Non|**Historique des appels transférés**|ForwardCallHistory |Indique si les informations d’historique des appels sont transférées via la jonction. Lorsque vous activez cette option, le proxy Microsoft 365 envoie un en-tête Historique et Informations référencées. |False|Vrai<br/>False|Boolean|
|Non|**Transférer l’en-tête P-Asserted-identity (PAI)**|ForwardPAI|Indique si l’en-tête PAI est transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant. Si ce paramètre est activé, l’en-tête Privacy:ID est également envoyé.|False|Vrai<br/>False|Boolean|
|Non|**Capacité d’appel simultanée**|MaxConcurrentSessions |Lorsque vous définissez une valeur, le système d’alerte vous avertit lorsque le nombre de sessions simultanées est supérieur ou égal à 90 % de cette valeur. Si vous ne définissez pas de valeur, les alertes ne sont pas générées. Toutefois, le système de surveillance signale le nombre de sessions simultanées toutes les 24 heures. |Null|Null<br/>1 à 100 000 ||
|Non|**Codes de réponse de basculement**|FailoverResponseCodes<br>|Si le routage direct reçoit un code d’erreur SIP 4xx ou 6xx en réponse à une invitation sortante, l’appel est considéré comme terminé par défaut. Sortant signifie un appel d’un client Teams au rtc avec flux de trafic : client Teams -> Routage direct -> SBC -> réseau téléphonique). Lorsque vous spécifiez un code de réponse de basculement, cela force le routage direct à essayer un autre SBC (s’il existe un autre SBC dans la stratégie de routage vocal de l’utilisateur) lorsqu’il reçoit les codes spécifiés si le SBC ne peut pas effectuer d’appel en raison de problèmes réseau ou autres. Pour plus d’informations, consultez [basculement de codes SIP spécifiques reçus du contrôleur de bordure de session (SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|Non|**Temps de basculement (secondes)**|FailoverTimeSeconds |Lorsque vous définissez une valeur, les appels sortants qui ne sont pas répondus par la passerelle dans le délai que vous définissez sont routés vers la jonction disponible suivante. S’il n’y a pas de jonctions supplémentaires, l’appel est automatiquement supprimé. La valeur par défaut est 10 secondes. Dans une organisation avec des réseaux lents et des réponses de passerelle, cela peut entraîner la suppression inutile des appels.|10|Numéro|Int|
|Non|**Pays ou région préféré pour le trafic multimédia**|MediaRelayRoutingLocationOverride | Non applicable au routage direct. Ce paramètre est réservé pour une utilisation avec des opérateurs gérés dans les forfaits d’appels |Aucun|||
|Non|**SBC prend en charge PIDF/LO pour les appels d’urgence**|PidfloSupported|Spécifiez si le SBC prend en charge l’objet PIDF/LO (Presence Information Data Format Location Object) pour les appels d’urgence.||||
|Non| - |MediaBypass|Ce paramètre indique si le SBC prend en charge le contournement multimédia et si vous souhaitez l’utiliser pour ce SBC. |Aucun|Vrai<br/>False|Boolean|

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)
