---
title: 'Lync Server 2013 : test de la configuration du serveur LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ca367d288b219f3873f511173626500d5d43aa3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Test de la configuration du serveur LIS dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsLisConfiguration. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsLisConfiguration vérifie votre capacité à contacter le service Web LIS. Si le service Web peut être contacté, le test sera considéré comme une réussite, que des emplacements spécifiques puissent être trouvés ou non.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsLisConfguration peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsLisConfiguration :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la LIS est configurée correctement, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée with **Success :**

TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. svc

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.1616913

«

Diagnostique

Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat s’affiche en panne et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetUri

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 11004, le nom demandé est valide, mais aucune donnée de la requête

le type a été trouvé

Diagnostique

Test-CsLisConfiguration : aucun cluster correspondant n’a été trouvé dans la topologie.

Par exemple, la sortie précédente inclut la note « aucun cluster de correspondance n’a été trouvé dans la topologie ». Cela indique généralement un problème avec le serveur Edge : la LIS qui utilise le serveur Edge pour se connecter au fournisseur de services et valider les adresses.

Si test-CsLisConfiguration échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsLisConfiguration renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple :

Appel du service d’informations d’emplacement.

Chemin d’accès du service =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Sous-réseau =

BssId = 5

ChassisId =

PortId =

PortIdSubType = type non défini

Mac

Une demande de service Web d’informations d’emplacement de l’exception a échoué avec un code de réponse Item400. s’est produite lors de l’exécution de flux de travail Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.

Si vous examinez attentivement la sortie précédente, vous verrez que l’applet de commande a échoué après avoir tenté d’appeler le service d’informations d’emplacement. L’un des paramètres qui ont été utilisés dans cet appel était le suivant :

BssId = 5

Il ne s’agit pas d’une valeur valide pour l’identificateur BssID (Basic Service Set Identifier). Au lieu de cela, un BssID doit ressembler à ceci :

12-34-56-78-90-AB

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsLisConfiguration :

  - Une valeur de paramètre incorrecte a été fournie. Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

</div>

</div>

<span> </span>

</div>

</div>

</div>

