---
title: 'Lync Server 2013 : tester les droits du topologie d’administrateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3681a3328f0e1e659377947919bbfc782f1fea7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Test de droits de topologie d’administrateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Après le déploiement initial de Lync Server. Le cas échéant, en cas de problèmes liés aux autorisations.</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsSetupPermission. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Par défaut, seuls les administrateurs de domaine peuvent activer une topologie de serveur Lync et apporter des modifications importantes à l’infrastructure du serveur Lync. Ce n’est pas un problème tant que les administrateurs de domaine et les administrateurs de votre serveur Lync sont les mêmes. Dans de nombreuses organisations, les administrateurs serveur Lync ne disposent pas des droits d’administration sur l’ensemble du domaine. Par défaut, cela signifie que ces administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peuvent pas apporter de modifications à la topologie Lync Server. Pour donner aux membres du groupe RTCUniversalServerAdmins l’autorisation de modifier la topologie, vous devez affecter les autorisations Active Directory requises à l’aide de l’applet de contrôle [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

L’applet de contrôle test-CsSetupPermission vérifie que les autorisations requises pour installer Lync Server ou l’un de ses composants sont configurées sur le conteneur Active Directory spécifié. Si les autorisations ne sont pas affectées, vous pouvez ensuite exécuter l’applet de passe Grant-CsSetupPermission pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’installer et d’activer Lync Server.

<div>


> [!NOTE]  
> Pour obtenir la liste détaillée des autorisations attribuées par Grant-CsSetupPermission, reportez-vous à la rubrique Grant- <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">CsSetupPermission and Grant-CsOUPermission</A>du billet de blog.



</div>

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour déterminer si des autorisations de configuration sont affectées pour un conteneur Active Directory, appelez l’applet de contrôle test-CsSetupPermission. Spécifiez le nom unique du conteneur à vérifier. Par exemple, cette commande vérifie les autorisations de configuration sur le conteneur ou = CsServers, DC = litwareinc, DC = com :

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, l’applet de contrôle renverra la valeur true :

Vrai

Si les autorisations ne sont pas définies, testez-CsSetupPermission renverra la valeur false. Notez que cette valeur est généralement incluse dans de nombreux messages d’avertissement. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) ATL-cs\\-001 RTCUniversalServerAdmins ; Verte ExtendedRight; Néant Néant 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet « CN = ordinateurs, DC = litwareinc, DC = com » ne sont pas prêtes.

False

AVERTISSEMENT : le traitement des « tests-CsSetupPermission » s’est terminé avec des avertissements. des avertissements "2" ont été enregistrés lors de cette exécution.

AVERTISSEMENT : des résultats détaillés sont disponibles à l’adresse\\suivante\\:\\«\\C\\:\\Users admin AppData Local Temp test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118. html ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Même s’il existe des exceptions rares, en cas de test-CsSetupPermission, cela signifie que les autorisations de configuration ne sont pas affectées pour le conteneur Active Directory spécifié. Ces autorisations peuvent être affectées à l’aide de l’applet de passe Grant-CsSetupPermission. Par exemple, cette commande accorde des autorisations de configuration au conteneur ordinateurs dans le domaine litwareinc.com :

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

