---
title: Expanseur des paramètres d’itinéraire de fédération
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Pour configurer l’affectation d’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur le serveur ou pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819464"
---
# <a name="federation-route-settings-expander"></a>Expandeur des paramètres d’itinéraire de fédération
 
Pour configurer l’affectation d’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur le serveur ou pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.

Si le paramètre de fédération du serveur Edge ou pool de serveurs Edge a été configuré, vous pouvez configurer les options suivantes : 
  
- **Autoriser les affectations d’itinéraires de fédération à tous les sites** Ce paramètre affectera tous les sites. Assurez-vous que le paramètre que vous configurez pour ce site s’adapte à tous les sites.
    
- **Activer la fédération SIP** Sélectionnez cette option pour activer un itinéraire de fédération SIP, puis sélectionnez un directeur ou un pool edge comme itinéraire de fédération.
    
- **Activer la fédération XMPP** Sélectionnez cette option pour activer un itinéraire de fédération XMPP, puis sélectionnez un directeur ou un pool edge comme itinéraire de fédération.
- 
  > [!NOTE]
  > Les passerelles et proxys XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.
    

