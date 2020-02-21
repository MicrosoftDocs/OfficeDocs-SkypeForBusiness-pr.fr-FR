---
title: Prise en charge de certificat générique Lync Server 2013
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
ms.openlocfilehash: 998787b3f052d2271eb2323bcdb71ddc106b57f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Prise en charge de certificat générique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-21_

Lync Server 2013 utilise des certificats pour le chiffrement des communications et l’authentification de l’identité du serveur. Dans certains cas, notamment la publication web via le proxy inverse, la saisie d’un autre nom de sujet (SAN) fort correspondant au nom de domaine complet (FQDN) du serveur hébergeant le service n’est pas requise. Dans de tels cas, il est possible d’utiliser des certificats avec des entrées SAN génériques (appelés également certificats génériques) pour réduire le coût d’un certificat exigé par une autorité de certification publique afin de réduire la complexité du processus de planification pour les certificats.

<div>


> [!WARNING]  
> Pour conserver les fonctionnalités des périphériques de communications unifiées (UC) tels que les téléphones de bureaux, il est important de tester avec soin le certificat déployé pour garantir le bon fonctionnement des périphériques après avoir implémenté un certificat générique.



</div>

Une entrée de certificat n’est pas prise en charge en tant que nom d’objet (aussi appelé nom commun ou CN) pour un rôle donné. Les rôles serveur suivants sont pris en charge lors de l’utilisation d’entrées génériques dans le SAN :

  - <span></span>  
    **Proxy inverse.**    L’entrée San générique est prise en charge pour les certificats de publication d’URL simples (de réunion et de numérotation).

  - <span></span>  
    **Proxy inverse.**    L’entrée San générique est prise en charge pour les entrées San pour LyncDiscover sur le certificat de publication.

  - <span></span>  
    **Directeur.**    L’entrée San générique est prise en charge pour les URL simples (de réunion et de numérotation) et pour les entrées San pour LyncDiscover et LyncDiscoverInternal dans les composants Web Director.

  - <span></span>  
    **Serveur frontal (Standard Edition) et pool frontal (Enterprise Edition).** L’entrée SAN générique est prise en charge pour les URL simples (de réunion et de numérotation) et pour les entrées SAN pour LyncDiscover et LyncDiscoverInternal dans les composants Web frontaux.

  - <span></span>  
    **Messagerie unifiée Exchange.**    Le serveur n’utilise pas les entrées San lorsqu’il est déployé en tant que serveur autonome.

  - <span></span>  
    **Serveur d’accès au client Microsoft Exchange Server.**    Les entrées de caractères génériques dans le San sont prises en charge pour les clients internes et externes.

  - <span></span>  
    **Messagerie unifiée Exchange et serveur d’accès au client Microsoft Exchange Server sur le même serveur.**    Les entrées San génériques sont prises en charge.

Rôles serveur non traités dans ce chapitre :

  - Rôles serveur internes (y compris, mais sans s’y limiter, le serveur de médiation, le serveur d’archivage et de surveillance, le Survivable Branch Appliance ou le serveur Survivable Branch Server)

  - Interfaces de serveur Edge externe

  - Serveur Edge interne
    
    <div>
    

    > [!NOTE]  
    > Pour l’interface de serveur Edge interne, une entrée générique peut être affectée au SAN et est prise en charge. Le SAN sur le serveur Edge interne n’est pas interrogé et une entrée SAN générique a une valeur limitée.

    
    </div>

Pour plus d’informations sur les configurations de certificats, y compris l’utilisation de caractères génériques dans les certificats, consultez les rubriques suivantes :

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Conditions requises pour les certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Résumé des certificats-charge DNS et charge matérielle équilibrée dans Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des certificats-directeur unique dans Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Résumé des certificats-proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Instructions pour l’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Pour plus d’informations sur la configuration des certificats pour Exchange, y compris l’utilisation de caractères génériques, voir la documentation du produit Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

