---
title: 'Lync Server 2013 : sauvegarde des bases de données d’archivage et de surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08eea156d1b12f607270ea3b6d7472519128e472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523171"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="e9823-102">Sauvegarde des bases de données d’archivage et de surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9823-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9823-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e9823-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="e9823-104">Si vous avez déployé l’archivage ou la surveillance, vous devez sauvegarder ces bases de données conformément à la stratégie de sauvegarde SQL Server de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e9823-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9823-105">Les paramètres d’archivage et de surveillance sont sauvegardés lorsque vous sauvegardez le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="e9823-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="e9823-106">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-backing-up-core-data-and-settings.md">backing Core Data and Settings in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9823-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e9823-107">Pour l’archivage et la surveillance, vous pouvez utiliser un outil SQL Server tel que SQL Server Management Studio pour effectuer une sauvegarde manuelle ou utiliser des outils de gestion SQL Server pour planifier des sauvegardes automatiques et régulières.</span><span class="sxs-lookup"><span data-stu-id="e9823-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

