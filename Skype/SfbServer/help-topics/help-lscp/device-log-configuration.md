---
title: Configuration du fichier journal du périphérique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils. Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille de cache de données, taille du fichier journal ou la durée pendant laquelle qu'un fichier journal sera conservé avant la purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin. Les paramètres des journaux peuvent être modifiés au niveau global ou par site.
ms.openlocfilehash: b4475efcee20846a7ff651265a13b34b3b9a43a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914029"
---
# <a name="device-log-configuration"></a><span data-ttu-id="f6708-107">Configuration du fichier journal du périphérique</span><span class="sxs-lookup"><span data-stu-id="f6708-107">Device Log Configuration</span></span>

<span data-ttu-id="f6708-108">Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des appareils.</span><span class="sxs-lookup"><span data-stu-id="f6708-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="f6708-109">Dans le cadre de la stratégie de gestion des données de votre organisation, vous souhaiterez peut-être définir des seuils pour la taille de cache de données, taille du fichier journal ou la durée pendant laquelle qu'un fichier journal sera conservé avant la purge.</span><span class="sxs-lookup"><span data-stu-id="f6708-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="f6708-110">Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f6708-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="f6708-111">Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, au besoin.</span><span class="sxs-lookup"><span data-stu-id="f6708-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="f6708-112">Les paramètres des journaux peuvent être modifiés au niveau global ou par site.</span><span class="sxs-lookup"><span data-stu-id="f6708-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="f6708-113">Vous pouvez également configurer une heure à laquelle vous souhaitez que le service web de mise à jour des appareils supprime automatiquement les fichiers journaux dont l’ancienneté dépasse le nombre de jours de conservation configuré (par défaut, les fichiers journaux datant de plus de 10 jours sont supprimés).</span><span class="sxs-lookup"><span data-stu-id="f6708-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="f6708-114">Ce paramètre ne peut pas être modifié à l’aide de Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="f6708-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f6708-115">Au lieu de cela, vous devez utiliser Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6708-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f6708-116">Pour spécifier l’heure du jour pour supprimer les fichiers journaux arrivés à expiration, utilisez l’applet de commande **New-CsDeviceUpdateConfiguration** avec le paramètre – LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="f6708-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="f6708-117">Pour plus d’informations, voir [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f6708-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="f6708-p104">Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer.</span><span class="sxs-lookup"><span data-stu-id="f6708-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f6708-120">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="f6708-120">Tasks you can perform</span></span>

<span data-ttu-id="f6708-121">Dans la page **Configuration du fichier journal de l'appareil**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6708-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="f6708-122">Ajout d’une configuration de fichier journal d'appareil au niveau global ou pour un site ou un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="f6708-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="f6708-123">Modification des options d’une configuration de fichier journal d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="f6708-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f6708-124">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="f6708-124">UI Reference</span></span>

<span data-ttu-id="f6708-125">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="f6708-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="f6708-126">**Nouveau** Vous pouvez ajouter une nouvelle configuration de journal de périphérique avec l’étendue suivante :</span><span class="sxs-lookup"><span data-stu-id="f6708-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="f6708-127">Globale</span><span class="sxs-lookup"><span data-stu-id="f6708-127">Global</span></span>

  - <span data-ttu-id="f6708-128">Site</span><span class="sxs-lookup"><span data-stu-id="f6708-128">Site</span></span>

- <span data-ttu-id="f6708-129">**Modifier** Vous pouvez modifier les options de configuration d’un journal de périphérique dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f6708-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="f6708-130">Utilisez cette option, vous pouvez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f6708-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="f6708-131">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options de configuration d’un journal de périphérique.</span><span class="sxs-lookup"><span data-stu-id="f6708-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="f6708-132">**Sélectionner tout** Cette option sélectionne toutes les configurations de fichier journal de périphérique dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f6708-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="f6708-133">**Supprimer** Cette option supprime toutes les configurations de fichier journal de périphérique sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f6708-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="f6708-134">**Actualiser** Vous pouvez actualiser la liste de configuration de journal de périphérique pour vérifier le statut des options de configuration du fichier journal tous les périphériques.</span><span class="sxs-lookup"><span data-stu-id="f6708-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6708-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6708-135">See also</span></span>

[<span data-ttu-id="f6708-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="f6708-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
