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
ms.openlocfilehash: 37343ad177e3408f94103296509e4b9bfc8ea759
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359410"
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

## <a name="voice-routing-policy-considerations"></a>Considérations relatives à la politique de routage vocale

Si un utilisateur dispose d’une licence de plan d’appel, les appels sortants de cet utilisateur sont automatiquement routés par le biais de l’infrastructure PSTN du plan d’appel Microsoft. Si vous configurez et attribuez une stratégie de routage téléphonique en ligne à un utilisateur de plan d’appel, les appels sortants de cet utilisateur sont examinés pour déterminer si le numéro numéroté correspond à un modèle défini dans la stratégie de routage de la voix en ligne. S’il existe une correspondance, l’appel est acheminé via le Trunk de routage direct. S’il n’y a aucune correspondance, l’appel est acheminé via l’infrastructure PSTN du plan d’appel.

> [!CAUTION]
> Si vous configurez et appliquez la stratégie globale de routage téléphonique en ligne par défaut de l’organisation, tous les utilisateurs à extension vocale de votre organisation hériteront de cette stratégie, ce qui peut entraîner des appels RTC involontairement routés vers un Trunk de routage direct. Si vous ne souhaitez pas que tous les utilisateurs utilisent la stratégie de routage de la voix en ligne globale, configurez une stratégie de routage de la voix en ligne personnalisée et attribuez-la à des utilisateurs vocaux individuels.

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

Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), l’itinéraire automatique est utilisé. S’il n’y a aucun résultat correspondant aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé par le biais du forfait d’appel Microsoft. Si l’utilisateur dispose uniquement d’un système Microsoft Phone, l’appel est abandonné, car aucune règle correspondante n’est disponible.

  > [!NOTE]
  > La valeur de priorité pour l’itinéraire « autres + 1 » n’a pas d’importance dans le cas du fait qu’il n’y a qu’un seul itinéraire qui correspond à la valeur du modèle + 1 XXX XX XX XX. Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.

Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux. Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN, « États-Unis et Canada ».  Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage téléphonique « États-Unis uniquement ».

|**Utilisation PSTN**|**Route vocale**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis et Canada|"Redmond 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis et Canada|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis et Canada|"Other + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Exemple 1 : étapes de configuration

L’exemple suivant montre comment :

1. Créez une utilisation PSTN unique.
2. Configurer trois itinéraires vocaux.
3. Créer une stratégie de routage de la voix.
4. Affectez la stratégie à un utilisateur nommé Spencer Low.

Vous pouvez utiliser le [Centre d’administration Microsoft teams](#admincenterexample1) ou [PowerShell](#powershellexample1) pour effectuer ces étapes.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Étape 1 : créer l’utilisation RTC des États-Unis et du Canada

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams,  >  **Direct Routing**sélectionnez **gérer les enregistrements d’utilisation RTC**dans le coin supérieur droit.
2. Cliquez sur **Ajouter**, tapez **États-Unis et Canada**, puis cliquez sur **appliquer**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Étape 2 : créer trois itinéraires vocaux (Redmond 1, Redmond 2 et autres + 1)

Les étapes suivantes décrivent la création d’un itinéraire vocal. Suivez ces étapes pour créer les trois itinéraires vocaux nommés Redmond 1, Redmond 2 et autres + 1 pour cet exemple en utilisant les paramètres définis dans le tableau précédent.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **routage direct**de la voix, puis sélectionnez l’onglet **itinéraires vocaux** .
2. Cliquez sur **Ajouter**, puis entrez le nom et la description de l’itinéraire.
3. Définissez la priorité et spécifiez le modèle de numéro numéroté.
4. Pour inscrire une SBC auprès de l’itinéraire de la voix, sous **SBCS inscrits (facultatif)**, cliquez sur **Ajouter SBCS**, sélectionnez le SBCS que vous voulez inscrire, puis cliquez sur **appliquer**.
5. Pour ajouter des enregistrements d’utilisation RTC, sous **enregistrements d’utilisation RTC (facultatif)**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez les enregistrements RTC que vous voulez ajouter, puis cliquez sur **appliquer**.
6. Cliquez sur **Enregistrer**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Étape 3 : créer une stratégie de routage de la voix nommée « États-Unis uniquement » et ajouter l’utilisation RTC « États-Unis et Canada » à la politique

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**stratégies de routage de voix vocales, puis  >  **Voice routing policies**cliquez sur **Ajouter**.
2. Tapez **-nous uniquement** le nom et ajoutez une description.
3. Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez l’enregistrement d’utilisation RTC « États-Unis et Canada », puis cliquez sur **appliquer**.
4. Cliquez sur **Enregistrer**.

Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Étape 4 : affecter la stratégie de routage téléphonique à un utilisateur nommé Spencer Low

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **politique de routage**de la voix, sélectionnez la stratégie « États-Unis uniquement », puis cliquez sur **Enregistrer**.

Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).

### <a name="using-powershell"></a>Utiliser PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Étape 1 : créer l’utilisation RTC des États-Unis et du Canada

Dans une session PowerShell distante dans Skype entreprise Online, tapez :

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
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

L’exemple suivant montre le résultat de l’exécution de la `(Get-CSOnlinePSTNUsage).usage` commande PowerShell pour afficher les noms complets (pas tronqués) :

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Étape 2 : créer trois itinéraires vocaux (Redmond 1, Redmond 2 et autres + 1)

