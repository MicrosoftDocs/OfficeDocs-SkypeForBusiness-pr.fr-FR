---
title: Table Phones
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823264"
---
# <a name="phones-table"></a><span data-ttu-id="4edd0-104">Table Phones</span><span class="sxs-lookup"><span data-stu-id="4edd0-104">Phones table</span></span>
 
<span data-ttu-id="4edd0-105">La table Phones est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4edd0-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="4edd0-106">Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4edd0-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="4edd0-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4edd0-107">**Column**</span></span>|<span data-ttu-id="4edd0-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4edd0-108">**Data Type**</span></span>|<span data-ttu-id="4edd0-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="4edd0-109">**Key/Index**</span></span>|<span data-ttu-id="4edd0-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="4edd0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4edd0-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="4edd0-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="4edd0-112">int</span><span class="sxs-lookup"><span data-stu-id="4edd0-112">int</span></span>  <br/> |<span data-ttu-id="4edd0-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="4edd0-113">Primary</span></span>  <br/> |<span data-ttu-id="4edd0-114">Numéro unique identifiant ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="4edd0-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="4edd0-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="4edd0-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="4edd0-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4edd0-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="4edd0-117">Numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="4edd0-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="4edd0-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4edd0-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4edd0-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="4edd0-119">dateTime</span></span>  <br/> ||<span data-ttu-id="4edd0-120">Horodaté (pour une utilisation interne uniquement).</span><span class="sxs-lookup"><span data-stu-id="4edd0-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="4edd0-121">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4edd0-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

