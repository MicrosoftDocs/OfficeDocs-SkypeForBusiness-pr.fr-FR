---
title: Effacement manuel des bases de données de l’enregistrement des détails des appels et de la qualité de l’activité dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Résumé : Découvrez comment purger manuellement les enregistrements de la base de données CDR et de la base de données QoE utilisée par Skype entreprise Server.'
ms.openlocfilehash: 5dbd2120e408dea0c3b34f87c17e4fbb18cc5055
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001153"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Effacement manuel des bases de données de l’enregistrement des détails des appels et de la qualité de l’activité dans Skype entreprise Server
 
**Résumé :** Découvrez comment purger manuellement les enregistrements de la base de données CDR et de la base de données QoE utilisée par Skype entreprise Server.
  
Les bases de données d’enregistrement des détails des appels (CDR) et de qualité de l’expérience (QoE) peuvent être manuellement ou automatiquement vidées des enregistrements. La purge des enregistrements peut s’avérer importante afin que les données ne deviennent pas obsolètes ou lorsque que l’on doit réinitialiser des rapports à partir d’un planning de référence initial.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Vider manuellement des enregistrements à partir de bases de données CDR et QoE

Les administrateurs peuvent configurer les bases de données d’enregistrement des détails des appels (CDR) et/ou de qualité de l’expérience (QoE) pour vider automatiquement la base de données des enregistrements anciens. Cette opération se produit si le vidage a été activé pour la base de données spécifiée (CDR ou QoE) et si celle-ci contient des enregistrements dont l’ancienneté dépasse la durée spécifiée. Par exemple, les administrateurs peuvent configurer le système pour que tous les jours à 1:00 les enregistrements QoE de plus de 60 jours soient supprimés de la base de données QoE.
  
Outre la purge automatique, deux nouvelles cmdlets &#x2014; Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge &#x2014; ont été ajoutées à Skype entreprise Server. ces applets de applet permettent aux administrateurs de purger manuellement les enregistrements des bases de données CDR et QoE à tout moment. Par exemple, pour purger manuellement tous les enregistrements de plus de 10 jours de la base de données CDR, vous pouvez utiliser une commande similaire à celle-ci :
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com. (Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session. Les enregistrements de données de diagnostic sont des journaux de diagnostic téléchargés par des applications clientes telles que Skype entreprise Server.)
  
Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays. Cependant, ces paramètres ne doivent pas avoir la même valeur. Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données. Pour cela, définissez PurgeCallDetailDataOlderThanDays sur 10 et PurgeDiagnosticDataOlderThanDays sur 0. Par exemple :
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Par défaut, à chaque fois que vous exécuterez Invoke-CsCdrDatabasePurge, vous obtiendrez une invite identique à celle-ci pour chaque table de base de données à vider :
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Vous devez taper Y (pour Oui) ou A (pour Oui pour tout) avant que le vidage de la base de données intervienne réellement. Si vous préférez supprimer ces invites de confirmation, ajoutez le paramètre suivant à la fin de votre appel à Invoke-CsCdrDatabasePurge :
  
```powershell
-Confirm:$False
```

Exemple :
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.
  
Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


