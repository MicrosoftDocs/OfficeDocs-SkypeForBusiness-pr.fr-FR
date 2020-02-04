---
title: Ajouter des options IP de serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype entreprise Server vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool Edge. Pour cela, procédez comme suit :'
ms.openlocfilehash: 8352826fff371e4d59a4cf915d034465ac1aee7f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703049"
---
# <a name="add-edge-server-ip-options"></a>Ajouter des options IP de serveur Edge
 
Skype entreprise Server vous permet de configurer des adresses IPv4 et IPv6 pour chaque interface pour le serveur Edge et le pool Edge. Pour cela, procédez comme suit :
  
- **Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques
    
- **Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques
    
- **Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques
    
- **Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques
    
Vous pouvez également configurer le serveur de périphérie ou le pool Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **l’adresse IP externe de ce pool Edge est traduite par tar**.
  
Prise en charge de tar. La traduction d’adresses réseau (NAT) n’est pas prise en charge dans le cadre de l’utilisation de l’équilibrage de charge matérielle, alors ne sélectionnez pas l’option NAT si vous déployez un pool de serveurs de frontière avec l’équilibrage de charge matérielle.
  

