---
title: "Lync Server 2013 : Migration des util. vers le magasin de contacts unifié"
TOCTitle: Migration des utilisateurs vers le magasin de contacts unifié
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204737(v=OCS.15)
ms:contentKeyID: 49296497
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des utilisateurs vers le magasin de contacts unifié dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-15_

Les contacts d’un utilisateur sont transférés automatiquement vers le serveur Exchange 2013 quand :

  - une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;

  - une boîte aux lettres Exchange 2013 a été mise en service pour cet utilisateur et qu’il s’y est connecté au moins une fois ;

  - l’utilisateur se connecte à l’aide d’un client riche Lync 2013.

Si l’utilisateur se connecte à l’aide d’un client Lync 2010 ou d’un client de version antérieure, ou s’il n’est pas connecté à un serveur Exchange 2013, la stratégie de services utilisateur est ignorée et les contacts de cet utilisateur restent dans Lync Server.

Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes :

  - Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur InUCSMode dont la valeur est 2165.

  - Exécutez l’applet de commande **Test-CsUnifiedContactStore**. Dans la ligne de commande Lync Server Management Shell, tapez :
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.

