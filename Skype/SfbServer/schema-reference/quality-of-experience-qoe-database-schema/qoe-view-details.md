---
title: Vue détaillée de la qualité de l’expérience
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Affichages couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL. Il est recommandé de vues utilisées pour la création de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont davantage de chances de conserver la compatibilité avec les futures versions à compatibilité descendante.
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876548"
---
# <a name="qoe-view-details"></a><span data-ttu-id="b86df-104">Vue détaillée de la qualité de l’expérience</span><span class="sxs-lookup"><span data-stu-id="b86df-104">QoE view details</span></span>
 
<span data-ttu-id="b86df-105">Affichages couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL.</span><span class="sxs-lookup"><span data-stu-id="b86df-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="b86df-106">Il est recommandé de vues utilisées pour la création de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont davantage de chances de conserver la compatibilité avec les futures versions à compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="b86df-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="b86df-107">**Nom de l’affichage**</span><span class="sxs-lookup"><span data-stu-id="b86df-107">**View Name**</span></span>|<span data-ttu-id="b86df-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b86df-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b86df-109">Vue audiostreamdetail</span><span class="sxs-lookup"><span data-stu-id="b86df-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="b86df-110">Stocke des informations sur chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b86df-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="b86df-111">Vue MediaLine</span><span class="sxs-lookup"><span data-stu-id="b86df-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="b86df-112">Stocke des informations sur chaque ligne de média dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b86df-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="b86df-113">Une session audio contient généralement une seule ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="b86df-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="b86df-114">Un audio et vidéo (A / V) session contient généralement un média audio et une ligne de média vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si le mode d’affichage galerie est utilisé.</span><span class="sxs-lookup"><span data-stu-id="b86df-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="b86df-115">Vue networkconfigurationsettings</span><span class="sxs-lookup"><span data-stu-id="b86df-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="b86df-116">Stocke des informations sur la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="b86df-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="b86df-117">Affichage de la session</span><span class="sxs-lookup"><span data-stu-id="b86df-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="b86df-118">Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b86df-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="b86df-119">Vue UserAgent</span><span class="sxs-lookup"><span data-stu-id="b86df-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="b86df-120">Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b86df-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="b86df-121">Vue videostreamdetail</span><span class="sxs-lookup"><span data-stu-id="b86df-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="b86df-122">Stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b86df-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

