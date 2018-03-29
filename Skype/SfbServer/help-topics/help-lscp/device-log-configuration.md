---
title: Configuration du fichier journal du périphérique
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils. Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille du cache de données de journal, taille du fichier journal ou la durée pendant laquelle qu'un fichier journal est conservé avant d’être purgée. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin. Les paramètres des journaux peuvent être modifiés au niveau global ou par site.
ms.openlocfilehash: e5a88c7437b654846fd464133b953465cd5d3e2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration"></a><span data-ttu-id="e4bf9-107">Configuration du fichier journal du périphérique</span><span class="sxs-lookup"><span data-stu-id="e4bf9-107">Device Log Configuration</span></span>
 
<span data-ttu-id="e4bf9-108">Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="e4bf9-109">Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille du cache de données de journal, taille du fichier journal ou la durée pendant laquelle qu'un fichier journal est conservé avant d’être purgée.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="e4bf9-110">Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="e4bf9-111">Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="e4bf9-112">Les paramètres des journaux peuvent être modifiés au niveau global ou par site.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-112">Log settings can be changed globally or per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4bf9-113">Vous pouvez également configurer une heure à laquelle vous souhaitez que le service web de mise à jour des appareils supprime automatiquement les fichiers journaux dont l’ancienneté dépasse le nombre de jours de conservation configuré (par défaut, les fichiers journaux datant de plus de 10 jours sont supprimés).</span><span class="sxs-lookup"><span data-stu-id="e4bf9-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="e4bf9-114">Ce paramètre ne peut pas être modifié pour le panneau de configuration de Business Server à l’aide de Skype.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e4bf9-115">Au lieu de cela, vous devez utiliser Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e4bf9-116">Pour spécifier l’heure de la journée pour supprimer les fichiers journaux arrivés à expiration, utilisez l’applet de commande **New-CsDeviceUpdateConfiguration** avec le paramètre - LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="e4bf9-117">Pour plus d’informations, consultez [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e4bf9-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e4bf9-p104">Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e4bf9-120">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="e4bf9-120">Tasks you can perform</span></span>

<span data-ttu-id="e4bf9-121">Dans la page **Configuration du fichier journal de l'appareil**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4bf9-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>
  
- <span data-ttu-id="e4bf9-122">Ajout d’une configuration de fichier journal d'appareil au niveau global ou pour un site ou un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="e4bf9-122">Add a device log configuration globally or for a particular site or pool.</span></span>
    
- <span data-ttu-id="e4bf9-123">Modification des options d’une configuration de fichier journal d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="e4bf9-123">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e4bf9-124">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e4bf9-124">UI Reference</span></span>

<span data-ttu-id="e4bf9-125">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="e4bf9-126">**Nouveau** Vous pouvez ajouter une nouvelle configuration de journal de périphérique avec la portée suivante :</span><span class="sxs-lookup"><span data-stu-id="e4bf9-126">**New** You can add a new device log configuration with the following scope:</span></span>
    
  - <span data-ttu-id="e4bf9-127">Globale</span><span class="sxs-lookup"><span data-stu-id="e4bf9-127">Global</span></span>
    
  - <span data-ttu-id="e4bf9-128">Site</span><span class="sxs-lookup"><span data-stu-id="e4bf9-128">Site</span></span>
    
- <span data-ttu-id="e4bf9-129">**Modifier** Vous pouvez modifier les options de configuration d’un journal de périphérique dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="e4bf9-130">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4bf9-130">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="e4bf9-131">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options de configuration d’un périphérique de journal.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>
    
  - <span data-ttu-id="e4bf9-132">**Sélectionner tout** Cette option sélectionne tous les configuration de journal de périphérique dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-132">**Select All** This option selects all device log configuration in the list.</span></span>
    
  - <span data-ttu-id="e4bf9-133">**Supprimer** Cette option supprime toutes les configuration de journal de périphérique sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-133">**Delete** This option deletes all selected device log configuration.</span></span>
    
- <span data-ttu-id="e4bf9-134">**Actualiser** Vous pouvez actualiser la liste de configuration des journaux de périphérique pour vérifier l’état des options de configuration du journal tous les périphériques.</span><span class="sxs-lookup"><span data-stu-id="e4bf9-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e4bf9-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4bf9-135">See also</span></span>

#### 

[<span data-ttu-id="e4bf9-136">Modifier les paramètres pour les fichiers journaux d’activité de mise à jour de périphérique</span><span class="sxs-lookup"><span data-stu-id="e4bf9-136">Modify Settings for Log Files of Device Update Activity</span></span>](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)

