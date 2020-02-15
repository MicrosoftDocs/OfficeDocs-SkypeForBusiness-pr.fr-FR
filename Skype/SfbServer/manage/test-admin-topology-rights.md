---
title: Test des droits de la topologie d’administration dans Skype entreprise Server
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
description: Procédure de test des droits de topologie dans Skype entreprise Server
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030147"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test des droits de la topologie d’administration dans Skype entreprise Server

| | |
|--|--|
|Planification de la vérification|Après le déploiement initial de Skype entreprise Server. Le cas échéant, si des problèmes liés aux autorisations se produisent.|
|Outil de test|Windows PowerShell|
|Autorisations requises|Lorsqu’ils sont exécutés localement à l’aide de Skype entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.<br/><br/>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsSetupPermission. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-match "test-CsSetupPermission"}|
|||

## <a name="description"></a>Description

Par défaut, seuls les administrateurs de domaine peuvent activer une topologie Skype entreprise Server et effectuer des modifications importantes dans l’infrastructure Skype entreprise Server. Cela n’est pas un problème tant que vos administrateurs de domaine et vos administrateurs Skype entreprise Server sont les mêmes. Dans de nombreuses organisations, les administrateurs de Skype entreprise Server ne possèdent pas de droits d’administration pour l’ensemble du domaine. Par défaut, cela signifie que ces administrateurs (définis en tant que membres du groupe RTCUniversalServerAdmins) ne peuvent pas modifier la topologie Skype entreprise Server. Pour donner aux membres du groupe RTCUniversalServerAdmins le droit de modifier la topologie, vous devez affecter les autorisations Active Directory requises à l’aide de l’applet de commande [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .
 
L’applet de commande test-CsSetupPermission vérifie que les autorisations requises pour installer Skype entreprise Server ou l’un de ses composants sont configurées sur le conteneur Active Directory spécifié. Si les autorisations ne sont pas affectées, vous pouvez ensuite exécuter l’applet de commande Grant-CsSetupPermission pour donner aux membres du groupe RTCUniversalServerAdmins le droit d’installer et d’activer Skype entreprise Server.

## <a name="running-the-test"></a>Exécution du test

Pour déterminer si des autorisations de configuration sont affectées à un conteneur Active Directory, appelez la cmdlet Test-CsSetupPermission. Spécifiez le nom unique du conteneur à vérifier. Par exemple, cette commande vérifie les autorisations d’installation sur le conteneur ou = serveurs, DC = litwareinc, DC = com :

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si test-CsSetupPermission détermine que les autorisations requises ont déjà été définies sur un conteneur Active Directory, l’applet de commande renverra la valeur true :

Vrai 

Si les autorisations ne sont pas définies, test-CsSetupPermission renverra la valeur false. Notez que cette valeur sera généralement placée dans de nombreux messages d’avertissement. Par exemple :

AVERTISSEMENT : entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalServerAdmins ; Acceptent ExtendedRight; Nul Nul 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVERTISSEMENT : les entrées de contrôle d’accès (ACE) sur l’objet "CN = Computers, DC = litwareinc, DC = com" ne sont pas prêtes. 

False 

AVERTISSEMENT : le traitement de « test-CsSetupPermission » s’est terminé avec des avertissements. les avertissements « 2 » ont été enregistrés pendant cette exécution. 

AVERTISSEMENT : les résultats détaillés sont disponibles à l’adresse « C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html ». 

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Bien qu’il existe de rares exceptions, si test-CsSetupPermission échoue, cela signifie généralement que les autorisations de configuration ne sont pas affectées au conteneur Active Directory spécifié. Ces autorisations peuvent être assignées à l’aide de la cmdlet Grant-CsSetupPermission. Par exemple, cette commande accorde des autorisations d’installation au conteneur ordinateurs dans le domaine litwareinc.com :

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .
