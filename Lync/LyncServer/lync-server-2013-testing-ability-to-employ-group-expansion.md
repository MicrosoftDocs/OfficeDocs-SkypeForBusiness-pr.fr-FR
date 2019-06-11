---
title: 'Lync Server 2013: possibilité de test d’utiliser l’extension de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Fonctionnalité de test permettant d’utiliser l’extension de groupe dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsGroupExpansion. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsGroupExpansion vous permet de déterminer si l’extension de groupe fonctionne au sein de votre organisation. Lorsque l’extension du groupe est activée, les utilisateurs configurent les groupes de distribution en tant que contact. Cela signifie que les utilisateurs peuvent alors envoyer le même message instantané à tous les membres du groupe en envoyant le message au groupe plutôt qu’à des membres individuels du groupe. L’extension de groupe vous permet d’afficher rapidement et facilement tous les membres du groupe et leur statut actuel.

À l’aide de l’applet de contrôle test-CsGroupExpansion, vous spécifiez un groupe de distribution Active Directory à l’aide de l’adresse de messagerie du groupe. Test-CsGroupExpansion utilise alors l’extension de groupe pour récupérer l’appartenance au groupe et comparer la liste récupérée à l’appartenance de l’adresse de messagerie de groupe que vous avez fournie. Si les deux listes correspondent, l’extension du groupe fonctionne correctement. Notez que vous pouvez tester l’extension du groupe de deux manières: en testant le service proprement dit ou en testant le service Web associé.

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsGroupExpansion à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte de tout utilisateur ayant activé Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé et l’adresse de courrier d’un groupe de distribution valide. Par exemple :

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Lync Server contenant le nom et le mot de passe du compte. Lorsque le système appelle test-CsGroupExpansion, vous devez inclure l’objet Credential et l’adresse SIP associée au compte.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié peut utiliser l’extension de groupe, vous recevrez une sortie similaire à celle-ci avec la propriété Result marquée comme **réussie:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:01.1234976

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas utiliser l’extension de groupe, le résultat s’affichera en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Error

Diagnostic

Test-CsGroupExpansion: le point de terminaison n’a pas pu s’inscrire. Afficher le code d’après pour une raison spécifique.

La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’a pas pu s’inscrire sur Lync Server. Cela se produit généralement si le compte de test n’existe pas ou n’a pas été activé pour Lync Server. Vous pouvez vérifier que le compte existe et déterminez si le compte a été activé pour nm-OCS-14-3e en exécutant une commande semblable à ce qui suit:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si test-CsGroupExpansion échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, le test-CsGroupExpansion renvoie un compte détaillé de chaque action qu’il a exécutée lorsqu’il a vérifié la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple, cette sortie indique que le groupe de distribution spécifié est introuvable:

Essayez d’obtenir le ticket Web.

URL du service Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

À l’aide de l’authentification NTLM/Kerb.

GetWebTicketActivity terminé.

Activité «VerifyDistributionList» démarrée.

DLX état de réponse du service Web est: NotFound.

Activité «VerifyDistributionList» terminée en «0,2597923» secondes.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsGroupExpansion peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - L’extension du groupe est peut-être désactivée. Il est possible de désactiver l’extension de groupe. Si l’extension du groupe a été désactivée, l’applet de contrôle CsGroupExpansion de test échoue. Pour déterminer si l’extension du groupe est activée, utilisez une commande semblable à celle-ci:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

