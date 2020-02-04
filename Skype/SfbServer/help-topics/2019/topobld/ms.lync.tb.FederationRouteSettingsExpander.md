---
title: Développeur des paramètres d’itinéraire de fédération
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Pour définir une affectation de routage de Fédération de site, vous devez d’abord disposer de la Fédération sur le serveur Edge ou le pool de serveurs Edge. Si la Fédération n’est pas activée sur le serveur Edge ou le pool, les paramètres d’attribution de l’itinéraire de Fédération pour le site ne seront pas disponibles à des fins de modification.
ms.openlocfilehash: a9679d5ddfe4652a79f58596940af7f450e4b470
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688560"
---
# <a name="federation-route-settings-expander"></a>Développeur des paramètres d’itinéraire de fédération
 
Pour définir une affectation de routage de Fédération de site, vous devez d’abord disposer de la Fédération sur le serveur Edge ou le pool de serveurs Edge. Si la Fédération n’est pas activée sur le serveur Edge ou le pool, les paramètres d’attribution de l’itinéraire de Fédération pour le site ne seront pas disponibles à des fins de modification.

Si le paramètre de Fédération sur le serveur Edge ou le pool a été configuré, vous pouvez configurer les options suivantes : 
  
- **Autoriser les affectations de routage de Fédération à tous les sites** Ce paramètre affecte tous les sites. Assurez-vous que le paramètre que vous configurez sur ce site est approprié pour tous les sites.
    
- **Activer la Fédération SIP** Sélectionnez cette option pour activer un itinéraire de Fédération SIP, puis sélectionnez un directeur ou un pool d’arêtes en tant qu’itinéraire de Fédération.
    
- **Activer la Fédération XMPP** Sélectionnez cette option pour activer un itinéraire de Fédération XMPP, puis sélectionnez un réalisateur ou un pool d’arêtes en tant qu’itinéraire de Fédération.
- 
  > [!NOTE]
  > Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    

