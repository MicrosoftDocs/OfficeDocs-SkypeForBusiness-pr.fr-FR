---
title: 'Lync Server 2013: configuration de plates-formes système pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configuration de plates-formes système pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

Avant de commencer le déploiement de l’archivage, vous devez installer le système d’exploitation requis et tout autre logiciel requis sur le matériel qui répond à la configuration système requise:

  - ****   Les déploiements Lync Server 2013 de la plateforme Lync Server 2013 ne disposent pas de serveurs d’archivage. À la place, les agents de collection de données unifiés s’exécutent sur des serveurs frontaux et sur les serveurs Standard Edition pour capturer les données pour l’archivage, de sorte qu’aucune plateforme système distincte n’est requise pour l’archivage.

  - **Plateforme de stockage de données**   dans Lync Server 2013, vous pouvez stocker des données à l’aide de l’une des méthodes suivantes:
    
      - **Intégration de Microsoft Exchange**   si vous voulez stocker les données d’archivage de Lync Server 2013 en utilisant votre déploiement Exchange 2013, au lieu d’une base de données séparée pour le stockage des données d’archivage, votre déploiement Exchange doit être exécutant Exchange 2013. Pour plus d’informations sur la configuration des plates-formes système pour Exchange 2013, voir la documentation du produit Exchange.
    
      - **SQL Server**   si vous souhaitez utiliser une base de données SQL Server distincte pour le stockage des données d’archivage, au lieu de ou en plus de l’intégration de Microsoft Exchange, vous devez configurer la plateforme système de la base de données avant le déploiement de l’archivage. La configuration requise pour la plateforme système spécifique dépend de l’utilisation de Microsoft SQL Server 2008 R2 ou de Microsoft SQL Server 2012 pour la base de données d’archivage. Pour plus d’informations sur la configuration de plates-formes système pour ces bases de données, consultez la documentation du produit Microsoft SQL Server 2008 R2 et Microsoft SQL Server 2012.

  - **Plateforme du serveur de fichiers**   Lync Server 2013 stocke les fichiers d’archivage de Lync Server dans le même emplacement que celui que vous spécifiez pour le stockage de fichiers lorsque vous configurez votre serveur frontal ou les serveurs Standard Edition. Dans le cas contraire, vous ne pouvez pas spécifier d’emplacement distinct pour l’archivage des fichiers. Si vous utilisez l’intégration de Microsoft Exchange, Exchange 2013 les fichiers pour les communications Lync archivées sont stockés sur les serveurs Exchange 2013 pour les utilisateurs hébergés sur les serveurs Exchange.

</div>

<span> </span>

</div>

</div>

</div>

