---
title: 'Lync Server 2013 : planification du jumelage de pools frontaux'
description: 'Lync Server 2013 : planification du jumelage de pools frontaux.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac235cf682e286132836e13b34b457adf2bfc233
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562790"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planification du jumelage de pools frontaux dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Pour les meilleures capacités de récupération d’urgence dans Lync Server 2013, déployez des paires de pools frontaux sur deux sites géographiquement dispersés. Chaque site contient un pool frontal couplé à un pool frontal correspondant dans l’autre site. Les deux sites sont actifs et le service de sauvegarde Lync Server fournit une réplication de données en temps réel pour maintenir les pools synchronisés. Le service de sauvegarde est une nouvelle fonctionnalité de Lync Server 2013, conçue pour prendre en charge la solution de récupération d’urgence. Il est installé sur un pool frontal lorsque vous couplez le pool avec un autre pool frontal.

Si le pool dans un site échoue, vous pouvez basculer les utilisateurs de ce pool vers le pool dans l’autre site, qui fournit alors les services à tous les utilisateurs dans les deux pools. À des fins de planification de capacité, chaque pool doit être conçu pour gérer les charges de travail de tous les utilisateurs dans les deux pools en cas de sinistre.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Options de jumelage des pools prises en charge et meilleures pratiques pour Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relations de serveur d’inscriptions de sauvegarde dans Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Temps de récupération pour le basculement de pool et la restauration automatique dans Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Basculement du magasin central de gestion dans Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Sécurité des données de jumelage des pools frontaux dans Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

