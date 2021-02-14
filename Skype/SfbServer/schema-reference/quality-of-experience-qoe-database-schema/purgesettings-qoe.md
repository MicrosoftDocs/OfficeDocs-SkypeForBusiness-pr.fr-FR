---
title: Table PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'La table PurgeSettings contient des informations indiquant si (et quand) les enregistrements de qualité de l’expérience obsolètes doivent être automatiquement supprimés de la base de données QoE. Notez que les informations relatives au purge peuvent également être obtenues à partir de Skype Entreprise Server Management Shell en exécutant la commande suivante :'
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815804"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="3f38e-104">Table PurgeSettings (QoE)</span><span class="sxs-lookup"><span data-stu-id="3f38e-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="3f38e-105">La table PurgeSettings contient des informations indiquant si (et quand) les enregistrements de qualité de l’expérience obsolètes doivent être automatiquement supprimés de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="3f38e-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="3f38e-106">Notez que les informations relatives au purge peuvent également être obtenues à partir de Skype Entreprise Server Management Shell en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="3f38e-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="3f38e-107">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f38e-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3f38e-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3f38e-108">**Column**</span></span>|<span data-ttu-id="3f38e-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3f38e-109">**Data Type**</span></span>|<span data-ttu-id="3f38e-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3f38e-110">**Key/Index**</span></span>|<span data-ttu-id="3f38e-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="3f38e-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f38e-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="3f38e-112">**ID**</span></span> <br/> |<span data-ttu-id="3f38e-113">int</span><span class="sxs-lookup"><span data-stu-id="3f38e-113">int</span></span>  <br/> |<span data-ttu-id="3f38e-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="3f38e-114">Primary</span></span>  <br/> |<span data-ttu-id="3f38e-115">Identificateur unique pour la collecte des paramètres de vidage QoE.</span><span class="sxs-lookup"><span data-stu-id="3f38e-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="3f38e-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="3f38e-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="3f38e-117">bit</span><span class="sxs-lookup"><span data-stu-id="3f38e-117">bit</span></span>  <br/> ||<span data-ttu-id="3f38e-118">Lorsque la valeur est True (1), Microsoft Lync Server 2013 purge régulièrement les enregistrements obsolètes de la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="3f38e-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="3f38e-119">LA suppression a lieu tous les jours à l’heure indiquée par le paramètre PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="3f38e-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="3f38e-120">Si la valeur est False (0), les enregistrements ne sont pas supprimés automatiquement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3f38e-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="3f38e-121">La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="3f38e-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="3f38e-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="3f38e-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="3f38e-123">int</span><span class="sxs-lookup"><span data-stu-id="3f38e-123">int</span></span>  <br/> ||<span data-ttu-id="3f38e-p104">Spécifie l’âge des enregistrements QoE (en jours) qui seront supprimés de la base de données : si le vidage est activé, les enregistrements QoE antérieurs à cette valeur seront supprimés de la base de données. La valeur par défaut est 60 jours.</span><span class="sxs-lookup"><span data-stu-id="3f38e-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="3f38e-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="3f38e-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="3f38e-127">int</span><span class="sxs-lookup"><span data-stu-id="3f38e-127">int</span></span>  <br/> ||<span data-ttu-id="3f38e-p105">Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des  heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM). Spécifie l’heure locale du jour auquel le vidage a lieu. L’heure du jour est indiquée au format 24 heures, 0 représentant minuit (12:00 AM) et 23 représentant 11:00 PM. Notez que vous ne pouvez spécifier que des  heures : la valeur 10 (10:00 AM) est autorisée, mais la valeur 10,5 (10:30 AM) n’est pas autorisée. La valeur par défaut est 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="3f38e-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

