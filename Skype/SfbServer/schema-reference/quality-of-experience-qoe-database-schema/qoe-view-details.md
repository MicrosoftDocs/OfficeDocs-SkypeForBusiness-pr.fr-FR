---
title: Vue détaillée de la qualité de l’expérience
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Les vues couvrent les cas les plus courants de retour de données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés plutôt que d’accéder directement aux tables de la base de données. en effet, les vues sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures.
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294753"
---
# <a name="qoe-view-details"></a><span data-ttu-id="eca14-104">Vue détaillée de la qualité de l’expérience</span><span class="sxs-lookup"><span data-stu-id="eca14-104">QoE view details</span></span>
 
<span data-ttu-id="eca14-105">Les vues couvrent les cas les plus courants de retour de données à partir de la base de données SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="eca14-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="eca14-106">Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés plutôt que d’accéder directement aux tables de la base de données. en effet, les vues sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="eca14-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="eca14-107">**Nom de la vue**</span><span class="sxs-lookup"><span data-stu-id="eca14-107">**View Name**</span></span>|<span data-ttu-id="eca14-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="eca14-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="eca14-109">Affichage AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="eca14-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="eca14-110">Stocke les informations relatives à chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="eca14-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="eca14-111">Affichage MediaLine</span><span class="sxs-lookup"><span data-stu-id="eca14-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="eca14-112">Stocke les informations relatives à chaque ligne multimédia dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="eca14-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="eca14-113">Une seule session audio contient généralement une ligne multimédia audio.</span><span class="sxs-lookup"><span data-stu-id="eca14-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="eca14-114">Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.</span><span class="sxs-lookup"><span data-stu-id="eca14-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="eca14-115">Affichage NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="eca14-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="eca14-116">Stocke des informations sur la configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="eca14-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="eca14-117">Affichage de session</span><span class="sxs-lookup"><span data-stu-id="eca14-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="eca14-118">Stocke les informations sur les sessions contenant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="eca14-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="eca14-119">Affichage UserAgent</span><span class="sxs-lookup"><span data-stu-id="eca14-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="eca14-120">Stocke les informations sur les agents utilisateur impliqués dans les sessions contenant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="eca14-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="eca14-121">Affichage VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="eca14-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="eca14-122">Stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="eca14-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

