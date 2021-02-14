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
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="9c57f-103">Exporter des données archivées dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9c57f-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="9c57f-104">**Résumé :** Découvrez comment exporter des données archivées pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9c57f-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="9c57f-105">Les données archivées dans les bases de données d’archivage ne sont pas consultables ou dans un format lisible, mais vous pouvez utiliser l’cmdlet **Export-CsArchivingData** pour extraire des enregistrements de la base de données et les enregistrer en tant que fichier EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="9c57f-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="9c57f-106">Si vous activez l’intégration de Microsoft Exchange, les données sont archivées dans les magasins Exchange.</span><span class="sxs-lookup"><span data-stu-id="9c57f-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="9c57f-107">Les données archivées dans Exchange sont accessibles à la recherche et découvrables.</span><span class="sxs-lookup"><span data-stu-id="9c57f-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="9c57f-108">Pour plus d’informations sur l’accès aux données archivées dans Exchange, voir la documentation Exchange.</span><span class="sxs-lookup"><span data-stu-id="9c57f-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c57f-109">Exportation des données d’archivage à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="9c57f-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9c57f-110">Vous pouvez exporter des données archivées à l’aide Export-CSArchivingData cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c57f-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="9c57f-111">La commande suivante exporte toutes les données d’archivage écrites dans la base de données d atl-sql-001.contoso.com’archivage depuis le 1er juin 2012.</span><span class="sxs-lookup"><span data-stu-id="9c57f-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="9c57f-112">Le fichier de résultats obtenu sera enregistré dans le dossier C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="9c57f-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="9c57f-113">La commande suivante exporte les données d’archivage pour un seul utilisateur : kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9c57f-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="9c57f-114">Pour ce faire, vous inclurez le paramètre UserUri suivi de l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c57f-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="9c57f-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9c57f-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="9c57f-116">Pour plus d’informations, voir la rubrique d’aide pour [l';export-CsArchivingData.)](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9c57f-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

