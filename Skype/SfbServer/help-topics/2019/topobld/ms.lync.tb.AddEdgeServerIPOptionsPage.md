---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype Entreprise Server vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool edge. Pour ce faire, procédez comme suit :'
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801074"
---
# <a name="add-edge-server-ip-options"></a>Ajouter des options IP de serveur Edge
 
Skype Entreprise Server vous permet de configurer les adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool edge. Pour ce faire, procédez comme suit :
  
- **Activer IPv4 sur l’interface** interne : activez la case à cocher si vous souhaitez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool edge
    
- **Activer IPv6 sur l’interface** interne : activez la case à cocher si vous souhaitez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool edge
    
- **Activer IPv4 sur l’interface** externe : activez la case à cocher si vous souhaitez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool edge
    
- **Activer IPv6 sur l’interface** externe : activez la case à cocher si vous souhaitez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool edge
    
Vous pouvez également configurer le serveur Edge ou le pool edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.
  
Prise en charge NAT. La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle. Ne sélectionnez donc pas l’option NAT si vous déployez un pool de serveurs Edge avec équilibrage de la charge matérielle.
  

