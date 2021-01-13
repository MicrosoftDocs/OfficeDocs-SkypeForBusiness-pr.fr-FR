---
title: Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Résumé : Découvrez comment vider manuellement les enregistrements de l’enregistrement des détails des appels et des bases de données QoE utilisées par Skype Entreprise Server.'
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802144"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="69043-103">Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="69043-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="69043-104">**Résumé :** Découvrez comment vider manuellement les enregistrements de l’enregistrement des détails des appels et des bases de données QoE utilisées par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="69043-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="69043-105">Les bases de données CDR et QoE peuvent être purgées manuellement ou automatiquement des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="69043-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="69043-106">La purge des enregistrements peut être importante afin que les données ne deviennent pas obsolètes ou lorsque vous avez besoin de réinitialiser les rapports à partir d’une ligne de base de départ.</span><span class="sxs-lookup"><span data-stu-id="69043-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="69043-107">Vider manuellement les enregistrements des bases de données CDR et QoE</span><span class="sxs-lookup"><span data-stu-id="69043-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="69043-108">Les administrateurs peuvent configurer l’enregistrement des détails des appels (CDR) et/ou les bases de données de qualité de l’expérience (QoE) pour vider automatiquement les anciens enregistrements de la base de données. Cela se produit si le purge a été activé pour la base de données spécifiée (CDR ou QoE) et si des enregistrements ont été dans la base de données plus longtemps que la durée spécifiée.</span><span class="sxs-lookup"><span data-stu-id="69043-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="69043-109">Par exemple, tous les jours à 13h00, les administrateurs peuvent configurer le système afin que les enregistrements QoE de plus de 60 jours soient supprimés de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="69043-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="69043-110">En plus de ce purge automatique, deux nouvelles cmdlets &#x2014; Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge &#x2014; ont été ajoutées à Skype Entreprise Server ; Ces cmdlets permettent aux administrateurs de vider manuellement les enregistrements des bases de données CDR et QoE à tout moment.</span><span class="sxs-lookup"><span data-stu-id="69043-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="69043-111">Par exemple, pour vider manuellement tous les enregistrements de plus de 10 jours de la base de données cdr, vous pouvez utiliser une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="69043-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="69043-112">Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="69043-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="69043-113">(Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session.</span><span class="sxs-lookup"><span data-stu-id="69043-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="69043-114">Les enregistrements de données de diagnostic sont des journaux de diagnostic téléchargés par des applications clientes telles que Skype Entreprise Server.)</span><span class="sxs-lookup"><span data-stu-id="69043-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="69043-115">Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="69043-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="69043-116">Cependant, ces paramètres ne doivent pas avoir la même valeur.</span><span class="sxs-lookup"><span data-stu-id="69043-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="69043-117">Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="69043-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="69043-118">Pour ce faire, définissez PurgeCallDetailDataOlderThanDays sur 10 et PurgeDiagnosticDataOlderThanDays sur 0.</span><span class="sxs-lookup"><span data-stu-id="69043-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="69043-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="69043-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="69043-120">Par défaut, à chaque fois que vous exécuterez Invoke-CsCdrDatabasePurge, vous obtiendrez une invite identique à celle-ci pour chaque table de base de données à vider :</span><span class="sxs-lookup"><span data-stu-id="69043-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="69043-p106">Vous devez taper Y (pour Oui) ou A (pour Oui pour tout) avant que le vidage de la base de données intervienne réellement. Si vous préférez supprimer ces invites de confirmation, ajoutez le paramètre suivant à la fin de votre appel à Invoke-CsCdrDatabasePurge :</span><span class="sxs-lookup"><span data-stu-id="69043-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="69043-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="69043-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="69043-124">Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.</span><span class="sxs-lookup"><span data-stu-id="69043-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="69043-125">Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :</span><span class="sxs-lookup"><span data-stu-id="69043-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


