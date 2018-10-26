---
title: "Purge man. des BD de l’enr. des détails des appels et de la qual. de l’exp."
TOCtitle: "Purge man. des BD de l’enr. des détails des appels et de la qual. de l’exp."
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204812(v=OCS.15)
ms:contentKeyID: 49296926
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Purge manuelle des bases de données de l’enregistrement des détails des appels et de la qualité de l’expérience

 

_**Dernière rubrique modifiée :** 2014-07-07_

Comme indiqué dans la section précédente, les administrateurs peuvent configurer les bases de données d’enregistrement des détails des appels (CDR) et/ou de qualité de l’expérience (QoE) pour vider automatiquement la base de données des enregistrements anciens. Cette opération se produit si le vidage a été activé pour la base de données spécifiée (CDR ou QoE) et si celle-ci contient des enregistrements dont l’ancienneté dépasse la durée spécifiée. Par exemple, les administrateurs peuvent configurer le système pour que tous les jours à 1:00 les enregistrements QoE de plus de 60 jours soient supprimés de la base de données QoE.

Outre le vidage automatique, deux nouvelles applets de commande (Invoke-CsCdrDatabasePurge et Invoke-CsQoEDatbasePurge) ont été ajoutées à Microsoft Lync Server 2013. Ces applets de commandes permettent aux administrateurs de vider manuellement les bases de données CDR et QoE d’enregistrements, à tout moment. Par exemple, pour vider manuellement la base de données CDR de tous les enregistrements de plus de 10 jours, vous pouvez utiliser une commande de ce type :

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

Dans la commande précédente, les enregistrements de détail des appels et les enregistrements de données de diagnostic de plus de 10 jours sont supprimés de la base de données de surveillance sur atl-sql-001.litwareinc.com. (Les enregistrements de détail des appels sont des rapports d’utilisateur ou de session. Les enregistrements de données de diagnostic correspondent à des journaux de diagnostic téléchargés par des applications clientes telles que Lync 2013.)

Comme le montre l’exemple précédent, au moment d’exécuter l’applet de commande Invoke-CsCdrDatabasePurge, vous devez inclure les paramètres PurgeCallDetaiDataOlderThanDays et PurgeDiagnosticDataOlderThanDays. Cependant, ces paramètres ne doivent pas avoir la même valeur. Par exemple, il est possible de vider les enregistrements de détail des appels de plus de 10 jours tout en conservant l’ensemble des enregistrements de données de diagnostic dans la base de données. Pour cela, PurgeCallDetailDataOlderThanDays doit avoir la valeur 10 et PurgeDiagnosticDataOlderThanDays la valeur 0. Par exemple :

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Par défaut, à chaque fois que vous exécuterez Invoke-CsCdrDatabasePurge, vous obtiendrez une invite identique à celle-ci pour chaque table de base de données à vider :

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Vous devez taper Y (pour Oui) ou A (pour Oui pour tout) avant que le vidage de la base de données intervienne réellement. Si vous préférez supprimer ces invites de confirmation, ajoutez le paramètre suivant à la fin de votre appel à Invoke-CsCdrDatabasePurge :

    -Confirm:$False

Par exemple :

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Dans ce cas, les invites de confirmation ne s’affichent pas et le vidage de la base de données intervient immédiatement.

Pour vider la base de données QoE, utilisez l’applet de commande Invoke-CsQoEDatabasePurge et spécifiez l’ancienneté (en jours) des enregistrements à supprimer :

    Invoke-CsQoEDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

