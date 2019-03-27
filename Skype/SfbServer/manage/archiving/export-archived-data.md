---
title: Exporter des données archivées dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Résumé : Découvrez comment exporter des données archivées pour Skype pour Business Server.'
ms.openlocfilehash: 7def9d2ea287c95695784161db72937ff4f2d5a4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890121"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exporter des données archivées dans Skype pour Business Server

**Résumé :** Découvrez comment exporter des données archivées pour Skype pour Business Server.
  
Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande **Export-CsArchivingData** pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail).
  
Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les banques Exchange. Données archivées dans Exchange sont disponible pour la recherche et facilement identifiables. Pour plus d’informations sur l’accès aux données archivées dans Exchange, consultez la documentation Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportation des données d’archivage à l’aide des applets de commande Windows PowerShell

Vous pouvez exporter les données archivées à l’aide de l’applet de commande Export-CSArchivingData. 
  
La commande suivante exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.contoso.com depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@contoso.com. Cela s’effectue en incluant le paramètre UserUri suivi d’adresse SIP de l’utilisateur. Par exemple : 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

