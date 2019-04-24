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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212886"
---
# <a name="phones-table"></a><span data-ttu-id="27e44-104">Table !Phones</span><span class="sxs-lookup"><span data-stu-id="27e44-104">Phones table</span></span>
 
<span data-ttu-id="27e44-105">Le tableau de téléphones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="27e44-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="27e44-106">Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="27e44-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="27e44-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="27e44-107">**Column**</span></span>|<span data-ttu-id="27e44-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="27e44-108">**Data Type**</span></span>|<span data-ttu-id="27e44-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="27e44-109">**Key/Index**</span></span>|<span data-ttu-id="27e44-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="27e44-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27e44-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="27e44-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="27e44-112">int</span><span class="sxs-lookup"><span data-stu-id="27e44-112">int</span></span>  <br/> |<span data-ttu-id="27e44-113">Principal</span><span class="sxs-lookup"><span data-stu-id="27e44-113">Primary</span></span>  <br/> |<span data-ttu-id="27e44-114">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="27e44-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="27e44-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="27e44-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="27e44-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="27e44-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="27e44-117">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="27e44-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="27e44-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="27e44-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="27e44-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="27e44-119">dateTime</span></span>  <br/> ||<span data-ttu-id="27e44-120">Horodatage (pour une utilisation interne uniquement).</span><span class="sxs-lookup"><span data-stu-id="27e44-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="27e44-121">Ce champ est une nouveauté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27e44-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

