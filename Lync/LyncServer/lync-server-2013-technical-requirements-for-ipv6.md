---
title: Configuration technique requise pour IPv6 dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0688319a1b37dbd609a2f2051b3b8c6dfc6a2d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Configuration technique requise pour IPv6 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Si vous envisagez de configurer Lync Server 2013 pour IPv6, gardez les éléments suivants à l’esprit :

  - Pour utiliser des adresses IPv6 avec Lync Server, vous devez créer des enregistrements DNS (Domain Name System) pour les enregistrements qui doivent être identifiés et résolus à une adresse IPv6. Le DNS IPv6 utilise des enregistrements AAAA (quadruple A). Si vous utilisez IPv4 et IPv6 dans votre déploiement, il est préférable de configurer et maintenir des enregistrements d’hôte A pour IPv4 et des enregistrements d’hôte AAAA pour IPv6. Même lors de la transition complète de votre déploiement vers IPv6, vous pouvez également nécessiter des enregistrements d’hôte DNS IPv4 pour les utilisateurs externes utilisant encore IPv4.
    
    Vous pouvez déployer les enregistrements d’hôte DNS IPv6 avant de commencer à utiliser IPv6. Si le client ou le serveur n’utilise pas IPv6, l’enregistrement ne sera pas référencé. Des technologies de transition décideront de l’enregistrement à utiliser, en fonction des stratégies et de la configuration des technologies de transition.

  - Chaque adresse IPv6 a une étendue. Les trois portes que vous pouvez utiliser pour l’adressage IPv6 sont les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses locales de liaison privée (similaires aux adresses IP privées automatiques dans Windows Server pour IPv4). Tous les serveurs au sein d’un pool doivent avoir des adresses IPv6 avec la même étendue.

<div>


> [!IMPORTANT]  
> Le protocole IPv6 est un sujet complexe et nécessite une planification soigneuse de votre équipe réseau et de votre fournisseur d’accès Internet pour garantir que les adresses que vous attribuez au niveau Windows Server et au niveau Lync Server 2013 fonctionnent comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Architecture d’adresse IP version 6](http://tools.ietf.org/html/rfc4291)  
[Format d’adresse monodiffusion global IPv6](http://tools.ietf.org/html/rfc3587)  
[Adresses monodiffusion IPv6 locales uniques](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

