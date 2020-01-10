---
title: Configuration de Trunks dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Découvrez comment configurer un Trunk entre un serveur de médiation et des homologues pour voix entreprise dans Skype entreprise Server.'
ms.openlocfilehash: 9bd285f1364d54940afd827858248656a6bb9f00
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001234"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configuration de Trunks dans Skype entreprise Server
 
**Résumé :** Apprenez à configurer une Trunk entre un serveur de médiation et des pairs pour l’entreprise voix dans Skype entreprise Server.
  
Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation :
  
- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
    
- Passerelle RTC
    
- Autocommutateur privé (PBX)
    
Pour plus d’informations, reportez-vous à la rubrique [planification de la connectivité PSTN dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
La fonctionnalité Skype entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP. Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).
  
- Pour attribuer ou supprimer un Trunk dans Skype entreprise Server, vous devez commencer par définir un Trunk dans le générateur de topologie. Un Trunk est composé de l’Association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.
    
- Pour configurer plusieurs Trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela fournit une résilience supplémentaire à l’infrastructure voix entreprise, qui est particulièrement utile dans les scénarios d’interopération de PBX (Private Branch Exchange). 
    
Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer un Trunk à un itinéraire, vous devez définir un nom simple pour le Trunk dans le générateur de topologie. Ce nom simple sert de nom de Trunk dans le panneau de configuration Skype entreprise Server, où les Trunks peuvent être associés à des itinéraires. Le nom simple de Trunk est utilisé comme nom de la passerelle de Skype entreprise Server Management Shell. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L’administrateur doit sélectionner une Trunk par défaut associée à un serveur de médiation. Dans le générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**. Spécifiez la passerelle par défaut du serveur de médiation. 
  

