---
title: 'Lync Server 2013 : test de la connexion Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b55ef9024caedaecb27bba3e01eb2bde5181fca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519021"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Test de la connexion de Lync Phone Edition dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsPhoneBootstrap. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsPhoneBootstrap permet aux administrateurs de vérifier qu’un utilisateur donné (en utilisant le numéro de téléphone et le code confidentiel qui lui sont attribués) peut se connecter au système à partir d’un appareil compatible avec Lync 2013 Phone Edition. (Aucun appareil n’est réellement nécessaire pour exécuter le test.)

Pour que l’applet de commande Test-CsPhoneBootstrap puisse effectuer cette vérification, le pool de serveurs d’inscriptions qui héberge le compte d’utilisateur testé doit pouvoir être détecté avec DHCP. Pour déterminer si un serveur d’inscriptions est détectable de cette manière, utilisez l’applet de commande Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer. Si cette propriété est définie sur false, vous devez utiliser Set-CsRegistrarConfiguration pour définir la valeur de la propriété sur true et faire en sorte que le Bureau d’enregistrement soit détectable à l’aide du protocole DHCP. Cela peut également être réalisé à l’aide du serveur DHCP d’entreprise et de la configuration des options spécifiques à Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter l’applet de commande Test-CsPhoneBootstrap, vous devez au minimum fournir le numéro de téléphone et le code confidentiel (PIN) du client pour un utilisateur Lync Server valide. Par exemple, cette commande teste la capacité d’ouverture de session de l’utilisateur qui a le numéro de téléphone 12065551219 et le code confidentiel 0712 :

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Pour une vérification plus complète, vous pouvez également inclure l’adresse SIP de l’utilisateur. Dans ce cas, le numéro de téléphone, le code confidentiel client et l’adresse SIP doivent tous être valides pour que le test réussisse :

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié a pu se connecter à Lync Server, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**

TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.3981276

«

Diagnostique

Si l’utilisateur spécifié n’a pas pu établir une connexion, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:04.1993845

Erreur : erreur-aucune réponse reçue pour le service de Web-Ticket.

Diagnostique

La sortie précédente indique que le test a échoué, car le service de ticket Web n’a pas répondu. Cela peut être dû à un problème avec le service lui-même ou à une adresse SIP, un numéro de téléphone ou un code confidentiel client transmis à test-CsPhoneBootstrap. Vous pouvez vérifier l’adresse SIP et le numéro de téléphone de l’utilisateur à l’aide d’une commande semblable à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Et vous pouvez vérifier que l’utilisateur dispose d’un code confidentiel valide à l’aide d’une commande comme suit :

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Si Test-CsPhoneBootstrap échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Lorsque le paramètre Verbose est inclus, Test-CsPhoneBootstrap renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, voici une partie de la sortie pour une ouverture de session infructueuse, une session dans laquelle un code confidentiel incorrect a été inclus :

Utilisation de l’authentification par code confidentiel avec le \\ code poste Tél. 12065551219:0712

Impossible d’obtenir le ticket Web

OPTION

\- L’URL de service Web est valide et les services Web sont fonctionnels

\- Si vous utilisez \\ le code confidentiel PhoneNo pour l’authentification, assurez-vous qu’ils correspondent à l’URI de l’utilisateur.

\- Si vous utilisez l' \\ authentification NTLM Kerberos, vérifiez que vous avez fourni des informations d’identification valides.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsPhoneBootstrap peut échouer :

  - Vous avez peut-être spécifié une adresse SIP qui n’est pas valide. Vous pouvez vérifier qu’une adresse SIP est correcte à l’aide d’une commande telle que celle-ci :
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Vous avez peut-être spécifié un code confidentiel qui n’est pas valide. Bien que vous ne puissiez pas récupérer le numéro de code confidentiel de l’utilisateur, vous pouvez vérifier que l’utilisateur a au moins un numéro de code confidentiel à l’aide d’une commande semblable à celle-ci :
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Vous avez peut-être spécifié un numéro de téléphone qui n’est pas valide. Vous pouvez vérifier le téléphone d’un utilisateur à l’aide d’une commande similaire à celle-ci :
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Le pool de serveurs d’inscriptions n’est pas activé pour DHCP. Pour déterminer si votre pool de serveurs d’inscriptions est activé pour DHCP, exécutez l’applet de commande Get-CsRegistrarConfiguration et vérifiez la valeur de la propriété EnableDHCPServer. Par exemple :
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

