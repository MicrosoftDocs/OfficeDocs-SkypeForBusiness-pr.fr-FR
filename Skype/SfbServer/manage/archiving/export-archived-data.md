---
title: Exportation des données archivées dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Résumé : Apprenez à exporter des données archivées pour Skype pour Business Server 2015.'
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a>Exportation des données archivées dans Skype Entreprise Server 2015

**Résumé :** Apprendre à exporter des données archivées pour Skype pour Business Server 2015.
  
Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande **Export-CsArchivingData** pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail).
  
Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les banques d’informations Exchange. Données archivées dans Exchange soient consultable et détectable. Pour plus d’informations sur l’accès aux données archivées dans Exchange, consultez la documentation d’Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportation de l’archivage des données à l’aide des applets de commande Windows PowerShell

Vous pouvez exporter les données archivées à l’aide de l’applet de commande Export-CSArchivingData. 
  
La commande suivante exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.contoso.com depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

La commande suivante exportations l’archivage des données pour un seul utilisateur : kenmyer@contoso.com. Pour ce faire, y compris le paramètre UserUri suivi d’adresse SIP de l’utilisateur. Par exemple : 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Exportation-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

