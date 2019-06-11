---
title: 'Lync Server 2013: possibilité de test de se connecter à un domaine fédéré'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2176008e3e941068f61a2fb385fa6230df6b25dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Le test de la capacité à se connecter à un domaine fédéré à partir de Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsFederatedPartner. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Test-CsFederatedPartner vérifie la possibilité de se connecter au domaine d’un partenaire fédéré. Pour vérifier la connectivité d’un domaine, ce domaine doit être répertorié dans la collection de domaines autorisés (fédéré). Vous pouvez récupérer la liste des domaines de votre liste de domaines autorisés en utilisant la commande suivante:

    Get-CsAllowedDomain

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-FederatedPartner nécessite deux éléments d’information: le nom de domaine complet (FQDN) de votre serveur Edge et le nom de domaine complet (FQDN) du partenaire fédéré. Par exemple, la commande suivante permet de tester la capacité à se connecter au domaine contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Cette commande vous permet de tester les connexions à tous les domaines figurant actuellement dans votre liste de domaines autorisés:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si le domaine spécifié est joignable, vous recevrez une sortie similaire à celle-ci avec la propriété Result marquée comme **réussie:**

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:00

Error

Diagnostic

Si le domaine spécifié ne peut pas être contacté, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Erreur: 504, délai du serveur

Diagnostic: codeerreur = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir

Code de réponse et phrase de raison.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué en raison d’une erreur de délai d’expiration du serveur. Cela indique généralement des problèmes de connectivité réseau ou des problèmes de contact du serveur Edge.

Si test-CsFederatedPartner échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsFederatedPartner peuvent échouer:

  - Le serveur de périphérie n’est peut-être pas disponible. Vous pouvez utiliser les noms de domaine complets de votre serveur Edge en utilisant la commande suivante:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Vous pouvez ensuite tester chaque serveur Edge pour vérifier qu’il est accessible via le réseau. Par exemple :
    
        ping atl-edge-001.litwareinc.com

  - Le domaine spécifié n’est peut-être pas répertorié dans la liste des domaines autorisés. Pour vérifier les domaines qui ont été ajoutés à la liste des domaines autorisés, utilisez la commande suivante:
    
        Get-CsAllowedDomain
    
    Pour afficher une liste des domaines avec lesquels les utilisateurs ne peuvent plus communiquer, utilisez la commande suivante:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

