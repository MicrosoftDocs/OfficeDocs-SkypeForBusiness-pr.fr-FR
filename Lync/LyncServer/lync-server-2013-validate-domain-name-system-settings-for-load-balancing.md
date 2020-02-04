---
title: 'Lync Server 2013 : valider les paramètres système de nom de domaine pour l’équilibrage de charge'
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
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Valider les paramètres système de nom de domaine pour l’équilibrage de charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-02_

Pour prendre en charge le FQDN utilisé par l’équilibrage de charge DNS, vous devez configurer le système DNS pour résoudre le nom de domaine complet (par exemple, pool01.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Vous ne devez inclure que les adresses IP des serveurs actuellement déployés.

Par ailleurs, si vous utilisez l’équilibrage de charge DNS pour les pools Edge, les entrées DNS suivantes sont nécessaires :

  - Pour le service Edge d’accès de Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès de Lync Server (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès de Lync Server sur l’un des serveurs Edge du pool.

  - Pour le service Edge de conférence Web Lync Server, vous devez disposer d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet (par exemple, webconf.contoso.com) du service Edge de conférence Web de Lync Server (par exemple,) à l’adresse IP du service Edge de conférence Web de Lync Server sur l’un des serveurs Edge du pool.

  - Pour le service Edge audio/vidéo de Lync Server, vous devez disposer d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (par exemple, av.contoso.com) de l’adresse IP du serveur Lync Server audio/vidéo de Lync Server sur l’un des serveurs Edge du pool.

  - Si vous souhaitez utiliser l’équilibrage de charge DNS sur l’interface interne du pool de bords, vous devez ajouter un enregistrement DNS, qui résout le nom de domaine complet (FQDN) du pool Edge vers l’adresse IP de chaque serveur du pool.

Pour vérifier que le DNS renvoie les valeurs correctes pour l’équilibrage de charge DNS, vous devez utiliser l’outil Nslookup. Pour renvoyer toutes les valeurs d’un enregistrement DNS avec nslookup, exécutez la commande suivante :

`nslookup <FQDN >`

Exécutez cette commande pour chaque nom de domaine complet utilisé dans la configuration de l’équilibrage de charge DNS pour vérifier que chaque jeu d’enregistrements pour l’équilibrage de charge DNS a renvoyé toutes les entrées correctes.

</div>

<span> </span>

</div>

</div>

</div>

