---
title: 'Lync Server 2013 : test de la connexion utilisateur à la messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cf7189df06549a3008fd86b9395617c6aea3e98
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Test de la connexion utilisateur à la messagerie unifiée Exchange dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsExUMConnectivity</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-CsExUMConnectivity** vérifie que l’utilisateur spécifié peut se connecter au service de messagerie unifiée Microsoft Exchange Server 2013. Notez que cette applet de commande vérifie uniquement qu’une connexion peut être établie avec le service. Il ne teste pas le service lui-même. Pour tester le service de messagerie unifiée (en exécutant une applet de commande de transaction synthétique qui laisse un message vocal dans la boîte aux lettres de l’utilisateur), utilisez l’applet de commande the Test-CsExUMVoiceMail.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple suivant teste la connectivité de messagerie unifiée Exchange pour le pool atl-cs-001.litwareinc.com. Cette commande fonctionne uniquement si les utilisateurs de test ont été définis pour le pool atl-cs-001.litwareinc.com. Si c’est le cas, la commande détermine si le premier utilisateur de test peut se connecter à la messagerie unifiée. Si les utilisateurs de test n’ont pas été configurés pour le pool, la commande échouera.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

Les commandes indiquées dans l’exemple suivant testent la connectivité de messagerie unifiée Exchange\\pour l’utilisateur litwareinc kenmyer. Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows\\PowerShell pour l’utilisateur litwareinc kenmyer. Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et garantir que la cmdlet **test-CsExUMConnectivity** peut exécuter sa vérification.

La deuxième commande de l’exemple utilise l’objet d’informations d’identification fourni ($x) et l’adresse SIP de l'\\utilisateur litwareinc kenmyer pour déterminer si l’utilisateur peut se connecter à la messagerie unifiée Exchange ou non.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

La commande illustrée dans l’exemple suivant est une variante de la commande qui vient d’apparaître. Dans ce cas, le paramètre OutLoggerVariable est inclus pour générer un journal détaillé de chaque étape effectuée par le **test-CsExUMConnectivity** cmdletand la réussite ou l’échec de chacune de ces étapes. Pour ce faire, le paramètre OutLoggerVariable est ajouté avec la valeur de paramètre ExumText ; les informations de journalisation détaillées sont alors stockées dans une variable nommée $ExumTest. Dans la dernière commande de l’exemple, la méthode ToXML () est utilisée pour convertir les informations du journal au format XML. Ces données XML sont ensuite écrites dans un fichier nommé C :\\logs\\ExumTest. XML à l’aide de l’applet de commande Out-File.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’intégration d’Exchange est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si l’utilisateur spécifié ne peut pas recevoir de notifications, le résultat est affiché sous la forme **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

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

Voici quelques-unes des causes courantes de l’échec **de test-CsExUMConnectivity** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - Cette commande échoue si le serveur Exchange est mal configuré ou s’il n’est pas encore déployé.

  - Cette commande échoue si le serveur Exchange n’est pas accessible sur votre réseau.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

