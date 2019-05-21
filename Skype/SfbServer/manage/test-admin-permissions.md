---
title: Test des autorisations d’administrateur dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Test des autorisations d’administrateur dans Skype entreprise Server
ms.openlocfilehash: 1bae61dd4e8d5a8636a64687d279536b4989d104
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279248"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test des autorisations d’administrateur dans Skype entreprise Server

| | |
|--|--|
|Échéancier de vérification|Après le déploiement initial de Skype entreprise Server. Le cas échéant, en cas de problèmes liés aux autorisations.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lors de l’exécution locale à l’aide de Skype entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br><br/>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsOUPermission. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-match "test-CsOUPermission"}|
|||

## <a name="description"></a>Description

Lorsque vous installez Skype entreprise Server, l’une des tâches effectuées par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, ordinateurs, contacts, contacts d’application et InetOrg personnes. Si vous avez désactivé l’héritage des autorisations dans Active Directory, le programme d’installation ne peut pas affecter ces autorisations. Les membres du groupe RTCUniversalUserAdmins ne seront donc pas en mesure de gérer les entités de Skype entreprise Server. Ces privilèges de gestion ne seront accessibles qu’aux administrateurs de domaine. 

L’applet de contrôle test-CsOUPermission vérifie que les autorisations nécessaires pour gérer les utilisateurs, les ordinateurs et d’autres objets sont définies sur un conteneur Active Directory. Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant l’applet de la [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Notez que Grant-CsOUPermission peut uniquement affecter des autorisations aux membres du groupe RTCUniversalUserAdmins. Vous ne pouvez pas utiliser cette applet de cmdlet pour accorder des autorisations à un utilisateur ou à un groupe arbitraire. Si vous souhaitez qu’un autre utilisateur ou groupe dispose d’autorisations de gestion des utilisateurs, vous devez ajouter cet utilisateur (ou groupe) au groupe RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Exécution du test

Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez l’applet de cmdlet Test-CsOUPermission suivie du nom unique du conteneur et du type d’autorisations que vous vérifiez. Par exemple, cette commande vérifie si les autorisations des utilisateurs sont définies sur l’unité d’organisation UO = Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Pour vérifier plusieurs autorisations en utilisant une seule commande, placez chaque type d’autorisation entre guillemets, puis séparez-les par des virgules. Par exemple, la commande suivante vérifie les autorisations de l’utilisateur, de l’ordinateur et des contacts:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Pour plus d’informations, consultez la [rubrique d’aide de l’applet de contrôle test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les autorisations requises ont déjà été définies, test-CsOUPermission renvoie une réponse en un mot:

True

Si les autorisations requises ne sont pas définies, test-CsOUPermission renvoie la valeur false. Il se peut que vous deviez rechercher un moment pour trouver cette valeur. En général, il est intégré à plusieurs avertissements. Par exemple :

AVERTISSEMENT: entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; verte ReadProperty; ContainerInherit; Descendants; bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVERTISSEMENT: les entrées de contrôle d’accès (ACE) sur l’objet «UO = AmeriqueduNord, DC = atl-cs-001\DC = litwareinc, DC = com» ne sont pas prêtes. 

False 

AVERTISSEMENT: le traitement des «tests-CsOUPermission» s’est terminé avec des avertissements. des avertissements "2" ont été enregistrés lors de cette exécution. 

AVERTISSEMENT: des résultats détaillés sont disponibles à l’adresse «C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html». 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

En cas d’échec de test-CsOUPermission, cela signifie généralement que l’autorisation spécifiée n’a pas été affectée au groupe RTCUniversalUserAdmins. Vous pouvez résoudre ce problème et affecter les autorisations requises à l’aide de l’applet de passe Grant-CsOUPermission. Par exemple, cette commande fournit les autorisations d’UO pour les utilisateurs, les contacts et inetOrgPersons au groupe RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Pour plus d’informations, consultez la [rubrique d’aide de l’applet de contrôle test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
