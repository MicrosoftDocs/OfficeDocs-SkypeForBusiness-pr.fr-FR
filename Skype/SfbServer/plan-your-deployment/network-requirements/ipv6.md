---
title: Planifier IPv6 dans Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Résumé : Implémentez IPv6 avant d’installer Skype pour Business Server.'
ms.openlocfilehash: b500a0b3f4b99b97b1fc3a89eda7c5736953d854
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888345"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planifier IPv6 dans Skype Entreprise
 
**Résumé :** Mettre en œuvre IPv6 avant d’installer Skype pour Business Server.
  
Skype pour Business Server prend en charge IP version 6 (IPv6) adresses, ainsi que la prise en charge continue d’IP version 4 (IPv4). 

Les adresses IPv4 sont des adresses 32 bits qui permettent aux ordinateurs de communiquer sur Internet. En raison du nombre croissant de périphériques dans le monde, les adresses IPv4 disponibles ont mené. Pour cette raison, de nombreux nouveaux périphériques passent à des adresses IPv6. Les adresses IPv6 ont le même rôle que les adresses IPv4 (avec des fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent 128 bits. Cela permet de nouvelles adresses, mais également un plus grand nombre d’adresses. 

Une adresse IPv4 classique ressemble à ceci : 192.0.2.235, tandis que d’une adresse IPv6 ressemble à ceci : 2001:0db8:85a3:0000:0000:8a2e:0370:7334. La modification de la mise en forme et les fonctionnalités pour les périphériques qui utilisent des adresses IPv6 requiert plusieurs considérations concernant le déploiement et la configuration de votre Skype pour l’installation de Business Server. 

Cette rubrique inclut les sections suivantes :
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Si vous avez déterminé que vous prévoyez d’utiliser des adresses IPv6, reportez-vous à l’article [types d’adresses IP configurer dans Skype pour les entreprises](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Présentation des types d’adresse IP
<a name="over"> </a>

Vous disposez de trois options lors de la configuration des adresses IP dans Skype pour Business Server. Vous pouvez configurer Skype pour Business Server prendre en charge uniquement IP version 4 (IPv4), seul IP version 6 (IPv6), ou une combinaison des deux (appelé une double pile). Chaque type de configuration implique certains problèmes à prendre en considération :
  
- **IPv4 uniquement** IPv6 a été créé, car le monde manque d’adresses IPv4. Au final, IPv6 sera entièrement pris en charge partout mais, pour l’instant, de nombreuses sociétés et périphériques avec lesquels votre entreprise peut avoir à communiquer ne prennent pas encore en charge IPv6, et ce pour encore quelque temps. Une configuration IPv4 uniquement permettra de vous assurer que votre Skype pour implémentation Business Server peut communiquer avec la plupart des périphériques existants.
    
- **IPv6 uniquement** Inversement, une implémentation du protocole IPv6 complète exclura la communication avec de nombreux périphériques existant.
    
- **Double pile** Double pile est un réseau où les adresses IPv4 et IPv6 sont activés. Cette configuration est pris en charge dans Skype pour Business Server car dans la plupart des cas, la transition entre intégral IPv4 et IPv6 complète prendra plusieurs années.
    
Les sections suivantes précisent la compatibilité ces trois configurations différentes Skype pour les fonctionnalités de Business Server.
  
> [!NOTE]
> La configuration client ou serveur avec IPv6 uniquement n’est prise en charge qu’à des fins de validation ou en laboratoire. La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production. 
  
### <a name="client-registration"></a>Enregistrement client
<a name="client"> </a>

|**Réseau de point de terminaison client**|**Réseau de serveur**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Double pile  <br/> |
|Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|Double pile  <br/> |IPv6  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Client P2P
<a name="peer"> </a>

Les communications P2P incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers. Lorsque les deux clients sont enregistrés, les combinaisons suivantes sont prises en charge.
  
|**Point de terminaison client 1**|**Point de terminaison client 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Double pile  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Téléconférence
<a name="conf"> </a>

La conférence comprend l’audio/vidéo, le partage d’application et la collaboration de données (applications telles que le tableau blanc et le partage de fichiers).
  
|**Réseau de point de terminaison client**|**Réseau de serveur**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Double pile  <br/> |
|Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|Double pile  <br/> |IPv6  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Serveur de médiation/RTC
<a name="med"> </a>

Skype pour Business Server ne prend en charge le contournement de média pour les appels de réseau public commuté si le trafic est via une interface IPv6. Si la déviation du trafic multimédia est requise, nous recommandons que la passerelle RTC soit configurée sur IPv4. 
  
|**Interface principale 1**|**Interface RTC (sur le serveur de médiation)**|**Paramètre de passerelle RTC**|
|:-----|:-----|:-----|
|IPv4  <br/> |Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |IPv6  <br/> |
   
1. L’interface principale est l’interface qui communique avec le Skype pour les composants de serveur d’entreprise.
  
### <a name="remote-user-peer-to-peer-communications"></a>Communications P2P d’utilisateur distant
<a name="remote"> </a>

Les communications P2P avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.
  
|**Réseau d’utilisateur distant**|**Serveur Edge (périmètre externe)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuration des pools frontal et Edge
<a name="FE_pool"> </a>

Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontaux et le pool de serveurs Edge interne.
  
**Matrice de pool frontal et de pool Edge (périmètre interne)**

||**Pool Edge : IPv4** <br/> |**Pool Edge : Double pile** <br/> |**Pool Edge : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool frontal : IPv4** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool frontal : Double pile** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool frontal : IPv6** <br/> |Non  <br/> |Non  <br/> |Oui\*  <br/> |
   
\*Utilisez cette combinaison uniquement dans un environnement de laboratoire.
  
Le tableau ci-dessous représente une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.
  
**Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)**

||**Pool Edge (périmètre externe) : IPv4** <br/> |**Pool Edge (périmètre externe) : Double pile** <br/> |**Pool Edge (périmètre externe) : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool Edge (périmètre interne) : IPv4** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool Edge (périmètre interne) : Double pile** <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|**Pool Edge (périmètre interne) : IPv6** <br/> |Non  <br/> |Non  <br/> |Oui\*  <br/> |
   
\*Utilisez cette combinaison uniquement dans un environnement de laboratoire.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Prise en charge Voix Entreprise pour IPv6 avancée
<a name="Ent_V"> </a>

Les déploiements qui incluent le service Contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1), ou la déviation du trafic multimédia doivent être configurés sur une implémentation IPv4 uniquement ou double pile. Les points de terminaison utilisant uniquement IPv6 ne peuvent utiliser aucune de ces fonctions.
  
