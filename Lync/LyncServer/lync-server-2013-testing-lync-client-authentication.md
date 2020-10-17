---
title: 'Lync Server 2013 : test de l’authentification de client Lync'
description: 'Lync Server 2013 : test de l’authentification client Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560580"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Test de l’authentification client Lync dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsClientAuth. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsClientAuth vous permet de déterminer si un utilisateur peut se connecter au serveur Lync à l’aide d’un certificat client, mais vous pouvez exécuter l’applet de commande Test-CsClientAuth. Une fois appelée, l’applet de commande Test-CsClientAuth contacte le service d’approvisionnement de certificats et télécharge un exemplaire des certificats clients pour l’utilisateur spécifié. S’il est possible de trouver un certificat client et de le télécharger, Test-CsClientAuth tentera de se connecter à l’aide de ce certificat. Si l’ouverture de session réussit, Test-CsClientAuth ferme la session et indique que le test a réussi. Si aucun certificat n’est disponible ou s’il n’est pas possible de télécharger un certificat, ou si l’applet de commande Test-CsClientAuth ne peut pas ouvrir une session avec un certificat téléchargé, l’applet de commande indique que le test a échoué.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsClientAuth est exécutée à l’aide du compte de n’importe quel utilisateur qui est activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque le système appelle test-CsClientAuth :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié peut se connecter à Lync Server à l’aide d’un certificat client, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

Si l’utilisateur spécifié ne peut pas se connecter, le résultat est affiché sous la forme échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:03.3645259

Erreur : impossible de télécharger un certificat CS pour l’utilisateur donné. Vérifier si

l’URI fourni et les informations d’identification sont corrects.

Diagnostique

Par exemple, la sortie précédente indique que le test a échoué, car il est impossible de trouver un certificat client valide pour l’utilisateur spécifié. Vous pouvez renvoyer la liste des certificats clients délivrés à un utilisateur en exécutant une commande comme suit :

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Si Test-CsClientAuth échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Lorsque le paramètre Verbose est inclus, Test-CsClientAuth renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple :

Tentative de téléchargement d’un certificat CS pour l’utilisateur : kenmyer@litwareinc.com Endpoint : STEpid

URL du service Web : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Impossible de télécharger un certificat CS à partir du service Web.

OPTION

\- L’URL de service Web est valide et les services Web sont fonctionnels

\-Si vous utilisez \\ \\ le code confidentiel PhoneNo pour l’authentification, assurez-vous qu’ils correspondent à l’URI de l’utilisateur.

\- Si vous utilisez l' \\ authentification NTLM Kerberos, vérifiez que vous avez fourni des informations d’identification valides.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsClientAuth peut échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Il est possible que l’utilisateur test ne dispose pas d’un certificat client valide. Vous pouvez renvoyer des informations sur les certificats clients affectés à un utilisateur à l’aide d’une commande semblable à celle-ci :
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

