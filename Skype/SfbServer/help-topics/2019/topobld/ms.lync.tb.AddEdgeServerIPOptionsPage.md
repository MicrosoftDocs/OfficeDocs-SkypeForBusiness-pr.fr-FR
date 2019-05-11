---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype pour Business Server vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge. Pour ce faire, vous procédez comme suit :'
ms.openlocfilehash: f9e83c5b457524ba4222075666384228cf1d5adc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889065"
---
# <a name="add-edge-server-ip-options"></a>Ajouter des options IP de serveur Edge
 
Skype pour Business Server vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge. Pour ce faire, vous procédez comme suit :
  
- **Activer les IPv4 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface interne du pool Edge
    
- **Activer le protocole IPv6 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface interne du pool Edge
    
- **Activer les IPv4 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface externe du pool Edge
    
- **Activer le protocole IPv6 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface externe du pool Edge
    
Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour cela, en activant la case à cocher **l’adresse IP externe de ce pool Edge est traduit par NAT**.
  
Prise en charge NAT. Traduction d’adresses réseau (NAT) n’est pas pris en charge lorsque vous utilisez l’équilibrage de charge matériel, afin de n’activez ne pas l’option NAT si vous déployez un pool de serveurs Edge avec l’équilibrage de charge matérielle.
  

