---
title: Configuration du fichier journal du périphérique
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des périphériques. Dans le cadre de la stratégie de gestion des données de votre organisation, vous pouvez définir des seuils sur la taille du cache de données du journal, la taille des fichiers journaux ou la durée de la durée de la mise à jour d’un fichier journal avant sa purge. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation. Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, le cas échéant. Les paramètres des journaux peuvent être modifiés globalement ou par site.
ms.openlocfilehash: c9bd2c3077325540e6151fabd7bc4127b909a12a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120273"
---
# <a name="device-log-configuration"></a><span data-ttu-id="e26db-107">Configuration du fichier journal de l’appareil</span><span class="sxs-lookup"><span data-stu-id="e26db-107">Device Log Configuration</span></span>

<span data-ttu-id="e26db-108">Le service web de mise à jour des appareils crée automatiquement des fichiers journaux qui enregistrent l’activité de mise à jour des périphériques.</span><span class="sxs-lookup"><span data-stu-id="e26db-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="e26db-109">Dans le cadre de la stratégie de gestion des données de votre organisation, vous pouvez définir des seuils sur la taille du cache de données du journal, la taille des fichiers journaux ou la durée de la durée de la mise à jour d’un fichier journal avant sa purge.</span><span class="sxs-lookup"><span data-stu-id="e26db-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="e26db-110">Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e26db-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="e26db-111">Si vous ne souhaitez pas que le service web de mise à jour des appareils supprime définitivement et automatiquement les fichiers journaux, vous pouvez les supprimer manuellement, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="e26db-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="e26db-112">Les paramètres des journaux peuvent être modifiés globalement ou par site.</span><span class="sxs-lookup"><span data-stu-id="e26db-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="e26db-113">Vous pouvez également configurer une heure à laquelle vous souhaitez que le service web de mise à jour des appareils supprime automatiquement les fichiers journaux dont l’ancienneté dépasse le nombre de jours de conservation que vous avez configuré (par défaut, les fichiers journaux de plus de 10 jours sont supprimés).</span><span class="sxs-lookup"><span data-stu-id="e26db-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="e26db-114">Ce paramètre ne peut pas être modifié à l’aide du Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e26db-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e26db-115">Au lieu de cela, vous devez utiliser Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e26db-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e26db-116">Pour spécifier l’heure de suppression des fichiers journaux expirés, utilisez **l’cmdlet New-CsDeviceUpdateConfiguration** avec le paramètre -LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="e26db-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="e26db-117">Pour plus d’informations, [voir New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e26db-117">For details, see [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="e26db-p104">Cette suppression les élimine définitivement du système de fichiers. Après avoir supprimé définitivement un fichier, vous ne pouvez pas le récupérer.</span><span class="sxs-lookup"><span data-stu-id="e26db-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e26db-120">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="e26db-120">Tasks you can perform</span></span>

<span data-ttu-id="e26db-121">Vous pouvez effectuer les tâches suivantes dans la page **Configuration du fichier journal du périphérique** :</span><span class="sxs-lookup"><span data-stu-id="e26db-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="e26db-122">Ajouter une configuration de fichier journal de périphérique globalement ou pour un site ou un pool particulier</span><span class="sxs-lookup"><span data-stu-id="e26db-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="e26db-123">Modifier les options d’une configuration existante de fichier journal de périphérique</span><span class="sxs-lookup"><span data-stu-id="e26db-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e26db-124">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e26db-124">UI Reference</span></span>

<span data-ttu-id="e26db-125">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="e26db-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="e26db-126">**Nouveau** Vous pouvez ajouter une nouvelle configuration de journal d’appareil avec l’étendue suivante :</span><span class="sxs-lookup"><span data-stu-id="e26db-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="e26db-127">Global</span><span class="sxs-lookup"><span data-stu-id="e26db-127">Global</span></span>

  - <span data-ttu-id="e26db-128">Site</span><span class="sxs-lookup"><span data-stu-id="e26db-128">Site</span></span>

- <span data-ttu-id="e26db-129">**Modifier** Vous pouvez modifier les options d’une configuration de journal d’appareil dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e26db-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="e26db-130">À l’aide de cette option, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e26db-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="e26db-131">**Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une configuration de journal d’appareil.</span><span class="sxs-lookup"><span data-stu-id="e26db-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="e26db-132">**Sélectionner tout** Cette option sélectionne toute la configuration du journal des appareils dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e26db-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="e26db-133">**Supprimer** Cette option supprime toutes les configurations de journal d’appareil sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="e26db-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="e26db-134">**Actualiser** Vous pouvez actualiser la liste de configuration des journaux de périphériques pour vérifier l’état des options de toutes les configurations du journal d’appareil.</span><span class="sxs-lookup"><span data-stu-id="e26db-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="e26db-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e26db-135">See also</span></span>

[<span data-ttu-id="e26db-136">Modifier les paramètres des fichiers journaux de l’activité de mise à jour des périphériques</span><span class="sxs-lookup"><span data-stu-id="e26db-136">Modify Settings for Log Files of Device Update Activity</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)