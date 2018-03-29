---
title: Planification des déploiements de serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé : Planifier votre Skype pour environnement d’entreprise serveur 2015 serveur Edge. Cette rubrique présente les concepts de bord et vous permet d’organiser avec nos rubriques plus détaillées.'
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a>Planification des déploiements de serveur Edge dans Skype Entreprise Server 2015
 
**Résumé :** planifiez votre environnement Edge Skype Entreprise Server 2015. Cette rubrique présente les concepts se rapportant aux serveurs Edge et vous permet d’organiser votre environnement à l’aide de rubriques plus détaillées.
  
Lorsque vous avez un Skype pour environnement Business Server 2015 qui fonctionne bien en interne, l’étape suivante vous est peut-être d’introduire un serveur Edge ou un pool d’arête à l’environnement. Ce rôle est essentiel si vous souhaitez que les services fournis par Skype pour 2015 de serveur Business être utilisé par les personnes qui sont en dehors de votre réseau interne. Il peuvent inclure :
  
- Utilisateurs distants : employés qui travaillent hors site, de manière temporaire ou permanente ;
    
- Fédérés : Les employés des partenaires.
    
- Utilisateurs d’appareils mobiles ;
    
- Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et à des présentations.
    
L’accès des utilisateurs externes, qui est ce que fournissent les serveurs Edge, autoriser tout cela se passe. Vos utilisateurs internes pourront bénéficier les services suivants hébergés par votre Skype pour le déploiement de Business Server 2015 :
  
- Messagerie instantanée et présence pour les communications : les utilisateurs externes autorisés peuvent participer à des conversations de messagerie instantanée et des conférences. Ils peuvent obtenir des informations de présence pour les autres utilisateurs (qui obtiennent également leurs informations de présence). Il se peut que vous ne pourrez pas faire de conférences à plusieurs participants si vous utilisez un fournisseur de messagerie instantanée publique, ce qui est strictement peer-to-peer communication. Il s’agit strictement de communications P2P, mais les protocoles SIP (Session Initiation Protocol) et XMPP sont tous deux pris en charge.
    
- Audio/vidéo (A / V) conférence : utilisateurs externes autorisés peuvent participer à votre Skype pour les conférences audio et vidéo de Business Server 2015.
    
- Conférence Web : vos utilisateurs externes autorisés peuvent participer à votre Skype pour des conférences. Vous pouvez également activer la participation des utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes si vous le souhaitez. Les utilisateurs de messagerie instantanée publiques ne peut pas participer aux conférences. Il existe également des options pour permettre à ces utilisateurs participer au partage d’application et postes de travail et même agissent comme les organisateurs de la réunion ou présentateurs.
    
Accès aux périphériques mobiles est pris en charge, comme des Voix Entreprise. Vous pouvez inviter des utilisateurs externes à participer à ces réunions si vous le souhaitez, ou encore des utilisateurs anonymes, si vous êtes disposé à leur donner les autorisations nécessaires.
  
Si ce scénario peut convenir à votre organisation, la planification d’un environnement Edge facilitera considérablement son déploiement. Pour en savoir plus, consultez les rubriques ci-après.
  
## <a name="planning-topics"></a>Rubriques concernant la planification :

Les articles consacrés à la planification sont les suivants :
  
- [Edge Server requise dans Skype pour Business Server 2015](system-requirements.md)
    
- [Bord des exigences de l’environnement de serveur dans Skype pour Business Server 2015](edge-environmental-requirements.md)
    
- [Scénarios de serveurs Edge dans Skype pour Business Server 2015](scenarios.md)
    

