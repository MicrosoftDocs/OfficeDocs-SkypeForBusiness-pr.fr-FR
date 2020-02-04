---
title: 'Lync Server 2013 : Planification du jumelage de pools frontaux'
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
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planification du jumelage de pools frontaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Pour les meilleures capacités de reprise après sinistre dans Lync Server 2013, le déploiement de paires de pools front-end sur deux sites à dispersion géographique. Chaque site comporte une réserve frontale associée à un pool frontal correspondant dans l’autre site. Les deux sites sont actifs et le service de sauvegarde de Lync Server fournit la réplication des données en temps réel pour que les pools restent synchronisés. Le service de sauvegarde est une nouvelle fonctionnalité de Lync Server 2013 conçue pour prendre en charge la solution de reprise après sinistre. Elle est installée sur un pool frontal lorsque vous jumelez la liste avec un autre pool frontal.

En cas d’échec du pool dans un site, vous pouvez faire basculer les utilisateurs de ce groupe vers le pool dans l’autre site, qui fournit ensuite les services à tous les utilisateurs des deux groupes. Dans le cadre de la planification de la capacité, chaque pool doit être conçu pour gérer les charges de travail de tous les utilisateurs dans les deux pools en cas de sinistre.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Options de jumelage de pool prises en charge et meilleures pratiques pour Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relations des serveurs d’inscriptions de sauvegarde dans Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Temps de récupération nécessaire pour basculer et restaurer les pools dans Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Basculement du magasin central de gestion dans Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Sécurité des données d’appariement de pools frontaux dans Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