> [!NOTE]
> Dans un déploiement en double pile, même si un Skype pour client Business Server se connecte à un Skype pour Business Server à l’aide du protocole IPv6, Skype pour Business Server permettra de son mieux pour mapper une adresse IPv4 appropriée pour prendre en charge E9-1-1. 
  
Service informations d’emplacement avec des adresses IPv6 n’est pas pris en charge.
  
La messagerie unifiée Exchange (UM) ne prend pas en charge IPv6. Pour cette fonctionnalité, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6. L’utilisation d’IPv6 peut entraîner des échecs lorsque les appels sont envoyés vers la messagerie vocale. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Autres Skype pour la prise en charge de la fonctionnalité Business Server pour IPv6
<a name="Ent_V"> </a>

Outre les fonctionnalités et composants mentionnés, Skype pour Business Server prend en charge IPv6 pour les fonctionnalités suivantes :
  
- **conversation permanente**
    
    Vous configurez IPv6 pour la conversation permanente à l’aide du Générateur de topologie. Pour plus d’informations sur la configuration de conversation permanente, consultez la documentation de déploiement des serveurs de conversation permanente.
    
- **Rapports de qualité de l’expérience (QoE) et d’enregistrement des détails des appels**
    
    Les rapports de suivi comportent l’adresse IP telle que stockée dans la base de données du serveur de suivi, qu’elle soit de type IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Configuration technique requise pour IPv6
<a name="tech"> </a>

Si vous envisagez de configurer Skype pour Business Server pour IPv6, n’oubliez pas les conditions suivantes :
  
- Pour utiliser des adresses IPv6 avec Skype pour Business Server, vous devez créer des enregistrements DNS pour les enregistrements qui doivent être identifiés et résolus à une adresse IPv6 de système de nom de domaine. Le DNS IPv6 utilise des enregistrements AAAA (quadruple A). Si vous utilisez IPv4 et IPv6 dans votre déploiement, il est préférable de configurer et maintenir des enregistrements d’hôte A pour IPv4 et des enregistrements d’hôte AAAA pour IPv6. Même lors de la transition complète de votre déploiement vers IPv6, vous pouvez également nécessiter des enregistrements d’hôte DNS IPv4 pour les utilisateurs externes utilisant encore IPv4.
    
    Vous pouvez déployer les enregistrements d’hôte DNS IPv6 avant de commencer à utiliser IPv6. Si le client ou le serveur n’utilise pas IPv6, l’enregistrement ne sera pas référencé. Des technologies de transition décideront de l’enregistrement à utiliser, en fonction des stratégies et de la configuration des technologies de transition.
    
- Chaque adresse IPv6 a une étendue. Les trois étendues que vous pouvez utiliser pour l’adressage IPv6 sont les adresses globales IPv6 (similaires aux adresses IPv4 publiques), IPv6 unique les adresses locales (comme les plages d’adresses IPv4 privées) et les adresses IPv6 lien-local (similaires à des adresses IP privées automatiques dans Windows Server pour IPv4). Tous les serveurs au sein d’un pool doivent avoir des adresses IPv6 avec la même étendue. 
    
> [!IMPORTANT]
> IPv6 est un sujet complexe et nécessite une planification minutieuse avec votre équipe de mise en réseau et votre fournisseur Internet pour s’assurer que les adresses que vous assignez au niveau du serveur Windows et à la Skype pour niveau Business Server fonctionnent comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Remarques sur la migration et la coexistence pour IPv6
<a name="migration"> </a>

IP version 6 (IPv6) n’est pas pris en charge dans Lync Server 2010 ou Office Communications Server. Pour les besoins de la phase pilote, vous pouvez tester Lync Server 2010 et Skype pour la coexistence Business Server double pile. Il est recommandé que tous les pools d’un site central donné sont mis à niveau vers Skype pour Business Server avant de pouvoir activer IPv6 (double pile réseau) pour tous les pools. Si vous devez configurer un pool uniquement pour IPv6, nous recommandons que vous configuriez un pool IPv6 uniquement dans votre environnement de laboratoire pour le test.
  
Les scénarios suivants sont pris en charge pendant la migration et la coexistence :
  
- Skype pour les pools Business Server, Lync Server 2013 et Lync Server 2010 en mode IPv4, coexistence avec Skype pour Business Server en mode double pile.
    
- Skype pour pool Business Server en mode IPv6 uniquement si le pool IPv6 uniquement est mis dans un silo.
    
## <a name="see-also"></a>Voir aussi
<a name="migration"> </a>

[Configuration des types d’adresse IP dans Skype Entreprise](ip-address-types.md)

[IP Version 6 Addressing Architecture](https://tools.ietf.org/html/rfc4291)
  
[Format d’adresse de monodiffusion globale IPv6](https://tools.ietf.org/html/rfc3587)
  
[Adresses de monodiffusion IPv6 locales uniques](https://tools.ietf.org/html/rfc4193)