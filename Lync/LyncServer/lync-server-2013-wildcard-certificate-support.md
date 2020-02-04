---
title: Prise en charge des certificats comportant des caractères génériques Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-21_

Lync Server 2013 utilise des certificats pour le chiffrement des communications et l’authentification par identité du serveur. Dans certains cas, par exemple, la publication sur le Web par le biais du proxy inverse, l’entrée de nouveau nom de l’élément de nom de domaine complet (FQDN) du serveur qui présente le service n’est pas requise. Dans ces cas, vous pouvez utiliser des certificats à l’aide d’entrées génériques pour réduire le coût d’un certificat demandé auprès d’une autorité de certification publique et réduire la complexité du processus de planification des certificats. .

<div>


> [!WARNING]  
> Pour conserver la fonctionnalité de périphériques de communications unifiées (UC) (par exemple, les téléphones de bureau), vous devez tester soigneusement le certificat déployé pour vous assurer que les appareils fonctionnent correctement après l’implémentation d’un certificat générique.



</div>

Il n’y a pas de prise en charge d’une entrée de caractère générique comme nom de sujet (également appelé nom commun ou NC) pour n’importe quel rôle. Les rôles de serveur suivants sont pris en charge lorsque vous utilisez des entrées de caractères génériques dans le SAN :

  - <span></span>  
    **Proxy inverse.**    L’entrée San générique est prise en charge pour les certificats de publication d’URL simples (de conférence et de numérotation).

  - <span></span>  
    **Proxy inverse.**    L’entrée San générique est prise en charge pour les entrées du San pour LyncDiscover sur le certificat de publication.

  - <span></span>  
    **Director.**    L’entrée San générique est prise en charge pour les URL simples (réunion et numéro de téléphone) et pour les entrées San pour LyncDiscover et LyncDiscoverInternal dans les composants Web Director.

  - <span></span>  
    **Serveur frontal (édition standard) et liste frontale (Enterprise Edition).** L’entrée SAN générique est prise en charge pour les URL simples (réunion et numéro de téléphone) et pour les entrées SAN pour LyncDiscover et LyncDiscoverInternal dans les composants webend Web.

  - <span></span>  
    **Exchange Unified Messaging (UM).**    Le serveur n’utilise pas d’entrées du San lorsqu’il est déployé en tant que serveur autonome.

  - <span></span>  
    **Serveur d’accès au client Microsoft Exchange Server.**    Les entrées génériques du San sont prises en charge pour les clients internes et externes.

  - <span></span>  
    **Exchange Unified Messaging (MU) et serveur d’accès au client Exchange Server sur le même serveur.**    Les entrées génériques du San sont prises en charge.

Rôles de serveur non mentionnés dans cette rubrique :

  - Rôles de serveur internes (y compris, mais sans s’y limiter, le serveur de médiation, l’archivage et la surveillance du serveur, de l’unité de branchement survivant ou du serveur de succursales survivant)

  - Interfaces de serveur Edge externes

  - Serveur Edge interne
    
    <div>
    

    > [!NOTE]  
    > Pour l’interface du serveur Edge interne, une entrée générique peut être affectée au SAN et est prise en charge. Le SAN sur le serveur Edge interne n’est pas interrogé, et une entrée SAN générique a une valeur limitée.

    
    </div>

Pour plus d’informations sur les configurations de certificats, y compris l’utilisation de caractères génériques dans les certificats, voir les rubriques suivantes :

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des certificats - Directeur unique dans Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Résumé des certificats - Proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Pour plus d’informations sur la configuration des certificats pour Exchange, y compris l’utilisation de caractères génériques, voir la documentation du produit Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

