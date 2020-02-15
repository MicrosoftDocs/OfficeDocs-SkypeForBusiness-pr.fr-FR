---
title: 'Lync Server 2013 : migration des utilisateurs vers le magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d170fa183e045203398725a7b7ec4bdd4c38203
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Migrer des utilisateurs vers le magasin de contacts unifié dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

Les contacts d’un utilisateur sont transférés automatiquement vers le serveur Exchange 2013 quand :

  - une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;

  - A été configuré avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.

  - Se connecte à l’aide d’un client riche Lync 2013.

Si l’utilisateur se connecte avec un client Lync 2010 ou version antérieure, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services d’utilisateurs est ignorée et les contacts de l’utilisateur restent dans Lync Server.

Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes :

  - Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY\_Current\_user\\Software\\Microsoft\\Office\\15,0\\Lync\\\<SIP URL\>\\
    
    Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur de InUCSMode avec une valeur de 2165.

  - Exécutez l’applet de commande **Test-CsUnifiedContactStore**. Sur la ligne de commande Lync Server Management Shell, tapez :
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.

</div>

<span> </span>

</div>

</div>

</div>

