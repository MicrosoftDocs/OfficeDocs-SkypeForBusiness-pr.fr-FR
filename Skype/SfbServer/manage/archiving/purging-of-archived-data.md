---
title: Gérer la purge des données archivées dans Skype Entreprise Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Résumé : Découvrez comment gérer la purge des données archivées pour Skype Entreprise Server.'
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828534"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="620d2-103">Gérer la purge des données archivées dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="620d2-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="620d2-104">**Résumé :** Découvrez comment gérer la purge des données archivées pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="620d2-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="620d2-105">La base de données d’archivage n’est pas destinée à une rétention à long terme, et Skype Entreprise Server ne fournit pas de solution de découverte électronique (recherche) pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage.</span><span class="sxs-lookup"><span data-stu-id="620d2-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="620d2-106">Skype Entreprise Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées dans des transcriptions utilisables dans une recherche.</span><span class="sxs-lookup"><span data-stu-id="620d2-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="620d2-107">Vous devez définir quand purger les données archivées et exportées.</span><span class="sxs-lookup"><span data-stu-id="620d2-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="620d2-108">Pour plus d’informations sur l’exportation de données à l’aide de l’cmdlet **Export-CsArchivingData,** voir Exporter des données [archivées dans Skype Entreprise Server.](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="620d2-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="620d2-109">Gérer la purge des données à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="620d2-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="620d2-110">Pour gérer la purge des données archivées à l’aide du Panneau de contrôle :</span><span class="sxs-lookup"><span data-stu-id="620d2-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="620d2-111">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="620d2-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="620d2-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="620d2-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="620d2-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="620d2-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="620d2-114">Cliquez sur le nom de la configuration appropriée (globale, du site ou du pool) dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="620d2-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="620d2-115">Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="620d2-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="620d2-116">Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="620d2-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="620d2-117">Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="620d2-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="620d2-118">Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="620d2-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="620d2-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="620d2-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="620d2-120">Gérer la purge des données à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="620d2-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="620d2-121">Vous pouvez gérer la purge des données archivées à l’aide des cmdlets Windows PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="620d2-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="620d2-122">**L’cmdlet Set-CsArchivingConfiguration** avec le paramètre EnablePurging vous permet d’activer ou de désactiver la purge des données archivées.</span><span class="sxs-lookup"><span data-stu-id="620d2-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="620d2-123">**Invoke-CsArchivingDatabasePurge** vous permet de vider manuellement les enregistrements de la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="620d2-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="620d2-124">Par exemple, la commande suivante permet de purger toutes les données archivées.</span><span class="sxs-lookup"><span data-stu-id="620d2-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="620d2-125">Une fois cette commande exécuté, Skype Entreprise Server purge tous les enregistrements d’archivage plus anciens que la valeur spécifiée pour le paramètre KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="620d2-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="620d2-126">La commande suivante limite le purge aux enregistrements archivés qui ont été exportés vers un fichier de données (à l’aide de **l';export-CSArchivingData).**</span><span class="sxs-lookup"><span data-stu-id="620d2-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="620d2-127">Vous devez également définir le paramètre PurgeExportedArchivesOnly sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="620d2-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="620d2-128">Une fois cette commande exécuté, Skype Entreprise Server purge uniquement les enregistrements d’archivage qui répondent à deux critères : 1) ils sont plus anciens que la valeur spécifiée pour le paramètre KeepArchivingDataForDays ; et, 2) ils ont été exportés à l’aide de **l';export-CsArchivingData** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="620d2-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="620d2-129">Pour désactiver le purge automatique des enregistrements d’archivage, définissez le paramètre EnablePurging sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="620d2-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="620d2-130">L’exemple suivant utilise l’cmdlet **Invoke-CsArchivingDatabasePurge** pour vider tous les enregistrements de plus de 24 heures de la base de données d’archivage sur atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="620d2-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="620d2-131">Pour vous assurer que tous les enregistrements sont supprimés, y compris les enregistrements qui n’ont pas été exportés, le paramètre PurgeExportedArchivesOnly a la valeur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="620d2-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
