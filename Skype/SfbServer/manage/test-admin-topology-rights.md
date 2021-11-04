---
title: Test des droits de topologie d’administrateur dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Comment tester les droits de topologie dans Skype Entreprise Server
ms.openlocfilehash: 2da77957baaa510ef7669fb6a980de2aacf428a4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759716"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test des droits de topologie d’administrateur dans Skype Entreprise Server

|&nbsp; |&nbsp; |
|--|--|
|Planification de vérification|Après le déploiement initial Skype Entreprise Server' Si nécessaire si des problèmes liés aux autorisations surviennent.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lorsqu’ils sont exécutés localement à l’Skype Entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br/><br/>Lorsqu’il est exécuté à l’aide d’une instance distante de Windows PowerShell, les utilisateurs doivent se voir attribuer un rôle RBAC qui est autorisé à exécuter l'Test-CsSetupPermission cmdlet. Pour voir la liste de tous les rôles RBAC qui peuvent utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell suivante :<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match « Test-CsSetupPermission"}|
|||

## <a name="description"></a>Description

Par défaut, seuls les administrateurs de domaine peuvent activer une topologie Skype Entreprise Server et apporter des modifications importantes à l’infrastructure Skype Entreprise Server réseau. Cela ne pose aucun problème tant que vos administrateurs de domaine et vos administrateurs Skype Entreprise Server sont identiques. Dans de nombreuses organisations, Skype Entreprise Server administrateurs ne détiennent pas de droits d’administration sur l’ensemble du domaine. Par défaut, cela signifie que ces administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peuvent pas apporter de modifications Skype Entreprise Server topologie. Pour accorder aux membres du groupe RTCUniversalServerAdmins le droit d’apporter des modifications à la topologie, vous devez attribuer les autorisations Active Directory requises à l’aide de l’cmdlet [Grant-CsSetupPermission.](/powershell/module/skype/Grant-CsSetupPermission)
 
La cmdlet Test-CsSetupPermission vérifie que les autorisations requises pour installer Skype Entreprise Server ou l’un de ses composants sont configurées sur le conteneur Active Directory spécifié. Si les autorisations ne sont pas attribuées, vous pouvez exécuter l’cmdlet Grant-CsSetupPermission pour accorder aux membres du groupe RTCUniversalServerAdmins le droit d’installer et d’activer Skype Entreprise Server.

## <a name="running-the-test"></a>Exécution du test

Pour déterminer si des autorisations d’installation sont affectées à un conteneur Active Directory, appelez la cmdlet Test-CsSetupPermission de configuration. Spécifiez le nom du conteneur à vérifier. Par exemple, cette commande vérifie les autorisations d’installation sur le conteneur ou=CsServers,dc=litwareinc,dc=com :

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si Test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, la cmdlet retourne la valeur True :

Vrai 

Si les autorisations ne sont pas définies, Test-CsSetupPermission retourne la valeur False. Notez que cette valeur est généralement incluse dans de nombreux messages d’avertissement. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalServerAdmins; Autoriser ; ExtendedRight; Aucun ; Aucun ; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVERTISSEMENT : les entrées de contrôle d’accès sur l’objet « CN=Computers,DC=litwareinc,DC=com » ne sont pas prêtes. 

Faux 

AVERTISSEMENT : le traitement « Test-CsSetupPermission » s’est terminé avec des avertissements. « 2 » avertissements ont été enregistrés au cours de cette run. 

AVERTISSEMENT : des résultats détaillés sont à l'C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html. 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a peut-être échoué

Bien qu’il existe de rares exceptions, si Test-CsSetupPermission échoue, cela signifie généralement que les autorisations d’installation ne sont pas attribuées pour le conteneur Active Directory spécifié. Ces autorisations peuvent être attribuées à l’aide Grant-CsSetupPermission cmdlet. Par exemple, cette commande accorde des autorisations d’installation au conteneur Ordinateurs dans le domaine litwareinc.com :

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)