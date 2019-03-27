---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge. Pour ce faire, vous procédez comme suit :'
ms.openlocfilehash: a78a1c31c31c0ebe9e271d2f00f2cb5c2e959270
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877663"
---
# <a name="add-edge-server-ip-options"></a>Ajouter des options IP de serveur Edge
 
Microsoft Lync Server 2013 vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur de périphérie et un pool de serveurs Edge. Pour ce faire, vous procédez comme suit :
  
- **Activer les IPv4 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface interne du pool Edge
    
- **Activer le protocole IPv6 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface interne du pool Edge
    
- **Activer les IPv4 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur Edge ou l’interface externe du pool Edge
    
- **Activer le protocole IPv6 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur Edge ou l’interface externe du pool Edge
    
Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour cela, en activant la case à cocher **l’adresse IP externe de ce pool Edge est traduit par NAT**.
  
Prise en charge NAT. Traduction d’adresses réseau (NAT) n’est pas pris en charge lorsque vous utilisez l’équilibrage de charge matériel, afin de n’activez ne pas l’option NAT si vous déployez un pool de serveurs Edge avec l’équilibrage de charge matérielle.
  

