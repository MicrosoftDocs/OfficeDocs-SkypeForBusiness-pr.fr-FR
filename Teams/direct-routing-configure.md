---
title: Configurer le routage Direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Découvrez comment configurer le routage Direct de Microsoft Phone System.
ms.openlocfilehash: e3551cf245b14a69fc9fd3731848c2bf2c006cc8
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870044"
---
# <a name="configure-direct-routing"></a>Configurer le routage Direct

Si vous n’avez pas déjà fait, lisez la [Planifier le routage Direct](direct-routing-plan.md) pour les composants requis et pour passer en revue les autres étapes, vous devrez prendre avant de configurer votre réseau de système téléphonique de Microsoft. 

Cet article explique comment configurer le routage Direct de Microsoft Phone System. Il décrit en détail comment associer un contrôleur de bordure Session pris en charge (SBC) pour le routage Direct et configurer les utilisateurs de Microsoft Teams pour utiliser le routage directe pour se connecter à la Public téléphone réseau commuté (RTC). Pour effectuer les étapes décrites dans cet article, les administrateurs doivent se familiariser avec les applets de commande PowerShell. Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Nous vous recommandons de vérifier que votre contrôleur SBC a déjà été configuré comme recommandé par votre fournisseur SBC : 

- Documentation de déploiement AudioCodes 
- Documentation de déploiement de Communications de ruban

Vous pouvez configurer votre système téléphonique de Microsoft et permettre aux utilisateurs d’utiliser le routage Direct, puis configurer Teams Microsoft en tant que client appelant par défaut en procédant comme suit : 

