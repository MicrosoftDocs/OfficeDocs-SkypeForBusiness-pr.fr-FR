---
title: 'Configuration requise pour Lync Server 2013: DNS (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Configuration requise pour le service DNS (Domain Name System) pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-18_

Pour déployer Lync Server, vous devez créer des enregistrements DNS (Domain Name System) qui autorisent la découverte de clients et de serveurs et, éventuellement, la prise en charge de la connexion automatique du client si votre organisation veut le prendre en charge.

Lync Server utilise le DNS de l’une des façons suivantes:

  - Pour découvrir les serveurs internes ou les pools de communications serveur à serveur.

  - Pour permettre aux clients de découvrir le pool frontal ou le serveur Standard Edition utilisé pour différentes transactions SIP.

  - Pour autoriser les appareils de communications unifiées (UC) qui ne sont pas connectés à un appareil pour découvrir le pool frontal ou le serveur Standard Edition Web exécutant la mise à jour des appareils, obtenez les mises à jour et envoyez les journaux.

  - Pour permettre à des serveurs et clients externes de se connecter à des serveurs Edge ou au proxy HTTP inverse pour la messagerie instantanée ou les conférences.

  - Pour autoriser les appareils à UC externes à se connecter à un service Web de mise à jour d’appareil via des serveurs Edge ou le proxy HTTP inverse, et obtenir des mises à jour.

  - Pour permettre aux clients mobiles de détecter automatiquement les ressources de services Web sans exiger l’entrée manuelle des URL dans les paramètres de l’appareil.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Configuration DNS requise pour les listes frontales dans Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Configuration DNS requise pour les serveurs Standard Edition Server dans Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Configuration DNS requise pour la connexion automatique au client dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Configuration DNS requise pour la mobilité avec Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

