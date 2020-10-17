---
title: 'Lync Server 2013 : prise en charge de l’infrastructure DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed40fb498b93f0c6f3b1a8d32c7642f7714998ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528941"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Prise en charge de l’infrastructure DNS dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-08_

Lync Server 2013 nécessite DNS (Domain Name System) et l’utilise de la manière suivante :

  - détecter les serveurs ou pools internes pour les communications de serveur à serveur ;

  - permettre aux clients de détecter le pool de serveurs frontaux ou le serveur Standard Edition utilisé pour diverses transactions SIP ;

  - associer les URL simples des conférences aux serveurs hébergeant ces conférences ;

  - permettre aux serveurs et clients externes de se connecter aux serveurs Edge ou au proxy inverse HTTP afin d’utiliser les fonctions de messagerie instantanée et de conférence ;

  - permettre aux périphériques de communications unifiées qui ne sont pas connectés de détecter le pool de serveurs frontaux ou le serveur Standard Edition exécutant le service web de mise à jour de périphériques, d’obtenir des mises à jour et d’envoyer des journaux ;

  - permettre aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des périphériques.

  - procéder à l’équilibrage de la charge DNS.

<div>


> [!NOTE]  
> Lync Server 2013 ne prend pas en charge les noms de domaine internationaux (IDN).



</div>

<div>


> [!IMPORTANT]  
> Le nom que vous spécifiez doit être identique au nom d’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas membre d’un domaine est un nom court, et non un nom de domaine complet (FQDN). Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Par conséquent, vous devez configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non membre d’un domaine. <STRONG>Utilisez uniquement des caractères standard</STRONG> (A–Z, a–z, 0–9 et tirets) lorsque vous assignez des noms de domaines complets à vos serveurs Lync, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaines complets ne sont généralement pas pris en charge par les DNS externes et les autorités publiques de certification (c’est-à-dire lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat).



</div>

</div>

<span> </span>

</div>

</div>

</div>

