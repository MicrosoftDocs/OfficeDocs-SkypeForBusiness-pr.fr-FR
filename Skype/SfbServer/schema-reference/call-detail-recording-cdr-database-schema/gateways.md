---
title: Table Gateways dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Le tableau de passerelles est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle impliqué dans les appels public commuté (PSTN) réseau disposant d’enregistrements dans la base de données.
ms.openlocfilehash: 2a3429b45a63c0c7765f4e9da0ea2baf3f0d11b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901037"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e8699-104">Table Gateways dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8699-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8699-105">Le tableau de passerelles est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e8699-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="e8699-106">Chaque enregistrement stocke des informations sur une passerelle impliqué dans les appels public commuté (PSTN) réseau disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e8699-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="e8699-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e8699-107">**Column**</span></span>|<span data-ttu-id="e8699-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e8699-108">**Data Type**</span></span>|<span data-ttu-id="e8699-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e8699-109">**Key/Index**</span></span>|<span data-ttu-id="e8699-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e8699-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8699-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="e8699-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="e8699-112">int</span><span class="sxs-lookup"><span data-stu-id="e8699-112">int</span></span>  <br/> |<span data-ttu-id="e8699-113">Principal</span><span class="sxs-lookup"><span data-stu-id="e8699-113">Primary</span></span>  <br/> |<span data-ttu-id="e8699-114">Numéro unique identifiant cette passerelle.</span><span class="sxs-lookup"><span data-stu-id="e8699-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="e8699-115">**Passerelle**</span><span class="sxs-lookup"><span data-stu-id="e8699-115">**Gateway**</span></span> <br/> |<span data-ttu-id="e8699-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e8699-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="e8699-117">Nom de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="e8699-117">Gateway name.</span></span>  <br/> |
   

