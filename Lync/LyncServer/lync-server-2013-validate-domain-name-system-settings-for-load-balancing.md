---
title: 'Lync Server 2013 : validation des paramètres système de nom de domaine pour l’équilibrage de charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc91b9f3c4ce28946830f6d91bd8cb90dd0544ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Valider les paramètres système de nom de domaine pour l’équilibrage de charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-02_

Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.

En outre, si vous utilisez l’équilibrage de charge DNS pour les pools de serveurs Edge, les entrées DNS suivantes sont requises :

  - Pour le service Edge d’accès Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge d’accès Lync Server (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès Lync Server sur l’un des serveurs Edge du pool.

  - Pour le service Edge de conférence Web Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge de conférence Web Lync Server (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence Web Lync Server sur l’un des serveurs Edge du pool.

  - Pour le service Edge audio/vidéo Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge audio/vidéo Lync Server (par exemple, av.contoso.com) en adresse IP du service Edge audio/vidéo Lync Server sur l’un des serveurs Edge du pool.

  - Si vous souhaitez utiliser l’équilibrage de charge DNS sur l’interface interne du pool de serveurs Edge, vous devez ajouter un enregistrement DNS, ce qui permet de résoudre le nom de domaine complet interne du pool de serveurs Edge en adresse IP de chaque serveur du pool.

Pour vérifier que DNS renvoie les valeurs correctes pour l’équilibrage de la charge DNS, vous devez utiliser l’outil Nslookup. Pour renvoyer toutes les valeurs d’un enregistrement DNS avec nslookup, exécutez la commande suivante :

`nslookup <FQDN >`

Vous devez exécuter cette commande pour chaque nom de domaine complet utilisé dans la configuration de l’équilibrage de charge DNS pour vérifier que chaque jeu d’enregistrements pour l’équilibrage de charge DNS a renvoyé toutes les entrées correctes.

</div>

<span> </span>

</div>

</div>

</div>

