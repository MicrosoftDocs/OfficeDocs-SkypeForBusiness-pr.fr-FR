---
title: 'Lync Server 2013 : test d’une session de conférence rendez-vous'
description: 'Lync Server 2013 : test de la session de conférence rendez-vous.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d0c51b16df674dbf8bf7f0a2c6c4c93c2606d95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560630"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Test d’une session de conférence rendez-vous dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsDialInConferencing. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsDialInConferencing vérifie si un utilisateur peut participer à une conférence rendez-vous. Test-CsDialInConferencing fonctionne en tentant de journaliser un utilisateur test sur le système. Si l’ouverture de session réussit, l’applet de commande utilise les informations d’identification et les autorisations de l’utilisateur pour essayer tous les numéros d’accès aux conférences rendez-vous disponibles. La réussite ou l’échec de chaque tentative d’accès à distance est indiqué, puis l’utilisateur de test est déconnecté de Lync Server. test-CsDialInConferencing vérifie uniquement que les connexions appropriées peuvent être établies. L’applet de commande ne passe pas réellement d’appels téléphoniques ou ne crée pas de conférences rendez-vous que d’autres utilisateurs peuvent rejoindre.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de commande Test-CsDialInConferencing peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure l’objet Credentials et l’adresse SIP du compte l’appel test-CsDialInConferencing :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié peut se connecter à Lync Server, puis établir une connexion à l’aide de l’un des numéros d’accès de conférence rendez-vous disponibles, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

Si l’utilisateur spécifié ne peut pas établir cette connexion, le résultat est affiché en tant que défaillance et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : la connexion a été refusée. Vérifiez que les informations d’identification correctes sont

en cours d’utilisation et que le compte est actif.

Exception interne : NegotiateSecurityAssociation failed, erreur :-

2146893044

Diagnostique

La sortie précédente indique que l’utilisateur test a été refusé l’accès à Lync Server lui-même. Cela signifie généralement que les informations d’identification de l’utilisateur transmises à Test-CsDialInConferencing n’étaient pas valides. Ensuite, vous devez recréer l’objet d’informations d’identification Windows PowerShell. Bien que vous puissiez récupérer le mot de passe du compte d’utilisateur, vous pouvez vérifier l’adresse SIP à l’aide d’une commande semblable à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsDialInConferencing peut échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Le numéro d’accès à la Conférence rendez-vous est peut-être incorrect. Vous pouvez retourner votre liste de numéros d’accès aux conférences rendez-vous en cours à l’aide de la commande suivante :
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

