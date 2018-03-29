---
title: Conception de la jonction SIP (Session Initiation Protocol) pour E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planification de vos topologies de trunking SIP pour un déploiement E9-1-1 qui utilise les fournisseurs de trunking SIP dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 588cd32d4c3c7f7aacc9a42d2a2ca8791d036dea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server-2015"></a>Conception de la jonction SIP (Session Initiation Protocol) pour E9-1-1 dans Skype Entreprise Server 2015
 
Planification de vos topologies de trunking SIP pour un déploiement E9-1-1 qui utilise les fournisseurs de trunking SIP dans Skype pour Business Server Voix Entreprise.
  
Skype pour Business Server utilise les trunks SIP pour se connecter à un appel d’urgence pour le fournisseur de service E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Toutefois, si la liaison WAN entre le site de l’appelant et le site qui héberge le SIP trunk de service d’urgence n’est pas disponible, puis un appel placé par un utilisateur sur le site déconnecté aurez besoin d’un enregistrement de l’utilisation de téléphone dans la stratégie de voix de l’utilisateur qui va acheminer l’appel vers la ECRC via la passerelle de réseau téléphonique public commuté. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.
  
Il existe deux façons d’implémenter un SIP trunk dans un Skype pour environnement Business Server :
  
- Utiliser les serveurs de médiation multirésident qui utilisent leurs interfaces de publiquement routé externe pour communiquer avec le fournisseur de jonction SIP.
    
- Utilisez un contrôleur de bordure de Session (SBC) sur site pour fournir un point de démarcation sécurisé entre les serveurs de médiation et la jonction SIP les services du fournisseur.
    
Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels parviennent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur SBCs certifiées, consultez [« Infrastructure qualifié pour Microsoft Lync »](https://go.microsoft.com/fwlink/p/?LinkId=248425) et [« téléphonie Infrastructure pour Skype pour Business »](https://technet.microsoft.com/en-us/office/dn947483).
  
Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie de serveur de médiation et d’appeler la configuration du routage. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?
  
Pour plus d’informations sur le déploiement d’un SIP trunk dans Skype pour Business Server, reportez-vous à la section [SIP trunking dans Skype pour Business Server 2015](sip-trunking.md). Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.
  
 **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**
  
> Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire. 
    
 **Votre déploiement E9-1-1 est conçu pour la tolérance aux sinistres ?**
  
> Puisqu’il s’agit d’une solution d’urgence, la résistance est importante. Déployez votre puits de serveurs de médiation et SIP principales et secondaires dans des emplacements à tolérance de reprise après sinistre. Il est conseillé de déployer le serveur de médiation principal le plus proche pour les utilisateurs qui prend en charge et basculement de gamme appelle via le serveur de médiation secondaire (situé dans un emplacement géographique différent). 
    
 **Devez-vous déployer une jonction SIP (Session Initiation Protocol) distincte pour chaque succursale ?**
  
> Skype pour Business Server fournit plusieurs stratégies pour gérer la résilience vocale dans les succursales, y compris : ayant des réseaux de données robuste, le déploiement d’un SIP trunk dans chaque succursale ou envoyant les appels à la passerelle locale pendant les pannes. Pour plus d’informations, reportez-vous à la section [SIP trunking dans Skype pour Business Server 2015](sip-trunking.md).
    
 **Le contrôle d’admission des appels est-il activé ?**
  
> Skype pour Business Server ne pas les appels d’urgence poignée tout différemment d’un appel normal. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle RTC locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.
    