Pour créer l’itinéraire « Redmond 1 » dans une session PowerShell dans Skype entreprise Online, entrez :

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
  > Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide. Vous pouvez le tester à l’aide du site Web suivant : [https://www.regexpal.com](https://www.regexpal.com)

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
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Étape 3 : créer une stratégie de routage de la voix nommée « États-Unis uniquement » et ajouter l’utilisation RTC « États-Unis et Canada » à la politique

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

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Étape 4 : affecter la stratégie de routage téléphonique à un utilisateur nommé Spencer Low

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

Dans l’exemple qui suit, vous pouvez créer la stratégie de routage vocale « sans restrictions ». La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation RTC « internationale ». Cette stratégie route tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.

Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur Beaune Low et la stratégie no restrictions à l’utilisateur Jean Martin de sorte que le routage se déroule comme suit :

- Beaune : politique de niveau faible-américaine uniquement.  Les appels ne sont admis qu’aux États-Unis et au Canada. Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé. Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.

- Jean bois-politique internationale.  Les appels sont autorisés à n’importe quel numéro. Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé. Les numéros non US seront routés à l’aide de sbc2.contoso.biz et sbc5.contoso.biz.

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé. S’il n’y a aucun résultat correspondant aux modèles de chiffres dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide d’un forfait d’appel Microsoft.  Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ». 

|**Utilisation PSTN**|**Route vocale**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis et Canada|"Redmond 1"|^\\+ 1 (425 \| 206) (\d {7} ) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis et Canada|"Redmond 2"|^\\+ 1 (425 \| 206) (\d {7} ) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX|
|États-Unis et Canada|"Other + 1"|^\\+ 1 (\d {10} ) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Itinéraire pour n’importe quel modèle numérique |

  > [!NOTE]
  > - L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel. Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées. L’utilisation RTC internationale doit être placée après l’utilisation du RTC des États-Unis et du Canada. Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande. <br/>Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué. Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».

## <a name="example-2-configuration-steps"></a>Exemple 2 : étapes de configuration

L’exemple suivant montre comment :

1. Créer une nouvelle utilisation RTC appelée international.
2. Créer un nouvel itinéraire vocal appelé international.
3. Création d’une stratégie de routage de la voix sans restrictions.
4. Affectez la stratégie à l’utilisateur Jean bois.

Vous pouvez utiliser le [Centre d’administration Microsoft teams](#admincenterexample2) ou [PowerShell](#powershellexample2) pour effectuer ces étapes.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Étape 1 : créer une utilisation RTC internationale

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams,  >  **Direct Routing**sélectionnez **gérer les enregistrements d’utilisation RTC**dans le coin supérieur droit.
2. Cliquez sur **Ajouter**, tapez **international**, puis cliquez sur **appliquer**.

#### <a name="step-2-create-the-international-voice-route"></a>Étape 2 : créer l’itinéraire vocal « international »

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **routage direct**de la voix, puis sélectionnez l’onglet **itinéraires vocaux** .
2. Cliquez sur **Ajouter**, entrez « international » comme nom, puis ajoutez la description.
3. Définissez la priorité sur 4, puis définissez le modèle de numérotation numérique sur \d +.
4. Sous **SBCS inscrits (facultatifs)**, cliquez sur **Ajouter sbcs**, sélectionnez sbc2.contoso.biz et sbc5.contoso.biz, puis cliquez sur **appliquer**.
5. Sous **enregistrements d’utilisation RTC (facultatif)**, cliquez sur **Ajouter l’utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC « international », puis cliquez sur **appliquer**.
6. Cliquez sur **Enregistrer**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Étape 3 : création d’une stratégie de routage téléphonique nommée « aucune restriction » et ajout des utilisations RTC « États-Unis et Canada » et « internationales » à la politique

L’utilisation RTC « États-Unis et Canada » est réutilisée dans cette politique de routage vocal pour garantir une gestion spéciale des appels vers le numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**stratégies de routage de voix vocales, puis  >  **Voice routing policies**cliquez sur **Ajouter**.
2. Tapez **aucune restriction** pour le nom et ajoutez une description.
3. Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez l’enregistrement d’utilisation RTC « États-Unis et Canada », puis sélectionnez l’enregistrement d’utilisation RTC « international ». Cliquez sur **Appliquer**.

    Prenez note de l’ordre des utilisations RTC :

    - Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans cet exemple, l’appel suit le routage défini au niveau de l’utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée. C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.

    - S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.

4. Cliquez sur **Enregistrer**.

Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Étape 4 : affecter la politique de routage téléphonique à un utilisateur intitulé Jean bois

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **politique de routage**de la voix, sélectionnez la stratégie « aucune restriction », puis cliquez sur **Enregistrer**.

Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.

### <a name="using-powershell"></a>Utiliser PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Étape 1 : créer une utilisation RTC internationale

Dans une session PowerShell distante dans Skype entreprise Online, entrez :

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Étape 2 : créer un nouvel itinéraire vocal nommé « international »

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

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Étape 3 : création d’une stratégie de routage téléphonique nommée « aucune restriction »

L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prenez note de l’ordre des utilisations RTC :

  - Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit le routage défini dans utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée. C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.

  - S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage. Entrez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Qui renvoie :

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Étape 4 : affecter la politique de routage de voix à l’utilisateur nommé Jean bois

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
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
