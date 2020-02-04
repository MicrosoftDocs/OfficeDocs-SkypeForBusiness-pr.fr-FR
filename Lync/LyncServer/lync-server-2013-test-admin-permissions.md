---
title: 'Lync Server 2013 : tester les autorisations d’administrateur'
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
ms.openlocfilehash: d4543501d668b61bbb90073c80c4e85373341d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Tester les autorisations d’administrateur dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsOUPermission. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Lorsque vous installez Lync Server 2013 1, les tâches effectuées par le programme d’installation fournissent au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, ordinateurs, contacts, contacts d’application et personnes InetOrg. Si vous avez désactivé l’héritage des autorisations dans le programme d’installation d’Active Directory, vous ne pourrez pas affecter ces autorisations. Les membres du groupe RTCUniversalUserAdmins ne seront donc pas en mesure de gérer les entités du serveur Lync. Ces privilèges de gestion ne seront accessibles qu’aux administrateurs de domaine.

L’applet de contrôle test-CsOUPermission vérifie que les autorisations requises nécessaires pour gérer les utilisateurs, les ordinateurs et d’autres objets sont définies sur un conteneur Active Directory. Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant l’applet de la cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Notez que Grant-CsOUPermission peut uniquement affecter des autorisations aux membres du groupe RTCUniversalUserAdmins. Vous ne pouvez pas utiliser cette applet de cmdlet pour accorder des autorisations à un utilisateur ou à un groupe arbitraire. Si vous souhaitez qu’un autre utilisateur ou groupe dispose d’autorisations de gestion des utilisateurs, vous devez ajouter cet utilisateur (ou groupe) au groupe RTCUniversalUserAdmins.

Pour plus d’informations sur les autorisations d’UO, voir l’article l' [héritage des autorisations est désactivé sur les ordinateurs, les utilisateurs ou les conteneurs InetOrgPerson dans Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez l’applet de cmdlet Test-CsOUPermission suivie du nom unique du conteneur et du type d’autorisations que vous vérifiez. Par exemple, cette commande vérifie si les autorisations des utilisateurs sont définies sur l’unité d’organisation UO = Redmond, DC = litwareinc, DC = com :

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Pour vérifier plusieurs autorisations en utilisant une seule commande, placez chaque type d’autorisation entre guillemets, puis séparez-les par des virgules. Par exemple, la commande suivante vérifie les autorisations de l’utilisateur, de l’ordinateur et des contacts :

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les autorisations requises ont déjà été définies, test-CsOUPermission renvoie une réponse en un mot :

Vrai

Si les autorisations requises ne sont pas définies, test-CsOUPermission renvoie la valeur false. Il se peut que vous deviez rechercher un moment pour trouver cette valeur. En général, il est intégré à plusieurs avertissements. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) ATL-cs\\-001 RTCUniversalUserReadOnlyGroup ; verte ReadProperty; ContainerInherit; Descendants ; bf967aba-0de6-11D0-00aa003049e2 ; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet « UO = AmeriqueduNord, DC = ATL-cs\\-001 DC = litwareinc, DC = com » ne sont pas prêtes.

False

AVERTISSEMENT : le traitement des « tests-CsOUPermission » s’est terminé avec des avertissements. des avertissements "2" ont été enregistrés lors de cette exécution.

AVERTISSEMENT : des résultats détaillés sont disponibles à l’adresse\\«\\C\\:\\Users\\admin AppData\\test-CsOUPermission-5d7a89af-f854-4A9C-87E3-69e37e58de. html ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

En cas d’échec du test-CsOUPermission, cela signifie généralement que l’autorisation spécifiée n’a pas été affectée au groupe RTCUniversalUserAdmins. Vous pouvez résoudre ce problème et affecter les autorisations requises à l’aide de l’applet de passe Grant-CsOUPermission. Par exemple, cette commande fournit les autorisations d’UO pour les utilisateurs, les contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

