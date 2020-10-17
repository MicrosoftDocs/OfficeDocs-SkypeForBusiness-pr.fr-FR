---
title: 'Lync Server 2013 : configuration des plateformes système pour l’archivage'
description: 'Lync Server 2013 : configuration des plateformes système pour l’archivage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554180"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configuration des plateformes système pour l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Avant de commencer à déployer l’archivage, vous devez installer le système d’exploitation requis et tout autre logiciel prérequis sur du matériel conforme à la configuration requise :

  - Plateforme Lync Server **2013**     Les déploiements Lync Server 2013 n’ont pas de serveurs d’archivage. Aucune plateforme système séparée n’est donc nécessaire pour héberger l’archivage.

  - Plateforme de stockage de **données**     Dans Lync Server 2013, vous pouvez stocker des données à l’aide de l’une des méthodes suivantes :
    
      - Intégration de Microsoft **Exchange**     Si vous souhaitez stocker les données d’archivage Lync Server 2013 à l’aide de votre déploiement Exchange 2013, au lieu de configurer une base de données distincte pour le stockage des données d’archivage, votre déploiement Exchange doit exécuter Exchange 2013. Pour plus d’informations sur la configuration des plateformes système pour Exchange 2013, voir la documentation du produit Exchange.
    
      - **SQL Server**     Si vous souhaitez utiliser une base de données SQL Server distincte pour le stockage des données d’archivage, au lieu ou en plus de l’utilisation de l’intégration de Microsoft Exchange, vous devez configurer la plateforme système pour la base de données avant le déploiement de l’archivage. La configuration requise de la plateforme système varie selon que vous utilisez Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour la base de données d’archivage. Pour plus d’informations sur la configuration des plateformes système pour ces bases de données, reportez-vous à la documentation du produit Microsoft SQL Server 2008 R2 et Microsoft SQL Server 2012.

  - Plateforme de serveur de **fichiers**     Lync Server 2013 stocke les fichiers d’archivage Lync Server dans le même emplacement que celui que vous spécifiez pour le stockage des fichiers lorsque vous configurez vos serveurs frontaux ou serveurs Standard Edition. Vous ne pouvez pas spécifier d’emplacement séparé pour le stockage des fichiers d’archivage, aucune plateforme système séparée n’est donc nécessaire. Si vous utilisez l’intégration de Microsoft Exchange, Exchange 2013 les fichiers pour les communications Lync archivées sont stockés sur les serveurs Exchange 2013 pour les utilisateurs hébergés sur ces serveurs Exchange.

</div>

<span> </span>

</div>

</div>

</div>

