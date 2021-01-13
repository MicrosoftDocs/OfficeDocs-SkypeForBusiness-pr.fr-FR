---
title: Modification de la configuration du journal des périphériques
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Vous pouvez ajouter une nouvelle configuration de fichier journal de périphérique dans la page Modifier les paramètres de journalisation qui détermine la taille maximale du cache des journaux, la taille maximale des fichiers journaux ou la durée de conservation d’un fichier journal avant sa suppression. Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.
ms.openlocfilehash: ac6c341460d0e196548a86620d89f67bc51d7b4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830294"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="50e4e-104">Configuration du fichier journal de l’appareil : Modifier</span><span class="sxs-lookup"><span data-stu-id="50e4e-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="50e4e-105">Vous pouvez ajouter une nouvelle configuration de fichier journal de périphérique dans la page **Modifier les paramètres de journalisation** qui détermine la taille maximale du cache des journaux, la taille maximale des fichiers journaux ou la durée de conservation d’un fichier journal avant sa suppression.</span><span class="sxs-lookup"><span data-stu-id="50e4e-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="50e4e-106">Vous pouvez modifier ces paramètres en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="50e4e-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="50e4e-p103">Cette suppression les élimine définitivement du système de fichiers. Après avoir supprimé définitivement un fichier, vous ne pouvez pas le récupérer.</span><span class="sxs-lookup"><span data-stu-id="50e4e-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="50e4e-109">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="50e4e-109">Tasks you can perform</span></span>

<span data-ttu-id="50e4e-110">Vous pouvez effectuer les tâches suivantes dans la page **Modifier les paramètres de journalisation** :</span><span class="sxs-lookup"><span data-stu-id="50e4e-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="50e4e-111">Ajouter une configuration de fichier journal de périphérique globalement ou pour un site particulier</span><span class="sxs-lookup"><span data-stu-id="50e4e-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="50e4e-112">Modifier les options d’une configuration de fichier journal de périphérique existante</span><span class="sxs-lookup"><span data-stu-id="50e4e-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="50e4e-113">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="50e4e-113">UI Reference</span></span>

<span data-ttu-id="50e4e-114">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="50e4e-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="50e4e-115">**Étendue** Identifie l’étendue (globale ou site) de la configuration du journal de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="50e4e-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="50e4e-116">**Nom** Vous pouvez ajouter ou modifier le nom de la configuration du journal de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="50e4e-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="50e4e-117">**Taille de fichier maximale (octets)** Vous pouvez spécifier la taille maximale qu’un fichier journal peut atteindre avant d’être purgé.</span><span class="sxs-lookup"><span data-stu-id="50e4e-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="50e4e-118">La valeur par défaut est 1 024 000 octets (1 Mo).</span><span class="sxs-lookup"><span data-stu-id="50e4e-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="50e4e-119">**Taille maximale du cache (octets)** Vous pouvez spécifier la quantité maximale d’informations (en octets) qui peut être détenue dans le cache de fichiers journaux avant que ce cache ne soit effacé et que les données soient écrites dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="50e4e-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="50e4e-120">La valeur par défaut est 512 000 octets (0,5 Mo).</span><span class="sxs-lookup"><span data-stu-id="50e4e-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="50e4e-121">**Minutes de purge du cache (1-60)** Vous pouvez spécifier la fréquence à quelle fréquence les informations stockées dans le cache des fichiers journaux sont écrites dans le fichier journal réel.</span><span class="sxs-lookup"><span data-stu-id="50e4e-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="50e4e-122">Une fois les données enregistrées, le cache est effacé.</span><span class="sxs-lookup"><span data-stu-id="50e4e-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="50e4e-123">La valeur par défaut est cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="50e4e-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="50e4e-124">**Jours de conserver les fichiers journaux (1-365)** Vous pouvez spécifier le nombre de jours pendant combien de jours les fichiers journaux sont conservés avant leur purge.</span><span class="sxs-lookup"><span data-stu-id="50e4e-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="50e4e-125">La valeur par défaut est 10 jours.</span><span class="sxs-lookup"><span data-stu-id="50e4e-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="50e4e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50e4e-126">See also</span></span>

[<span data-ttu-id="50e4e-127">Configuration du fichier journal du périphérique</span><span class="sxs-lookup"><span data-stu-id="50e4e-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
