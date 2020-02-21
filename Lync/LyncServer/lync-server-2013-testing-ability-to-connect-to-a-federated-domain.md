---
title: 'Lync Server 2013 : test de la fonctionnalité de connexion à un domaine fédéré'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ce7f6855e792b5edd339ee87f2955336a943615
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Test de la possibilité de se connecter à un domaine fédéré à partir de Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsFederatedPartner. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Test-CsFederatedPartner vérifie votre capacité à vous connecter au domaine d’un partenaire fédéré. Pour vérifier la connectivité à un domaine, ce domaine doit être mentionné dans la collection de domaines autorisés (fédérés). Vous pouvez récupérer la liste des domaines de votre liste de domaines autorisés à l’aide de la commande suivante :

    Get-CsAllowedDomain

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-FederatedPartner nécessite deux informations : le nom de domaine complet (FQDN) de votre serveur Edge et le nom de domaine complet (FQDN) du partenaire fédéré. Par exemple, cette commande teste la capacité à se connecter au domaine contoso.com :

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Cette commande vous permet de tester les connexions à tous les domaines figurant actuellement dans la liste des domaines autorisés :

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si le domaine spécifié peut être contacté, vous recevrez un résultat semblable à celui-ci avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:00

«

Diagnostique

Si le domaine spécifié ne peut pas être contacté, le résultat est affiché en tant que échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 504, délai d’attente du serveur

Diagnostic : ErrorCode = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir

Code de réponse et expression de motif.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué en raison d’une erreur de délai d’attente du serveur. Cela indique généralement des problèmes de connectivité réseau ou des problèmes de contact avec le serveur Edge.

Si test-CsFederatedPartner échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsFederatedPartner :

  - Le serveur Edge n’est peut-être pas disponible. Vous pouvez utiliser cette commande pour les noms de domaine complets de vos serveurs Edge :
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Vous pouvez ensuite exécuter la commande ping sur chaque serveur Edge pour vérifier qu’il est accessible sur le réseau. Par exemple :
    
        ping atl-edge-001.litwareinc.com

  - Le domaine spécifié n’est peut-être pas répertorié dans la liste des domaines autorisés. Pour vérifier les domaines qui ont été ajoutés à la liste des domaines autorisés, utilisez la commande suivante :
    
        Get-CsAllowedDomain
    
    Si vous souhaitez afficher la liste des domaines avec lesquels les utilisateurs ne peuvent pas communiquer, utilisez la commande suivante :
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

