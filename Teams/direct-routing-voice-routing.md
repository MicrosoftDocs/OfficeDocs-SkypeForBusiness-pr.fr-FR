---
title: Configurer le routage des appels pour le routage direct
ms.reviewer: ''
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
description: Découvrez comment configurer le routage des appels avec le routage direct de Microsoft.
ms.openlocfilehash: cb8f33d8e5e2ea3e3e14ac47b57d9b5920f2bb2a
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60635043"
---
# <a name="configure-call-routing-for-direct-routing"></a>Configurer le routage des appels pour le routage direct

Cet article décrit comment configurer le routage des appels pour le routage direct. Voici l’étape 3 de la procédure de configuration du routage direct :

- Étape 1. [Connecter SBC avec votre système Téléphone Microsoft données et valider la connexion](direct-routing-connect-the-sbc.md) 
- Étape 2. [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](direct-routing-enable-users.md)
- **Étape 3. Configurer le routage des appels** (cet article)
- Étape 4. [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)

## <a name="call-routing-overview"></a>Vue d’ensemble du routage des appels

Téléphone Microsoft Le système possède un mécanisme de routage qui permet d’envoyer un appel vers un contrôleur de session en bordure spécifique (SBC) sur la base des données suivantes : 

- Modèle de numéro appelé 
- Le schéma de numéro appelé ainsi que l’utilisateur spécifique qui effectue l’appel
 
Les SCS peuvent être désignés comme actifs et de sauvegarde. Lorsque le SBC configuré comme actif n’est pas disponible pour un itinéraire d’appel spécifique, l’appel est alors acheminé vers un SBC de sauvegarde.
 
Le routage d’appel est composé des éléments suivants : 

- **Stratégie de routage des appels** (ou stratégie de routage vocale). Conteneur des utilisations PSTN, qui peut être affecté à un utilisateur ou à plusieurs utilisateurs. 

- **Utilisations PSTN :** conteneur pour les itinéraires vocaux et les utilisations PSTN, qui peuvent être partagés dans différentes stratégies de routage voix. 

- **Itinéraires vocaux** : modèle de numéro et ensemble de passerelles RST en ligne à utiliser pour les appels pour lequel le numéro d’appel correspond à ce modèle.

- Passerelle **RTC** en ligne : pointeur sur un SBC qui stocke également la configuration qui est appliquée lorsqu’un appel est passé via SBC, telle que le forward P-Ed-Identity (XX) ou les codecs préférés ; peuvent être ajoutés aux itinéraires vocux.

## <a name="voice-routing-policy-considerations"></a>Considérations sur la stratégie de routage voix

Si un utilisateur dispose d’une licence Forfait d’appels, les appels sortants de cet utilisateur sont automatiquement acheminés via l’infrastructure PSTN du plan d’appels Microsoft. Si vous configurez et affectez une stratégie de routage vocal en ligne à un utilisateur du plan d’appels, les appels sortants de cet utilisateur sont vérifiés pour déterminer si le numéro à composer correspond à un modèle de numéro défini dans la stratégie de routage vocal en ligne. En cas de correspondance, l’appel est routant via le ligne de routage direct. En l’absence de correspondance, l’appel est acheminé via l’infrastructure PSTN du plan d’appel.

> [!CAUTION]
> Si vous configurez et appliquez la stratégie de routage voix en ligne globale (à l’échelle de l’organisation) et l’appliquez, tous les utilisateurs à commande vocale de votre organisation hériteront de cette stratégie, ce qui peut entraîner le routage par inadvertance d’appels PSTN des utilisateurs du plan d’appel vers une ligne de routage direct. Si vous ne souhaitez pas que tous les utilisateurs utilisent la stratégie globale de routage voix en ligne, configurez une stratégie personnalisée de routage vocal en ligne et affectez-la à des utilisateurs individuels à commande vocale.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Exemple 1 : routage vocal avec une utilisation PSTN

Le diagramme suivant montre deux exemples de stratégies de routage vocal dans un flux d’appels.

**Appeler Flow 1 (sur la gauche) :** Si un utilisateur appelle le +1 425 XXX XX XX ou le +1 206 XXX XX XX, l’appel est acheminé vers le sbc1.contoso.biz SBC ou sbc2.contoso.biz. Si ni votre sbc1.contoso.biz ni sbc2.contoso.biz disponibles, l’appel est supprimé. 

