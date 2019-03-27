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
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="63c56-103">Exporter des données archivées dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="63c56-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="63c56-104">**Résumé :** Découvrez comment exporter des données archivées pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="63c56-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="63c56-105">Il n’est pas possible de faire des recherches dans les données archivées dans les bases de données d’archivage ou bien ces données ne sont pas dans un format lisible. Cependant, vous pouvez utiliser l’applet de commande **Export-CsArchivingData** pour les extraire et les enregistrer en tant que fichier EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="63c56-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="63c56-106">Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les banques Exchange.</span><span class="sxs-lookup"><span data-stu-id="63c56-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="63c56-107">Données archivées dans Exchange sont disponible pour la recherche et facilement identifiables.</span><span class="sxs-lookup"><span data-stu-id="63c56-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="63c56-108">Pour plus d’informations sur l’accès aux données archivées dans Exchange, consultez la documentation Exchange.</span><span class="sxs-lookup"><span data-stu-id="63c56-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="63c56-109">Exportation des données d’archivage à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="63c56-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="63c56-110">Vous pouvez exporter les données archivées à l’aide de l’applet de commande Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="63c56-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="63c56-p102">La commande suivante exporte toutes les données d’archivage enregistrées dans la base de données d’archivage atl-sql-001.contoso.com depuis le 1er juin 2012. Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="63c56-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="63c56-113">La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="63c56-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="63c56-114">Cela s’effectue en incluant le paramètre UserUri suivi d’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63c56-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="63c56-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="63c56-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="63c56-116">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="63c56-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

