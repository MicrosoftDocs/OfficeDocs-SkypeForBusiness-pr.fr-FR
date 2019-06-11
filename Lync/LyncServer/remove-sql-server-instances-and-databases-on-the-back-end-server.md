---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Suppression des instances et des bases de données SQL Server sur le serveur principal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Vous supprimez les bases de données et instances Microsoft SQL Server après la suppression des serveurs exécutant Lync Server 2010 qui en dépendent, ou après la reconfiguration des serveurs exécutant Lync Server 2010 pour utiliser une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous supprimez le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel exécutant Lync Server 2010 de telle sorte qu’il affiche les bases de données obsolètes ou indisponibles.

Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle de serveur. De même, pour supprimer les instances ou bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant. Ces procédures n’effectuent aucune distinction entre les bases de données colocalisées ou les instances distinctes pour les serveurs. Les procédures ne sont pas affectées par la colocalisation des bases de données.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Suppression de la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Suppression de la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Suppression de la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

