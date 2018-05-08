---
title: Configuration des jonctions dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Découvrez comment configurer une jonction entre un serveur de médiation et des homologues pour Enterprise Voice dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4944cac2b06d837facf0cf014fb3a4fd32343305
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>Configuration des jonctions dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer une jonction entre un serveur de médiation et des homologues pour Enterprise Voice dans Skype pour Business Server 2015.
  
Dans le cadre du déploiement d’Enterprise Voice, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs des homologues suivantes pour fournir un réseau téléphonique commuté (RTC) pour les clients Enterprise Voice et les périphériques de votre organisation :
  
- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
    
- Passerelle RTC
    
- Autocommutateur privé (PBX)
    
Pour plus d’informations, voir [planifier la connectivité PSTN dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype pour la fonctionnalité Business Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont effectuées en définissant une jonction, qui est une association entre un pool de serveurs de médiation et une passerelle réseau téléphonique commuté, contrôleur de Session en périphérie (SBC) ou IP-PBX logique. Utilisez le Générateur de topologies pour associer les passerelles avec les serveurs de médiation (c'est-à-dire, jonctions).
  
- Pour affecter ou supprimer une jonction dans Skype pour Business Server, vous devez d’abord définir une jonction dans le Générateur de topologie. Une jonction se compose de l’association suivante : serveur de médiation complet nom de domaine (FQDN), le port d’écoute du serveur de médiation, la nom de domaine complet de la passerelle et le port d’écoute de passerelle.
    
- Pour configurer plusieurs jonctions, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela offre une résilience supplémentaire à l’infrastructure Enterprise Voice, qui est particulièrement utile dans les scénarios d’interoperational autocommutateur privé (PBX) exchange. 
    
Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer une jonction à un itinéraire, vous définissez un nom simple pour la jonction dans le Générateur de topologie. Ce nom simple est utilisé comme nom de jonction dans le Skype pour Business Server Control Panel, où les jonctions peuvent être associées à des itinéraires. Le nom de la jonction simple est utilisé en tant que le nom de la passerelle à partir de la Skype pour Business Server Management Shell. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L’administrateur doit sélectionner une jonction par défaut associée à un serveur de médiation. Dans le Générateur de commandes, cliquez sur le serveur de médiation associé, puis cliquez sur **Propriétés**. Spécifiez la passerelle par défaut pour le serveur de médiation. 
  

