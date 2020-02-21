---
title: Purge manuelle des bases de données d’enregistrement des détails des appels et de qualité de l’expérience
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6797d5e65f182e8a28bb442858070ffed19fcc80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="8edb0-102">Purge manuelle des bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8edb0-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8edb0-103">_**Dernière modification de la rubrique :** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="8edb0-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="8edb0-104">Les administrateurs peuvent configurer les bases de données d’enregistrement des détails des appels et/ou de qualité de l’expérience pour purger automatiquement les anciens enregistrements de la base de données ; Cela se produit si la purge a été activée pour la base de données spécifiée (CDR ou QoE) et si des enregistrements se trouvaient dans la base de données plus longtemps que la durée spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8edb0-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="8edb0-105">Par exemple, tous les jours à 1:00 AM les administrateurs peuvent configurer le système de manière à ce que les enregistrements QoE datant de plus de 60 jours soient supprimés de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="8edb0-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="8edb0-106">En plus de cette purge automatique, deux nouvelles applets de commande--Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge ont été ajoutées à Microsoft Lync Server 2013 ; ces applets de commande permettent aux administrateurs de purger manuellement les enregistrements des bases de données CDR et QoE à tout moment.</span><span class="sxs-lookup"><span data-stu-id="8edb0-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="8edb0-107">Par exemple, pour purger manuellement tous les enregistrements datant de plus de 10 jours de la base de données CDR, vous pouvez utiliser une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="8edb0-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="8edb0-108">Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8edb0-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="8edb0-109">(Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session.</span><span class="sxs-lookup"><span data-stu-id="8edb0-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="8edb0-110">Les enregistrements de données de diagnostic sont des journaux de diagnostic téléchargés par des applications clientes telles que Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="8edb0-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="8edb0-111">Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="8edb0-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="8edb0-112">Cependant, ces paramètres ne doivent pas avoir la même valeur.</span><span class="sxs-lookup"><span data-stu-id="8edb0-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="8edb0-113">Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="8edb0-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="8edb0-114">Pour ce faire, définissez PurgeCallDetailDataOlderThanDays sur 10 et PurgeDiagnosticDataOlderThanDays sur 0.</span><span class="sxs-lookup"><span data-stu-id="8edb0-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="8edb0-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8edb0-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="8edb0-116">Par défaut, à chaque fois que vous exécuterez Invoke-CsCdrDatabasePurge, vous obtiendrez une invite identique à celle-ci pour chaque table de base de données à vider :</span><span class="sxs-lookup"><span data-stu-id="8edb0-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="8edb0-p105">Vous devez taper Y (pour Oui) ou A (pour Oui pour tout) avant que le vidage de la base de données intervienne réellement. Si vous préférez supprimer ces invites de confirmation, ajoutez le paramètre suivant à la fin de votre appel à Invoke-CsCdrDatabasePurge :</span><span class="sxs-lookup"><span data-stu-id="8edb0-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="8edb0-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8edb0-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="8edb0-120">Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.</span><span class="sxs-lookup"><span data-stu-id="8edb0-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="8edb0-121">Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :</span><span class="sxs-lookup"><span data-stu-id="8edb0-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

