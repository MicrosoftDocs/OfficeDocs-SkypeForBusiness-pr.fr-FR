---
title: 'Lync Server 2013 : Migration des utilisateurs vers le magasin de contacts unifié'
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
ms.openlocfilehash: 5a57ea93af90176009fff43ed4dcca9f1880a658
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Migration des utilisateurs vers le magasin de contacts unifié dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

Les contacts d’un utilisateur sont automatiquement déplacés vers le serveur Exchange 2013 lorsque l’utilisateur :

  - une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;

  - A été configuré avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.

  - Se connecte à l’aide d’un client enrichi Lync 2013.

Si l’utilisateur se connecte à l’aide d’un client Lync 2010 ou antérieur, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services des utilisateurs est ignorée et les contacts de l’utilisateur restent dans Lync Server.

Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes :

  - Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY\_logiciel\_\\utilisateur\\actuel Microsoft\\Office\\15,0\\\\\<URL\>SIP\\de Lync
    
    Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur de InUCSMode avec une valeur de 2165.

  - Exécutez l’applet de commande **Test-CsUnifiedContactStore**. Dans la ligne de commande Lync Server Management Shell, tapez :
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.

</div>

<span> </span>

</div>

</div>

</div>

