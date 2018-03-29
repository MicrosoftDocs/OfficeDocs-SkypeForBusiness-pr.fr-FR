---
title: Afficher les détails de QoE
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL. Il est recommandé de vues utilisées pour la génération de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont plus susceptibles d’assurer la compatibilité avec les versions ultérieures vers l’arrière.
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a><span data-ttu-id="bab93-104">Afficher les détails de QoE</span><span class="sxs-lookup"><span data-stu-id="bab93-104">QoE view details</span></span>
 
<span data-ttu-id="bab93-105">Vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL.</span><span class="sxs-lookup"><span data-stu-id="bab93-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="bab93-106">Il est recommandé de vues utilisées pour la génération de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont plus susceptibles d’assurer la compatibilité avec les versions ultérieures vers l’arrière.</span><span class="sxs-lookup"><span data-stu-id="bab93-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="bab93-107">**Nom de la vue**</span><span class="sxs-lookup"><span data-stu-id="bab93-107">**View Name**</span></span>|<span data-ttu-id="bab93-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="bab93-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="bab93-109">Vue de AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="bab93-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="bab93-110">Stocke des informations sur chaque flux de données audio dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="bab93-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="bab93-111">Vue de MediaLine</span><span class="sxs-lookup"><span data-stu-id="bab93-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="bab93-112">Stocke des informations sur chaque ligne de support dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="bab93-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="bab93-113">Une session audio contient généralement une seule ligne de média audio.</span><span class="sxs-lookup"><span data-stu-id="bab93-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="bab93-114">Un audio et vidéo (A / V) session contient en général un média audio et une ligne de la vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la galerie est utilisée.</span><span class="sxs-lookup"><span data-stu-id="bab93-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="bab93-115">Vue de NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="bab93-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="bab93-116">Stocke des informations sur la configuration du réseau.</span><span class="sxs-lookup"><span data-stu-id="bab93-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="bab93-117">Affichage de la session</span><span class="sxs-lookup"><span data-stu-id="bab93-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="bab93-118">Stocke des informations sur les sessions qui ont des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="bab93-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="bab93-119">Affichage de UserAgent</span><span class="sxs-lookup"><span data-stu-id="bab93-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="bab93-120">Stocke des informations sur les agents utilisateur qui ont été impliquées dans des sessions avec des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="bab93-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="bab93-121">Vue de VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="bab93-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="bab93-122">Stocke des informations sur chaque flux vidéo dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="bab93-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

