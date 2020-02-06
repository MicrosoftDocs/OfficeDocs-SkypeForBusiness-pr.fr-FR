---
title: Exporter des données archivées dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Résumé : Découvrez comment exporter des données archivées pour Skype entreprise Server.'
ms.openlocfilehash: 12ba59ff11a988fd95eb2207cd826a4399db2779
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818906"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exporter des données archivées dans Skype entreprise Server

**Résumé :** Découvrez comment exporter des données archivées pour Skype entreprise Server.
  
Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande **Export-CsArchivingData** pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail).
  
Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les banques Exchange. Les données archivées dans Exchange sont consultables et détectables. Pour plus d’informations sur l’accès aux données archivées dans Exchange, voir la documentation Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportation des données d’archivage à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez exporter les données archivées à l’aide de l’applet de commande Export-CSArchivingData. 
  
La commande suivante exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.contoso.com depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@contoso.com. Pour ce faire, vous pouvez inclure le paramètre UserUri suivi de l’adresse SIP de l’utilisateur. Par exemple : 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

