---
title: 'Lync Server 2013: test de l’accès au magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Test de l’accès au magasin de contacts unifié dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-05-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsUnifiedContactStore</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le magasin de contacts unifié introduit dans Lync Server 2013 permet aux administrateurs de stocker les contacts d’un utilisateur dans Microsoft Exchange Server 2013 au lieu de Lync Server. Cela permet à l’utilisateur d’accéder au même jeu de contacts dans Outlook Web Access en plus de Lync 2013. (Vous pouvez continuer à stocker vos contacts dans Lync Server. Dans ce cas, les utilisateurs doivent tenir compte de deux ensembles de contacts distincts: un pour une utilisation avec Outlook et Outlook Web Access, et un pour une utilisation avec Lync 2013.)

Vous pouvez déterminer si les contacts d’un utilisateur ont été déplacés dans le magasin de contacts unifié en exécutant l’applet de **contrôle CsUnifiedContactStore de test** . L’applet de connexion **test-CsUnifiedContactStore** prend le compte d’utilisateur spécifié, se connecte au magasin de contacts unifié et tente de récupérer un contact pour l’utilisateur. Si aucun contact ne peut être récupéré, la commande échoue avec le message «aucun contact n’a été reçu pour l’utilisateur. Vérifiez qu’il existe des contacts pour l’utilisateur.»

Notez que l’applet **de contrôle test-CsUnifiedContactStore** échoue si l’utilisateur a effectué une migration réussie vers le magasin de contacts unifié, mais qu’aucun contact n’a été trouvé dans sa liste de contacts. L’utilisateur spécifié doit avoir au moins un contact pour que l’applet de **contrôle test-CsUnifiedContactStore** se termine correctement.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Les commandes indiquées dans l’exemple ci-dessous déterminent si les contacts\\de l’utilisateur litwareinc kenmyer se trouvent dans le magasin de contacts unifié. Pour ce faire, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’information d’identification d’interface de ligne de commande\\Windows PowerShell pour l’utilisateur litwareinc kenmyer. Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et vérifier que l’applet de contrôle **CsUnifiedContactStore** peut exécuter sa vérification.

La deuxième commande de l’exemple utilise l’objet Credentials fourni ($x) et l’adresse SIP de l’utilisateur litwareinc\\kenmyer pour déterminer si ses contacts sont accessibles dans le magasin de contacts unifié.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’accès au magasin de contacts est correctement configuré, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:14.9862716

Message d’erreur:

Diagnostic

Si l’accès au magasin de contacts n’est pas configuré correctement, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

AVERTISSEMENT: impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni

nom de domaine (FQDN). Utilisation du numéro de port de bureau par défaut. Sauf

System. InvalidOperationException: aucun cluster correspondant détecté dans la topologie.

dès

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Message d’erreur: 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement après un certain temps, ou

échec de la connexion établie, car l’hôte connecté a

échec de la réponse à 10.188.116.96:5061

Exception interne: une tentative de connexion a échoué, car le

la fête connectée ne répond pas correctement après un délai de

heure ou échec de la connexion en raison d’un hôte connecté

échec de la réponse à 10.188.116.96:5061

Diagnostic

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsUnifiedContactStore** peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - La connexion au magasin de contacts unifié a échoué et la tentative de récupération d’un contact pour l’utilisateur n’est pas possible. Il y a peut-être des problèmes de connectivité réseau.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

