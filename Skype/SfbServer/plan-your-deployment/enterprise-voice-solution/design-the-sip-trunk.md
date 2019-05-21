---
title: Concevoir le Trunk SIP pour E9-1-1 dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planification de vos topologies de trunking SIP pour un déploiement E9-1-1 qui utilise des fournisseurs de trunking SIP dans Skype entreprise Server Voice.
ms.openlocfilehash: 1d3b55fd6bb61fbf83f1a2294c96503b816f9c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276977"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Concevoir le Trunk SIP pour E9-1-1 dans Skype entreprise Server
 
Planification de vos topologies de trunking SIP pour un déploiement E9-1-1 qui utilise des fournisseurs de trunking SIP dans Skype entreprise Server Voice.
  
Skype entreprise Server utilise des lignes SIP pour connecter un appel d’urgence au fournisseur de services E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Toutefois, si la liaison WAN entre le site de l’appelant et le site qui héberge le service d’urgence SIP Trunk n’est pas disponible, un appel placé par un utilisateur sur le site déconnecté aura besoin d’un enregistrement d’utilisation du téléphone spécial dans la stratégie vocale de l’utilisateur, qui dirigera l’appel vers le ECRC par le biais de la passerelle RTC (réseau téléphonique commuté) locale. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.
  
Il existe deux façons d’implémenter une ligne SIP dans un environnement Skype entreprise Server:
  
- Utiliser des serveurs de médiation multi-résidents qui utilisent leurs interfaces routées vers l’extérieur pour communiquer avec le fournisseur de Trunks SIP.
    
- Utilisez un contrôleur de bordure de session (SBC) local pour fournir un point de délimitation sécurisé entre les serveurs de médiation et les services du fournisseur de Trunks SIP.
    
Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels parviennent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur la certification SBCs, voir [«infrastructure Qualified pour Microsoft Lync»](https://go.microsoft.com/fwlink/p/?LinkId=248425) et [«infrastructure de téléphonie pour Skype entreprise»](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration de l’acheminement des appels. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?
  
Pour plus d’informations sur le déploiement d’un Trunk SIP dans Skype entreprise Server, reportez-vous à la rubrique [SIP Trunking dans Skype entreprise Server](sip-trunking.md). Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.
  
 **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**
  
> Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire. 
    
 **Votre déploiement E9-1-1 est-il conçu pour la tolérance au désastre?**
  
> Puisqu’il s’agit d’une solution d’urgence, la résistance est importante. Déployez vos serveurs de médiation principaux et secondaires et les Trunks SIP dans les emplacements tolérants aux sinistres. Il peut s’avérer utile de déployer votre serveur de médiation principal le plus proche des utilisateurs qu’il prend en charge, et d’acheminer les appels de basculement par le biais du serveur de médiation secondaire (situé dans un autre emplacement géographique). 
    
 **Devez-vous déployer une jonction SIP (Session Initiation Protocol) distincte pour chaque succursale ?**
  
> Skype entreprise Server offre plusieurs stratégies de gestion de la résilience de la voix dans les bureaux de succursales, notamment: disposer de réseaux de données résilients, le déploiement d’une ligne SIP dans chaque succursale ou le transfert d’appels vers la passerelle locale lors des pannes. Pour plus d’informations, reportez-vous à la rubrique [SIP Trunking dans Skype entreprise Server](sip-trunking.md).
    
 **Le contrôle d’admission des appels est-il activé ?**
  
> Skype entreprise Server ne gère pas les appels d’urgence de la même manière que les appels ordinaires. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle RTC locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.
    

