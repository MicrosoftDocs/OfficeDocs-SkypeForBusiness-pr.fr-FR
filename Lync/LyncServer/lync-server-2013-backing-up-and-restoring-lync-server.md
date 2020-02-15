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
ms.openlocfilehash: d65d06ac9c72e776eee51b9b3dff6c6db3a59031
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Sauvegarde et restauration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Dans cette section, vous trouverez les meilleures pratiques de sauvegarde de vos données Lync Server 2013 et de restauration en cas de défaillance. Ces meilleures pratiques s’appliquent aux situations suivantes :

  - Un pool Lync Server entier de n’importe quel type (serveur frontal, serveur Edge, serveur de médiation, serveur de conversation permanente ou directeur) ou un serveur individuel dans l’un de ces pools.

  - Le serveur de gestion centralisée

  - Un serveur Standard Edition

  - Un serveur principal Enterprise Edition

  - Un magasin de fichiers

  - Une base de données d’archivage, une base de données de surveillance ou une base de données de conversation permanente

Cette section n’inclut pas d’informations sur la restauration d’un site entier ou sur le développement d’un site de secours. Pour plus d’informations sur le développement d’une solution de récupération d’urgence avec des pools frontaux couplés, consultez la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Il s’agit de la méthode recommandée pour la planification de la récupération d’urgence.

Si vous avez déployé des pools frontaux couplés, si l’un de ces pools échoue et devient irrécupérable, vous pouvez restaurer ce pool avec un nouveau nom de domaine complet (FQDN) à partir de son pool associé. Pour plus d’informations sur les étapes à suivre pour effectuer cette récupération, voir [basculement d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Par ailleurs, si vous souhaitez recréer ultérieurement un pool défaillant et irrécupérable qui faisait partie d’une paire de serveurs frontaux, vous pouvez suivre les étapes décrites dans la section [exécution d’un basculement de pool frontal ABC dans Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La méthodologie décrite dans ce document implique des considérations spécifiques lors de la phase de planification. Pour plus d’informations, reportez-vous à [la rubrique établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Préparation de la sauvegarde et de la restauration de Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Sauvegarde des données et des paramètres dans Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Restauration des données et des paramètres dans Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

