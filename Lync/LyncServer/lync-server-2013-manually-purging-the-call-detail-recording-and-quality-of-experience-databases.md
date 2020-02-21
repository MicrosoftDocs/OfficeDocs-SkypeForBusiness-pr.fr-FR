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

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Purge manuelle des bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-07_

Les administrateurs peuvent configurer les bases de données d’enregistrement des détails des appels et/ou de qualité de l’expérience pour purger automatiquement les anciens enregistrements de la base de données ; Cela se produit si la purge a été activée pour la base de données spécifiée (CDR ou QoE) et si des enregistrements se trouvaient dans la base de données plus longtemps que la durée spécifiée. Par exemple, tous les jours à 1:00 AM les administrateurs peuvent configurer le système de manière à ce que les enregistrements QoE datant de plus de 60 jours soient supprimés de la base de données QoE.

En plus de cette purge automatique, deux nouvelles applets de commande--Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge ont été ajoutées à Microsoft Lync Server 2013 ; ces applets de commande permettent aux administrateurs de purger manuellement les enregistrements des bases de données CDR et QoE à tout moment. Par exemple, pour purger manuellement tous les enregistrements datant de plus de 10 jours de la base de données CDR, vous pouvez utiliser une commande semblable à celle-ci :

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com. (Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session. Les enregistrements de données de diagnostic sont des journaux de diagnostic téléchargés par des applications clientes telles que Lync 2013.)

Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays. Cependant, ces paramètres ne doivent pas avoir la même valeur. Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données. Pour ce faire, définissez PurgeCallDetailDataOlderThanDays sur 10 et PurgeDiagnosticDataOlderThanDays sur 0. Par exemple :

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Par défaut, à chaque fois que vous exécuterez Invoke-CsCdrDatabasePurge, vous obtiendrez une invite identique à celle-ci pour chaque table de base de données à vider :

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Vous devez taper Y (pour Oui) ou A (pour Oui pour tout) avant que le vidage de la base de données intervienne réellement. Si vous préférez supprimer ces invites de confirmation, ajoutez le paramètre suivant à la fin de votre appel à Invoke-CsCdrDatabasePurge :

    -Confirm:$False

Par exemple :

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.

Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

