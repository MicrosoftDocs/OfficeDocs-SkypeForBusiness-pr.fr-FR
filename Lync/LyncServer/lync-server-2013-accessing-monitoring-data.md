---
title: 'Lync Server 2013 : accès aux données d’analyse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 609963f3248d5bdd1c50eac45b74c188ab2e6c56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="37c62-102">Accès aux données d’analyse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37c62-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37c62-103">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="37c62-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="37c62-p101">Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="37c62-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="37c62-106">L’un des outils que vous devez prendre en compte lors de l’accès aux données de surveillance et de leur analyse est le rapport de surveillance du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="37c62-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="37c62-107">Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="37c62-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="37c62-108">Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.</span><span class="sxs-lookup"><span data-stu-id="37c62-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="37c62-109">Les rapports d’analyse livrés avec Lync Server 2013 peuvent être installés à partir de l’Assistant Déploiement de Lync Server après l’installation et la surveillance de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37c62-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="37c62-p103">Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="37c62-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="37c62-112">Pour plus d’informations, reportez-vous à la rubrique [installation de rapports d’analyse Lync server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) dans le Guide de déploiement de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37c62-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

