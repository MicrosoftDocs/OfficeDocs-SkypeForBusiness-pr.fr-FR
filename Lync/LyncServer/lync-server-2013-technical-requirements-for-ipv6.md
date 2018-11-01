---
title: Configuration technique requise pour IPv6 dans Lync Server 2013
TOCTitle: Configuration technique requise pour IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205278(v=OCS.15)
ms:contentKeyID: 49298830
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour IPv6 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous souhaitez configurer Lync Server 2013 pour IPv6, vous devez garder les conditions suivantes à l’esprit :

  - Pour utiliser les adresses IPv6 avec Lync Server, vous devez créer des enregistrements DNS (Domain Name System) pour les enregistrements qui doivent être découverts et résolus vers une adresse IPv6. Le DNS IPv6 utilise des enregistrements AAAA (quadruple A). Si vous utilisez IPv4 et IPv6 dans votre déploiement, il est préférable de configurer et maintenir des enregistrements d’hôte A pour IPv4 et des enregistrements d’hôte AAAA pour IPv6. Même lors de la transition complète de votre déploiement vers IPv6, vous pouvez également nécessiter des enregistrements d’hôte DNS IPv4 pour les utilisateurs externes utilisant encore IPv4.
    
    Vous pouvez déployer les enregistrements d’hôte DNS IPv6 avant de commencer à utiliser IPv6. Si le client ou le serveur n’utilise pas IPv6, l’enregistrement ne sera pas référencé. Des technologies de transition décideront de l’enregistrement à utiliser, en fonction de la configuration des technologies de transition et des stratégies.

  - Chaque adresse IPv6 a une étendue. Les trois étendues que vous pouvez utiliser pour l’adressage IPv6 sont les adresses globales IPv6 (semblables aux adresses IPv4 publiques), les adresses locales uniques IPv6 (semblables aux plages d’adresses IPv4 privées) et les adresses locales de lien IPv6 (semblables aux adresses IP privées automatiques dans Windows Server pour IPv4). Tous les serveurs au sein d’un pool doivent avoir des adresses IPv6 avec la même étendue.

> [!IMPORTANT]  
> IPv6 est un sujet complexe et nécessite une planification minutieuse avec votre équipe de gestion de réseau et votre fournisseur Internet afin de vérifier que les adresses que vous affectez au niveau de Windows Server et de Lync Server 2013 fonctionnent comme prévu. Consultez les liens à la fin de cette rubrique pour accéder à des ressources supplémentaires sur l’adressage et la planification IPv6.

## Voir aussi

#### Autres ressources

[Architecture d’adressage IP Version 6](http://tools.ietf.org/html/rfc4291)  
[Format d’adresse de monodiffusion globale IPv6](http://tools.ietf.org/html/rfc3587)  
[Adresses de monodiffusion IPv6 locales uniques](http://tools.ietf.org/html/rfc4193)

