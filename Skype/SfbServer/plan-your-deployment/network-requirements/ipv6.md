---
title: Planifier IPv6 dans Skype Entreprise
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Résumé : Implémentez IPv6 avant d’installer Skype Entreprise Server.'
ms.openlocfilehash: ff58da4a4064c91949446e9107d0f3ff07b720e1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593508"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planifier IPv6 dans Skype Entreprise
 
**Résumé :** Implémentez IPv6 avant d’installer Skype Entreprise Server.
  
Skype Entreprise Server inclut la prise en charge des adresses IP version 6 (IPv6), ainsi que la prise en charge continue des adresses IP version 4 (IPv4). 

Les adresses IPv4 sont des adresses 32 bits qui permettent à un ordinateur de communiquer sur Internet. En raison du nombre croissant d’appareils dans le monde, les adresses IPv4 disponibles sont à court. C’est pourquoi de nombreux nouveaux appareils utilisent des adresses IPv6. Les adresses IPv6 exécutent la même fonction que les adresses IPv4 (avec certaines fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement des adresses 32 bits, les adresses IPv6 utilisent des adresses 128 bits. Cela fournit non seulement un nouvel ensemble d’adresses, mais également un plus grand nombre d’adresses. 

Une adresse IPv4 classique ressemble à ceci : 192.0.2.235, alors qu’une adresse IPv6 ressemble à ceci : 2001:0db8:85a3:0000:0000:8a2e:0370:7334. La modification de la mise en forme et des fonctionnalités pour les appareils qui utilisent des adresses IPv6 nécessite plusieurs considérations en ce qui concerne le déploiement et la configuration dans Skype Entreprise Server’installation. 

Cette rubrique comprend les sections suivantes :
  
- [Vue d’ensemble des types d’adresses IP](ipv6.md#over)
    
- [Conditions techniques requises pour IPv6](ipv6.md#tech)
    
- [Considérations sur la migration et la coexistence pour IPv6](ipv6.md#migration)
    
Si vous déterminez que vous utiliserez des adresses IPv6, reportez-vous à l’article Configurer les [types d’adresses IP](ip-address-types.md) Skype Entreprise’article.
  
## <a name="overview-of-ip-address-types"></a>Vue d’ensemble des types d’adresses IP
<a name="over"> </a>

Vous avez trois options pour configurer des adresses IP dans Skype Entreprise Server. Vous pouvez configurer Skype Entreprise Server pour prendre en charge uniquement IP version 4 (IPv4), uniquement IP version 6 (IPv6) ou une combinaison des deux (appelée double pile). Il existe plusieurs problèmes à prendre en compte pour chaque type de configuration :
  
- **IPv4 uniquement** IPv6 a été créé car le monde n’a plus d’adresses IPv4. En fin de compte, IPv6 sera entièrement pris en charge dans le monde entier, mais pour l’instant, de nombreuses sociétés et appareils avec qui votre entreprise devra peut-être communiquer ne ront peut-être pas encore prendre en charge IPv6 et ne le seront peut-être pas pendant un certain temps. Une configuration IPv4 uniquement permet de s’assurer que votre implémentation Skype Entreprise Server peut communiquer avec la plupart des appareils existants.
    
- **IPv6 uniquement** À l’inverse, une implémentation IPv6 complète exclura la communication avec de nombreux appareils existants.
    
- **Double pile** La double pile est un réseau sur lequel les adresses IPv4 et IPv6 sont activées. Cette configuration est prise en charge Skype Entreprise Server car, dans la plupart des cas, la transition de l’IPv4 complet au IPv6 complet prendra plusieurs années.
    
Les sections suivantes décrivent la compatibilité entre ces trois configurations pour diverses Skype Entreprise Server de configuration.
  
> [!NOTE]
> La configuration du client ou du serveur avec IPv6 uniquement est prise en charge uniquement à des fins d’atelier ou de validation. La configuration IPv6 uniquement n’est pas prise en charge dans le déploiement de production. 
  
### <a name="client-registration"></a>Inscription du client
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
   
### <a name="peer-to-peer-client"></a>Client D’égal à égal
<a name="peer"> </a>

Les communications D’égal à égal incluent l’audio, l’audio/vidéo, le partage d’application et le transfert de fichiers. Une fois les deux clients enregistrés, les combinaisons suivantes sont pris en charge.
  
|**Point de terminaison du client 1**|**Point de terminaison du client 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Double pile  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Conférence
<a name="conf"> </a>

La conférence inclut l’audio/vidéo, le partage d’application et les applications de collaboration de données, telles que le tableau blanc et le partage de fichiers.
  
|**Réseau de point de terminaison client**|**Réseau de serveur**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Double pile  <br/> |
|Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|Double pile  <br/> |IPv6  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Serveur de médiation/PSTN
<a name="med"> </a>

Skype Entreprise Server ne prend pas en charge le contournement de média pour les appels de réseau téléphonique commuté (PSTN) si le trafic passe par une interface IPv6. Si la déviation du média est requise, nous vous recommandons de configurer la passerelle PSTN sur IPv4. 
  
|**Interface principale 1**|**Interface PSTN (sur le serveur de médiation)**|**Paramètre de passerelle PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |IPv6  <br/> |
   
1. L’interface principale est l’interface qui communique avec les Skype Entreprise Server composants.
  
### <a name="remote-user-peer-to-peer-communications"></a>Communications D’égal à égal d’utilisateur distant
<a name="remote"> </a>

Les communications D’égal à égal avec des utilisateurs distants incluent la messagerie instantanée, l’audio/vidéo, le partage d’application et le transfert de fichiers.
  
|**Réseau d’utilisateurs distants**|**Serveur Edge (serveur Edge externe)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Double pile  <br/> |IPv4  <br/> |
|Double pile  <br/> |Double pile  <br/> |
|IPv6  <br/> |Double pile  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configuration du pool frontal et du pool edge
<a name="FE_pool"> </a>

Le tableau suivant présente la matrice de prise en charge entre le pool de serveurs frontiers et le pool de serveurs Edge interne.
  
**Matrice de pool frontal et de pool edge (edge interne)**

||**Pool edge : IPv4** <br/> |**Pool edge : double pile** <br/> |**Pool edge : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool frontal : IPv4** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool frontal : double pile** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool frontal : IPv6** <br/> |Non  <br/> |Non  <br/> |Oui\*  <br/> |
   
\* Utilisez cette combinaison uniquement dans un environnement de laboratoire.
  
Le tableau suivant est une matrice des combinaisons d’interfaces Edge internes et externes pris en charge.
  
**Matrice de pool de périphérie (edge interne) et de pool edge (edge externe)**

||**Pool Edge (edge externe) : IPv4** <br/> |**Pool Edge (edge externe) : double pile** <br/> |**Pool Edge (edge externe) : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool Edge (edge interne) : IPv4** <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|**Pool Edge (edge interne) : double pile** <br/> |Non  <br/> |Oui  <br/> |Non  <br/> |
|**Pool Edge (edge interne) : IPv6** <br/> |Non  <br/> |Non  <br/> |Oui\*  <br/> |
   
\* Utilisez cette combinaison uniquement dans un environnement de laboratoire.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Prise en charge Voix Entreprise avancé pour IPv6
<a name="Ent_V"> </a>

Les déploiements qui incluent le contrôle d’admission des appels(CAC), Enhanced 9-1-1 (E9-1-1) ou le contournement de média doivent être configurés en tant qu’IPv4 uniquement ou en tant qu’implémentation à double pile. Les points de terminaison utilisant uniquement IPv6 ne peuvent pas utiliser l’une de ces fonctionnalités.
  
> [!NOTE]
> Dans un déploiement à double pile, même si un client Skype Entreprise Server se connecte à un Skype Entreprise Server à l’aide d’IPv6, Skype Entreprise Server s’adressera au mieux à une adresse IPv4 appropriée pour prendre en charge E9-1-1. 
  
Le service Informations d’emplacement avec adresses IPv6 n’est pas pris en charge.
  
Exchange La messagerie unifiée ne prend pas en charge IPv6. Pour Exchange la um, assurez-vous que la résolution DNS ne retourne pas d’adresse IPv6. L’utilisation d’IPv6 peut entraîner un échec lorsque des appels sont envoyés à la messagerie vocale. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Autres fonctionnalités Skype Entreprise Server prise en charge des fonctionnalités IPv6
<a name="Ent_V"> </a>

Outre les fonctionnalités et composants mentionnés précédemment, Skype Entreprise Server prend en charge IPv6 pour les fonctionnalités suivantes :
  
- **Conversation permanente**
    
    Vous configurez IPv6 pour la conversation permanente à l’aide du Générateur de topologie. Pour plus d’informations sur la configuration de la conversation permanente, voir la documentation de déploiement du serveur de conversation permanente.
    
- **Rapports de qualité de l’expérience (QoE) et d’enregistrement des détails des appels**
    
    Les rapports de surveillance incluent l’adresse IP telle qu’elle est stockée dans la base de données du serveur de surveillance, qu’elle soit de type IPv4 ou IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Conditions techniques requises pour IPv6
<a name="tech"> </a>

Si vous envisagez de configurer Skype Entreprise Server pour IPv6, gardez les exigences suivantes à l’esprit :
  
- Pour utiliser des adresses IPv6 avec Skype Entreprise Server, vous devez créer des enregistrements DNS (Domain Name System) pour les enregistrements qui doivent être découverts et résolus en adresse IPv6. Le DNS IPv6 utilise des enregistrements AAAA (quadruple A). Si vous utilisez IPv4 et IPv6 dans votre déploiement, il est préférable de configurer et maintenir des enregistrements d’hôte A pour IPv4 et des enregistrements d’hôte AAAA pour IPv6. Même lors de la transition complète de votre déploiement vers IPv6, vous pouvez également nécessiter des enregistrements d’hôte DNS IPv4 pour les utilisateurs externes utilisant encore IPv4.
    
    Vous pouvez déployer les enregistrements d’hôte DNS IPv6 avant de commencer à utiliser IPv6. Si le client ou le serveur n’utilise pas IPv6, l’enregistrement ne sera pas référencé. Des technologies de transition décideront de l’enregistrement à utiliser, en fonction de la configuration des technologies de transition et des stratégies.
    
- Chaque adresse IPv6 a une étendue. Les trois étendues que vous pouvez utiliser pour l’adressaînage IPv6 sont les adresses globales IPv6 (semblables aux adresses IPv4 publiques), les adresses locales uniques IPv6 (semblables aux plages d’adresses IPv4 privées) et les adresses locales de liaison IPv6 (semblables aux adresses IP privées automatiques dans Windows Server pour IPv4). Tous les serveurs au sein d’un pool doivent avoir des adresses IPv6 avec la même étendue. 
    
> [!IMPORTANT]
> IPv6 est un sujet complexe qui nécessite une planification minutieuse avec votre équipe réseau et votre fournisseur Internet pour vous assurer que les adresses que vous affectez au niveau du serveur Windows et au niveau du Skype Entreprise Server fonctionnent comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considérations sur la migration et la coexistence pour IPv6
<a name="migration"> </a>

IP version 6 (IPv6) n’est pas pris en charge sur Lync Server 2010 ou Office Communications Server. À des fins de pilotage, vous pouvez tester Lync Server 2010 et Skype Entreprise Server coexistence à double pile. Nous vous recommandons de mettre à niveau tous les pools d’un site central donné vers Skype Entreprise Server avant d’activer IPv6 (réseau à double pile) pour l’un des pools. Si vous devez configurer un pool uniquement pour IPv6, nous recommandons que vous configuriez un pool IPv6 uniquement dans votre environnement de laboratoire pour le test.
  
Les scénarios suivants sont pris en charge pendant la migration et la coexistence :
  
- Skype Entreprise Server pools, Lync Server 2013 et Lync Server 2010 en mode IPv4, coexistant avec Skype Entreprise Server en mode double pile.
    
- Skype Entreprise Server pool en mode IPv6 uniquement, si le pool IPv6 uniquement est cloisoné.
    
## <a name="see-also"></a>Voir aussi
<a name="migration"> </a>

[Configurer les types d’adresses IP dans Skype Entreprise](ip-address-types.md)

[Architecture d’adressare IP version 6](https://tools.ietf.org/html/rfc4291)
  
[Format d’adresse IPv6 unicast global](https://tools.ietf.org/html/rfc3587)
  
[Adresses IPv6 unicast locales uniques](https://tools.ietf.org/html/rfc4193)
