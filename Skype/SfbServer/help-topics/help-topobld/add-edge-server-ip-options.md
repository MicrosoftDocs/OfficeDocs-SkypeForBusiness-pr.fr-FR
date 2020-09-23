---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool de serveurs Edge. Pour ce faire, procédez comme suit :'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219789"
---
# <a name="add-edge-server-ip-options"></a>Ajouter des options IP de serveur Edge
 
Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool de serveurs Edge. Pour ce faire, procédez comme suit :
  
- **Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
- **Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge
    
- **Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
- **Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge
    
Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.
  
Prise en charge de NAT. La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle, donc ne sélectionnez pas l’option NAT si vous déployez un pool de serveurs Edge avec équilibrage de la charge matérielle.
  

