---
title: 'Lync Server 2013 : test de la fonctionnalité d’utilisation de l’expansion de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3178b96d156b64fc55f05403d50b3f7fcaa246bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Test de la fonctionnalité d’utilisation de l’expansion de groupe dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsGroupExpansion. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsGroupExpansion vous permet de déterminer si le développement de groupe fonctionne au sein de votre organisation. Lorsque le développement de groupe est activé, les utilisateurs configurent les groupes de distribution en tant que contact. Cela signifie que ces utilisateurs peuvent ensuite envoyer le même message instantané à tous les membres du groupe en adressant le message au groupe plutôt qu’aux membres individuels de ce groupe. Le développement de groupe permet de visualiser de manière simple et rapide les membres du groupe et leur statut.

Avec la cmdlet Test-CsGroupExpansion, vous spécifiez un groupe de distribution Active Directory à l’aide de l’adresse de messagerie du groupe. Test-CsGroupExpansion utilise ensuite l’expansion de groupe pour récupérer l’appartenance au groupe et comparer la liste récupérée à l’appartenance de l’adresse de messagerie de groupe que vous avez fournie. Si les deux listes correspondent, c’est que le développement de groupes fonctionne correctement. Notez que vous pouvez tester l’expansion de groupe de deux manières : en testant le service lui-même ou en testant le service Web associé.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsGroupExpansion peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de n’importe quel utilisateur qui a été activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool Lync Server testé et l’adresse de messagerie d’un groupe de distribution valide. Par exemple :

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Lync Server qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque le système appelle test-CsGroupExpansion :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié peut utiliser le développement de groupe, vous recevrez un résultat semblable à celui-ci avec la propriété Result marquée comme **Success :**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:01.1234976

«

Diagnostique

Si l’utilisateur spécifié ne peut pas utiliser le développement de groupe, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

«

Diagnostique

Test-CsGroupExpansion : le point de terminaison n’a pas pu être enregistré. Voir le code d’ErrorCode pour des raisons spécifiques.

La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’a pas pu s’inscrire auprès de Lync Server. Cela se produit généralement si le compte de test n’existe pas ou n’a pas été activé pour Lync Server. Vous pouvez vérifier que le compte existe et déterminer si le compte a été activé pour nm-OCS-14-3ème en exécutant une commande semblable à la suivante :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si test-CsGroupExpansion échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsGroupExpansion renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, cette sortie indique que le groupe de distribution spécifié est introuvable :

Tentative d’obtention d’un ticket Web.

URL du service Web :https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

À l’aide de l’authentification NTLM/Kerb.

GetWebTicketActivity terminé.

Activité « VerifyDistributionList » démarrée.

L’état de réponse du service Web DLX est le suivant : NotFound.

Activité « VerifyDistributionList » terminée en « 0,2597923 » secondes.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsGroupExpansion :

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Le développement de groupe peut être désactivé. Il est possible de désactiver le développement de groupe. Si le développement de groupe a été désactivé, la cmdlet Test-CsGroupExpansion échouera. Pour déterminer si le développement du groupe est activé, utilisez une commande semblable à celle-ci :
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

