---
title: Modification de Configuration de journal de périphérique
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Vous pouvez ajouter une configuration de périphérique de journal à la page Modifier les paramètres de journal qui détermine la taille maximale du cache du journal, la taille maximale du journal ou la durée pendant laquelle qu'un fichier journal est conservé avant d’être purgée. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
ms.openlocfilehash: 8003014f7b94824d0ef36a8d1328c6430e98d894
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="6cfb9-104">Configuration des journaux de périphérique : modifier</span><span class="sxs-lookup"><span data-stu-id="6cfb9-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="6cfb9-105">Vous pouvez ajouter une configuration de périphérique de journal à la page **Modifier les paramètres de journal** qui détermine la taille maximale du cache du journal, la taille maximale du journal ou la durée pendant laquelle qu'un fichier journal est conservé avant d’être purgée.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="6cfb9-106">Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6cfb9-p103">Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="6cfb9-109">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="6cfb9-109">Tasks you can perform</span></span>

<span data-ttu-id="6cfb9-110">Vous pouvez effectuer les tâches suivantes dans la page **Modifier les paramètres de journal** :</span><span class="sxs-lookup"><span data-stu-id="6cfb9-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="6cfb9-111">Ajouter une configuration de journal de périphérique globalement ou pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="6cfb9-112">Modification des options d’une configuration de fichier journal d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="6cfb9-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="6cfb9-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="6cfb9-113">UI Reference</span></span>

<span data-ttu-id="6cfb9-114">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="6cfb9-115">**Champ d’application** Identifie la portée (Global ou Site) de la configuration de journal de périphérique.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="6cfb9-116">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration de journaux de périphérique.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="6cfb9-117">**Taille de fichier maximale (octets)** Vous pouvez spécifier la taille maximale, qu'un fichier journal peut devenir avant d’être purgée.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="6cfb9-118">La valeur par défaut est de 1,024,000 octets (1 Mo).</span><span class="sxs-lookup"><span data-stu-id="6cfb9-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="6cfb9-119">**Taille de cache maximale (octets)** Vous pouvez spécifier la quantité d’informations maximale (en octets) qui peuvent être présentes dans le cache de fichier journal avant que cache doit être effacé et les données sont écrites dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="6cfb9-120">La valeur par défaut est de 512,000 octets (0,5 Mo).</span><span class="sxs-lookup"><span data-stu-id="6cfb9-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="6cfb9-121">**Minutes pour vider le cache (1-60)** Vous pouvez spécifier la fréquence à laquelle les informations stockées dans le cache de fichier journal sont écrit dans le fichier journal actuel.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="6cfb9-122">Une fois que les données sont enregistrées, le cache est effacé.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="6cfb9-123">La valeur par défaut est de cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="6cfb9-124">**Jours de conservation des journaux (1-365)** Vous pouvez spécifier le nombre de jours que les fichiers journaux sont conservés avant leur suppression.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="6cfb9-125">La valeur par défaut est de 10 jours.</span><span class="sxs-lookup"><span data-stu-id="6cfb9-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6cfb9-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cfb9-126">See also</span></span>

#### 

[<span data-ttu-id="6cfb9-127">Configuration des journaux de périphérique</span><span class="sxs-lookup"><span data-stu-id="6cfb9-127">Device Log Configuration</span></span>](device-log-configuration.md)

