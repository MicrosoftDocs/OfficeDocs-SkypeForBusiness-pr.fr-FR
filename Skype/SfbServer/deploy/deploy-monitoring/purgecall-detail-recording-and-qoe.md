---
title: Vider manuellement l’enregistrement des détails des appels et les bases de données de qualité de l’expérience dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Résumé : Apprenez à vider manuellement les enregistrements à partir de la détails des appels et les bases de données QoE utilisés par Skype pour Business Server.'
ms.openlocfilehash: 14218bbc6af3d05cba3c9886da70ab7155d05159
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006081"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Vider manuellement l’enregistrement des détails des appels et les bases de données de qualité de l’expérience dans Skype pour Business Server
 
**Résumé :** Apprenez à vider manuellement les enregistrements à partir de la détails des appels et les bases de données QoE utilisés par Skype pour Business Server.
  
Les bases de données d’enregistrement des détails des appels (CDR) et de qualité de l’expérience (QoE) peuvent être manuellement ou automatiquement vidées des enregistrements. La purge des enregistrements peut s’avérer importante afin que les données ne deviennent pas obsolètes ou lorsque que l’on doit réinitialiser des rapports à partir d’un planning de référence initial.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Vider manuellement des enregistrements à partir de bases de données CDR et QoE

Les administrateurs peuvent configurer les bases de données d’enregistrement des détails des appels (CDR) et/ou de qualité de l’expérience (QoE) pour vider automatiquement la base de données des enregistrements anciens. Cette opération se produit si le vidage a été activé pour la base de données spécifiée (CDR ou QoE) et si celle-ci contient des enregistrements dont l’ancienneté dépasse la durée spécifiée. Par exemple, les administrateurs peuvent configurer le système pour que tous les jours à 1:00 les enregistrements QoE de plus de 60 jours soient supprimés de la base de données QoE.
  
Outre cette automatique le vidage, deux nouvelles applets de commande & #x 2014 ; Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge & #x 2014 ; ont été ajoutés à Skype pour Business Server ; ces applets de commande pour autoriser les administrateurs à vider manuellement les enregistrements à partir de la détails des appels et les bases de données QoE à tout moment. Par exemple, pour vider manuellement tous les enregistrements de plus de 10 jours ancien à partir de la base de données CDR vous pouvez utiliser une commande similaire à celle-ci :
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com. (Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session. Enregistrements de données de diagnostic sont les journaux de diagnostic téléchargés par les applications clientes telles que Skype pour Business Server).
  
Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays. Cependant, ces paramètres ne doivent pas avoir la même valeur. Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données. Pour ce faire, définissez le paramètre PurgeCallDetailDataOlderThanDays à 10 et PurgeDiagnosticDataOlderThanDays sur 0. Par exemple :
  
```
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
  
```
-Confirm:$False
```

Exemple :
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.
  
Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


