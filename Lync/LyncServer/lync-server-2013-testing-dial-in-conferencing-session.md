---
title: 'Lync Server 2013 : test de la session de conférence rendez-vous'
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
ms.openlocfilehash: 1afb4ee2e1a500b08c3481f71994f585298bc8c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Test de la session de conférence rendez-vous dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsDialInConferencing. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsDialInConferencing vérifie si un utilisateur peut participer à une conférence rendez-vous. Test-CsDialInConferencing fonctionne en essayant de consigner un utilisateur de test sur le système. En cas de réussite de l’ouverture de session, l’applet de connexion utilise les informations d’identification et les autorisations de l’utilisateur pour essayer tous les numéros d’accès à la Conférence rendez-vous disponibles. Le succès ou l’échec de chaque tentative de connexion est noté, l’utilisateur de test sera déconnecté de Lync Server. test-CsDialInConferencing vérifie uniquement que les connexions appropriées peuvent être effectuées. L’applet de connexion n’effectue aucun appel téléphonique ou ne crée pas de conférences rendez-vous que d’autres utilisateurs peuvent rejoindre.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsDialInConferencing à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Vous devez alors inclure cet objet Credential et le protocole SIP correspondant à l’appel de test-CsDialInConferencing :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié peut se connecter à Lync Server et établir une connexion à l’aide de l’un des numéros d’accès pour les conférences rendez-vous disponibles, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:06.8630376

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas établir cette connexion, le résultat s’affichera en panne et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : la connexion a été refusée. Vérifiez que les informations d’identification appropriées sont

utilisé et le compte est actif.

Exception interne : NegotiateSecurityAssociation a échoué, erreur :-

2146893044

Diagnostic

La sortie précédente indique que l’utilisateur de test a été refusé d’accéder au serveur Lync. En règle générale, cela signifie que les informations d’identification de l’utilisateur transmises à test-CsDialInConferencing n’étaient pas valides. Ensuite, vous devez recréer l’objet des informations d’identification Windows PowerShell. Même si vous pouvez récupérer le mot de passe du compte d’utilisateur, vous pouvez vérifier l’adresse SIP à l’aide d’une commande similaire à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsDialInConferencing peuvent échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Vous avez peut-être un numéro d’accès à une conférence rendez-vous incorrect. Vous pouvez revenir à la liste actuelle des numéros d’accès aux conférences rendez-vous à l’aide de la commande suivante :
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

