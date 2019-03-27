---
title: Table !Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Le tableau de téléphones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894641"
---
# <a name="phones-table"></a><span data-ttu-id="3ec16-104">Table !Phones</span><span class="sxs-lookup"><span data-stu-id="3ec16-104">Phones table</span></span>
 
<span data-ttu-id="3ec16-105">Le tableau de téléphones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3ec16-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="3ec16-106">Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3ec16-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="3ec16-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3ec16-107">**Column**</span></span>|<span data-ttu-id="3ec16-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="3ec16-108">**Data Type**</span></span>|<span data-ttu-id="3ec16-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="3ec16-109">**Key/Index**</span></span>|<span data-ttu-id="3ec16-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="3ec16-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ec16-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="3ec16-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="3ec16-112">int</span><span class="sxs-lookup"><span data-stu-id="3ec16-112">int</span></span>  <br/> |<span data-ttu-id="3ec16-113">Principal</span><span class="sxs-lookup"><span data-stu-id="3ec16-113">Primary</span></span>  <br/> |<span data-ttu-id="3ec16-114">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="3ec16-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="3ec16-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="3ec16-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="3ec16-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3ec16-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="3ec16-117">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="3ec16-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="3ec16-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3ec16-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3ec16-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="3ec16-119">dateTime</span></span>  <br/> ||<span data-ttu-id="3ec16-120">Horodatage (pour une utilisation interne uniquement).</span><span class="sxs-lookup"><span data-stu-id="3ec16-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="3ec16-121">Ce champ est une nouveauté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ec16-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

