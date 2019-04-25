---
title: Test des autorisations d’administrateur dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Comment tester des autorisations d’administrateur dans Skype pour Business Server
ms.openlocfilehash: 3f3f649ea01f974cf0462cabb7784bedc7a6df4f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214714"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test des autorisations d’administrateur dans Skype pour Business Server

| | |
|--|--|
|Planification de la vérification|Après avoir Skype initiale pour le déploiement de serveur d’entreprise. Selon les besoins en cas de problèmes d’autorisation.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lorsque vous exécutez localement à l’aide de la Skype pour Business Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br><br/>Lorsque vous exécutez à l’aide d’une instance de Windows PowerShell à distance, les utilisateurs doivent disposer un rôle RBAC qui est autorisé à exécuter l’applet de commande Test-CsOUPermission. Pour afficher une liste de tous les rôles RBAC que vous pouvez utiliser cette applet de commande, exécutez la commande suivante à l’invite de Windows PowerShell :<br/><br/>Get-CsAdminRole \| Where-Object {$_. Applets de commande-correspond à « Test-CsOUPermission »}|
|||

## <a name="description"></a>Description

Lorsque vous installez Skype pour Business Server, une des tâches qui a été effectuée par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory qui sont nécessaires pour gérer les utilisateurs, ordinateurs, contacts, contacts d’application et InetOrgPerson personnes. Si vous avez désactivé l’héritage des autorisations dans Active Directory, le programme d’installation ne pourrez attribuer les autorisations. Par conséquent, les membres du groupe RTCUniversalUserAdmins ne puissent gérer Skype pour les entités Business Server. Ces privilèges d’administration ne seront disponibles pour les administrateurs de domaine. 

L’applet de commande Test-CsOUPermission vérifie que les autorisations requises pour gérer les utilisateurs, ordinateurs et autres objets sont définies sur un conteneur Active Directory. Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant la [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Notez que Grant-CsOUPermission permettre uniquement attribuer des autorisations aux membres du groupe RTCUniversalUserAdmins. Vous ne pouvez pas utiliser cette applet de commande pour accorder des autorisations à un groupe ou un utilisateur arbitraire. Si vous souhaitez un autre utilisateur ou un groupe d’avoir des autorisations de gestion des utilisateurs, vous devez ajouter cet utilisateur (ou groupe) au groupe RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Exécutez le test

Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez l’applet de commande Test-CsOUPermission suivi par le nom unique du conteneur et par le type d’autorisations que vous vérifiez. Par exemple, cette commande vérifie si les autorisations utilisateur sont définies sur l’unité d’organisation de l’unité d’organisation = Redmond, dc = litwareinc, dc = com :

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Pour vérifier plusieurs autorisations à l’aide d’une seule commande, mettez-le entouré guillemets chaque type d’autorisation, puis séparez ces par des virgules. Par exemple, une seule commande vérifie les utilisateurs, ordinateurs et contact autorisations :

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Pour plus d’informations, consultez la [rubrique d’aide de l’applet de commande Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Déterminer la réussite ou l’échec

Si les autorisations requises ont déjà été définies, Test-CsOUPermission retourne une réponse d’un mot :

True

Si les autorisations ne sont pas définies, Test-CsOUPermission retourne la valeur False. Vous devrez peut-être un moment à trouver la valeur de recherche. Il sera généralement incorporé à l’intérieur de plusieurs avertissements correspondante. Par exemple :

Avertissement : contrôle d’accès (ACE) d’entrée atl-cs-001\RTCUniversalUserReadOnlyGroup ; Autoriser ; ReadProperty ; ContainerInherit ; Descendants ; 00aa003049e2-bf967aba-0de6 - 11d 0 ; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Avertissement : Les entrées contrôle d’accès (ACE) sur l’objet « unité d’organisation = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com » ne sont pas prêt. 

False 

Avertissement : Traitement de « Test-CsOUPermission » est terminée avec des avertissements. « 2 » avertissements ont été enregistrés au cours de l’exécution. 

Avertissement : Les résultats détaillés se trouvent à « C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html ». 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pourquoi le test a peut-être échoué

Si Test-CsOUPermission échoue, cela signifie généralement que l’autorisation spécifiée n’a pas été affectée au groupe RTCUniversalUserAdmins. Vous pouvez résoudre ce problème et affecter les autorisations requises, à l’aide de l’applet de commande Grant-CsOUPermission. Par exemple, cette commande donne des autorisations de l’unité d’organisation pour les utilisateurs, contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Pour plus d’informations, consultez la [rubrique d’aide de l’applet de commande Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
