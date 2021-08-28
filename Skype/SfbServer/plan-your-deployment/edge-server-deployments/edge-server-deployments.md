---
title: Planifier les déploiements de serveurs Edge dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Résumé : Planifiez votre environnement Skype Entreprise Server Edge. Cette rubrique présente les concepts Edge et vous permet de vous organiser avec nos rubriques plus détaillées.'
ms.openlocfilehash: 9acdb42e4ebc46fd6597ab047ee523b0ff309fb5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602459"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planifier les déploiements de serveurs Edge dans Skype Entreprise Server
 
**Résumé :** Planifiez votre environnement Skype Entreprise Server Edge. Cette rubrique présente les concepts Edge et vous permet de vous organiser avec nos rubriques plus détaillées.
  
Lorsque vous avez un environnement Skype Entreprise Server qui fonctionne correctement en interne, l’étape suivante consiste peut-être à introduire un serveur Edge ou un pool edge dans l’environnement. Ce rôle serait vital si vous souhaitez que les services fournis par Skype Entreprise Server soient utilisés par des personnes extérieures à votre réseau interne. Il peut s’agir des éléments suivants :
  
- Utilisateurs distants : employés qui sont hors site, de manière temporaire ou continue.
    
- Utilisateurs fédérés : employés de vos organisations partenaires.
    
- Utilisateurs mobiles.
    
- Clients potentiels, partenaires et même utilisateurs anonymes que vous souhaitez inviter à des réunions et des présentations.
    
L’accès des utilisateurs externes, qui est fourni par les serveurs Edge, permet tout cela. Vos utilisateurs internes pourront bénéficier des services suivants qui sont hébergés par votre Skype Entreprise Server déploiement :
  
- Messagerie instantanée et présence pour la communication : les utilisateurs externes autorisés peuvent participer à des conversations par messagerie instantanée et à des conférences. Ils peuvent obtenir des informations de présence pour d’autres utilisateurs (qui obtiennent également leurs informations de présence). Vous ne pourrez pas faire de conférences à plusieurs si vous utilisez un fournisseur de messagerie instantanée public, c’est-à-dire une communication pair à pair. Toutefois, les protocoles SIP et XMPP sont pris en charge.
    
- Conférence audio/vidéo (A/V) : les utilisateurs externes autorisés peuvent participer à Skype Entreprise Server conférences audio et vidéo.
    
- Conférence web : vos utilisateurs externes autorisés peuvent participer à Skype Entreprise conférences. Vous pouvez également activer la participation pour les utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes si vous le souhaitez. Les utilisateurs de messagerie instantanée publique ne peuvent pas participer à des conférences. Il existe également des options pour laisser ces utilisateurs participer au partage d’application et de bureau, et même agir en tant qu’organisateurs ou présentateurs de réunion.
    
L’accès aux appareils mobiles est pris en charge, Voix Entreprise. Vous pouvez inviter des utilisateurs externes à participer à ces réunions, même anonymes, si vous souhaitez leur accorder des autorisations.
  
Si cela ressemble à quelque chose dont votre organisation a besoin, la planification d’un environnement Edge sera très utile pour son déploiement. Pour plus d’informations, les rubriques ci-dessous sont répertoriées.

> [!NOTE]
> Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP. 
  
## <a name="planning-topics"></a>Rubriques de planification :

Les articles de planification sont les suivants :
  
- [Conditions requises pour le système du serveur Edge Skype Entreprise Server 2015](system-requirements.md)
    
- [Exigences environnementales du serveur Edge Skype Entreprise Server 2015](edge-environmental-requirements.md)
    
- [Scénarios de serveur Edge Skype Entreprise Server 2015](scenarios.md)
    

