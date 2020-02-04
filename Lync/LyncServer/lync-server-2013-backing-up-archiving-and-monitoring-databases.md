---
title: 'Lync Server 2013 : sauvegarde de bases de données d’archivage et de surveillance'
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
ms.openlocfilehash: 4092ddc3c86496053cc0ebbb367188490096de4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="4f111-102">Sauvegarde de bases de données d’archivage et de surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f111-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f111-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4f111-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4f111-104">Si vous avez déployé l’archivage ou le contrôle, vous devez sauvegarder ces bases de données en fonction de la stratégie de sauvegarde SQL Server de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4f111-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f111-105">Les paramètres d’archivage et de surveillance sont sauvegardés lorsque vous sauvegardez le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="4f111-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="4f111-106">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-backing-up-core-data-and-settings.md">sauvegarde de données principales et de paramètres dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4f111-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4f111-107">Dans le cadre de l’archivage et de la surveillance, vous pouvez utiliser un outil SQL Server tel que SQL Server Management Studio pour effectuer une sauvegarde manuelle, ou vous pouvez utiliser les outils de gestion SQL Server pour planifier des sauvegardes régulières et automatiques.</span><span class="sxs-lookup"><span data-stu-id="4f111-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