- [Paire le contrôleur SBC avec un système téléphonique de Microsoft et valider l’appariement](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [Activer les utilisateurs pour le Service de routage Direct](#enable-users-for-direct-routing-service)
- [Assurez-vous que Microsoft Teams est le client appelant par défaut pour les utilisateurs](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a>Paire le contrôleur SBC pour diriger le Service de routage du système téléphonique 

Voici les trois étapes principales pour vous permettre de vous connecter, ou paire, le contrôleur SBC à l’interface de routage Direct : 

- Se connecter au centre d’administration de **Skype pour Business Online** à l’aide de PowerShell 
- Paire le contrôleur SBC 
- Valider l’appariement 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a>Se connecter à Skype pour Business Online à l’aide de PowerShell 

Vous pouvez utiliser une session PowerShell connectée au client pour le couplage le contrôleur SBC à l’interface de routage Direct. Pour ouvrir une session PowerShell, suivez les étapes décrites dans la [configuration de votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer le contrôleur SBC. Pour valider les commandes, tapez ou copier/coller dans ce qui suit dans la session PowerShell et appuyez sur ENTRÉE : 

```
gcm *onlinePSTNGateway*
```

Votre commande renverra les quatre fonctions indiquées ici qui vous permet de gérer les SBCs. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Paire le contrôleur SBC au client 

Pour associer le contrôleur SBC au client, dans la session PowerShell, tapez ce qui suit et appuyez sur ENTRÉE : 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Nous vous recommandons la définition d’une limite pour le contrôleur SBC, en utilisant les informations que vous trouverez dans la documentation de SBC. La limite de déclencher une notification si le contrôleur SBC est au niveau de la capacité.
  > 2. Vous pouvez uniquement paire le contrôleur SBC avec le nom de domaine complet, où la partie domaine du nom correspond à l’un des domaines enregistrés dans votre client, à l’exception de \*. onmicrosoft.com. À l’aide de \*. omicrosoft.com les noms de domaine n’est pas pris en charge pour les noms FQDN SBC. Par exemple, si vous avez deux noms de domaine :<br/><br/>
  > .xyz **ABC**<br/>**ABC**. onmicrosoft.com<br/><br/>
  > Pour le nom SBC, vous pouvez utiliser le nom sbc.abc.xyz. Si vous essayez de paire le contrôleur SBC avec un nom de sbc.xyz.abc, le système ne vous permettra pas, comme le domaine n’est pas détenu par ce client.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Propriété renvoie :
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
Il existe des options supplémentaires qui peuvent être définies lors de l’appariement. Dans l’exemple précédent, toutefois, seulement la configuration minimale requise paramètres sont affichés. 
 
Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser dans la définition des paramètres de *New-CsOnlinePstnGateway*. 

|Obligatoire ?|Nom|Description|Par défaut|Valeurs possibles|Type et restrictions|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Oui|FQDN|Le nom de domaine complet de le SBC |Aucun|Nom de NoneFQDN, limite 63 caractères|Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’attribution de noms dans Active Directory pour les ordinateurs, les domaines, les sites et les unités d’organisation](https://support.microsoft.com/help/909264)|
|Non|MediaBypass |Le paramètre est réservé pour une utilisation future. Paramètre indiqué du contrôleur SBC prend en charge le contournement de média et l’administrateur souhaite l’utiliser.|Aucun|True<br/>Faux|Boléen|
|Oui|SipSignallingPort |Port d’écoute utilisé pour communiquer avec les services de routage Direct à l’aide du protocole de Transport Layer Security (TLS).|Aucun|N’importe quel port|comprise entre 0 et 65535 |
|Non|FailoverTimeSeconds |Lorsque la valeur 10 (valeur par défaut), les appels sortants qui ne sont pas traitées par la passerelle dans les 10 secondes sont routés vers le tronçon suivant disponible ; s’il n’y a aucune jonctions supplémentaires, l’appel est automatiquement supprimé. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels. La valeur par défaut est 10.|10|Numéro|Int|
|Non|ForwardCallHistory |Indique si les informations d’historique d’appel sont transférées par le biais de la jonction. Si activé, le Proxy de PSTN Office 365 envoie deux en-têtes : historique-info et visé par. La valeur par défaut est **False** ($False). |Faux|True<br/>Faux|Boléen|
|Non|ForwardPAI|Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI est un moyen de vérifier l’identité de l’appelant. La valeur par défaut est **False** ($False).|Faux|True<br/>Faux|Boléen|
|Non|SendSIPOptions |Définit si un contrôleur SBC sera ou n’envoie pas les options SIP. Si désactivé, le contrôleur SBC sera exclu de système de surveillance et d’alerte. Il est vivement recommandé d’activer les options de SIP. Valeur par défaut est **True**. |True|True<br/>Faux|Boléen|
|Non|MaxConcurrentSessions |Utilisé par le système d’alerte. Lorsqu’une valeur est définie, le système d’alerte génère une alerte à l’administrateur de clients lorsque le nombre de sessions simultanées est 90 % ou supérieure à cette valeur. Si le paramètre n’est pas défini, les alertes ne sont pas générés. Toutefois, le système de surveillance signalera nombre de sessions simultanées toutes les 24 heures. |Null|Null<br/>1 et 100 000 ||
|Non|Activé *|Permet d’activer cette SBC pour les appels sortants. Peut être utilisée pour supprimer temporairement le contrôleur SBC, pendant qu’il est en cours de mise à jour ou lors de la maintenance. |Faux|True<br/>Faux|Boléen|
 
### <a name="verify-the-sbc-pairing"></a>Vérifiez l’appariement SBC 

Vérifiez la connexion : 
- Vérifiez si le contrôleur SBC est dans la liste des paires SBCs. 
- Valider les Options SIP. 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a>Valider si SBC se trouve dans la liste des paires SBCs 

Après avoir paire le contrôleur SBC, vérifier que le contrôleur SBC est présent dans la liste des paires SBCs en exécutant la commande suivante dans une session PowerShell distante :`Get-CSOnlinePSTNGateway`

La passerelle couplée doit apparaissent dans la liste, comme illustré dans l’exemple ci-dessous, puis vérifiez que le paramètre *Enabled* affiche la valeur **True**. Entrez :

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Qui retourne :
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

#### <a name="validate-sip-options-flow"></a>Contrôler le flux d’Options SIP 

Pour valider l’association à l’aide des Options SIP sortant, utilisez l’interface de gestion SBC et voir que le contrôleur SBC 200 OK réponses aux OPTIONS sortantes.
  
Lorsque le routage Direct voit des OPTIONS entrantes, il démarre sortantes options d’envoi pour le nom de domaine complet SBC configuré dans le champ en-tête de Contact dans le message entrant d’OPTIONS. 

Pour valider l’association à l’aide des Options SIP entrants, utilisez l’interface de gestion SBC et voir que le contrôleur SBC réponse sur les messages OPTIONS provenant routage Direct, et que le code de réponse est 200 OK.  

## <a name="enable-users-for-direct-routing-service"></a>Activer les utilisateurs pour le Service de routage Direct 

Lorsque vous êtes prêt à activer les utilisateurs pour le Service de routage Direct, procédez comme suit : 

1. Créer un utilisateur dans Office 365 et attribuer une licence de système téléphonique. 
2. Assurez-vous que l’utilisateur est hébergé dans Skype pour Business Online. 
3. Configurer le numéro de téléphone et activer la messagerie vocale et enterprise voice. 
4. Configurer le routage des communications vocales. L’itinéraire est automatiquement validé.  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Créer un utilisateur dans Office 365 et attribuer la licence 

Il existe deux options pour la création d’un nouvel utilisateur dans Office 365. Toutefois, nous conseillons de votre organisation sélectionner une option permet d’éviter les problèmes de routage : 

- Créer l’utilisateur dans Active Directory de locaux et synchroniser l’utilisateur vers le nuage. Voir les [répertoires intégrer votre locale avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).  
- Créer l’utilisateur directement dans le portail d’administrateur Office 365. Consultez la rubrique [Ajouter des utilisateurs individuellement ou par lot pour Office 365 - aide d’administration](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

  Si vous générez le système coexiste avec Skype pour Business 2015 ou Lync 2010/2013 locale, la seule option prise en charge consiste à créer l’utilisateur dans l’annuaire local et synchronisation de l’utilisateur vers le nuage (Option 1). 

Licences requises : 

- Office 365 entreprise E3 (y compris SfB Plan2, Plan2 Exchange et les équipes) + système de téléphone.  
- Office 365 entreprise E5 (y compris SfB Plan2 Plan2 Exchange et les équipes système téléphonique) 

Licences facultatifs : 

- Appel de Plan 
- Audioconférence 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Assurez-vous que l’utilisateur est hébergé dans Skype pour Business Online 

Routage direct, l’utilisateur doit être hébergé dans Skype pour Business Online. Vous pouvez le vérifier en regardant le paramètre RegistrarPool. Il doit avoir une valeur dans le domaine infra.lync.com.

1. Se connecter à PowerShell à distance.
2. Exécutez la commande : 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurer le numéro de téléphone et activer la messagerie vocale et enterprise voice 

Après avoir créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer leur numéro de téléphone et la messagerie vocale. Pour cela, en une seule étape. 

Pour ajouter le numéro de téléphone et activer pour la messagerie vocale :
 
1. Se connecter à une session PowerShell distante. 
2. Entrez la commande : 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Spencer faible », entrez ce qui suit : 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Le numéro de téléphone utilisé doit être configuré comme un numéro de téléphone E.164 complète avec le code de pays. 

  > [!NOTE]
  > Si le numéro de téléphone de l’utilisateur est géré sur site, utilisez locale Skype pour Business Management Shell ou le panneau de configuration pour configurer le numéro de téléphone de l’utilisateur. 

### <a name="configure-voice-routing"></a>Configurer le routage des communications vocales 

Système téléphonique de Microsoft dispose d’un mécanisme de routage qui permet à un appel à envoyer à un SBC spécifique en fonction de : 

- Modèle de numéro appelé 
- Modèle de numéro appelé + utilisateur spécifique qui effectue l’appel
 
SBC peut être désignés comme actif et de sauvegarde. Cela signifie que lorsque la SBC est configuré comme active pour ce modèle de numéro, ou un modèle de numéro + un utilisateur spécifique, n’est pas disponible, puis les appels sont acheminés vers un contrôleur SBC sauvegarde.
 
Routage des appels est composé des éléments suivants : 
- Stratégie de routage voix – conteneur pour les utilisations RTC ; peuvent être attribuées à un utilisateur ou à plusieurs utilisateurs 
- Utilisations PSTN – conteneur pour les itinéraires de communications vocales et les utilisations RTC ; peuvent être partagées dans différentes stratégies de routage des communications vocales 
- Itinéraires-modèle de numéro et un ensemble de Online passerelles PSTN à utiliser pour les appels où l’appel de numéro correspond au modèle de voix 
- Passerelle PSTN Online - pointeur SBC, stocke également la configuration est appliquée lors de l’appel est passé via le contrôleur SBC, telles que le transfert P-Asserted-Identity (PAI) ou Codecs par défaut ; peuvent être ajoutés à des itinéraires de communications vocales 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Création d’une stratégie de routage des communications vocales avec une seule utilisation PSTN 

Le diagramme suivant illustre les deux exemples de stratégies de routage voix dans le flux d’appels.

**Appel flux 1 (à gauche) :** Si un utilisateur effectue un appel à XXX-XX-XX +1 425 ou XXX-XX-XX +1 206, l’appel est acheminé vers SBC sbc1<span></span>. contoso.biz ou sbc2<span></span>. contoso.biz. Si ni sbc1<span></span>. contoso.biz, ni sbc2<span></span>. contoso.biz sont disponibles, l’appel est abandonné. 

**Call flux 2 (à droite) :** Si un utilisateur effectue un appel à XXX-XX-XX +1 425 ou XXX-XX-XX +1 206, l’appel est tout d’abord dirigé vers SBC sbc1<span></span>. contoso.biz ou sbc2<span></span>. contoso.biz. Si aucun contrôleur SBC est disponible, l’itinéraire dont la priorité est tentée (sbc3<span></span>. contoso.biz et sbc4<span></span>. contoso.biz). Si aucune des SBCs n’est disponibles, l’appel est abandonné. 

![Présente des exemples de stratégie de routage voix](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Dans les deux exemples, tandis que l’itinéraire de communications vocales est assignée les priorités, les SBCs dans les itinéraires sont traités dans l’ordre aléatoire.

  > [!NOTE]
  > À moins que l’utilisateur a également une licence Plan de l’appel de Microsoft, les appels vers n’importe quel nombre à l’exception des numéros qui correspondent à des modèles + XXX-XX-XX +1 425 ou +1 206 XXX XX XX dans l’exemple de configuration sont supprimées. Si l’utilisateur possède une licence de planifier l’appel, l’appel est acheminé automatiquement en fonction des stratégies de l’appel de Plan Microsoft. 

Le Plan d’appel de Microsoft s’applique automatiquement en tant que dernier à tous les utilisateurs dont la licence de l’appel de Plan de Microsoft et ne nécessite pas de configuration du routage des appels supplémentaires.

Dans l’exemple illustré dans le diagramme suivant, un itinéraire de communications vocales est ajouté pour envoyer les appels vers tous les autres États-Unis et du Canada numéro (appels qui accèdent à un modèle de numéro appelé + 1 XXX XXX XX XX).

![Stratégie de routage avec un itinéraire tiers de voix affiche](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Si l’utilisateur a les deux licences (système téléphonique de Microsoft et Microsoft appel de Plan) itinéraire automatique est utilisée pour tous les autres appels. Si rien ne correspond au numéros modèles créés par l’administrateur en ligne itinéraires des communications vocales, l’itinéraire par le biais de l’appel de Plan de Microsoft.

Si l’utilisateur a Microsoft Phone System, l’appel est supprimé, car aucune règle correspondante n’est disponibles.

  > [!NOTE]
  > Valeur de la priorité d’itinéraire « Autres + 1 » n’a aucune importance dans ce cas, comme c’est le seul itinéraire qui correspond au modèle + 1 XXX XXX XX XX. Si un utilisateur effectue un appel à + 1 324 567 89 89 et à la fois sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.

Le tableau suivant récapitule la configuration à l’aide de trois itinéraires de communications vocales. Dans cet exemple, tous les itinéraires de trois font partie de la même utilisation PSTN « Nous et Canada ».

|**Utilisation PSTN**|**Itinéraire de communications vocales**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nous uniquement|« Redmond 1 »|^\\+ 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Itinéraire actif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206|
|Nous uniquement|« Redmond 2 »|^\\+ 1 (425\|206)(\d{7})$|2|SBC3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Itinéraire alternatif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206|
|Nous uniquement|« Autres + 1 »|^\\+ 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Routage de numéros appelés + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206)|
|||||||

Tous les itinéraires sont associés à l’utilisation PSTN « Nous et Canada » et l’utilisation RTC est associée à la stratégie de routage voix « US uniquement ». Dans cet exemple, la stratégie de routage voix est attribuée à l’utilisateur Spencer Low.

#### <a name="examples-of-call-routes"></a>Exemples d’itinéraires d’appels

Dans l’exemple suivant, nous vous montrer comment configurer des itinéraires, des utilisations PSTN et des stratégies de routage et nous attribuer la stratégie à l’utilisateur.

**Étape 1 :** Créer l’utilisation PSTN « États-Unis et au Canada. »

Dans un Skype de session Business Remote PowerShell, tapez :

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

Vérifiez que l’utilisation a été créée en entrant : 
```
Get-CSOnlinePSTNUsage
``` 
Qui retourne une liste de noms qui peuvent être tronqués :
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de la commande PowerShell *`(Get-CSOnlinePSTNUsage).usage`* pour afficher les noms complets (non tronquées).    
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

**Étape 2 :** Dans une session dans Skype pour Business Online PowerShell, créez des trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme indiqué dans le tableau précédent. 

Pour créer l’itinéraire « Redmond 1 », entrez :

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Qui retourne :
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
Pour créer l’itinéraire Redmond 2, entrez :

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Pour créer l’itinéraire de + 1 autres, entrez :

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide. Vous pouvez tester à l’aide de ce site Web :[https://www.regexpal.com](https://www.regexpal.com)

Dans certains cas, il est nécessaire pour acheminer tous les appels vers la même SBC ; Utilisez - NumberPattern «. * »

- Tous les appels vers la même SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Valider que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande Powershell à l’aide des options comme : 

```
New-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
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
NumberPattern       : ^\\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

Dans l’exemple, l’itinéraire « Autres + 1 » a été attribué automatiquement priorité. 

**Étape 3 :** Créer une stratégie de routage voix « Nous uniquement » et l’ajouter à la stratégie de l’utilisation PSTN « États-Unis et au Canada. »

Dans une session dans Skype pour Business Online PowerShell, tapez :

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Le résultat est indiqué dans cet exemple :

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Étape 4 :** Accorder à l’utilisateur Spence Low une stratégie de routage voix à l’aide de PowerShell.

- Dans une session dans Skype pour Business Online Powershell, tapez :

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Valider l’affectation de stratégie en entrant la commande suivante :

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Qui retourne :
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Création d’une stratégie de routage des communications vocales avec plusieurs utilisations PSTN

La stratégie de routage des communications vocales créée précédemment n’autorise les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de l’appel de Plan de Microsoft est également affectée à l’utilisateur.

Dans l’exemple qui suit, vous ne pouvez créer la stratégie de routage voix « Aucune restriction ». La stratégie réutilise l’utilisation PSTN « Nous et Canada » créé dans l’exemple précédent, ainsi que la nouvelle utilisation PSTN « International ». 

Cela achemine tous les autres appels vers le sbc2 SBCs<span></span>. contoso.biz et sbc5<span></span>. contoso.biz. Les exemples figurent attribuer des États-Unis uniquement une stratégie à l’utilisateur « Spencer faible » et sans Restrictions à l’utilisateur « John Woods ».

Spencer faible – appels autorisés uniquement aux États-Unis et au Canada numéros. Lors de l’appel à la plage de numéros de Redmond, le jeu spécifique de SBC doit être utilisé. Les numéros non US seront acheminés pas, sauf si la licence de planifier l’appel est attribuée à l’utilisateur.

John Woods – appels autorisés à n’importe quel nombre. Lors de l’appel à la plage de numéros de Redmond, le jeu spécifique de SBC doit être utilisé. Les numéros non US seront acheminés via sbc2<span></span>. contoso.biz et sbc5<span></span>. contoso.biz.

![Indique la stratégie de routage voix attribuée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Si l’utilisateur a les deux licences (système téléphonique de Microsoft et Microsoft appel de Plan) itinéraire automatique est utilisée pour tous les autres appels. Si rien ne correspond au numéros modèles créés par l’administrateur en ligne itinéraires des communications vocales, l’itinéraire par le biais de l’appel de Plan de Microsoft.

Si l’utilisateur a Microsoft Phone System, l’appel est supprimé, car aucune règle correspondante n’est disponibles.

![Indique la stratégie de routage voix attribuée à l’utilisateur John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Le tableau suivant récapitule les itinéraires de communications vocales et de dénomination de l’utilisation de routage stratégie « No Restrictions ». 

|**Utilisation PSTN**|**Itinéraire de communications vocales**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nous uniquement|« Redmond 1 »|^ + 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Gamme active pour les numéros appelé XXX-XX-XX +1 425 ou XXX-XX-XX +1 206|
|Nous uniquement|« Redmond 2 »|^ + 1 (425\|206)(\d{7})$|2|SBC3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Itinéraire alternatif pour les numéros appelé XXX-XX-XX +1 425 ou XXX-XX-XX +1 206|
|Nous uniquement|« Autres + 1 »|^ + 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Itinéraire pour appelé numéros + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206)|
|International|International|\d+|4|sbc2<span></span>. contoso.biz<br/>sbc5<span></span>. contoso.biz|Itinéraire pour n’importe quel modèle de numéro |


  > [!NOTE]
  > - L’ordre des utilisations PSTN dans les stratégies de routage voix est essentielle. Les utilisations sont appliquées dans l’ordre, et si une correspondance est trouvée dans la première utilisation, puis autres utilisations ne sont jamais évaluées. L’utilisation PSTN « International » doit être placée après l’utilisation PSTN « Nous uniquement. » Pour modifier l’ordre des utilisations PSTN, exécutez le `Set-CSOnlineRouteRoutingPolicy` commande. <br/>Par exemple, pour modifier l’ordre de « Nous et Canada » deuxième prénom et « International » à l’ordre inverse exécutez :<br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorité de « Autres + 1 » et « International » des itinéraires sont affectés automatiquement. Ils n’a pas d’importance tant qu’ils ont des priorités inférieures à « Redmond 1 » et « Redmond 2 ».

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Exemple de la stratégie de routage voix pour l’utilisateur John Woods

Stratégie de routage « No Restrictions, » vocale itinéraire « International », vocale à la procédure de création d’utilisation PSTN « International », et puis en l’affectant à l’utilisateur « John Woods » sont les suivantes.


1.  Tout d’abord, créez l’utilisation PSTN « International ». Dans une session PowerShell distante dans Skype pour Business Online, entrez :

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  Ensuite, créez l’itinéraire des communications vocales « International ».

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  Qui retourne :

  <pre>
  Identity                  : International 
  Priority                      : 5
  Description                   : 
  NumberPattern                 : \d+
  OnlinePstnUsages          : {International}    
  OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
  Name                            : International
  SupressCallerId           :
  AlternateCallerId         :
</pre>
3.  Ensuite, ne créez une stratégie de routage voix « Aucune restriction ». L’utilisation PSTN « Redmond 1 » et « Redmond » sont réutilisés dans cette stratégie de routage voix pour conserver les appels vers le numéro « +1 425 XX XXX XX » et « +1 206 XX XXX XX » comme des appels locaux ou dans les locaux de traitement particulier.

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   Qui retourne

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4.  Attribuer la stratégie de routage voix à l’utilisateur « John Woods » à l’aide de la commande suivante.

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  Vérifiez l’affectation à l’aide de la commande :   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  Qui retourne :

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

Le résultat est que la stratégie de voix appliquée aux appels de John Woods sont non restreint et doit suivre la logique de routage des appels disponible pour les États-Unis, au Canada et International appel.

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a>Définir Teams Microsoft en tant que client appelant par défaut pour les utilisateurs

Routage direct achemine uniquement les appels vers et depuis les utilisateurs s’ils utilisent le client d’équipes. Si votre organisation utilise uniquement des équipes, « Équipes uniquement » mode dans la stratégie de mise à niveau est recommandé de définir. Si votre organisation utilise Skype pour Business Server ou Skype pour Business Online, consultez l’article suivant pour plus d’informations et sélectionnez l’option appropriée : [comprendre la coexistence et voyage Skype pour professionnels et les équipes de mise à niveau](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 


## <a name="see-also"></a>Voir aussi

[Planifier le routage Direct](direct-routing-plan.md)
