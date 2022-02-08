---
title: Composants requis pour les Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Résumé des composants de Voix Entreprise dans Skype Entreprise Server.
ms.openlocfilehash: 2fbc5aa6a7ece34db0d0ae9360d4be7c8b6f2a8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390046"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Composants requis pour les Voix Entreprise dans Skype Entreprise Server
 
Résumé des composants de Voix Entreprise dans Skype Entreprise Server.
  
Pour déployer Voix Entreprise, les composants suivants sont requis dans votre topologie. 
  
- Un ou plusieurs serveurs de médiation, qui traduisent la signalisation et, dans certaines configurations, les médias entre votre infrastructure Skype Entreprise Server interne, votre infrastructure Voix Entreprise et une passerelle PSTN (réseau téléphonique commuté) ou une session SIP (Session Initiation Protocol). Les serveurs de médiation sont le composant le plus crucial de votre déploiement Voix Entreprise de médiation. Pour plus d’informations, [voir composant serveur de médiation dans Skype Entreprise Server](mediation-server.md).
    
    Les serveurs de médiation peuvent être cocalisé avec des serveurs frontaux ou installés en tant que serveurs autonomes.
    
- Composants de connectivité PSTN, qui peuvent inclure des passerelles SIP ou PSTN. Pour plus d’informations, [voir composants de connectivité PSTN dans Skype Entreprise Server](pstn-connectivity.md).
    
- Les serveurs Edge, qui permettent à vos utilisateurs d’utiliser Voix Entreprise fonctionnalités de sécurité lorsqu’ils se sont situés à l’extérieur du pare-feu de votre organisation. 
    
    Le service Edge d’accès fournit une signalisation SIP pour les appels provenant Skype Entreprise utilisateurs externes au pare-feu de votre organisation. Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu. Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.
    
    Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.
    
- En outre, certains composants Voix Entreprise s’exécutent sur des serveurs frontaux. Pour plus d’informations sur ces composants, voir [composants VoIP](front-end-server-voip.md) du serveur frontal pour Skype Entreprise Server
    

