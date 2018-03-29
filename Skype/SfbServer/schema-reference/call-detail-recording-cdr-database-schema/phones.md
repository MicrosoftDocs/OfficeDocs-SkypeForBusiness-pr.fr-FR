---
title: Table !Phones
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La table de téléphones est une table de prise en charge. Chaque enregistrement dans la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a><span data-ttu-id="c6ddd-104">Table !Phones</span><span class="sxs-lookup"><span data-stu-id="c6ddd-104">Phones table</span></span>
 
<span data-ttu-id="c6ddd-105">La table de téléphones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c6ddd-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="c6ddd-106">Chaque enregistrement dans la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c6ddd-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="c6ddd-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-107">**Column**</span></span>|<span data-ttu-id="c6ddd-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-108">**Data Type**</span></span>|<span data-ttu-id="c6ddd-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-109">**Key/Index**</span></span>|<span data-ttu-id="c6ddd-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c6ddd-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="c6ddd-112">int</span><span class="sxs-lookup"><span data-stu-id="c6ddd-112">int</span></span>  <br/> |<span data-ttu-id="c6ddd-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c6ddd-113">Primary</span></span>  <br/> |<span data-ttu-id="c6ddd-114">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6ddd-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="c6ddd-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="c6ddd-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c6ddd-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="c6ddd-117">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6ddd-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="c6ddd-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c6ddd-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c6ddd-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="c6ddd-119">dateTime</span></span>  <br/> ||<span data-ttu-id="c6ddd-120">Horodatage (à usage interne uniquement).</span><span class="sxs-lookup"><span data-stu-id="c6ddd-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="c6ddd-121">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6ddd-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

