---
title: Test de droits de topologie d’administrateur dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Comment tester les droits topologiques dans Skype entreprise Server
ms.openlocfilehash: d70809ba929c4f1934adce2bd3c60b261bd30d71
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279242"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test de droits de topologie d’administrateur dans Skype entreprise Server

| | |
|--|--|
|Échéancier de vérification|Après le déploiement initial de Skype entreprise Server. Le cas échéant, en cas de problèmes liés aux autorisations.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lors de l’exécution locale à l’aide de Skype entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br/><br/>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsSetupPermission. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-match "test-CsSetupPermission"}|
|||

## <a name="description"></a>Description

Par défaut, seuls les administrateurs de domaine peuvent activer une topologie Skype entreprise Server et apporter des modifications importantes à l’infrastructure de Skype entreprise Server. Ce n’est pas un problème tant que les administrateurs de votre domaine et les administrateurs de votre serveur Skype entreprise sont les mêmes. Dans de nombreuses organisations, les administrateurs de Skype entreprise Server ne disposent pas des droits d’administration sur l’ensemble du domaine. Par défaut, cela signifie que les administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peuvent pas apporter de modifications à la topologie de Skype entreprise Server. Pour donner aux membres du groupe RTCUniversalServerAdmins l’autorisation de modifier la topologie, vous devez affecter les autorisations Active Directory requises à l’aide de l’applet de contrôle [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
L’applet de contrôle test-CsSetupPermission vérifie que les autorisations requises pour l’installation de Skype entreprise Server ou l’un de ses composants sont configurées sur le conteneur Active Directory spécifié. Si les autorisations ne sont pas affectées, vous pouvez ensuite exécuter l’applet de passe Grant-CsSetupPermission pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’installer et d’activer Skype entreprise Server.

## <a name="running-the-test"></a>Exécution du test

Pour déterminer si des autorisations de configuration sont affectées pour un conteneur Active Directory, appelez l’applet de contrôle test-CsSetupPermission. Spécifiez le nom unique du conteneur à vérifier. Par exemple, cette commande vérifie les autorisations de configuration sur le conteneur ou = CsServers, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, l’applet de contrôle renverra la valeur true:

True 

Si les autorisations ne sont pas définies, testez-CsSetupPermission renverra la valeur false. Notez que cette valeur est généralement incluse dans de nombreux messages d’avertissement. Par exemple :

AVERTISSEMENT: entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalServerAdmins; Verte ExtendedRight; Néant Néant 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVERTISSEMENT: les entrées de contrôle d’accès (ACE) sur l’objet «CN = ordinateurs, DC = litwareinc, DC = com» ne sont pas prêtes. 

False 

AVERTISSEMENT: le traitement des «tests-CsSetupPermission» s’est terminé avec des avertissements. des avertissements "2" ont été enregistrés lors de cette exécution. 

AVERTISSEMENT: des résultats détaillés sont disponibles à l’adresse «C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html». 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Même s’il existe des exceptions rares, en cas de test-CsSetupPermission, cela signifie que les autorisations de configuration ne sont pas affectées pour le conteneur Active Directory spécifié. Ces autorisations peuvent être affectées à l’aide de l’applet de passe Grant-CsSetupPermission. Par exemple, cette commande accorde des autorisations de configuration au conteneur ordinateurs dans le domaine litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
