---
title: Planifier le déploiement de serveurs de périphérie dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé : planifiez votre environnement Edge Skype entreprise Server. Cette rubrique présente les concepts d’arête et vous permet de vous organiser grâce à de nouvelles rubriques détaillées.'
ms.openlocfilehash: f19f00aab393ed94735f47f2e66ab0a2869d2d7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803364"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planifier le déploiement de serveurs de périphérie dans Skype entreprise Server
 
**Résumé :** Planifiez votre environnement Edge Skype entreprise Server. Cette rubrique présente les concepts d’arête et vous permet de vous organiser grâce à de nouvelles rubriques détaillées.
  
Lorsque vous disposez d’un environnement Skype entreprise Server qui fonctionne bien en interne, l’étape suivante consiste à introduire un serveur Edge ou un pool Edge pour l’environnement. Ce rôle serait vital si vous souhaitez que les services fournis par Skype entreprise Server soient utilisés par des personnes extérieures à votre réseau interne. Les éléments suivants peuvent éventuellement être :
  
- Utilisateurs distants : employés qui travaillent hors site, de manière temporaire ou permanente ;
    
- Utilisateurs fédérés : employés de votre organisation partenaire.
    
- Utilisateurs d’appareils mobiles ;
    
- Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et à des présentations.
    
L’accès des utilisateurs externes, qui est fourni par les serveurs de périphérie, permettent à tous ces opérations de se produire. Vos utilisateurs internes pourront profiter des services suivants hébergés par votre déploiement de Skype entreprise Server :
  
- Messagerie instantanée et présence pour les communications : les utilisateurs externes autorisés peuvent participer à des conversations de messagerie instantanée et des conférences. Ils peuvent obtenir des informations de présence pour les autres utilisateurs (qui obtiennent également leurs informations de présence). Vous ne serez pas en mesure d’effectuer des conférences multipostes si vous utilisez un fournisseur de messagerie instantanée publique, c’est strictement la communication P2P. Il s’agit strictement de communications P2P, mais les protocoles SIP (Session Initiation Protocol) et XMPP sont tous deux pris en charge.
    
- Conférences audio/vidéo (A/V) : les utilisateurs externes autorisés peuvent participer à vos conférences audio et vidéo Skype entreprise Server.
    
- Conférences Web : vos utilisateurs externes autorisés peuvent participer à vos conférences Skype entreprise. Si vous le souhaitez, vous pouvez également activer la participation à des utilisateurs distants, des utilisateurs fédérés et des utilisateurs anonymes. Les utilisateurs de messagerie instantanée publique ne peuvent pas participer à des conférences. Il existe également des options permettant aux utilisateurs de participer à des applications et au partage du bureau, et même de fonctionner en tant qu’organisateurs ou présentateurs de la réunion.
    
L’accès aux appareils mobiles est pris en charge, comme c’est le cas pour Enterprise Voice. Vous pouvez inviter des utilisateurs externes à participer à ces réunions si vous le souhaitez, ou encore des utilisateurs anonymes, si vous êtes disposé à leur donner les autorisations nécessaires.
  
Si ce scénario peut convenir à votre organisation, la planification d’un environnement Edge facilitera considérablement son déploiement. Pour en savoir plus, consultez les rubriques ci-après.

> [!NOTE]
> Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Rubriques concernant la planification :

Les articles consacrés à la planification sont les suivants :
  
- [Configuration système requise pour le serveur Edge dans Skype Entreprise Server 2015](system-requirements.md)
    
- [Conditions préalables d’environnement pour le serveur Edge dans Skype Entreprise Server 2015](edge-environmental-requirements.md)
    
- [Scénarios de serveur Edge dans Skype Entreprise Server 2015](scenarios.md)
    

