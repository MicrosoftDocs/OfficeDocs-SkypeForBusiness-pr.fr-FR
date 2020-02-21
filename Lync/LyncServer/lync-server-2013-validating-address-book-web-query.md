---
title: 'Lync Server 2013 : validation de la requête Web du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 548ec62a56de829955647a696e33578b9ab3dfd8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Validation de la requête Web du carnet d’adresses dans Lync Server 2013

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
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsAddressBookWebQuery. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsAddressBookWebQuery permet aux administrateurs de vérifier que les utilisateurs peuvent utiliser le service de requête Web du carnet d’adresses pour rechercher un contact spécifique. Lorsque vous exécutez l’applet de commande, test-CsAddressBookWebQuery se connecte au service de ticket Web pour être authentifié. Si l’authentification réussit, l’applet de commande se connecte au service de requête Web du carnet d’adresses et recherche le contact spécifié. Si ce contact est trouvé, l’applet de commande tente de renvoyer ces informations à l’ordinateur local. Le test sera marqué comme étant une réussite uniquement si toutes ces étapes peuvent être effectuées.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsAddressBookWebQuery peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server et l’adresse SIP de l’utilisateur agissant comme cible de la recherche. Par exemple :

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell qui contient un nom d’utilisateur et un mot de passe valides. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque le code appelle test-CsAddressBookWebQuery :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié peut se connecter au service de carnet d’adresses et récupérer l’adresse de l’utilisateur ciblé, vous obtiendrez un résultat similaire à celui-ci avec la propriété Result marquée comme Success :

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.2611356

«

Diagnostique

Si l’utilisateur spécifié ne peut pas se connecter ou si l’adresse de l’utilisateur cible ne peut pas être récupérée, le résultat s’affiche en panne et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : la demande de service Web du carnet d’adresses a échoué avec le code de réponse

NoEntryFound.

Diagnostique

La sortie précédente indique que le test a échoué, car l’utilisateur cible est introuvable. Vous pouvez déterminer si une adresse SIP valide a été transmise à test-CsAddressBookWebQuery en exécutant une commande semblable à la suivante :

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Si test-CsAddressBookWebQuery échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsAddressBookWebQuery renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, cette sortie indique que test-CsAddressBookWebQuery était en mesure de se connecter au service de carnet d’adresses, mais qu’il n’a pas pu trouver l’adresse SIP cible :

Activité « QueryAddressBookWebService » démarrée.

Appel du service de requête Web du carnet d’adresses. URL ABWS =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Exception de requête de carnet d’adresses : échec de la demande de service Web de carnet d’adresses avec le code de réponse NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsAddressBookWebQuery :

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas activé pour Lync Server.

  - L’utilisateur cible n’est peut-être pas dans le carnet d’adresses.

  - Il se peut que le carnet d’adresses ne dispose pas de la mise à jour et de la réplication complètes. Vous pouvez forcer une mise à jour de tous les serveurs de carnet d’adresses de votre organisation en exécutant la commande suivante :
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

