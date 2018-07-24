---
title: Gérer la purge des données archivées dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Résumé : Découvrez comment gérer le vidage des données archivées de Skype pour Business Server.'
ms.openlocfilehash: fce7c8214eddd55736a54b960d57053a88cdc859
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997943"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="9f61e-103">Gérer la purge des données archivées dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9f61e-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="9f61e-104">**Résumé :** Découvrez comment gérer le vidage des données archivées de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f61e-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="9f61e-105">La base de données d’archivage n’est pas conçue pour la rétention à long terme et Skype pour Business Server ne fournit pas une solution d’e-discovery (recherche) pour les données archivées, afin que les données doivent être déplacés vers d’autres systèmes de stockage.</span><span class="sxs-lookup"><span data-stu-id="9f61e-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="9f61e-106">Skype pour Business Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées dans des transcriptions de recherche.</span><span class="sxs-lookup"><span data-stu-id="9f61e-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="9f61e-107">Vous devez définir quand exécuter la purge des données archivées et exportées.</span><span class="sxs-lookup"><span data-stu-id="9f61e-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="9f61e-108">Pour plus d’informations sur l’exportation de données à l’aide de l’applet de commande **Export-CsArchivingData** , voir [exporter des données archivées dans Skype pour Business Server](export-archived-data.md).</span><span class="sxs-lookup"><span data-stu-id="9f61e-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="9f61e-109">Gestion de la purge des données à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="9f61e-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="9f61e-110">Pour gérer la purge des données archivées à l’aide du panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="9f61e-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="9f61e-111">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9f61e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9f61e-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="9f61e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9f61e-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="9f61e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="9f61e-114">Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9f61e-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="9f61e-115">Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f61e-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="9f61e-116">Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="9f61e-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="9f61e-117">Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="9f61e-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="9f61e-118">Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="9f61e-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="9f61e-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9f61e-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="9f61e-120">Gestion de la purge des données à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f61e-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="9f61e-121">Vous pouvez gérer la purge des données archivées à l’aide des applets de commande de Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9f61e-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="9f61e-122">Utilisez l’applet de commande **Set-CsArchivingConfiguration** avec le paramètre EnablePurging pour activer ou désactiver la purge des données archivées.</span><span class="sxs-lookup"><span data-stu-id="9f61e-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="9f61e-123">Utilisez l’applet **Invoke-CsArchivingDatabasePurge** pour purger manuellement les enregistrements de la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9f61e-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="9f61e-124">La commande suivante, permet de purger toutes les données archivées, par exemple.</span><span class="sxs-lookup"><span data-stu-id="9f61e-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="9f61e-125">Une fois que cette commande est exécutée, Skype pour Business Server supprime tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour le paramètre KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="9f61e-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="9f61e-126">La commande suivante limite la purge aux enregistrements archivés qui ont été exportés dans un fichier de données (à l’aide de l’applet de commande **Export-CSArchivingData**).</span><span class="sxs-lookup"><span data-stu-id="9f61e-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="9f61e-127">Vous devez également définir le paramètre PurgeExportedArchivesOnly sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="9f61e-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="9f61e-128">Une fois que cette commande est exécutée, Skype pour Business Server ne purge que les enregistrements d’archivage qui répondent à deux critères : 1) ils sont antérieurs à la valeur spécifiée pour le paramètre KeepArchivingDataForDays ; et, 2) ils ont été exportés à l’aide de l’applet de commande **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="9f61e-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="9f61e-129">Pour désactiver la purge automatique des enregistrements archivés, définissez le paramètre EnablePurging sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="9f61e-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="9f61e-130">L’exemple suivant utilise l’applet de commande **Invoke-CsArchivingDatabasePurge** pour vider tous les enregistrements plus de 24 heures à partir de la base de données d’archivage sur atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9f61e-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="9f61e-131">Pour garantir la suppression de tous les enregistrements, y compris les enregistrements qui n’ont pas été exportés, le paramètre PurgeExportedArchivesOnly est défini sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="9f61e-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```