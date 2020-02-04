---
title: 'Lync Server 2013 : Prise en charge des infrastructures DNS'
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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Prise en charge des infrastructures DNS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-08_

Lync Server 2013 nécessite DNS (Domain Name System) et l’utilise comme suit :

  - Pour découvrir les serveurs internes ou les pools de communications serveur à serveur.

  - Pour permettre aux clients de découvrir le pool frontal ou le serveur Standard Edition utilisé pour différentes transactions SIP.

  - Pour associer les URL simples aux conférences avec les serveurs hébergeant ces conférences.

  - Pour permettre à des serveurs et clients externes de se connecter à des serveurs Edge ou au proxy HTTP inverse pour la messagerie instantanée ou les conférences.

  - Pour activer les appareils de communications unifiées (UC) qui ne sont pas connectés pour détecter le pool frontal ou le serveur Standard Edition Web exécutant des mises à jour de périphériques, obtenez des mises à jour et envoyez des journaux.

  - Pour permettre aux clients mobiles de détecter automatiquement les ressources de services Web sans exiger l’entrée manuelle des URL dans les paramètres de l’appareil.

  - Pour l’équilibrage de charge DNS.

<div>


> [!NOTE]  
> Lync Server 2013 ne prend pas en charge les noms de domaines internationaux (IDNs).



</div>

<div>


> [!IMPORTANT]  
> Le nom spécifié doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas lié à un domaine est un nom court, pas un nom de domaine complet (FQDN). Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine. <STRONG>Utilisez uniquement les caractères standard</STRONG> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools. N’utilisez pas les caractères ou traits de soulignement Unicode. Souvent, les caractères non standard dans un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand le FQDN doit être assigné au SN dans le certificat).



</div>

</div>

<span> </span>

</div>

</div>

</div>

