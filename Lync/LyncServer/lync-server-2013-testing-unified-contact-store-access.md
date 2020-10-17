---
title: 'Lync Server 2013 : test de l’accès au magasin de contacts unifié'
description: 'Lync Server 2013 : test de l’accès au magasin de contacts unifié.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58238685133c51130c414e0d7a8cd761d0233f5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556080"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Test de l’accès au magasin de contacts unifié dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Journalière</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsUnifiedContactStore</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le magasin de contacts unifié introduit dans Lync Server 2013 offre aux administrateurs la possibilité de stocker les contacts d’un utilisateur dans Microsoft Exchange Server 2013 et non dans Lync Server. Cela permet à l’utilisateur d’accéder au même ensemble de contacts dans Outlook Web Access en plus de Lync 2013. (Ou vous pouvez continuer à stocker des contacts dans Lync Server. Dans ce cas, les utilisateurs doivent conserver deux ensembles de contacts distincts : un pour une utilisation avec Outlook et Outlook Web Access, et un autre pour une utilisation avec Lync 2013.)

Vous pouvez déterminer si les contacts d’un utilisateur ont été déplacés vers le magasin de contacts unifié en exécutant l’applet de commande **test-CsUnifiedContactStore** . La cmdlet **test-CsUnifiedContactStore** prend le compte d’utilisateur spécifié, se connecte au magasin de contacts unifié et tente de récupérer un contact pour l’utilisateur. Si aucun contact ne peut être récupéré, la commande échoue en même temps que le message «aucun contact n’a été reçu pour l’utilisateur. Veuillez vérifier que l’utilisateur possède des contacts ».

Notez que l’applet de commande **test-CsUnifiedContactStore** échoue si l’utilisateur a effectué une migration vers le magasin de contacts unifié, mais qu’il n’a pas de contacts dans sa liste de contacts. L’utilisateur spécifié doit disposer d’au moins un contact pour que la cmdlet **test-CsUnifiedContactStore** s’exécute correctement.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Les commandes indiquées dans l’exemple suivant déterminent si les contacts de l’utilisateur litwareinc \\ kenmyer se trouvent dans le magasin de contacts unifié. Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell pour l’utilisateur litwareinc \\ kenmyer. Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et garantir que la cmdlet **test-CsUnifiedContactStore** peut exécuter sa vérification.

La deuxième commande de l’exemple utilise l’objet d’informations d’identification fourni ($x) et l’adresse SIP de l’utilisateur litwareinc \\ kenmyer pour déterminer si ses contacts se trouvent dans le magasin de contacts unifié.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’accès au magasin de contacts est correctement configuré, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:14.9862716

Message d’erreur :

Diagnostique

Si l’accès au magasin de contacts n’est pas configuré correctement, le résultat est indiqué comme étant un **échec**et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet

nom de domaine (FQDN). À l’aide du numéro de port de serveur d’inscriptions par défaut. Rogation

System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.

Regardez

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement au bout d’un certain temps, ou

échec de la connexion établie car l’hôte connecté a

échec de la réponse de 10.188.116.96:5061

Exception interne : une tentative de connexion a échoué car le

la partie connectée n’a pas répondu correctement après une période de

heure ou échec de la connexion établie car l’hôte connecté

échec de la réponse de 10.188.116.96:5061

Diagnostique

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsUnifiedContactStore** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - La connexion au magasin de contacts unifié a échoué et la tentative de récupération d’un contact pour l’utilisateur n’est pas possible. Il peut y avoir des problèmes de connectivité réseau.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[New-applet csuserservicespolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-applet csuserservicespolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

