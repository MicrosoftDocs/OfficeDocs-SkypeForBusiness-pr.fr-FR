---
title: Ajouter des Options IP du serveur Edge
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur de transport Edge et le pool de bord. Pour ce faire, vous effectuez les opérations suivantes :'
ms.openlocfilehash: a6f4dd60355a4e241c70ec28c72fa86d91c66a9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-ip-options"></a>Ajouter des Options IP du serveur Edge
 
Microsoft Lync Server 2013 vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur de transport Edge et le pool de bord. Pour ce faire, vous effectuez les opérations suivantes :
  
- **Activer les IPv4 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur de transport Edge ou interface de bord pool interne
    
- **Activation d’IPv6 sur l’interface interne**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur de transport Edge ou interface de bord pool interne
    
- **Activer les IPv4 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv4 pour le serveur de transport Edge ou interface de bord pool externe
    
- **Activation d’IPv6 sur l’interface externe**: activez la case à cocher si vous souhaitez appliquer une adresse IPv6 pour le serveur de transport Edge ou interface de bord pool externe
    
Vous pouvez également configurer le serveur de transport Edge ou le pool de bord pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour cela, vous devez en activant la case à cocher **l’adresse IP externe de ce pool de bord est convertie par NAT**.
  
Prise en charge NAT. Traduction d’adresses réseau (NAT) n’est pas pris en charge lorsque vous utilisez l’équilibrage de charge matériel, et ne sélectionnez ne pas l’option NAT si vous déployez un pool de serveur de transport Edge avec l’équilibrage de charge matériel.
  

