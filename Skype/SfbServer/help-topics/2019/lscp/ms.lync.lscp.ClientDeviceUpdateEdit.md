---
title: Modification de la configuration du journal des appareils
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez ajouter une configuration du journal de périphériques à la page modifier le paramètre du journal qui détermine la taille maximale du cache, la taille maximale du fichier journal ou la durée de conservation du fichier journal avant sa suppression définitive. Vous pouvez modifier ces paramètres en fonction de la configuration requise de votre organisation.
ms.openlocfilehash: f2c169038b69fbbb3e68838827a9a77d472c87e4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794523"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="c2d88-104">Configuration du fichier journal du périphérique : modifier</span><span class="sxs-lookup"><span data-stu-id="c2d88-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="c2d88-105">Vous pouvez ajouter une configuration du journal de périphériques à la page **modifier le paramètre du journal** qui détermine la taille maximale du cache, la taille maximale du fichier journal ou la durée de conservation du fichier journal avant sa suppression définitive.</span><span class="sxs-lookup"><span data-stu-id="c2d88-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="c2d88-106">Vous pouvez modifier ces paramètres en fonction de la configuration requise de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c2d88-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c2d88-p103">Cette suppression les supprime définitivement du système de fichiers. Une fois qu’un fichier est supprimé définitivement, vous ne pouvez pas le récupérer.</span><span class="sxs-lookup"><span data-stu-id="c2d88-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="c2d88-109">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="c2d88-109">Tasks you can perform</span></span>

<span data-ttu-id="c2d88-110">Dans la page **modifier le paramètre journal** , vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c2d88-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="c2d88-111">Ajoutez une configuration du journal de périphériques globalement ou pour un site particulier.</span><span class="sxs-lookup"><span data-stu-id="c2d88-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="c2d88-112">Modification des options d’une configuration de fichier journal d’appareil existante</span><span class="sxs-lookup"><span data-stu-id="c2d88-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="c2d88-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="c2d88-113">UI Reference</span></span>

<span data-ttu-id="c2d88-114">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="c2d88-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="c2d88-115">**Scope** Identifie l’étendue (globale ou site) de la configuration du journal des appareils.</span><span class="sxs-lookup"><span data-stu-id="c2d88-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="c2d88-116">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration du journal de périphériques.</span><span class="sxs-lookup"><span data-stu-id="c2d88-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="c2d88-117">**Taille de fichier maximale (octets)** Vous pouvez spécifier la taille maximale d’un fichier journal avant sa suppression définitive.</span><span class="sxs-lookup"><span data-stu-id="c2d88-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="c2d88-118">La valeur par défaut est 1 024 000 octets (1 Mo).</span><span class="sxs-lookup"><span data-stu-id="c2d88-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="c2d88-119">**Taille maximale du cache (octets)** Vous pouvez spécifier la quantité maximale d’informations (en octets) qui peut être stockée dans le cache du fichier journal avant que ce cache ne doit être vidé et que les données soient écrites dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="c2d88-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="c2d88-120">La valeur par défaut est 512 000 octets (0,5 Mo).</span><span class="sxs-lookup"><span data-stu-id="c2d88-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="c2d88-121">**Minutes pour vider le cache (1-60)** Vous pouvez spécifier la fréquence à laquelle les informations stockées dans le cache du fichier journal sont écrites dans le fichier journal réel.</span><span class="sxs-lookup"><span data-stu-id="c2d88-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="c2d88-122">Lorsque les données sont enregistrées, le cache est vidé.</span><span class="sxs-lookup"><span data-stu-id="c2d88-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="c2d88-123">La valeur par défaut est 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="c2d88-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="c2d88-124">**Jours de conservation des fichiers journaux (1-365)** Vous pouvez spécifier le nombre de jours pendant lequel les fichiers journaux sont conservés avant d’être supprimés.</span><span class="sxs-lookup"><span data-stu-id="c2d88-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="c2d88-125">La valeur par défaut est 10 jours.</span><span class="sxs-lookup"><span data-stu-id="c2d88-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c2d88-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2d88-126">See also</span></span>

[<span data-ttu-id="c2d88-127">Configuration du fichier journal du périphérique</span><span class="sxs-lookup"><span data-stu-id="c2d88-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
