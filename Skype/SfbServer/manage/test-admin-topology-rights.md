---
title: Test de droits d’administrateur topologie dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Comment tester les droits de topologie dans Skype pour Business Server
ms.openlocfilehash: 6a1bbd6c052acb6488189e466522edf1aa59f2cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222820"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test de droits d’administrateur topologie dans Skype pour Business Server

| | |
|--|--|
|Planification de la vérification|Après avoir Skype initiale pour le déploiement de serveur d’entreprise. Selon les besoins en cas de problèmes d’autorisation.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lorsque vous exécutez localement à l’aide de la Skype pour Business Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br/><br/>Lorsque vous exécutez à l’aide d’une instance de Windows PowerShell à distance, les utilisateurs doivent disposer un rôle RBAC qui est autorisé à exécuter l’applet de commande Test-CsSetupPermission. Pour afficher une liste de tous les rôles RBAC que vous pouvez utiliser cette applet de commande, exécutez la commande suivante à l’invite de Windows PowerShell :<br/><br/>Get-CsAdminRole \| Where-Object {$_. Applets de commande-correspond à « Test-CsSetupPermission »}|
|||

## <a name="description"></a>Description

Par défaut, seuls les administrateurs de domaine peuvent activer un Skype pour la topologie du serveur d’entreprise et modifier grande le Skype pour l’infrastructure de serveur d’entreprise. Ce ne sera pas un problème dans la mesure où les administrateurs de votre domaine et votre Skype pour les administrateurs Business Server sont les mêmes. Dans de nombreuses organisations Skype pour les administrateurs de serveur d’entreprise ne contiennent pas de droits d’administration pour l’ensemble du domaine. Par défaut, ce qui signifie que ces administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peut pas faire Skype pour que les modifications de topologie Business Server. Pour accorder aux membres du groupe RTCUniversalServerAdmins le droit d’apporter des modifications de topologie, vous devez affecter les autorisations Active Directory à l’aide de l’applet de commande [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
L’applet de commande Test-CsSetupPermission vérifie que les autorisations qui sont requises pour installer Skype pour Business Server ou l’un de ses composants sont configurées dans le conteneur Active Directory spécifié. Si les autorisations ne sont pas affectées, vous pouvez ensuite exécuter l’applet de commande Grant-CsSetupPermission pour accorder aux membres du groupe RTCUniversalServerAdmins le droit d’installer et activer Skype pour Business Server.

## <a name="running-the-test"></a>Exécutez le test

Pour déterminer si des autorisations de configuration sont assignées pour un conteneur Active Directory, appelez la cmdlet Test-CsSetupPermission. Spécifiez le nom unique du conteneur à vérifier. Par exemple, cette commande vérifie les autorisations de configuration dans l’unité d’organisation de conteneur = CsServers, dc = litwareinc, dc = com :

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Déterminer la réussite ou l’échec

Si le Test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, l’applet de commande retourne la valeur True :

True 

Si les autorisations ne sont pas définies, Test-CsSetupPermission retourne la valeur False. Notez que cette valeur est généralement placée dans plusieurs messages d’avertissement. Par exemple :

Avertissement : Contrôle d’accès (ACE) d’entrée atl-cs-001\RTCUniversalServerAdmins ; Autoriser ; ExtendedRight ; None ; None ; 1131f6aa-9c07-11D1-f79f-00C04FC2DCD2 

Avertissement : Les entrées contrôle d’accès (ACE) sur l’objet « CN = Computers, DC = litwareinc, DC = com » ne sont pas prêt. 

False 

Avertissement : Traitement de « Test-CsSetupPermission » est terminée avec des avertissements. « 2 » avertissements ont été enregistrés au cours de l’exécution. 

Avertissement : Les résultats détaillés se trouvent à « C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html ». 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pourquoi le test a peut-être échoué

Bien qu’il existe des exceptions rares, en cas de Test-CsSetupPermission qui généralement signifie que les autorisations d’installation n’est pas affectés pour le conteneur Active Directory spécifié. Ces autorisations peuvent être attribuées à l’aide de l’applet de commande Grant-CsSetupPermission. Par exemple, cette commande accorde des autorisations pour le conteneur ordinateurs dans le domaine litwareinc.com :

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
