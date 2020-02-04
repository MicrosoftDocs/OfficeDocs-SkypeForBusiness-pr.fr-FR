---
title: 'Lync Server 2013 : sauvegarde et restauration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Sauvegarde et restauration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Cette section présente les meilleures pratiques en matière de sauvegarde de vos données 2013 Lync Server et de restauration en cas d’échec. Ces bonnes pratiques s’appliquent aux situations suivantes :

  - Un pool de serveurs Lync de n’importe quel type (serveur frontal, serveur Edge, serveur de médiation, serveur de chat permanent ou directeur), ou un serveur individuel dans l’un de ces groupes.

  - Serveur de gestion central

  - Un serveur Standard Edition Server

  - Serveur principal d’Enterprise Edition

  - Magasin de fichiers

  - Une base de données d’archivage, une base de données de surveillance ou une base de données de chat permanent

Cette section n’inclut pas d’informations sur la restauration d’un site entier ou sur le développement d’un site de secours. Pour plus d’informations sur le développement d’une solution de reprise après sinistre avec des listes frontales couplées, voir [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Il s’agit de la méthode recommandée pour la planification de la reprise après sinistre.

Si vous avez déployé des pools frontaux couplés, si l’un de ces groupes échoue et devient irrécupérable, vous pouvez restaurer ce pool avec un nouveau nom de domaine complet (FQDN) du pool couplé. Pour plus d’informations sur la procédure d’exécution de cette récupération, voir [échec d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Par ailleurs, si vous voulez recréer un pool failed et unrécupérable qui faisait partie d’une paire frontale, vous pouvez suivre la procédure décrite dans la section [exécution d’un basculement de pool frontal ABC dans Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La méthodologie décrite dans ce document implique des considérations spéciales lors de la phase de planification. Pour plus d’informations, reportez-vous à [la rubrique établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Préparation pour la sauvegarde et la restauration de Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Sauvegarder des données et des paramètres dans Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Restauration de données et de paramètres dans Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Sauvegarder et restaurer des feuilles de calcul pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

