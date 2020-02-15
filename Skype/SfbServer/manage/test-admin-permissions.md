---
title: Test des autorisations d’administrateur dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Procédure de test des autorisations d’administrateur dans Skype entreprise Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030157"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test des autorisations d’administrateur dans Skype entreprise Server

| | |
|--|--|
|Planification de la vérification|Après le déploiement initial de Skype entreprise Server. Le cas échéant, si des problèmes liés aux autorisations se produisent.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lorsqu’ils sont exécutés localement à l’aide de Skype entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br><br/>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsOUPermission. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-match "test-CsOUPermission"}|
|||

## <a name="description"></a>Description

Lorsque vous installez Skype entreprise Server, l’une des tâches effectuées par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, les ordinateurs, les contacts, les contacts d’application et InetOrg agents. Si vous avez désactivé l’héritage des autorisations dans Active Directory, le programme d’installation ne pourra pas attribuer ces autorisations. Par conséquent, les membres du groupe RTCUniversalUserAdmins ne pourront pas gérer les entités Skype entreprise Server. Ces privilèges de gestion ne seront accessibles qu’aux administrateurs de domaine. 

L’applet de commande test-CsOUPermission vérifie que les autorisations requises pour gérer les utilisateurs, les ordinateurs et les autres objets sont définies sur un conteneur Active Directory. Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant l’applet de commande [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission). 

Notez que Grant-CsOUPermission peut uniquement attribuer des autorisations aux membres du groupe RTCUniversalUserAdmins. Vous ne pouvez pas utiliser cette applet de commande pour accorder des autorisations à un utilisateur ou un groupe arbitraire. Si vous souhaitez qu’un autre utilisateur ou groupe dispose des autorisations de gestion des utilisateurs, vous devez ajouter cet utilisateur (ou ce groupe) au groupe RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Exécution du test

Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez l’applet de commande test-CsOUPermission suivie du nom unique du conteneur et du type d’autorisations que vous vérifiez. Par exemple, cette commande vérifie si les autorisations de l’utilisateur sont définies sur l’unité d’organisation OU = Redmond, DC = litwareinc, DC = com :

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Pour vérifier plusieurs autorisations à l’aide d’une seule commande, placez chaque type d’autorisation entre guillemets, puis séparez ces types à l’aide de virgules. Par exemple, cette commande vérifie les autorisations utilisateur, ordinateur et contact :

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Pour plus d’informations, consultez la [rubrique d’aide relative à l’applet de commande test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les autorisations requises ont déjà été définies, la fonction test-CsOUPermission renverra une réponse d’un mot :

Vrai

Si les autorisations requises ne sont pas définies, test-CsOUPermission renverra la valeur false. Il se peut que vous deviez rechercher un moment pour trouver cette valeur. Elle est généralement incorporée dans plusieurs avertissements associés. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup ; acceptent Readpropertywriteproperty ContainerInherit; Descendants bf967aba-0de6-11D0-00aa003049e2 ; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet "OU = AmeriqueduNord, DC = atl-cs-001\DC = litwareinc, DC = com" ne sont pas prêtes. 

False 

AVERTISSEMENT : le traitement de « test-CsOUPermission » s’est terminé avec des avertissements. les avertissements « 2 » ont été enregistrés pendant cette exécution. 

AVERTISSEMENT : les résultats détaillés sont disponibles à l’adresse « C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html ». 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si test-CsOUPermission échoue, cela signifie généralement que l’autorisation spécifiée n’a pas été affectée au groupe RTCUniversalUserAdmins. Vous pouvez résoudre ce problème et attribuer les autorisations requises à l’aide de la cmdlet Grant-CsOUPermission. Par exemple, cette commande donne des autorisations d’unité d’organisation pour les utilisateurs, contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Pour plus d’informations, consultez la [rubrique d’aide relative à l’applet de commande test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
