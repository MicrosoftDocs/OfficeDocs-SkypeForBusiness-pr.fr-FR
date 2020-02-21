---
title: 'Lync Server 2013 : configuration requise pour DNS (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13fcb074ea5ce90bbe7097bf5c2f1f975de809c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Configuration requise pour le système DNS (Domain Name System) pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-18_

Pour déployer Lync Server, vous devez créer des enregistrements DNS (Domain Name System) qui activent la découverte des clients et des serveurs, et, éventuellement, la prise en charge de la connexion automatique des clients si votre organisation souhaite la prendre en charge.

Lync Server utilise le système DNS des manières suivantes :

  - détecter les serveurs ou pools internes pour les communications de serveur à serveur ;

  - Pour permettre aux clients de détecter le pool frontal ou le serveur Standard Edition utilisé pour diverses transactions SIP ;

  - Pour autoriser les périphériques de communications unifiées qui ne sont pas connectés pour découvrir le pool frontal ou le serveur Standard Edition exécutant le service Web de mise à jour des périphériques, récupérez les mises à jour et envoyez des journaux.

  - Pour permettre aux serveurs et clients externes de se connecter aux serveurs Edge ou au proxy inverse HTTP pour la messagerie instantanée ou la Conférence.

  - Pour permettre aux périphériques de communications unifiées externes de se connecter au service Web de mise à jour des périphériques via les serveurs Edge ou le proxy inverse HTTP et d’obtenir des mises à jour.

  - pour permettre aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Configuration DNS requise pour les pools frontaux dans Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Configuration DNS requise pour les serveurs Standard Edition Server dans Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Configuration DNS requise pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Configuration DNS requise pour la mobilité avec Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Équilibrage de la charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

