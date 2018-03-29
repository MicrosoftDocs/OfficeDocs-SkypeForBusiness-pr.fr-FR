---
title: Purge manuelle des bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Résumé : Découvrez comment purger manuellement les enregistrements à partir du CD-r et les bases de données QoE utilisés par Skype pour Business Server 2015.'
ms.openlocfilehash: 805bf72b3d4846bb00d3c3772b033242976cd7c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="0ee69-103">Purge manuelle des bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ee69-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0ee69-104">**Résumé :** Découvrez comment purger manuellement les enregistrements à partir du CD-r et les bases de données QoE utilisés par Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0ee69-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0ee69-p101">Les bases de données d’enregistrement des détails des appels (CDR) et de qualité de l’expérience (QoE) peuvent être manuellement ou automatiquement vidées des enregistrements. La purge des enregistrements peut s’avérer importante afin que les données ne deviennent pas obsolètes ou lorsque que l’on doit réinitialiser des rapports à partir d’un planning de référence initial.</span><span class="sxs-lookup"><span data-stu-id="0ee69-p101">The CDR and QoE databases can be manually or automatically purged of records. Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="0ee69-107">Vider manuellement des enregistrements à partir de bases de données CDR et QoE</span><span class="sxs-lookup"><span data-stu-id="0ee69-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="0ee69-p102">Les administrateurs peuvent configurer les bases de données d’enregistrement des détails des appels (CDR) et/ou de qualité de l’expérience (QoE) pour vider automatiquement la base de données des enregistrements anciens. Cette opération se produit si le vidage a été activé pour la base de données spécifiée (CDR ou QoE) et si celle-ci contient des enregistrements dont l’ancienneté dépasse la durée spécifiée. Par exemple, les administrateurs peuvent configurer le système pour que tous les jours à 1:00 les enregistrements QoE de plus de 60 jours soient supprimés de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="0ee69-p102">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="0ee69-110">En plus de ce automatique purge, deux nouvelles applets de commande & #x 2014 ; Appeler-CsCdrDatabasePurge et -CsQoEDatbasePurge appeler & #x 2014 ; ont été ajoutés à Skype pour 2015 de serveur d’entreprise ; ces applets de commande permettent aux administrateurs de purger manuellement des enregistrements à partir du CD-r et les bases de données QoE à tout moment.</span><span class="sxs-lookup"><span data-stu-id="0ee69-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server 2015; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="0ee69-111">Par exemple, pour purger manuellement tous les enregistrements de plus de 10 jours anciens à partir de la base de données CDR vous pouvez utiliser une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="0ee69-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="0ee69-112">Dans la commande précédente à l’appel d’enregistrements de détail et les enregistrements de données de diagnostic plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com. (Les enregistrements de détail appel sont les rapports de session de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0ee69-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com. (Call detail records are user/session reports.</span></span> <span data-ttu-id="0ee69-113">Les enregistrements de données de diagnostic sont les journaux de diagnostic chargés par les applications clientes telles que Skype pour Business Server 2015.)</span><span class="sxs-lookup"><span data-stu-id="0ee69-113">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server 2015.)</span></span>
  
<span data-ttu-id="0ee69-114">Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="0ee69-114">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="0ee69-115">Cependant, ces paramètres ne doivent pas avoir la même valeur.</span><span class="sxs-lookup"><span data-stu-id="0ee69-115">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="0ee69-116">Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0ee69-116">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="0ee69-117">Pour ce faire, définissez PurgeCallDetailDataOlderThanDays sur 10 et PurgeDiagnosticDataOlderThanDays sur 0.</span><span class="sxs-lookup"><span data-stu-id="0ee69-117">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="0ee69-118">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0ee69-118">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="0ee69-119">Par défaut, à chaque fois que vous exécuterez Invoke-CsCdrDatabasePurge, vous obtiendrez une invite identique à celle-ci pour chaque table de base de données à vider :</span><span class="sxs-lookup"><span data-stu-id="0ee69-119">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
```
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="0ee69-p106">Vous devez taper Y (pour Oui) ou A (pour Oui pour tout) avant que le vidage de la base de données intervienne réellement. Si vous préférez supprimer ces invites de confirmation, ajoutez le paramètre suivant à la fin de votre appel à Invoke-CsCdrDatabasePurge :</span><span class="sxs-lookup"><span data-stu-id="0ee69-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="0ee69-122">Exemple :</span><span class="sxs-lookup"><span data-stu-id="0ee69-122">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="0ee69-123">Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.</span><span class="sxs-lookup"><span data-stu-id="0ee69-123">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="0ee69-124">Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :</span><span class="sxs-lookup"><span data-stu-id="0ee69-124">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


