---
title: 'Lync Server 2013 : droits de topologie des administrateurs de test'
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
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Droits de topologie des administrateurs de test dans Lync Server 2013

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
<td><p>Planification de la vérification</p></td>
<td><p>Après le déploiement initial de Lync Server. Le cas échéant, si des problèmes liés aux autorisations se produisent.</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsSetupPermission. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Par défaut, seuls les administrateurs de domaine peuvent activer une topologie Lync Server et effectuer des modifications importantes dans l’infrastructure Lync Server. Cela n’est pas un problème tant que vos administrateurs de domaine et vos administrateurs Lync Server sont les mêmes. Dans de nombreuses organisations, les administrateurs Lync Server ne disposent pas de droits d’administration sur l’ensemble du domaine. Par défaut, cela signifie que ces administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peuvent pas modifier les topologies Lync Server. Pour donner aux membres du groupe RTCUniversalServerAdmins le droit de modifier la topologie, vous devez affecter les autorisations Active Directory requises à l’aide de l’applet de commande [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

L’applet de commande test-CsSetupPermission vérifie que les autorisations requises pour installer Lync Server ou l’un de ses composants sont configurées sur le conteneur Active Directory spécifié. Si les autorisations ne sont pas affectées, vous pouvez ensuite exécuter l’applet de commande Grant-CsSetupPermission pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’installer et d’activer Lync Server.

<div>


> [!NOTE]  
> Pour obtenir la liste détaillée des autorisations attribuées par Grant-CsSetupPermission, consultez le billet de blog <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission et Grant-CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour déterminer si des autorisations de configuration sont affectées à un conteneur Active Directory, appelez la cmdlet Test-CsSetupPermission. Spécifiez le nom unique du conteneur à vérifier. Par exemple, cette commande vérifie les autorisations d’installation sur le conteneur ou = serveurs, DC = litwareinc, DC = com :

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, l’applet de commande renverra la valeur true :

Vrai

Si les autorisations ne sont pas définies, test-CsSetupPermission renverra la valeur false. Notez que cette valeur sera généralement placée dans de nombreux messages d’avertissement. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) ATL-cs\\-001 RTCUniversalServerAdmins ; Acceptent ExtendedRight; Nul Nul 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet "CN = Computers, DC = litwareinc, DC = com" ne sont pas prêtes.

False

AVERTISSEMENT : le traitement de « test-CsSetupPermission » s’est terminé avec des avertissements. les avertissements « 2 » ont été enregistrés pendant cette exécution.

AVERTISSEMENT : vous trouverez des résultats détaillés à la page\\«\\C\\:\\Users admin AppData Local\\Temp\\test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118. html ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Bien qu’il existe de rares exceptions, si test-CsSetupPermission échoue, cela signifie généralement que les autorisations de configuration ne sont pas affectées au conteneur Active Directory spécifié. Ces autorisations peuvent être assignées à l’aide de la cmdlet Grant-CsSetupPermission. Par exemple, cette commande accorde des autorisations d’installation au conteneur ordinateurs dans le domaine litwareinc.com :

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

