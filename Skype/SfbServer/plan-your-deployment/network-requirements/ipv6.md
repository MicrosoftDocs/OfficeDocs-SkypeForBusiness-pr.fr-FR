---
title: Planifier IPv6 dans Skype Entreprise
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Résumé: mettez en œuvre le protocole IPv6 avant d’installer Skype entreprise Server.'
ms.openlocfilehash: e4af5403ce416332ec7c75ca26522038fd9c42df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297042"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planifier IPv6 dans Skype Entreprise
 
**Résumé:** Mettre en œuvre le protocole IPv6 avant d’installer Skype entreprise Server.
  
Skype entreprise Server prend en charge les adresses IP version 6 (IPv6), ainsi que la prise en charge des adresses IP version 4 (IPv4). 

Les adresses IPv4 sont des adresses 32 bits qui permettent aux ordinateurs de communiquer sur Internet. En raison de l’augmentation du nombre d’appareils dans le monde entier, les adresses IPv4 disponibles sont épuisées. C’est la raison pour laquelle de nombreux nouveaux appareils sont déplacés vers l’adresse IPv6. Les adresses IPv6 ont le même rôle que les adresses IPv4 (avec des fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent 128 bits. Cela permet de nouvelles adresses, mais également un plus grand nombre d’adresses. 

Une adresse IPv4 classique ressemble à ceci: 192.0.2.235, alors qu’une adresse IPv6 ressemble à ceci: 2001:0DB8:85a3:0000:0000:8a2e: 0370:7334. La modification de la mise en forme et des fonctionnalités pour les appareils qui utilisent des adresses IPv6 nécessite plusieurs considérations de déploiement et de configuration dans votre installation de Skype entreprise Server. 

Cette rubrique inclut les sections suivantes :
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Si vous décidez d’utiliser des adresses IPv6, reportez-vous à l’article [configurer les types d’adresses IP dans Skype entreprise](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Présentation des types d’adresse IP
<a name="over"> </a>

Trois options s’offrent à vous lorsque vous configurez les adresses IP dans Skype entreprise Server. Vous pouvez configurer Skype entreprise Server de sorte qu’il prenne uniquement en charge les protocoles IP version 4 (IPv4), uniquement le protocole IP version 6 (IPv6) ou une combinaison des deux (appelé pile double). Chaque type de configuration implique certains problèmes à prendre en considération :
  
- **IPv4 uniquement** Le protocole IPv6 a été créé, car le monde ne dispose pas d’adresses IPv4. Au final, IPv6 sera entièrement pris en charge partout mais, pour l’instant, de nombreuses sociétés et périphériques avec lesquels votre entreprise peut avoir à communiquer ne prennent pas encore en charge IPv6, et ce pour encore quelque temps. Une configuration IPv4 uniquement vous permet de vous assurer que votre implémentation de Skype entreprise Server peut communiquer avec la plupart des appareils existants.
    
- **IPv6 uniquement** À l’inverse, une implémentation IPv6 complète exclut la communication entre de nombreux appareils existants.
    
- **Pile double** La double pile est un réseau sur lequel les adresses IPv4 et IPv6 sont activées. Cette configuration est prise en charge dans Skype entreprise Server, car dans la plupart des cas, la transition de l’intégralité du protocole IPv4 vers l’intégralité du protocole IPv6 nécessite plusieurs années.
    
Les sections suivantes décrivent la compatibilité entre ces trois configurations pour différentes fonctionnalités de Skype entreprise Server.
  
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

Skype entreprise Server ne prend pas en charge le contournement du contenu multimédia pour les appels de réseau téléphonique commuté (PSTN) si le trafic provient d’une interface IPv6. Si la déviation du trafic multimédia est requise, nous recommandons que la passerelle RTC soit configurée sur IPv4. 
  
|**Interface principale 1**|**Interface RTC (sur le serveur de médiation)**|**Paramètre de passerelle RTC**|
|:-----|:-----|:-----|
|IPv4  <br/> |Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |IPv6  <br/> |
   
1. L’interface principale est l’interface qui communique avec les composants du serveur Skype entreprise.
  
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

Le tableau suivant montre la matrice de prise en charge entre le pool de serveurs frontal et le pool de serveurs Edge interne.
  
**Matrice de pool frontal et de pool Edge (périmètre interne)**

||**Pool Edge : IPv4** <br/> |**Pool Edge : Double pile** <br/> |**Pool Edge : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool frontal : IPv4** <br/> |Oui   <br/> |Oui  <br/> |Non  <br/> |
|**Pool frontal : Double pile** <br/> |Oui   <br/> |Oui  <br/> |Non  <br/> |
|**Pool frontal : IPv6** <br/> |Non  <br/> |Non  <br/> |Oui\*  <br/> |
   
\*Utilisez cette combinaison uniquement dans un environnement Lab.
  
Le tableau ci-dessous représente une matrice des combinaisons d’interfaces Edge internes et externes prises en charge.
  
**Matrice de pool Edge (périmètre interne) et de pool Edge (périmètre externe)**

||**Pool Edge (périmètre externe) : IPv4** <br/> |**Pool Edge (périmètre externe) : Double pile** <br/> |**Pool Edge (périmètre externe) : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool Edge (périmètre interne) : IPv4** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool Edge (périmètre interne) : Double pile** <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|**Pool Edge (périmètre interne) : IPv6** <br/> |Non  <br/> |Non  <br/> |Oui\*  <br/> |
   
\*Utilisez cette combinaison uniquement dans un environnement Lab.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Prise en charge Voix Entreprise pour IPv6 avancée
<a name="Ent_V"> </a>

Les déploiements qui incluent le service Contrôle d’admission des appels (CAC), Enhanced 9-1-1 (E9-1-1), ou la déviation du trafic multimédia doivent être configurés sur une implémentation IPv4 uniquement ou double pile. Les points de terminaison utilisant uniquement IPv6 ne peuvent utiliser aucune de ces fonctions.
  
> [!NOTE]
> Dans le cas d’un déploiement double-empilé, même si un client Skype entreprise Server se connecte à un serveur Skype entreprise à l’aide du protocole IPv6, Skype entreprise Server vous permet de mapper une adresse IPv4 appropriée pour prendre en charge E9-1-1. 
  
Le service d’information d’emplacement avec les adresses IPv6 n’est pas pris en charge.
  
La messagerie unifiée Exchange (UM) ne prend pas en charge IPv6. Pour cette fonctionnalité, assurez-vous que la résolution DNS ne renvoie pas une adresse IPv6. L’utilisation d’IPv6 peut entraîner des échecs lorsque les appels sont envoyés vers la messagerie vocale. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Autres fonctionnalités de Skype entreprise Server prises en charge pour IPv6
<a name="Ent_V"> </a>

Outre les fonctionnalités et composants mentionnés précédemment, Skype entreprise Server prend en charge le protocole IPv6 pour les fonctionnalités suivantes:
  
- **Conversation permanente**
    
    Vous pouvez configurer le protocole IPv6 pour une conversation permanente à l’aide du générateur de topologie. Pour plus d’informations sur la configuration d’une conversation permanente, voir la documentation déploiement d’un serveur de chat permanent.
    
- **Rapports de qualité de l’expérience (QoE) et d’enregistrement des détails des appels**
    
    Les rapports de suivi comportent l’adresse IP telle que stockée dans la base de données du serveur de suivi, qu’elle soit de type IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Configuration technique requise pour IPv6
<a name="tech"> </a>

Si vous envisagez de configurer Skype entreprise Server pour IPv6, gardez les éléments suivants à l’esprit:
  
- Pour utiliser des adresses IPv6 avec Skype entreprise Server, vous devez créer des enregistrements DNS (Domain Name System) pour les enregistrements qui doivent être identifiés et résolus à une adresse IPv6. Le DNS IPv6 utilise des enregistrements AAAA (quadruple A). Si vous utilisez IPv4 et IPv6 dans votre déploiement, il est préférable de configurer et maintenir des enregistrements d’hôte A pour IPv4 et des enregistrements d’hôte AAAA pour IPv6. Même lors de la transition complète de votre déploiement vers IPv6, vous pouvez également nécessiter des enregistrements d’hôte DNS IPv4 pour les utilisateurs externes utilisant encore IPv4.
    
    Vous pouvez déployer les enregistrements d’hôte DNS IPv6 avant de commencer à utiliser IPv6. Si le client ou le serveur n’utilise pas IPv6, l’enregistrement ne sera pas référencé. Des technologies de transition décideront de l’enregistrement à utiliser, en fonction des stratégies et de la configuration des technologies de transition.
    
- Chaque adresse IPv6 a une étendue. Les trois portes que vous pouvez utiliser pour l’adressage IPv6 sont les adresses globales IPv6 (similaires aux adresses IPv4 publiques), les adresses locales uniques IPv6 (similaires aux plages d’adresses IPv4 privées) et les adresses locales de liaison privée (similaires aux adresses IP privées automatiques dans Windows Server pour IPv4). Tous les serveurs au sein d’un pool doivent avoir des adresses IPv6 avec la même étendue. 
    
> [!IMPORTANT]
> Le protocole IPv6 est un sujet complexe et nécessite une planification soigneuse de votre équipe réseau et de votre fournisseur d’accès Internet pour garantir que les adresses que vous attribuez au niveau Windows Server et au niveau Skype entreprise Server fonctionneront comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Remarques sur la migration et la coexistence pour IPv6
<a name="migration"> </a>

Le protocole IP version 6 (IPv6) n’est pas pris en charge sur Lync Server 2010 ou Office Communications Server. Dans le cadre de la phase de test, vous pouvez tester la coexistence de Lync Server 2010 et de Skype entreprise Server en double-pile. Nous vous recommandons d’effectuer la mise à niveau de tous les pools pour un site central donné vers Skype entreprise Server avant d’activer le protocole IPv6 (réseau à double pile) pour tous les pools. Si vous devez configurer un pool uniquement pour IPv6, nous recommandons que vous configuriez un pool IPv6 uniquement dans votre environnement de laboratoire pour le test.
  
Les scénarios suivants sont pris en charge pendant la migration et la coexistence :
  
- Skype entreprise Server, Lync Server 2013 et Lync Server 2010 pools en mode IPv4, coexistant avec Skype entreprise Server en mode double pile.
    
- Pool Skype entreprise Server en mode IPv6 uniquement, si le pool IPv6 uniquement est silo.
    
## <a name="see-also"></a>Voir aussi
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[Architecture d’adresse IP version 6](https://tools.ietf.org/html/rfc4291)
  
[Format d’adresse monodiffusion global IPv6](https://tools.ietf.org/html/rfc3587)
  
[Adresses monodiffusion IPv6 locales uniques](https://tools.ietf.org/html/rfc4193)
