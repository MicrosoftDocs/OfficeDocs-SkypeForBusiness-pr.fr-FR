---
title: Plan de déploiement de serveur de transport Edge dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé : Planifiez votre Skype pour un environnement d’entreprise serveur Edge. Cette rubrique présente les concepts de périphérie et vous permet d’organiser avec notre rubriques plus détaillées.'
ms.openlocfilehash: f558a4a9623e54a38e134716afe9b95021f237dc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886121"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Plan de déploiement de serveur de transport Edge dans Skype pour Business Server
 
**Résumé :** Planifier votre Skype pour un environnement d’entreprise serveur Edge. Cette rubrique présente les concepts de périphérie et vous permet d’organiser avec notre rubriques plus détaillées.
  
Lorsque vous avez un Skype pour environnement Business Server qui fonctionne bien en interne, l’étape suivante vous est peut-être d’introduire un serveur Edge ou un pool de serveurs Edge à l’environnement. Ce rôle est essentiel si vous souhaitez que les services fournis par Skype pour Business Server devant être utilisé par les personnes qui sont trouvent en dehors de votre réseau interne. Il peuvent inclure :
  
- Utilisateurs distants : employés qui travaillent hors site, de manière temporaire ou permanente ;
    
- Fédérés : Les employés les partenaires.
    
- Utilisateurs d’appareils mobiles ;
    
- Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et à des présentations.
    
Accès des utilisateurs externes, c'est-à-dire que les serveurs Edge permettent autoriser tout ceci se produire. Les utilisateurs internes pourront bénéficient des services qui sont hébergés par votre Skype pour le déploiement de Business Server suivants :
  
- Messagerie instantanée et présence pour les communications : les utilisateurs externes autorisés peuvent participer à des conversations de messagerie instantanée et des conférences. Ils peuvent obtenir des informations de présence pour les autres utilisateurs (qui obtiennent également leurs informations de présence). Vous ne pourrez pas effectuer des conférences si vous utilisez un fournisseur de messagerie instantanée publique, qui est la communication d’égal à égal strictement. Il s’agit strictement de communications P2P, mais les protocoles SIP (Session Initiation Protocol) et XMPP sont tous deux pris en charge.
    
- Audio/vidéo (A / V) conférence : votre Skype pour les conférences audio et vidéo Business Server peuvent participer à des utilisateurs externes autorisés.
    
- Conférence Web : vos utilisateurs externes autorisés peuvent participer à votre Skype pour des conférences. Vous pouvez également activer la participation des utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes si vous le souhaitez. Les utilisateurs de messagerie instantanée publique ne peut pas participer à des conférences. Il existe également des options pour permettre à ces utilisateurs participer à des applications et le partage du bureau et même agir en tant que les organisateurs de réunion ou sur présentateurs.
    
Accès aux appareils mobiles est pris en charge, comme c’est Enterprise Voice. Vous pouvez inviter des utilisateurs externes à participer à ces réunions si vous le souhaitez, ou encore des utilisateurs anonymes, si vous êtes disposé à leur donner les autorisations nécessaires.
  
Si ce scénario peut convenir à votre organisation, la planification d’un environnement Edge facilitera considérablement son déploiement. Pour en savoir plus, consultez les rubriques ci-après.

> [!NOTE]
> XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Rubriques concernant la planification :

Les articles consacrés à la planification sont les suivants :
  
- [Configuration système requise pour le serveur Edge dans Skype Entreprise Server 2015](system-requirements.md)
    
- [Conditions préalables d’environnement pour le serveur Edge dans Skype Entreprise Server 2015](edge-environmental-requirements.md)
    
- [Scénarios de serveur Edge dans Skype Entreprise Server 2015](scenarios.md)
    

