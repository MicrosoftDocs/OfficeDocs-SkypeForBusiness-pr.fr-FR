---
title: Table EdgeServers dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: La table EdgeServers est un tableau de prise en charge. Chaque enregistrement stocke des informations sur un serveur de transport Edge qui est impliqué dans les appels ayant des enregistrements dans la base de données.
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c0199-104">Table EdgeServers dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c0199-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c0199-105">La table EdgeServers est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c0199-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="c0199-106">Chaque enregistrement stocke des informations sur un serveur de transport Edge qui est impliqué dans les appels ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c0199-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="c0199-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c0199-107">**Column**</span></span>|<span data-ttu-id="c0199-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c0199-108">**Data Type**</span></span>|<span data-ttu-id="c0199-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="c0199-109">**Key/Index**</span></span>|<span data-ttu-id="c0199-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c0199-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c0199-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="c0199-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="c0199-112">int</span><span class="sxs-lookup"><span data-stu-id="c0199-112">int</span></span>  <br/> |<span data-ttu-id="c0199-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c0199-113">Primary</span></span>  <br/> |<span data-ttu-id="c0199-114">Numéro unique qui identifie ce serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="c0199-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="c0199-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="c0199-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="c0199-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c0199-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="c0199-117">Nom du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="c0199-117">Edge Server name.</span></span>  <br/> |
   

