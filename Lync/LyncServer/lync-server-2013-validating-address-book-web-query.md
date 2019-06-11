---
title: 'Lync Server 2013: validation de la requête Web du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Validation de la requête Web du carnet d’adresses dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsAddressBookWebQuery. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsAddressBookWebQuery permet aux administrateurs de vérifier que les utilisateurs peuvent utiliser le service de requête Web du carnet d’adresses pour rechercher un contact spécifique. Lorsque vous exécutez l’applet de contrôle, test-CsAddressBookWebQuery va d’abord se connecter au service de tickets Web pour être authentifié. Si l’authentification est réussie, l’applet de requête se connecte alors au service de requête sur le carnet d’adresses et recherche le contact spécifié. Si le contact est trouvé, l’applet de passe tente de renvoyer ces informations à l’ordinateur local. Le test sera marqué comme succès uniquement si toutes ces étapes peuvent être effectuées.

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsAddressBookWebQuery à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync et l’adresse SIP de l’utilisateur agissant en tant que cible de la recherche. Par exemple :

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell contenant un nom d’utilisateur et un mot de passe valides. Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque le code appelle test-CsAddressBookWebQuery:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié peut se connecter au service de carnet d’adresses et récupérer l’adresse utilisateur ciblée, vous renverra une sortie similaire à celle-ci avec la propriété Result marquée comme réussie:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.2611356

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas se connecter ou si l’adresse de l’utilisateur cible ne peut pas être récupérée, le résultat s’affichera en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Erreur: le service Web du carnet d’adresses a échoué avec le code de réponse

NoEntryFound.

Diagnostic

La sortie précédente indique que le test a échoué car l’utilisateur cible est introuvable. Vous pouvez déterminer si une adresse SIP valide a été transmise à test-CsAddressBookWebQuery en exécutant une commande semblable à ce qui suit:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Si test-CsAddressBookWebQuery échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsAddressBookWebQuery renvoie un compte étape par étape de chaque action exécutée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, cette sortie indique que test-CsAddressBookWebQuery a réussi à se connecter au service de carnet d’adresses, mais qu’il n’a pas été en mesure de localiser l’adresse SIP cible:

Activité «QueryAddressBookWebService» démarrée.

Appel au service de requête sur le Web du carnet d’adresses. URL ABWS =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Exception de requête dans le carnet d’adresses: échec de la demande de service Web du carnet d’adresses avec le code de réponse NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsAddressBookWebQuery peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est pas actuellement activé pour Lync Server.

  - L’utilisateur cible n’est peut-être pas dans le carnet d’adresses.

  - Le carnet d’adresses n’a peut-être pas été entièrement mis à jour et répliqué. Vous pouvez forcer la mise à jour de tous les serveurs du carnet d’adresses de votre organisation en exécutant la commande suivante:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

