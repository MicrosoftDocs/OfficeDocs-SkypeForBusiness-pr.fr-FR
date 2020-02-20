---
title: Supprimer des instances et des bases de données SQL Server sur le serveur principal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02aa65c631e62d7ffb699d85d982858164848c2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Supprimer des instances et des bases de données SQL Server sur le serveur principal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs exécutant Lync Server 2010 qui en dépendent, ou après avoir reconfiguré les serveurs exécutant Lync Server 2010 pour utiliser une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous désactivez le serveur SQL Server actuel ou reconfigurez le serveur actuel exécutant Lync Server 2010 de manière à ce qu’il restitue les bases de données obsolètes ou indisponibles.

Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle serveur. De même, pour supprimer les instances ou les bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant. Ces procédures ne font pas de distinction entre les bases de données colocalisées et les instances séparées des serveurs. Elles ne sont pas affectées par la colocalisation des bases de données.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Supprimer la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Supprimer la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Supprimer la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

