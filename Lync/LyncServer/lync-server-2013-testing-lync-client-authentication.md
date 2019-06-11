---
title: 'Lync Server 2013: test de l’authentification du client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8ea26c39582a69062526c7b4ae00343bb19482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Test de l’authentification du client Lync dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsClientAuth. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsClientAuth vous permet de déterminer si un utilisateur peut se connecter au serveur Lync à l’aide d’un certificat client, vous pouvez exécuter l’applet de contrôle CsClientAuth. Après avoir appelé test-CsClientAuth, l’applet de commande contacte le service de mise en service des certificats et télécharge une copie des certificats clients pour l’utilisateur spécifié. S’il est possible de trouver et de télécharger un certificat client, test-CsClientAuth tente alors de se connecter à l’aide de ce certificat. En cas de réussite de l’ouverture de session, la fonction test-CsClientAuth se déconnecte et signale que le test a réussi. Si un certificat est introuvable ou n’a pas pu être téléchargé, ou si l’applet de connexion n’est pas en mesure de se connecter à l’aide de ce certificat, le test-CsClientAuth indique que le test a échoué.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsClientAuth est exécutée en utilisant le compte de tout utilisateur autorisé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Lorsque le système appelle test-CsClientAuth, vous devez inclure l’objet Credential et l’adresse SIP associée au compte.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié peut se connecter à Lync Server à l’aide d’un certificat client, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie:**

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.8630376

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas se connecter, le résultat s’affichera en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:03.3645259

Erreur: nous n’avons pas pu télécharger un certificat CS pour l’utilisateur donné. Vérifier si

les informations d’identification et URI fournies sont correctes.

Diagnostic

Par exemple, la sortie précédente indique que le test a échoué car un certificat client valide a pu être localisé pour l’utilisateur spécifié. Vous pouvez renvoyer une liste des certificats clients émis à un utilisateur en exécutant une commande comme suit:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Si test-CsClientAuth échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Lorsque le paramètre Verbose est inclus, test-CsClientAuth renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple :

Tentative de téléchargement d’un certificat CS pour l’utilisateur: kenmyer@litwareinc.com Endpoint: STEpid

URL du service Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Impossible de télécharger un certificat CS à partir du service Web.

Recherchez

\-L’URL du service Web est valide et les services Web sont opérationnels

\-Si vous utilisez\\\\PhoneNo code confidentiel pour l’authentification, vérifiez qu’il correspond à l’URI de l’utilisateur.

\-Si vous utilisez\\l’authentification Kerberos NTLM, assurez-vous d’avoir fourni les informations d’identification valides.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsClientAuth peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Il est possible que l’utilisateur test ne dispose pas d’un certificat client valide. Vous pouvez renvoyer des informations sur les certificats clients attribués à un utilisateur à l’aide d’une commande semblable à ce qui suit:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

