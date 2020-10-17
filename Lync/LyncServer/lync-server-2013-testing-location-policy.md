---
title: 'Lync Server 2013 : test de la stratégie d’emplacement'
description: 'Lync Server 2013 : test de la stratégie d’emplacement.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4efc7ac6f3beef875ce1496b19b875ff252b145b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560600"
---
# <a name="testing-location-policy-in-lync-server-2013"></a>Test de la stratégie d’emplacement dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsLocationPolicy. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsLocationPolicy vérifie qu’une stratégie d’emplacement est attribuée à un utilisateur. La stratégie d’emplacement est utilisée pour appliquer des paramètres liés à la fonctionnalité E9-1-1 et la position du client. La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si la réponse est « oui », quel est le comportement d’un appel d’urgence. Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro qui constitue un appel d’urgence (911 aux États-Unis), si la sécurité de l’entreprise doit être automatiquement notifiée et comment l’appel doit être acheminé.

Vous pouvez tester les stratégies d’emplacement sur les utilisateurs ou les sous-réseaux. Si vous effectuez un test sur un sous-réseau (en spécifiant la valeur pour le paramètre de sous-réseau), l’applet de commande essaiera de résoudre la stratégie d’emplacement pour ce sous-réseau. Si aucune stratégie d’emplacement n’a été assignée au sous-réseau, c’est la stratégie d’emplacement de l’utilisateur configuré qui sera récupérée. Si la stratégie de sous-réseau est récupérée, la sortie inclut une valeur LocationPolicyTagID qui commence par Subnet-TagId. Si la stratégie d’emplacement pour le sous-réseau n’a pas été récupérée, LocationPolicyTagID commencera par l’identifiant de l’utilisateur.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de commande Test-CsLocationPolicy peut être exécutée à l’aide d’un compte de test préconfiguré (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsLocationPolicy :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié possède une stratégie d’emplacement valide, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**

EnhancedEmergencyServicesEnabled : true

LocationPolicyTagID : User-TagId

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

S’il n’est pas possible de trouver une stratégie d’emplacement valide pour l’utilisateur spécifié, result est affiché en tant que Failure et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,

Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas

présent.

Microsoft. RTC. signalisation. DiagnosticHeader

La sortie précédente indique que le test a échoué, car l’utilisateur spécifié n’est pas valide : le compte n’existe pas ou l’utilisateur n’a pas été activé pour Lync Server. Vous pouvez vérifier la validité d’un compte et déterminer si ce compte a été activé pour nm-OCS-14-3e, en exécutant une commande semblable à celle-ci :

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si Test-CsLocationPolicy échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, Test-CsLocationPolicy renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la stratégie d’emplacement. Par exemple, cette sortie indique que Lync Server n’a pas pu se connecter à l’utilisateur test, probablement parce qu’un mot de passe incorrect a été fourni :

Envoi d’une demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port de serveur d’inscriptions = 5061

Le type d’authentification « IWA » est sélectionné.

Accès à l’inscription sur SIP/ATL-CS-001. litwareinc. com

Activité « Register » terminée dans le « 0,0601795 » secondes.

Une exception’l’ouverture de session a été refusée. Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. ' s’est produite pendant le flux de travail.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsLocationPolicy peut échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

