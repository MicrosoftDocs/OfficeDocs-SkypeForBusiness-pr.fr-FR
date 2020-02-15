---
title: 'Lync Server 2013 : jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe2ea13628e9a4ede3daa2b14ebbb3941ce30aa1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-13_

Le protocole SIP (Session Initiation Protocol) sert à initier et à gérer les sessions de communications Voix sur IP (VoIP) pour le service téléphonique de base et d’autres services de communication en temps réel, tels que messagerie instantanée, conférence, détection de présence et multimédia. Cette section fournit des informations de planification pour l’implémentation de *jonctions SIP*, un type de connexion SIP qui s’étend au-delà des limites de votre réseau local.

<div>

## <a name="what-is-sip-trunking"></a>Qu’est-ce que la jonction SIP ?

Une jonction SIP est une connexion IP qui établit un lien de communications SIP entre votre organisation et un fournisseur de services de téléphonie Internet (ITSP) à l’extérieur de votre pare-feu. En règle générale, une jonction SIP sert à connecter le site central de votre organisation à un fournisseur de services de téléphonie Internet (ITSP). Dans certains cas, vous pouvez également décider d’utiliser la jonction SIP pour connecter votre site de succursale à un fournisseur de services de téléphonie Internet (ITSP).

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>Différences entre les jonctions SIP et les connexions SIP directes

Le terme *jonction* est dérivé de la technologie de commutation. Il fait référence à une ligne physique dédiée qui connecte les équipements téléphoniques de commutation. Comme leur prédécesseur, les jonctions de multiplexage temporel (TDM), les jonctions SIP sont des connexions entre deux réseaux SIP distincts : Lync Server 2013 Enterprise et téléphonie Internet. Contrairement aux jonctions de commutation, les jonctions SIP sont des connexions virtuelles pouvant être établies sur n’importe quel type de connexion de jonction SIP pris en charge. Pour plus d’informations sur les types de connexion pris en charge, voir [How do I implement SIP Trunking in Lync Server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md).

En revanche, les connexions SIP directes sont des connexions SIP qui ne franchissent pas les limites du réseau local (c’est-à-dire qu’elles se connectent à une passerelle PSTN ou à un PBX dans votre réseau interne). Pour plus d’informations sur l’utilisation des connexions SIP directes avec Lync Server 2013, reportez-vous à [direct SIP connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).

</div>

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Vue d’ensemble de la jonction SIP dans Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Comment implémenter la jonction SIP dans Lync Server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Composants et topologies pour la jonction SIP dans Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Jonction SIP de site de succursale dans Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

