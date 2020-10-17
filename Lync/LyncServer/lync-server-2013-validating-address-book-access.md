---
title: 'Lync Server 2013 : validation de l’accès au carnet d’adresses'
description: 'Lync Server 2013 : validation de l’accès au carnet d’adresses.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547240"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a>Validation de l’accès au carnet d’adresses dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsAddressBookService. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsAddressBookService vous permet de vérifier qu’un utilisateur peut se connecter au service Web de téléchargement du carnet d’adresses. Lorsque vous exécutez l’applet de commande, Test-CsAddressBookService se connecte au service Web de téléchargement du carnet d’adresses sur le pool spécifié et demande l’emplacement des fichiers du carnet d’adresses. Si le service Web de téléchargement du carnet d’adresses fournit cet emplacement, le test est considéré comme réussi. Si la demande est rejetée, cela signifie que la vérification a échoué.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsAddressBookService peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de n’importe quel utilisateur qui a été activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool Lync Server testé. Par exemple :

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lors de l’appel de test-CsAddressBookService :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié est en mesure de se connecter au service de carnet d’adresses, vous obtiendrez un résultat similaire à celui-ci, avec la propriété Result marquée comme **Success**:

TargetUri https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.2260399

«

Diagnostique

Si l’utilisateur spécifié ne parvient pas à établir cette connexion, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetUri

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,

Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas

présent.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué, car l’utilisateur spécifié (c’est-à-dire, « l’URI de destination ») n’existe pas ou n’a pas été activé pour Lync Server. Vous pouvez vérifier si un compte d’utilisateur est valide, et vérifier que vous avez fourni l’adresse SIP correcte en exécutant une commande semblable à celle-ci :

Get-CsUser-Identity « sip :kenmyer@litwareinc.com » | Select-Object SipAddress, activé

Si Test-CsAddressBookService échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Lorsque le paramètre Verbose est inclus Test-CsAddressBookService renverra un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, cet exemple de sortie indique que test-CsAddressBookService, au moins dans cet exemple, a pu télécharger le fichier de carnet d’adresses :

Envoi d’une demande HTTP GET.

Chemin d’accès du fichier = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Numéro de tentative = 1

Délai d’expiration (msec) = 60000

Téléchargement du fichier ABS réussi https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsAddressBookService peut échouer :

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas activé pour Lync Server.

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

