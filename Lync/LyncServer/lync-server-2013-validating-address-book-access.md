---
title: 'Lync Server 2013: validation de l’accès au carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Validation de l’accès au carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-05_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsAddressBookService. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsAddressBookService vous permet de vérifier qu’un utilisateur peut se connecter au service Web de téléchargement du carnet d’adresses. Lorsque vous exécutez l’applet de requête, test-CsAddressBookService se connecte au service Web de téléchargement du carnet d’adresses sur le pool spécifié et demande l’emplacement des fichiers du carnet d’adresses. Si le service Web de téléchargement de carnet d’adresses fournit cet emplacement, le test est considéré comme réussi. Si la requête est refusée, le test est considéré comme un échec.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle de test-CsAddressBookService à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui a été activé pour Lync Server. Pour exécuter cette recherche à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lors de l’appel de test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié est en mesure de se connecter au service de carnet d’adresses, vous obtiendrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie**:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.2260399

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas établir cette connexion, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Diagnostic: codeerreur = 4005, source = ATL-CS-001.litwareinc.com,

Raison = URI de destination non activé pour le SIP ou non

Il.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique qu’un test a échoué, car l’utilisateur spécifié (autrement dit, l’URI de destination) n’existe pas ou n’a pas été activé pour Lync Server. Vous pouvez vérifier qu’un compte d’utilisateur est valide ou non et que vous avez fourni l’adresse SIP correcte en exécutant une commande semblable à celle-ci:

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | SipAddress de sélection d’objet activée

Si test-CsAddressBookService échoue alors, vous souhaiterez peut-être réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

Test-CsAddressBookService-TargetFqdn «atl-cs-001.litwareinc.com»-détails

Lorsque le paramètre Verbose est inclus, le test-CsAddressBookService renvoie un compte étape par étape de chaque action qu’il a lancée lors de la vérification de la possibilité de connexion de l’utilisateur spécifié à Lync Server. Par exemple, cet exemple de sortie montre que test-CsAddressBookService, au moins dans cet exemple, a pu télécharger le fichier du carnet d’adresses:

Envoi de la requête HTTP GET.

Chemin d’accès du fichier =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Tentative de numérotation = 1

Délai d’expiration (MS) = 60000

Téléchargement du fichier ABS réussihttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsAddressBookService peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas actuellement activé pour Lync Server.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

