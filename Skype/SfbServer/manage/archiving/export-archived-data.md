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
# <a name="export-archived-data-in-skype-for-business-server-2015"></a><span data-ttu-id="093a6-103">Exportation des données archivées dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="093a6-103">Export archived data in Skype for Business Server 2015</span></span>

<span data-ttu-id="093a6-104">**Résumé :** Apprendre à exporter des données archivées pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="093a6-104">**Summary:** Learn how to export archived data for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="093a6-105">Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande **Export-CsArchivingData** pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="093a6-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="093a6-106">Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les banques d’informations Exchange.</span><span class="sxs-lookup"><span data-stu-id="093a6-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="093a6-107">Données archivées dans Exchange soient consultable et détectable.</span><span class="sxs-lookup"><span data-stu-id="093a6-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="093a6-108">Pour plus d’informations sur l’accès aux données archivées dans Exchange, consultez la documentation d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="093a6-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="093a6-109">Exportation de l’archivage des données à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="093a6-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="093a6-110">Vous pouvez exporter les données archivées à l’aide de l’applet de commande Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="093a6-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="093a6-p102">La commande suivante exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.contoso.com depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="093a6-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="093a6-113">La commande suivante exportations l’archivage des données pour un seul utilisateur : kenmyer@contoso.com. Pour ce faire, y compris le paramètre UserUri suivi d’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="093a6-113">The following command exports archiving data for a single user: kenmyer@contoso.com. This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="093a6-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="093a6-114">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="093a6-115">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Exportation-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="093a6-115">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

