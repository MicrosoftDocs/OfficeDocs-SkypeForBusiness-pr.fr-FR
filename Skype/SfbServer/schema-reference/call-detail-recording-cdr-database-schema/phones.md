---
title: Table !Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La table Telephones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui contiennent des enregistrements dans la base de données.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815002"
---
# <a name="phones-table"></a><span data-ttu-id="a1748-104">Table !Phones</span><span class="sxs-lookup"><span data-stu-id="a1748-104">Phones table</span></span>
 
<span data-ttu-id="a1748-105">La table Telephones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a1748-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="a1748-106">Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui contiennent des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a1748-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="a1748-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a1748-107">**Column**</span></span>|<span data-ttu-id="a1748-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a1748-108">**Data Type**</span></span>|<span data-ttu-id="a1748-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="a1748-109">**Key/Index**</span></span>|<span data-ttu-id="a1748-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a1748-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1748-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="a1748-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="a1748-112">int</span><span class="sxs-lookup"><span data-stu-id="a1748-112">int</span></span>  <br/> |<span data-ttu-id="a1748-113">Principal</span><span class="sxs-lookup"><span data-stu-id="a1748-113">Primary</span></span>  <br/> |<span data-ttu-id="a1748-114">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="a1748-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="a1748-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="a1748-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="a1748-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a1748-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="a1748-117">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="a1748-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="a1748-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="a1748-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a1748-119">Valeur</span><span class="sxs-lookup"><span data-stu-id="a1748-119">dateTime</span></span>  <br/> ||<span data-ttu-id="a1748-120">Horodatage (pour une utilisation interne uniquement).</span><span class="sxs-lookup"><span data-stu-id="a1748-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="a1748-121">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1748-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

