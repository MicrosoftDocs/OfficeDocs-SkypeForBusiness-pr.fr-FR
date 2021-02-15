---
title: Vue détaillée de la qualité de l’expérience (QoE)
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Les vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des vues pour créer des rapports personnalisés au lieu d’accéder directement aux tables de base de données . Cela est dû au fait que les affichages sont plus susceptibles de maintenir une compatibilité ascendante avec les futures sorties.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834474"
---
# <a name="qoe-view-details"></a><span data-ttu-id="14ed1-104">Vue détaillée de la qualité de l’expérience (QoE)</span><span class="sxs-lookup"><span data-stu-id="14ed1-104">QoE view details</span></span>
 
<span data-ttu-id="14ed1-105">Les vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="14ed1-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="14ed1-106">Il est recommandé d’utiliser des vues pour créer des rapports personnalisés au lieu d’accéder directement aux tables de base de données . Cela est dû au fait que les affichages sont plus susceptibles de maintenir une compatibilité ascendante avec les futures sorties.</span><span class="sxs-lookup"><span data-stu-id="14ed1-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="14ed1-107">**Nom de la vue**</span><span class="sxs-lookup"><span data-stu-id="14ed1-107">**View Name**</span></span>|<span data-ttu-id="14ed1-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="14ed1-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="14ed1-109">Affichage AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="14ed1-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="14ed1-110">Stocke les informations sur chaque flux audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="14ed1-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="14ed1-111">Affichage MediaLine</span><span class="sxs-lookup"><span data-stu-id="14ed1-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="14ed1-112">Stocke des informations sur chaque ligne de média dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="14ed1-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="14ed1-113">Une session audio contient généralement une ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="14ed1-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="14ed1-114">Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.</span><span class="sxs-lookup"><span data-stu-id="14ed1-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="14ed1-115">Affichage NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="14ed1-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="14ed1-116">Stocke des informations sur la configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="14ed1-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="14ed1-117">Affichage de session</span><span class="sxs-lookup"><span data-stu-id="14ed1-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="14ed1-118">Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="14ed1-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="14ed1-119">Affichage UserAgent</span><span class="sxs-lookup"><span data-stu-id="14ed1-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="14ed1-120">Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="14ed1-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="14ed1-121">Vue VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="14ed1-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="14ed1-122">Stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="14ed1-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

