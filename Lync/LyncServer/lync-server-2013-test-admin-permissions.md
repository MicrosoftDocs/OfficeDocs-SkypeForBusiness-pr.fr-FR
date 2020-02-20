---
title: 'Lync Server 2013 : autorisations d’administrateur de test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d12707cbbd03181b5606c835d50bb2f173f10da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Tester les autorisations d’administration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_


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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsOUPermission. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Lorsque vous installez Lync Server 2013 1 des tâches effectuées par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, les ordinateurs, les contacts, les contacts d’application et les personnes InetOrg. Si vous avez désactivé l’héritage des autorisations dans le programme d’installation d’Active Directory, vous ne pourrez pas attribuer ces autorisations. Par conséquent, les membres du groupe RTCUniversalUserAdmins ne pourront pas gérer les entités Lync Server. Ces privilèges de gestion ne seront accessibles qu’aux administrateurs de domaine.

L’applet de commande test-CsOUPermission vérifie que les autorisations requises pour gérer les utilisateurs, les ordinateurs et les autres objets sont définies sur un conteneur Active Directory. Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant l’applet de commande [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Notez que Grant-CsOUPermission peut uniquement attribuer des autorisations aux membres du groupe RTCUniversalUserAdmins. Vous ne pouvez pas utiliser cette applet de commande pour accorder des autorisations à un utilisateur ou un groupe arbitraire. Si vous souhaitez qu’un autre utilisateur ou groupe dispose des autorisations de gestion des utilisateurs, vous devez ajouter cet utilisateur (ou ce groupe) au groupe RTCUniversalUserAdmins.

Pour plus d’informations sur les autorisations d’unité d’organisation, voir l’article [héritage des autorisations est désactivé sur les conteneurs ordinateurs, utilisateurs ou InetOrgPerson dans Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez l’applet de commande test-CsOUPermission suivie du nom unique du conteneur et du type d’autorisations que vous vérifiez. Par exemple, cette commande vérifie si les autorisations de l’utilisateur sont définies sur l’unité d’organisation OU = Redmond, DC = litwareinc, DC = com :

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Pour vérifier plusieurs autorisations à l’aide d’une seule commande, placez chaque type d’autorisation entre guillemets, puis séparez ces types à l’aide de virgules. Par exemple, cette commande vérifie les autorisations utilisateur, ordinateur et contact :

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les autorisations requises ont déjà été définies, test-CsOUPermission renverra une réponse à mot unique :

Vrai

Si les autorisations requises ne sont pas définies, test-CsOUPermission renverra la valeur false. Il se peut que vous deviez rechercher un moment pour trouver cette valeur. Elle est généralement incorporée dans plusieurs avertissements associés. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) ATL-cs\\-001 RTCUniversalUserReadOnlyGroup ; acceptent Readpropertywriteproperty ContainerInherit; Descendants bf967aba-0de6-11D0-00aa003049e2 ; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet "OU = AmeriqueduNord, DC = ATL-cs\\-001 DC = litwareinc, DC = com" ne sont pas prêtes.

False

AVERTISSEMENT : le traitement de « test-CsOUPermission » s’est terminé avec des avertissements. les avertissements « 2 » ont été enregistrés pendant cette exécution.

AVERTISSEMENT : vous trouverez des résultats détaillés à la page\\«\\C\\:\\Users admin AppData Local\\Temp\\test-CsOUPermission-5d7a89af-f854-4A9C-87E3-69e37e58de. html ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si test-CsOUPermission échoue, cela signifie généralement que l’autorisation spécifiée n’a pas été affectée au groupe RTCUniversalUserAdmins. Vous pouvez résoudre ce problème et attribuer les autorisations requises à l’aide de la cmdlet Grant-CsOUPermission. Par exemple, cette commande donne des autorisations d’unité d’organisation pour les utilisateurs, contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

