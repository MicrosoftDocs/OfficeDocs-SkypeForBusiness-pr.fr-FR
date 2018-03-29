---
title: Composants requis pour Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un résumé des composants de Voix Entreprise dans Skype pour Business Server.
ms.openlocfilehash: 2c5df4c0d580d767693717cf48585ceb0d4c7365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a>Composants requis pour Voix Entreprise dans Skype Entreprise Server 2015
 
Un résumé des composants de Voix Entreprise dans Skype pour Business Server.
  
Pour déployer la Voix Entreprise, les composants suivants sont requis dans votre topologie. 
  
- Un ou plusieurs serveurs de médiation, traduire de signalisation et, dans certaines configurations, les médias entre votre Skype interne pour le serveur d’entreprise, infrastructure de Voix Entreprise et d’une passerelle de réseau téléphonique public commuté ou d’un protocole d’Initiation de Session Jonction de le (SIP). Les serveurs de médiation sont les plus indispensables dans votre déploiement de Voix Entreprise. Pour plus d’informations, reportez-vous à la section [composant de serveur de médiation dans Skype pour Business Server 2015](mediation-server.md).
    
    Serveurs de médiation peuvent être colocalisés avec les serveurs frontaux ou installés en tant que serveurs autonomes.
    
- Des composants de connectivité PSTN, pouvant inclure des jonctions SIP ou des passerelles PSTN. Pour plus d’informations, reportez-vous à la section [composants de connectivité RTPC dans Skype pour Business Server 2015](pstn-connectivity.md).
    
- Serveurs Edge, qui permet d’utiliser des fonctionnalités de Voix Entreprise par vos utilisateurs lorsqu’ils sont en dehors du pare-feu de votre organisation. 
    
    Le service Edge d’accès fournit la signalisation SIP pour les appels Skype pour les utilisateurs professionnels qui sont en dehors du pare-feu de votre organisation. Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu. Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.
    
    Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.
    
- En outre, certains composants de Voix Entreprise exécutent sur les serveurs frontaux. Pour plus d’informations sur ces composants, consultez [composants VoIP de serveur avant fin pour Skype pour Business Server 2015](front-end-server-voip.md)
    

