---
title: 'Lync Server 2013: test de la connexion utilisateur à la messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc54577e94f7679e833f06a4a5de060aaf761a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Test de la connexion utilisateur à la messagerie unifiée Exchange dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-11-01_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsExUMConnectivity</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsExUMConnectivity** vérifie que l’utilisateur spécifié est en mesure de se connecter au service de messagerie unifiée Microsoft Exchange Server 2013. Notez que cette cmdlet vérifie uniquement qu’une connexion peut être établie au service. Le service proprement dit n’est pas testé. Pour tester le service de messagerie unifiée (en exécutant une cmdlet de transaction synthétique qui quitte réellement un message de messagerie vocale dans la boîte aux lettres de l’utilisateur), utilisez l’applet de contrôle test-CsExUMVoiceMail.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple suivant teste la connectivité de messagerie unifiée Exchange pour le pool atl-cs-001.litwareinc.com. Cette commande ne fonctionnera que si les utilisateurs de test étaient définis pour le pool atl-cs-001.litwareinc.com. Si tel est le cas, la commande détermine si le premier utilisateur de test peut se connecter à la messagerie unifiée. Si les utilisateurs test n’ont pas été configurés pour le pool, la commande échoue.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

Les commandes indiquées dans l’exemple suivant testent la connectivité de messagerie unifiée Exchange\\pour l’utilisateur litwareinc kenmyer. Pour ce faire, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’information d’identification d’interface de ligne de commande\\Windows PowerShell pour l’utilisateur litwareinc kenmyer. Notez que vous devez fournir le mot de passe de ce compte pour créer un objet d’informations d’identification valide et garantir que l’applet de contrôle **CsExUMConnectivity** puisse exécuter sa vérification.

La deuxième commande de l’exemple utilise l’objet Credentials fourni ($x) et l’adresse SIP de l’utilisateur litwareinc\\kenmyer pour déterminer si l’utilisateur peut se connecter à la messagerie unifiée Exchange.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Dans l’exemple qui suit, la commande est une variante de la commande qui s’affiche. Dans ce cas, le paramètre OutLoggerVariable est inclus pour générer un journal détaillé de chaque étape réalisée par le **test-CsExUMConnectivity** cmdletand le succès ou l’échec de chacune de ces étapes. Pour ce faire, le paramètre OutLoggerVariable est ajouté avec la valeur de paramètre ExumText; les informations de journalisation détaillées sont alors stockées dans une variable nommée $ExumTest. Dans la commande final de l’exemple, la méthode ToXML () est utilisée pour convertir les informations du journal au format XML. Ces données XML sont alors écrites dans un fichier nommé C:\\logs\\ExumTest. XML en utilisant l’applet de connexion Out-File.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’intégration Exchange est correctement configurée, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie**:

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:00

Message d’erreur:

Diagnostic

Si l’utilisateur spécifié ne peut pas recevoir de notifications, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

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

Voici quelques raisons courantes pour lesquelles **les tests-CsExUMConnectivity** peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - Si le serveur Exchange n’est pas configuré correctement ou n’est pas encore déployé, cette commande échoue.

  - Cette commande échoue si le serveur Exchange n’est pas joignable sur votre réseau.

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

