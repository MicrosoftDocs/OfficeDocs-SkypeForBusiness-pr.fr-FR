---
title: Ajouter un pool MCU audio/vidéo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Tous les serveurs Enterprise Edition frontaux d’un site central qui n’ont pas un colocalisé un service de conférence V peut utiliser le même Stand-Alone A / pool de conférence V. Pour chaque A / pool de conférence V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et si elle aura uniquement un seul A / V Conferencing Server ou multiples, à charge équilibrée A / V Conferencing Servers.
ms.openlocfilehash: dd2dd53ae2d3b66da88d39567b4d20e0960633e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889320"
---
# <a name="add-av-mcu-pool"></a>Ajouter un pool MCU audio/vidéo
 
Tous les serveurs Enterprise Edition frontaux d’un site central qui n’ont pas un colocalisé un service de conférence V peut utiliser le même Stand-Alone A / pool de conférence V. Pour chaque A / pool de conférence V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et si elle aura uniquement un seul A / V Conferencing Server ou multiples, à charge équilibrée A / V Conferencing Servers.
  
> [!IMPORTANT]
> Impossible de convertir un pool de serveur unique vers un pool de plusieurs serveurs. Si vous décidez ultérieurement que votre organisation a besoin d’un pool de plusieurs serveurs, vous devez supprimer le pool de serveur unique et puis ajouter le pool de plusieurs serveurs. 
  
> [!TIP]
> Si vous envisagez d’implémenter un / pool de conférence V activez à l’avenir, le **pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez le Générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer la nouvelle A / V Conferencing pool membre via le Skype pour l’Assistant de déploiement Business Server. A / pools V Conferencing Server sont uniques dans la mesure où ils ne pas besoin équilibreurs de charge pour créer un pool. A / pools de conférence V équilibrer la charge en interne et n’avez pas besoin de matériel supplémentaire. 
  

