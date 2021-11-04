---
title: Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Résumé : Découvrez comment vider manuellement les enregistrements des bases de données CDR et QoE utilisées par les Skype Entreprise Server.'
ms.openlocfilehash: cc5cf41351992715f59e45d86d7965f256aaf8cc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740090"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server
 
**Résumé :** Découvrez comment vider manuellement les enregistrements des bases de données CDR et QoE utilisées par les Skype Entreprise Server.
  
Les bases de données CDR et QoE peuvent être purgées manuellement ou automatiquement des enregistrements. La purge des enregistrements peut être importante afin que les données ne deviennent pas obsolètes ou lorsque vous avez besoin de réinitialiser les rapports à partir d’une ligne de base de départ.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Vider manuellement les enregistrements des bases de données CDR et QoE

Les administrateurs peuvent configurer l’enregistrement des détails des appels (CDR) et/ou les bases de données de qualité de l’expérience (QoE) pour vider automatiquement les anciens enregistrements de la base de données. Cela se produit si le purge a été activé pour la base de données spécifiée (CDR ou QoE) et si des enregistrements ont été dans la base de données plus longtemps que la durée spécifiée. Par exemple, tous les jours à 13h00, les administrateurs peuvent configurer le système afin que les enregistrements QoE de plus de 60 jours soient supprimés de la base de données QoE.
  
Outre ce purge automatique, deux nouvelles cmdlets &#x2014; Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge &#x2014; ajoutées à Skype Entreprise Server ; Ces cmdlets permettent aux administrateurs de vider manuellement les enregistrements des bases de données CDR et QoE à tout moment. Par exemple, pour vider manuellement tous les enregistrements de plus de 10 jours de la base de données cdr, vous pouvez utiliser une commande semblable à celle-ci :
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com. (Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session. Les enregistrements de données de diagnostic sont des journaux de diagnostic téléchargés par des applications clientes telles que Skype Entreprise Server.)
  
Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays. Cependant, ces paramètres ne doivent pas avoir la même valeur. Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données. Pour ce faire, définissez PurgeCallDetailDataOlderThanDays sur 10 et PurgeDiagnosticDataOlderThanDays sur 0. Par exemple :
  
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

Par exemple :
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.
  
Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


