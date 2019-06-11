---
title: 'Lync Server 2013: test de connexion à Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2cf0dae748cf82e83e86389abf55c55c8c70e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Test de la connexion Lync Phone Edition dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsPhoneBootstrap. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsPhoneBootstrap permet aux administrateurs de vérifier qu’un utilisateur donné (en utilisant le numéro de téléphone et le code confidentiel qui lui est affecté) peut se connecter au système à partir d’un appareil compatible Lync 2013 Phone Edition. (Aucun appareil n’est réellement requis pour exécuter le test.)

Pour que test-CsPhoneBootstrap effectue sa vérification, le pool d’inscriptions qui héberge le compte d’utilisateur testé doit être détectable par le biais du protocole DHCP. Pour déterminer si un bureau d’enregistrement est détectable de cette manière, utilisez la cmdlet Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer. Si cette propriété est définie sur false, vous devez utiliser SET-CsRegistrarConfiguration pour définir la valeur de la propriété sur true et rendre le Bureau d’enregistrement détectable par le biais du protocole DHCP. Vous pouvez également effectuer cette opération à l’aide du serveur DHCP d’entreprise et de la configuration des options spécifiques de Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter l’applet de contrôle de test-CsPhoneBootstrap, vous devez, au minimum, fournir le numéro de téléphone et le code confidentiel (PIN) du client pour un utilisateur valide de Lync Server. Par exemple, cette commande teste la capacité de connexion de l’utilisateur disposant du numéro de téléphone 12065551219 et du code confidentiel 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Pour une vérification plus complète, vous pouvez également inclure l’adresse SIP de l’utilisateur. Dans ce cas, le numéro de téléphone, le code confidentiel du client et l’adresse SIP doivent être valides pour que le test réussisse:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié a réussi à se connecter à Lync Server, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.3981276

Error

Diagnostic

Si l’utilisateur spécifié n’a pas réussi à établir une connexion, le résultat s’affichera en panne et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:04.1993845

Erreur: erreur-absence de réponse pour le service de ticket Web.

Diagnostic

La sortie précédente indique que le test a échoué, car le service de ticket Web ne répond pas. Cela peut être dû à un problème avec le service proprement dit, ou à l’adresse du SIP, au numéro de téléphone ou au code confidentiel client transmis à test-CsPhoneBootstrap. Vous pouvez vérifier l’adresse SIP et le numéro de téléphone de l’utilisateur à l’aide d’une commande similaire à celle-ci:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Vous pouvez aussi vérifier que l’utilisateur dispose d’un code confidentiel valide à l’aide d’une commande comme suit:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Si test-CsPhoneBootstrap échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsPhoneBootstrap renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple, voici une partie de la sortie d’un échec d’ouverture de session, une session dans laquelle un code confidentiel incorrect a été inclus:

Utilisation de PIN auth avec\\le numéro de téléphone: 12065551219 code confidentiel: 0712

Impossible d’obtenir le ticket Web

Recherchez

\-L’URL du service Web est valide et les services Web sont opérationnels

\-Si vous utilisez\\PhoneNo code confidentiel pour l’authentification, vérifiez qu’il correspond à l’URI de l’utilisateur.

\-Si vous utilisez\\l’authentification Kerberos NTLM, assurez-vous d’avoir fourni les informations d’identification valides.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsPhoneBootstrap peuvent échouer:

  - Vous avez peut-être spécifié une adresse SIP qui n’est pas valide. Vous pouvez vérifier l’exactitude d’une adresse SIP en utilisant une commande telle que celle-ci:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Vous avez peut-être spécifié un code confidentiel qui n’est pas valide. Même si vous ne pouvez pas récupérer le numéro de téléphone de l’utilisateur, vous pouvez vérifier que l’utilisateur a au moins un numéro de code confidentiel en utilisant une commande semblable à ce qui suit:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Vous avez peut-être spécifié un numéro de téléphone qui n’est pas valide. Vous pouvez vérifier le téléphone d’un utilisateur à l’aide d’une commande semblable à ce qui suit:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Le pool d’inscriptions n’est pas activé par DHCP. Pour déterminer si votre pool d’inscriptions est activé pour DHCP, exécutez l’applet de contrôle Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer. Par exemple :
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

