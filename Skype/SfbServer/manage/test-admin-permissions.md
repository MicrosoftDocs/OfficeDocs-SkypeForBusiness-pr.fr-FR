---
title: Test des autorisations d’administrateur dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Comment tester les autorisations d’administrateur dans Skype Entreprise Server
ms.openlocfilehash: 535911c26bac5e3f1dadb2c8d59cffe82dc20c7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122398"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test des autorisations d’administrateur dans Skype Entreprise Server

| | |
|--|--|
|Planification de vérification|Après le déploiement initial de Skype Entreprise Server. Si nécessaire si des problèmes liés aux autorisations surviennent.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lorsqu’ils sont exécutés localement à l’aide de Skype Entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br><br/>Lorsqu’il est exécuté à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui disposent de l’autorisation d’exécuter la cmdlet Test-CsOUPermission commande. Pour voir la liste de tous les rôles RBAC qui peuvent utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell suivante :<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match « Test-CsOUPermission"}|
|||

## <a name="description"></a>Description

Lorsque vous installez Skype Entreprise Server, l’une des tâches effectuées par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, les ordinateurs, les contacts, les contacts d’application et les personnes InetOrg. Si vous avez désactivé l’héritage des autorisations dans Active Directory, le programme d’installation ne pourra pas attribuer ces autorisations. Par conséquent, les membres du groupe RTCUniversalUserAdmins ne pourront pas gérer les entités Skype Entreprise Server. Ces privilèges de gestion seront uniquement disponibles pour les administrateurs de domaine. 

LTest-CsOUPermission cmdlet vérifie que les autorisations requises pour gérer les utilisateurs, les ordinateurs et d’autres objets sont définies sur un conteneur Active Directory. Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant [l’cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission). 

Notez Grant-CsOUPermission pouvez uniquement attribuer des autorisations aux membres du groupe RTCUniversalUserAdmins. Vous ne pouvez pas utiliser cette cmdlet pour accorder des autorisations à un utilisateur ou un groupe arbitraire. Si vous souhaitez qu’un autre utilisateur ou groupe soit autorisé à gérer les utilisateurs, vous devez ajouter cet utilisateur (ou groupe) au groupe RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Exécution du test

Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez la cmdlet Test-CsOUPermission suivie du nom du conteneur et du type d’autorisations que vous vérifiez. Par exemple, cette commande vérifie si les autorisations utilisateur sont définies sur l’UO ou=Redmond,dc=litwareinc,dc=com :

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Pour vérifier plusieurs autorisations à l’aide d’une seule commande, insérez chaque type d’autorisation entre guillemets, puis séparez ces types par des virgules. Par exemple, cette commande vérifie les autorisations des utilisateurs, des ordinateurs et des contacts :

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Pour plus d’informations, voir la [rubrique d’aide Test-CsOUPermission cmdlet .](/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les autorisations requises ont déjà été définies, Test-CsOUPermission renvoyer une réponse en un mot :

Vrai

Si les autorisations requises ne sont pas définies, Test-CsOUPermission renvoyer la valeur False. Vous de devez peut-être rechercher un moment pour trouver cette valeur. Il est généralement incorporé dans plusieurs avertissements qui l’accompagnent. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendants ; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVERTISSEMENT : les entrées de contrôle d’accès sur l’objet « OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com » ne sont pas prêtes. 

False 

AVERTISSEMENT : le traitement « Test-CsOUPermission » s’est terminé avec des avertissements. « 2 » avertissements ont été enregistrés au cours de cette run. 

AVERTISSEMENT : des résultats détaillés sont à l'C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html. 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a peut-être échoué

Si Test-CsOUPermission échoue, cela signifie généralement que l’autorisation spécifiée n’a pas été attribuée au groupe RTCUniversalUserAdmins. Vous pouvez résoudre ce problème et attribuer les autorisations requises à l’aide Grant-CsOUPermission cmdlet. Par exemple, cette commande accorde des autorisations d’unité d’unité d’utilisateur pour les utilisateurs, les contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Pour plus d’informations, voir la [rubrique d’aide Test-CsOUPermission cmdlet .](/powershell/module/skype/test-csoupermission)