**Appeler Flow 2 (sur la droite) :** Si un utilisateur appelle le +1 425 XXX XX XX ou le +1 206 XXX XX XX, l’appel est d’abord acheminé vers le sbc1.contoso.biz SBC ou sbc2.contoso.biz. Si aucun SBC n’est disponible, l’itinéraire à priorité inférieure est essayé (sbc3.contoso.biz et sbc4.contoso.biz). Si aucun des SBCs n’est disponible, l’appel est supprimé. 

![Affiche des exemples de stratégie de routage voix.](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Dans les deux exemples, tandis que la route vocale est affectée à des priorités, les SBCS dans les itinéraires sont essayés dans un ordre aléatoire.

  > [!NOTE]
  > À moins que l’utilisateur ne dispose également d’une licence Plan d’appels Microsoft, les appels vers n’importe quel nombre sauf les nombres correspondant aux modèles +1 425 XXX XX XX ou +1 206 XXX XX dans l’exemple de configuration sont supprimés. Si l’utilisateur dispose d’une licence Forfait d’appels, l’appel est automatiquement acheminé conformément aux stratégies du plan d’appels Microsoft. Le plan d’appels Microsoft s’applique automatiquement comme dernier itinéraire à tous les utilisateurs titulaires de la licence Microsoft Calling Plan et ne nécessite pas de configuration de routage d’appel supplémentaire.

Dans l’exemple illustré dans le diagramme suivant, une route vocale est ajoutée pour envoyer des appels à tous les autres numéros des États-Unis et du Canada (appels appelés modèle de numéro +1 XXX XXX XX XX).

![Affiche la stratégie de routage vocal avec un troisième itinéraire.](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Pour tous les autres appels, si un utilisateur dispose des deux licences (Téléphone Microsoft Système et Microsoft Calling Plan), l’itinéraire automatique est utilisé. Si rien ne correspond aux modèles de numéro dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé via le plan d’appel Microsoft. Si l’utilisateur ne dispose que Téléphone Microsoft système informatique, l’appel est supprimé car aucune règle correspondante n’est disponible.

  > [!NOTE]
  > La valeur Priorité pour l’itinéraire « Autres +1 » n’a pas d’importance dans ce cas, car il n’existe qu’un seul itinéraire qui correspond au modèle +1 XXX XXX XX XX. Si un utilisateur appelle le +1 324 567 89 89 et que sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est supprimé.

Le tableau suivant récapitule la configuration à l’aide de trois itinéraires vocaux. Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN, « États-Unis et Canada ».  Tous les itinéraires sont associés à l’utilisation PSTN « États-Unis et Canada », et l’utilisation PSTN est associée à la stratégie de routage voix « États-Unis uniquement ».

|**Utilisation PSTN**|**Itinéraire vocal**|**Schéma de numéro**|**Priorité**|**SBC**|**Description**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis et Canada|« Redmond 1 »|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les nombres +1 425 XXX XX XX ou +1 206 XXX XX XX|
|États-Unis et Canada|« Redmond 2 »|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros +1 425 XXX XX XX ou +1 206 XXX XX XX|
|États-Unis et Canada|« Autre +1 »|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route pour les nombres appelés +1 XXX XXX XX XX (sauf +1 425 XXX XX XX ou +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Exemple 1 : étapes de configuration

L’exemple suivant montre comment :

1. Créez une utilisation PSTN unique.
2. Configurez trois itinéraires vocables.
3. Créer une stratégie de routage vocal.
4. Attribuez la stratégie à un utilisateur nommé Base.

Vous pouvez utiliser le [Microsoft Teams d’administration](#admincenterexample1) de l’utilisateur ou [PowerShell](#powershellexample1) pour effectuer ces étapes.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Étape 1 : créer l’utilisation PSTN « États-Unis et Canada »

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, sélectionnez **Acheminement** direct de la voix, puis dans le coin supérieur droit, sélectionnez Gérer les enregistrements d’utilisation  >   **PSTN.**
2. Cliquez **sur Ajouter,** **tapez US et Canada,** puis cliquez **sur Appliquer.**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Étape 2 : créer trois itinéraires vocux (Redmond 1, Redmond 2 et Autres +1)

Les étapes suivantes décrivent la création d’un itinéraire vocal. Pour créer les trois itinéraires vocaux nommés Redmond 1, Redmond 2 et Autres +1 pour cet exemple, utilisez les paramètres du tableau précédent.

1. Dans le panneau de navigation de gauche Microsoft Teams d’administration, sélectionnez **l’onglet**  >  **Itinéraires** vocants. 
2. Cliquez **sur** Ajouter, puis entrez un nom et une description pour l’itinéraire vocal.
3. Définissez la priorité et spécifiez le modèle de numérotation.
4. Pour inscrire un SBC sur l’itinéraire vocal, sous **SBCs inscrits (facultatif),** cliquez sur Ajouter des **SBC,** sélectionnez les SBC que vous voulez inscrire, puis cliquez sur **Appliquer.**
5. Pour ajouter des enregistrements d’utilisation PSTN, sous Enregistrements d’utilisation **PSTN (facultatif),** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez les enregistrements PSTN que vous voulez ajouter, puis cliquez sur **Appliquer.**
6. Cliquez sur **Enregistrer**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Étape 3 : créer une stratégie de routage vocal nommée « États-Unis uniquement » et ajouter l’utilisation PSTN « États-Unis et Canada » à la stratégie

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans les stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**
2. Tapez **US Only** as the name and add a description.
3. Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez l’enregistrement d’utilisation PSTN « États-Unis et Canada », puis cliquez sur **Appliquer.**
4. Cliquez sur **Enregistrer**.

Pour plus d’informations, voir [Gérer les stratégies de routage vocal.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Étape 4 : affecter la stratégie de routage vocal à un utilisateur nomméSSoin Low

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez **sur Stratégies,** puis, en côté **de Stratégies affectées,** cliquez **sur Modifier.**
3. Sous **La stratégie de routage voix,** sélectionnez la stratégie « États-Unis uniquement », puis cliquez sur **Enregistrer.**

Pour plus d’informations, voir [Gérer les stratégies de routage vocal.](manage-voice-routing-policies.md)

### <a name="using-powershell"></a>Utiliser PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Étape 1 : créer l’utilisation PSTN « États-Unis et Canada »

Dans une session PowerShell distante dans Skype Entreprise Online, tapez :

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Vérifiez que l’utilisation a été créée en entrant :

```PowerShell
Get-CSOnlinePSTNUsage
``` 

La renvoie une liste de noms qui peuvent être tronqués :

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

L’exemple suivant illustre le résultat de l’exécution de la commande PowerShell pour afficher des noms `(Get-CSOnlinePSTNUsage).usage` complets (non tronqués) :

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Étape 2 : créer trois itinéraires vocux (Redmond 1, Redmond 2 et Autres +1)

Pour créer l’itinéraire « Redmond 1 », dans une session PowerShell Skype Entreprise Online, entrez :

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Ce qui renvoie :

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

Pour créer l’itinéraire Redmond 2, entrez :

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Pour créer l’itinéraire Autres +1, entrez :

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Assurez-vous que votre expression régulière dans l’attribut NumberPattern est valide. Vous pouvez la tester à l’aide de ce site web : [https://www.regexpal.com](https://www.regexpal.com)

Dans certains cas, il est nécessaire de router tous les appels vers le même SBC. use -NumberPattern « .* »

Routez tous les appels vers le même SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la commande PowerShell à l’aide des `Get-CSOnlineVoiceRoute` options présentées ci-après :

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Ce qui doit renvoyer :

```console
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
```

Dans l’exemple, la priorité 4 de l’itinéraire « Autres +1 » a été automatiquement attribuée. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Étape 3 : créer une stratégie de routage vocal nommée « États-Unis uniquement » et ajouter l’utilisation PSTN « États-Unis et Canada » à la stratégie

Dans une session PowerShell dans Skype Entreprise Online, tapez :

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Le résultat est affiché dans cet exemple :

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Étape 4 : affecter la stratégie de routage vocal à un utilisateur nomméSSoin Low

Dans une session PowerShell dans Skype Entreprise Online, tapez :

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Validez l’affectation de stratégie en entrant la commande suivante :

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

La commande renvoie les commandes suivantes :

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Exemple 2 : routage vocal avec plusieurs utilisations PSTN

La stratégie de routage vocal créée dans l’exemple 1 autorise uniquement les appels vers des numéros de téléphone aux États-Unis et au Canada, sauf si la licence Du plan d’appels Microsoft est également affectée à l’utilisateur.

Dans l’exemple suivant, vous pouvez créer la stratégie de routage vocal « Aucune restriction ». La stratégie réutilise l’utilisation PSTN « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation PSTN « international ». Cette stratégie a route tous les autres appels vers les sbc2.contoso.biz et sbc5.contoso.biz.

Les exemples affichés attribuent la stratégie États-Unis uniquement à l’utilisateurSSuper Qu’il est bas et la stratégie Aucune restriction à l’utilisateur John Bois afin que le routage se produise comme suit :

- Autant de choses dont le taux d’intérêt est faible pour les États-Unis uniquement.  Les appels sont autorisés uniquement vers les numéros américains et canadien. Lorsque vous appelez une plage de numéro de Redmond, l’ensemble spécifique de SBCs doit être utilisé. Les numéros hors États-Unis ne seront acheminés que si la licence Forfait d’appels est affectée à l’utilisateur.

- John Bois – Politique internationale.  Les appels sont autorisés sur n’importe quel numéro. Lorsque vous appelez une plage de numéro de Redmond, l’ensemble spécifique de SBCs doit être utilisé. Les numéros hors États-Unis seront acheminés à l’aide sbc2.contoso.biz et sbc5.contoso.biz.

![Affiche la stratégie de routage voix attribuée à l’utilisateur Nommé Bas.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Pour tous les autres appels, si un utilisateur dispose des deux licences (Téléphone Microsoft Système et Microsoft Calling Plan), l’itinéraire automatique est utilisé. Si rien ne correspond aux schémas de numéro dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide du plan d’appel Microsoft.  Si l’utilisateur dispose uniquement Téléphone Microsoft système informatique, l’appel est supprimé car aucune règle correspondante n’est disponible.

![Affiche la stratégie de routage vocal attribuée à l’utilisateur John Bois.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Le tableau suivant récapitule les désignations d’utilisation et les itinéraires vocaux de la stratégie de routage « Aucune restriction ». 

| Utilisation PSTN | Itinéraire vocal | Type de numéro | Priority (Priorité) | SBC | Description |
|:-----|:-----|:-----|:-----|:-----|:-----|
|États-Unis et Canada|« Redmond 1 »|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Itinéraire actif pour les numéros de l’appelant +1 425 XXX XX XX ou +1 206 XXX XX XX|
|États-Unis et Canada|« Redmond 2 »|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Itinéraire de sauvegarde pour les numéros de l’appelant +1 425 XXX XX XX ou +1 206 XXX XX XX|
|États-Unis et Canada|« Autre +1 »|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route pour les numéros des appelants +1 XXX XXX XX XX (sauf +1 425 XXX XX XX ou +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route pour n’importe quel modèle de numéro |

  > [!NOTE]
  > - L’ordre d’utilisation PSTN dans les stratégies de routage voix est essentiel. Les utilisations sont appliquées dans l’ordre, et si une correspondance est trouvée lors de la première utilisation, les autres utilisations ne sont jamais évaluées. L’utilisation PSTN « international » doit être placée après l’utilisation PSTN « États-Unis et Canada ». Pour modifier l’ordre des utilisations PSTN, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande. <br/>Par exemple, pour modifier la commande de « États-Unis et Canada » en premier et « International » en deuxième de la commande inverse, exécutez :<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - La priorité des itinéraires vocux « Autres +1 » et « Internationaux » est attribuée automatiquement. Peu importe s’ils ont des priorités inférieures à celles de « Redmond 1 » et de « Redmond 2 ».

## <a name="example-2-configuration-steps"></a>Exemple 2 : étapes de configuration

L’exemple suivant montre comment :

1. Créez une utilisation RSTN appelée International.
2. Créez une nouvelle ligne vocale appelée International.
3. Créez une stratégie de routage vocal nommée Aucune restriction.
4. Attribuez la stratégie à l’utilisateur John Boiss.

Vous pouvez utiliser le [Microsoft Teams d’administration](#admincenterexample2) de l’utilisateur ou [PowerShell](#powershellexample2) pour effectuer ces étapes.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Étape 1 : créer l’utilisation PSTN « international »

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, sélectionnez **Acheminement** direct de la voix, puis dans le coin supérieur droit, sélectionnez Gérer les enregistrements d’utilisation  >   **PSTN.**
2. Cliquez **sur Ajouter,** **tapez International,** puis cliquez **sur Appliquer.**

#### <a name="step-2-create-the-international-voice-route"></a>Étape 2 : créer l’itinéraire vocal « International »

1. Dans le panneau de navigation de gauche Microsoft Teams d’administration, sélectionnez **l’onglet**  >  **Itinéraires** vocants. 
2. Cliquez **sur** Ajouter, entrez « International » comme nom, puis ajoutez la description.
3. Définissez la priorité sur 4, puis définissez le modèle de numérotation sur \d+.
4. Sous **SBCs inscrits (facultatif),** cliquez sur Ajouter des **SBCs,** sélectionnez sbc2.contoso.biz et sbc5.contoso.biz, puis cliquez sur **Appliquer.**
5. Sous **Enregistrements d’utilisation PSTN (facultatif),** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez l’enregistrement d’utilisation PSTN « International », puis cliquez sur **Appliquer.**
6. Cliquez sur **Enregistrer**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Étape 3 : créez une stratégie de routage vocal nommée « Aucune restriction » et ajoutez les utilisations PSTN « États-Unis et Canada » et « International » à la stratégie

L’utilisation PSTN « États-Unis et Canada » est réutilisée dans cette stratégie de routage vocal afin de préserver la gestion spéciale pour les appels au numéro « +1 425 XXX XX XX » et « +1 206 XXX XX XX » en tant qu’appels locaux ou locaux.

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans les stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**
2. Tapez **Le nom «** Aucune restriction » et ajoutez une description.
3. Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez l’enregistrement d’utilisation PSTN « États-Unis et Canada », puis sélectionnez l’enregistrement d’utilisation PSTN « International ». Cliquez sur **Appliquer**.

    Prenez note de l’ordre d’utilisation PSTN :

    - Si un appel a été effectué sur le numéro « +1 425 XXX XX XX » avec les utilisations configurées comme dans cet exemple, l’appel suit l’itinéraire tracé dans l’utilisation des « États-Unis et Canada » et la logique de routage spéciale est appliquée. Autrement dit, l’appel est acheminé d’abord à l’aide d sbc1.contoso.biz sbc2.contoso.biz puis en utilisant les itinéraires sbc3.contoso.biz et sbc4.contoso.biz les itinéraires de sauvegarde.

    - Si l’utilisation PSTN « international » est avant « États-Unis et Canada », les appels vers le +1 425 XXX XX XX sont acheminés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.

4. Cliquez sur **Enregistrer**.

Pour plus d’informations, voir [Gérer les stratégies de routage vocal.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Étape 4 : affecter la stratégie de routage vocal à un utilisateur nommé John Boiss

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez **sur Stratégies,** puis, en côté de **Stratégies affectées,** cliquez **sur Modifier.**
3. Sous **Stratégie de routage voix,** sélectionnez la stratégie « Aucune restriction », puis cliquez sur **Enregistrer.**

Par conséquent, la stratégie vocale appliquée aux appels de John Bois n’est pas restreinte et suit la logique du routage des appels disponibles pour les appels aux États-Unis, au Canada et à l’international.

### <a name="using-powershell"></a>Utiliser PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Étape 1 : créer l’utilisation PSTN « international »

Dans une session PowerShell distante dans Skype Entreprise Online, entrez :

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Étape 2 : créer une nouvelle route vocale nommée « International »

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

Ce qui renvoie :

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Étape 3 : créer une stratégie de routage vocal nommée « Aucune restriction »

L’utilisation PSTN « Redmond 1 » et « Redmond » est réutilisée dans cette stratégie de routage vocal afin de préserver la gestion spéciale des appels pour le numéro « +1 425 XXX XX XX » et « +1 206 XXX XX XX » en tant qu’appels locaux ou locaux.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Prenez note de l’ordre d’utilisation PSTN :

  - Si un appel a été effectué sur le numéro « +1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit l’itinéraire tracé dans l’utilisation des « États-Unis et Canada » et la logique de routage spéciale est appliquée. Autrement dit, l’appel est acheminé d’abord à l’aide d sbc1.contoso.biz sbc2.contoso.biz puis en utilisant les itinéraires sbc3.contoso.biz et sbc4.contoso.biz les itinéraires de sauvegarde.

  - Si l’utilisation PSTN « international » est avant « États-Unis et Canada », les appels vers le +1 425 XXX XX XX sont acheminés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage. Entrez la commande :

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Ce qui renvoie :

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Étape 4 : affecter la stratégie de routage vocal à l’utilisateur John Boiss

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Vérifiez ensuite le devoir à l’aide de la commande suivante : 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Ce qui renvoie :

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

Par conséquent, la stratégie vocale appliquée aux appels de John Bois n’est pas restreinte et suit la logique du routage des appels disponibles pour les appels aux États-Unis, au Canada et à l’international.

## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
