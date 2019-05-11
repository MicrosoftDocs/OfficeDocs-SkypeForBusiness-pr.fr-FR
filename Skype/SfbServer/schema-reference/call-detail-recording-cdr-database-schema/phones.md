---
title: Table !Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Le tableau de téléphones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930615"
---
# <a name="phones-table"></a><span data-ttu-id="cac3d-104">Table !Phones</span><span class="sxs-lookup"><span data-stu-id="cac3d-104">Phones table</span></span>
 
<span data-ttu-id="cac3d-105">Le tableau de téléphones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="cac3d-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="cac3d-106">Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="cac3d-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="cac3d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cac3d-107">**Column**</span></span>|<span data-ttu-id="cac3d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cac3d-108">**Data Type**</span></span>|<span data-ttu-id="cac3d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="cac3d-109">**Key/Index**</span></span>|<span data-ttu-id="cac3d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cac3d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cac3d-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="cac3d-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="cac3d-112">int</span><span class="sxs-lookup"><span data-stu-id="cac3d-112">int</span></span>  <br/> |<span data-ttu-id="cac3d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="cac3d-113">Primary</span></span>  <br/> |<span data-ttu-id="cac3d-114">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="cac3d-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="cac3d-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="cac3d-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="cac3d-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="cac3d-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="cac3d-117">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="cac3d-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="cac3d-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="cac3d-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="cac3d-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="cac3d-119">dateTime</span></span>  <br/> ||<span data-ttu-id="cac3d-120">Horodatage (pour une utilisation interne uniquement).</span><span class="sxs-lookup"><span data-stu-id="cac3d-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="cac3d-121">Ce champ est une nouveauté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cac3d-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

