---
title: Concevoir la trunk SIP pour E9-1-1 dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planification de vos topologies de trunking SIP pour un déploiement E9-1-1 qui utilise des fournisseurs de trunking SIP, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 8454b50d5d2f55a8df05e70cb2737eccce81a793
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759546"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Concevoir la trunk SIP pour E9-1-1 dans Skype Entreprise Server
 
Planification de vos topologies de trunking SIP pour un déploiement E9-1-1 qui utilise des fournisseurs de trunking SIP, Skype Entreprise Server Voix Entreprise.
  
Skype Entreprise Server utilise des trunks SIP pour connecter un appel d’urgence au fournisseur de services E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Toutefois, si la liaison de réseau wan entre le site de l’appelant et le site qui héberge la ligne SIP du service d’urgence n’est pas disponible, un appel passé par un utilisateur sur le site déconnecté aura besoin d’un enregistrement d’utilisation téléphonique spécial dans la stratégie de voix de l’utilisateur qui routera l’appel vers la ECRC via la passerelle PSTN locale. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.
  
Il existe deux façons d’implémenter une trunk SIP dans un environnement Skype Entreprise Server:
  
- Utilisez des serveurs de médiation multi-accueil qui utilisent leurs interfaces acheminées publiquement vers l’extérieur pour communiquer avec le fournisseur de la liaison SIP.
    
- Utilisez un contrôleur SBC (Session Border Controller) local pour fournir un point de délimitation sécurisé entre les serveurs de médiation et les services du fournisseur de services de la session SIP.
    
Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels arrivent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur les SCS certifiés, voir « Infrastructure qualifiée pour [Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) » et « Infrastructure téléphonique pour [Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md)». 
  
Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration du routage des appels. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?
  
Pour plus d’informations sur le déploiement d’une Skype Entreprise Server [SIP](sip-trunking.md)dans Skype Entreprise Server . Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.
  
 **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**
  
> Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire. 
    
 **Votre déploiement E9-1-1 est-il conçu pour la tolérance aux sinistres ?**
  
> Puisqu’il s’agit d’une solution d’urgence, la résilience est importante. Déployez vos serveurs de médiation principaux et secondaires et vos trunks SIP dans des emplacements à tolérance d’urgence. Il est bon de déployer votre serveur de médiation principal le plus proche des utilisateurs qu’il est en charge et d’router les appels deover via le serveur de médiation secondaire (situé dans un autre emplacement géographique). 
    
 **Devez-vous déployer une jonction SIP distincte pour chaque succursale ?**
  
> Skype Entreprise Server fournit plusieurs stratégies de gestion de la résistance vocale dans les succursales, notamment : avoir des réseaux de données résilients, déployer une branche SIP dans chaque succursale ou faire passer des appels vers la passerelle locale en cas de panne. Pour plus d’informations, [voir la trunking SIP dans Skype Entreprise Server](sip-trunking.md).
    
 **Le contrôle d’admission des appels (CAC) est-il activé ?**
  
> Skype Entreprise Server ne gère pas les appels d’urgence différemment d’un appel ordinaire. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle PSTN locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.
