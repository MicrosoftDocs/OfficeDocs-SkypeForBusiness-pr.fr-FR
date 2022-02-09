---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool edge. Pour ce faire, procédez comme suit :'
ms.openlocfilehash: b0a7483b7d9f8c19b045611ebcbc6c9b2d6e8237
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401248"
---
# <a name="add-edge-server-ip-options"></a>Ajouter des options IP de serveur Edge
 
Microsoft Lync Server 2013 vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool edge. Pour ce faire, procédez comme suit :
  
- **Activer IPv4 sur l’interface** interne : activez la case à cocher si vous souhaitez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool edge
    
- **Activer IPv6 sur l’interface** interne : activez la case à cocher si vous souhaitez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool edge
    
- **Activer IPv4 sur l’interface** externe : activez la case à cocher si vous souhaitez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool edge
    
- **Activer IPv6 sur l’interface** externe : activez la case à cocher si vous souhaitez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool edge
    
Vous pouvez également configurer le serveur Edge ou le pool edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.
  
Prise en charge NAT. La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle. Ne sélectionnez donc pas l’option NAT si vous déployez un pool de serveurs Edge avec équilibrage de la charge matérielle.
  

