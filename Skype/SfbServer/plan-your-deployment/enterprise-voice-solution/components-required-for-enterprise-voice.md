---
title: Composants requis pour Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Résumé des composants Voix Entreprise dans Skype Entreprise Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825824"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Composants requis pour Voix Entreprise dans Skype Entreprise Server
 
Résumé des composants Voix Entreprise dans Skype Entreprise Server.
  
Pour déployer Voix Entreprise, les composants suivants sont requis dans votre topologie. 
  
- Un ou plusieurs serveurs de médiation, qui traduisent la signalisation et, dans certaines configurations, les médias entre votre infrastructure skype entreprise interne, votre infrastructure Voix Entreprise et une passerelle de réseau téléphonique commuté (PSTN) ou une session SIP (Session Initiation Protocol). Les serveurs de médiation sont le composant le plus crucial de votre déploiement Voix Entreprise de médiation. Pour plus d’informations, [voir composant serveur de médiation dans Skype Entreprise Server.](mediation-server.md)
    
    Les serveurs de médiation peuvent être cocalisé avec des serveurs frontaux ou installés en tant que serveurs autonomes.
    
- Composants de connectivité PSTN, qui peuvent inclure des passerelles SIP ou PSTN. Pour plus d’informations, voir composants de [connectivité PSTN dans Skype Entreprise Server.](pstn-connectivity.md)
    
- Les serveurs Edge, qui permettent à vos utilisateurs d’utiliser Voix Entreprise fonctionnalités de sécurité lorsqu’ils sont en dehors du pare-feu de votre organisation. 
    
    Le service Edge d’accès fournit une signalisation SIP pour les appels provenant d’utilisateurs Skype Entreprise qui se sont produits à l’extérieur du pare-feu de votre organisation. Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu. Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.
    
    Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.
    
- En outre, certains composants Voix Entreprise s’exécutent sur des serveurs frontaux. Pour plus d’informations sur ces composants, voir [Composants VoIP](front-end-server-voip.md) du serveur frontal pour Skype Entreprise Server
    

