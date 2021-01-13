---
title: Exporter des données archivées dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Résumé : Découvrez comment exporter des données archivées pour Skype Entreprise Server.'
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817564"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exporter des données archivées dans Skype Entreprise Server

**Résumé :** Découvrez comment exporter des données archivées pour Skype Entreprise Server.
  
Les données archivées dans les bases de données d’archivage ne sont pas consultables ou dans un format lisible, mais vous pouvez utiliser l’cmdlet **Export-CsArchivingData** pour extraire des enregistrements de la base de données et les enregistrer en tant que fichier EML (Outlook Electronic Mail).
  
Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les magasins Exchange. Les données archivées dans Exchange sont accessibles à la recherche et découvrables. Pour plus d’informations sur l’accès aux données archivées dans Exchange, voir la documentation Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportation des données d’archivage à l’aide Windows PowerShell cmdlets

Vous pouvez exporter des données archivées à l’aide Export-CSArchivingData cmdlet. 
  
La commande suivante exporte toutes les données d’archivage écrites dans la base de données d atl-sql-001.contoso.com’archivage depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@contoso.com. Pour ce faire, vous inclurez le paramètre UserUri suivi de l’adresse SIP de l’utilisateur. Par exemple : 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Pour plus d’informations, voir la rubrique d’aide pour [l';export-CsArchivingData.)](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)
  

