---
title: Conception de la jonction SIP pour E9-1-1 dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planification de vos topologies de jonction SIP pour un déploiement E9-1-1 qui utilise les fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 25d961c00eb701dce6386ce2a901c1fbe5cf3cde
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893639"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Conception de la jonction SIP pour E9-1-1 dans Skype pour Business Server
 
Planification de vos topologies de jonction SIP pour un déploiement E9-1-1 qui utilise les fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
  
Skype pour Business Server utilise les jonctions SIP pour se connecter à un appel d’urgence pour le fournisseur de services E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Toutefois, si la liaison WAN entre les sites de l’appelant et le site qui héberge la jonction SIP de service d’urgence n’est pas disponible, puis un appel par un utilisateur au niveau du site déconnecté devra un enregistrement d’utilisation de téléphone dans la stratégie de voix de l’utilisateur qui achemine l’appel à la ECRC via la passerelle de réseau téléphonique commuté public. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.
  
Il existe deux façons d’implémenter une jonction SIP dans un Skype pour un environnement Business Server :
  
- Utiliser des serveurs de médiation multirésidents utilisant leurs interfaces routées publiquement vers l’extérieur pour communiquer avec le fournisseur de jonction SIP.
    
- Utiliser un contrôleur de bordure de Session (SBC) local pour fournir un point de démarcation sécurisé entre les serveurs de médiation et la jonction SIP services du fournisseur.
    
Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels parviennent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur certifié SBC, voir [« Infrastructure pour Microsoft Lync qualifiées »](https://go.microsoft.com/fwlink/p/?LinkId=248425) et [« téléphonie Infrastructure pour Skype pour Business »](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie de serveur de médiation et configuration du routage des appels. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?
  
Pour plus d’informations sur le déploiement d’une jonction SIP dans Skype pour Business Server, consultez la [jonction SIP dans Skype pour Business Server](sip-trunking.md). Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.
  
 **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**
  
> Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire. 
    
 **Votre déploiement E9-1-1 est conçu pour la tolérance de panne d’urgence ?**
  
> Puisqu’il s’agit d’une solution d’urgence, la résistance est importante. Déployez votre jonctions SIP et les serveurs de médiation principales et secondaires dans les emplacements de panne d’urgence. Il est judicieux de déployer votre serveur de médiation principal le plus proche pour les utilisateurs qui prend en charge et basculement de routage des appels via le serveur de médiation secondaire (situé dans un autre emplacement géographique). 
    
 **Devez-vous déployer une jonction SIP (Session Initiation Protocol) distincte pour chaque succursale ?**
  
> Skype pour Business Server fournit plusieurs stratégies de gestion de la résilience vocale dans les succursales, y compris : ayant des réseaux de données résistantes, le déploiement d’une jonction SIP à chaque branche ou diffuser les appels vers la passerelle locale pendant les pannes. Pour plus d’informations, voir la [jonction SIP dans Skype pour Business Server](sip-trunking.md).
    
 **Le contrôle d’admission des appels est-il activé ?**
  
> Skype pour Business Server ne prend pas les appels d’urgence poignée les différemment d’un appel ordinaire. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle RTC locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.
    

