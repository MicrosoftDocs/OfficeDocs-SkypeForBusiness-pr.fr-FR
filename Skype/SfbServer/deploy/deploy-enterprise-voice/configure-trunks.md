---
title: Configuration des jonctions dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Apprenez à configurer un tronc d’un serveur de médiation et d’homologues de Voix Entreprise dans Skype pour Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>Configuration des jonctions dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer un tronc d’un serveur de médiation et d’homologues de Voix Entreprise dans Skype pour Business Server 2015.
  
Dans le cadre du déploiement de Voix Entreprise, vous pouvez configurer un tronc d’un serveur de médiation et un ou plusieurs des homologues suivants pour fournir un réseau téléphonique public commuté (RTPC) pour les clients de Voix Entreprise et périphériques de votre organisation :
  
- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
    
- Passerelle RTC
    
- Autocommutateur privé (PBX)
    
Pour plus de détails, reportez-vous à la section [planifier la connectivité RTPC dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype pour les fonctionnalités de Business Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont effectuées en définissant un tronc, qui est une association entre un pool de serveur de médiation et une public commuté (RTPC) passerelle, contrôleur de Session en périphérie (SBC) ou IP-PBX de logique. Utilisez le Générateur de topologie pour associer des passerelles avec les serveurs de médiation (autrement dit, les trunks).
  
- Pour affecter ou supprimer une ligne dans Skype pour Business Server, vous devez d’abord définir un tronc dans le Générateur de topologies. Un tronc se compose de l’association suivante : serveur de médiation qualifié le nom de domaine (FQDN), le port d’écoute de serveur de médiation, la nom de domaine complet de la passerelle et le port d’écoute de passerelle.
    
- Pour configurer plusieurs troncs, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela fournit des capacités supplémentaires de résistance à l’infrastructure de Voix Entreprise, ce qui est particulièrement utile dans les scénarios d’interoperational private branch exchange (PBX). 
    
Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer un tronc d’un itinéraire, vous définissez un nom simple pour le tronc dans le Générateur de topologies. Ce nom simple est utilisé comme nom de tronc dans le Skype pour panneau de commande de serveur Business, où les puits peuvent être associés à des itinéraires. Le nom de jonction simple est utilisé comme nom de passerelle de la Skype pour Business Server Management Shell. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L’administrateur doit sélectionner un tronc par défaut associé à un serveur de médiation. Dans le Générateur de topologie, sélectionnez le serveur de médiation associé et puis cliquez sur **Propriétés**. Spécifiez la passerelle par défaut pour le serveur de médiation. 
  

