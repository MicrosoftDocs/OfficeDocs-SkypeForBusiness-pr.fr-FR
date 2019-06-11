---
title: 'Lync Server 2013: test de la configuration du serveur LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Test de la configuration du serveur LIS dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsLisConfiguration. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsLisConfiguration vérifie la possibilité de contacter le service Web LIS. Si le service Web peut être contacté, le test sera considéré comme ayant réussi, qu’il y ait ou non d’emplacements spécifiques.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsLisConfguration à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsLisConfiguration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si le LIS est configuré correctement, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. svc

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.1616913

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Erreur: 11004, le nom demandé est valide, mais aucune donnée de la requête

type détecté

Diagnostic

Test-CsLisConfiguration: aucun cluster correspondant détecté dans la topologie.

Par exemple, la sortie précédente inclut la remarque «aucun cluster correspondant trouvé dans la topologie». Il s’agit généralement d’un problème avec le serveur Edge: les LIS utilisant le serveur de périphérie pour se connecter au fournisseur de services et valider les adresses.

Si test-CsLisConfiguration échoue alors, vous souhaiterez peut-être réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsLisConfiguration renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple :

Appel de service d’information d’emplacement.

Path du service =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Sous-réseau =

BssId = 5

ChassisId =

PortId =

PortIdSubType = type non défini

Mac

Une demande de service Web d’information d’emplacement d’exception a échoué avec le code de réponse Item400. ' Il s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTrsnactions. flux de travail. STLisConfigurationWorkflow.

Si vous examinez soigneusement la sortie précédente, vous verrez que l’applet de la cmdlet a essayé d’appeler le service d’information d’emplacement. L’un des paramètres qui ont été utilisés dans cet appel est le suivant:

BssId = 5

Ce n’est pas une valeur valide pour le champ BssID (Service Set Identifier). Au lieu de cela, un BssID doit ressembler à ceci:

12-34-56-78-90-AB

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsLisConfiguration peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

</div>

</div>

<span> </span>

</div>

</div>

</div>

