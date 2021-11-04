---
title: Exigences d’équilibrage de charge pour Skype Entreprise
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
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Résumé : Examinez les considérations d’équilibrage de charge avant d’implémenter Skype Entreprise Server.'
ms.openlocfilehash: a738a615c773b3f2861899e061fbdbd664e05636
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777944"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Exigences d’équilibrage de charge pour Skype Entreprise
 
**Résumé :** Examinez les considérations d’équilibrage de charge avant d’implémenter Skype Entreprise Server.
  
L’équilibrage de charge distribue le trafic entre les serveurs d’un pool. Si vous avez des pools frontux, des pools de serveurs de médiation ou des pools de serveurs Edge, vous devez déployer l’équilibrage de charge pour ces pools.
  
Skype Entreprise Server prend en charge deux types de solutions d’équilibrage de charge pour le trafic client à serveur : l’équilibrage de charge DNS (Domain Name System) et l’équilibrage de la charge matérielle (souvent abrégé en Équilibrage de la charge matérielle). L’équilibrage de la charge DNS offre plusieurs avantages, notamment une administration plus simple, un dépannage plus efficace et la possibilité d’isoler la plus grande partie de votre trafic Skype Entreprise Server de tout problème potentiel d’équilibrage de la charge matérielle.
  
Déterminez par vous-même la solution d’équilibrage de charge appropriée pour chaque pool de votre déploiement, mais gardez à l’esprit les restrictions suivantes : 
  
- Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface et l’équilibrage de la charge matérielle sur l’autre.
    
- Certains types de trafic nécessitent un programme d’équilibrage de la charge matérielle. Par exemple, le trafic HTTP requiert un programme d’équilibrage de la charge matérielle plutôt que l’équilibrage de la charge DNS. Celui-ci ne fonctionne pas avec le trafic web client-à-serveur.
    
Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des programmes d’équilibrage de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des programmes d’équilibrage de la charge matérielle est grandement simplifiée. Par exemple, la configuration de l’équilibrage de la charge matérielle sera plus simple, car elle gérera uniquement le trafic HTTP et HTTPS, tandis que tous les autres protocoles seront gérés par l’équilibrage de charge DNS. Pour plus de détails, voir [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Pour le trafic de serveur à serveur, Skype Entreprise Server utilise l’équilibrage de charge pris en charge par la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir le FQDN des serveurs de la topologie et distribuent automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge. 
  
Si vous utilisez l’équilibrage de charge DNS et que vous devez bloquer le trafic vers un ordinateur spécifique, il ne suffit pas de supprimer simplement les entrées d’adresse IP du FQDN du pool. Vous devez également supprimer l’entrée DNS de l’ordinateur. 
  
## <a name="hardware-load-balancer-requirements"></a>Configuration requise pour l’équilibrage de la charge matérielle

La topologie Edge consolidée Skype Entreprise Server mise à l’échelle est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements fédérés principalement avec d’autres organisations utilisant Skype Entreprise Server ou Lync Server. Si, dans l’un des scénarios suivants, la haute disponibilité est requise, vous devez utiliser un programme d’équilibrage de la charge matérielle sur les pools de serveurs Edge pour prendre en charge ce qui suit : 
  
- Fédération avec des organisations utilisant Office Communications Server 2007 R2 ou Office Communications Server 2007
    
- Exchange Um for remote users using Exchange UM prior to Exchange 2010 with SP1
    
- connectivité avec les utilisateurs de messagerie instantanée publique.
    
> [!IMPORTANT]
> L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS. 
  
> [!NOTE]
> Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne. 
  
> [!NOTE]
> La nat de retour direct du serveur (DSR) n’est pas prise en charge avec Skype Entreprise Server. 
  
Pour déterminer si votre programme d’équilibrage de la charge matérielle prend en charge les fonctionnalités requises par Skype Entreprise Server, voir [Infrastructure for Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V

Les conditions requises pour l’équilibrage de la charge matérielle pour les serveurs Edge exécutant le service Edge A/V sont les suivantes :
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux, afin de rendre la transmission plus efficace.
    
- Désactiver le nagling TCP pour la plage de ports externes 50 000 à 59 999. 
    
- N’utilisez pas NAT sur le pare-feu interne ou externe. 
    
- L’interface interne Edge doit se trouver sur un autre réseau que l’interface externe Edge Server, et le routage entre elles doit être désactivé. 
    
- L’interface externe du serveur Edge qui exécute le service Edge A/V doit utiliser des adresses IP publiquement routables et aucune traduction nat ou de port sur l’une des adresses IP externes edge. 
    
- L’équilibreur de charge ne doit pas modifier l’adresse source du client.
    
### <a name="other-hardware-load-balancer-requirements"></a>Autres exigences relatives au programme d’équilibrage de la charge matérielle

Les exigences en matière d’affinité basée sur les cookies sont considérablement réduites Skype Entreprise Server pour les services Web. Si vous déployez Skype Entreprise Server et que vous ne conservez aucun serveur frontal ou pools frontux Lync Server 2010, vous n’avez pas besoin de persistance basée sur les cookies. Toutefois, si vous conservez temporairement ou définitivement des serveurs frontux ou des pools frontux Lync Server 2010, vous utilisez toujours la persistance basée sur les cookies lorsqu’elle est déployée et configurée pour Lync Server 2010. 
  
> [!NOTE]
> **Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin**, aucun impact négatif n’en résultera. 
  
Pour les déploiements qui **n’utiliseront pas** l’affinité basée sur les cookies :
  
- Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.
    
Pour les déploiements qui **utiliseront** l’affinité basée sur les cookies :
  
- Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée
    
> [!NOTE]
> Les configurations d’équilibrage de la charge matérielle classiques utilisent l’affinité d’adresse source et une durée de vie de session TCP de 20 minutes, ce qui est bien pour les clients Lync Server et Lync 2013, car l’état de session est maintenu par le biais de l’utilisation du client et/ou de l’interaction avec les applications. 
  
Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!CAUTION]
> Si vous déployez des appareils mobiles, votre programme d’équilibrage de la charge matérielle doit pouvoir équilibrer individuellement la charge de chaque demande au sein d’une connexion TCP. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security).  
  
> [!CAUTION]
> Pour plus d’informations sur les équilibreurs de la charge matérielle tiers, voir [Infrastructure for Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md).  
  
La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :
  
- Pour les adresses IP virtuelles (VIP) des services web internes, définissez la persistance Source_addr (port interne 80, 443) sur l’équilibreur de la charge matérielle. Par Skype Entreprise Server, Source_addr persistance signifie que plusieurs connexions provenant d’une seule adresse IP sont toujours envoyées à un serveur pour maintenir l’état de session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre le proxy inverse et l’équilibreur de la charge matérielle du pool du saut suivant, créez une règle pour autoriser le trafic https: sur le port 4443, du proxy inverse au équilibreur de charge matérielle. L’équilibreur de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes**|
|:-----|:-----|:-----|
|Lync Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Surveillance des ports pour les programmes d’équilibrage de la charge matérielle

Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication. Par exemple, si le service de serveur frontal (RTCSRV) s’arrête en raison de l’échec du serveur frontal ou du pool frontal, la surveillance de l’programme d’programmes d’programmes d’émission de programmes d’émission de programmes d’urgence doit également cesser de recevoir du trafic sur les services Web. Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :
  
**Pool d’utilisateurs du serveur frontal - Interface interne HLB**

|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTPS  <br/> |
|\<pool\>web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTP  <br/> |
   
**Pool d’utilisateurs du serveur frontal - Interface externe HLB**

|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucun  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucun  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype Entreprise Server active l’équilibrage de charge DNS, une solution logicielle qui peut considérablement réduire la charge d’administration pour l’équilibrage de charge sur votre réseau. L’équilibrage de charge DNS équilibre le trafic réseau propre à Skype Entreprise Server, tel que le trafic SIP et le trafic multimédia.
  
Si vous déployez l’équilibrage de charge DNS, la charge d’administration de votre organisation pour les équilibreurs de charge matérielle sera réduite. De plus, le travail ardu de dépannage qu’imposent les problèmes découlant d’une mauvaise configuration des programmes d’équilibrage de la charge pour le trafic SIP sera évité. Vous pouvez aussi empêcher les connexions serveur afin de mettre les serveurs hors connexion. L’équilibrage de la charge DNS permet également d’éviter que des problèmes liés aux programmes d’équilibrage de la charge matérielle n’aient une incidence sur des éléments du trafic SIP, notamment le routage de base des appels.

Le diagramme suivant montre un exemple qui inclut l’équilibrage de charge DNS interne et externe : 
  
**Diagramme du réseau Edge à l’aide d’adresses IPv4 publiques**

![exemple de diagramme réseau DNS.](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
En optant pour l’équilibrage de la charge DNS, vous pouvez aussi acheter des programmes d’équilibrage de la charge matérielle moins chers que ceux proposés pour tous les types de trafic. Vous devez utiliser des équilibreurs de charge qui ont réussi des tests de qualification d’interopérabilité Skype Entreprise Server. Pour plus d’informations sur les tests d’interopérabilité de l’équilibreur de charge, voir [Lync Server 2010 Load Balancer Partners](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). Le contenu s’applique aux Skype Entreprise Server.
  
L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools directeurs et les pools de serveurs de médiation autonomes.
  
L’équilibrage de la charge DNS est généralement implémenté au niveau de l’application. L’application (par exemple, un client exécutant Skype Entreprise) tente de se connecter à un serveur dans un pool en se connectant à l’une des adresses IP renvoyées par la requête d’enregistrement DNS A et AAAA (si l’adressare IPv6 est utilisée) pour le nom de domaine complet (FQDN) du pool. 
  
Si par exemple il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, voilà ce qui se produit :
  
- Les clients exécutant Skype Entreprise DNS pour obtenir pool01.contoso.com. La requête renvoie trois adresses IP et les met en cache comme suit (pas nécessairement dans cet ordre) :
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Le client tente d’établir une connexion TCP (Transmission Control Protocol) à l’une des adresses IP. En cas d’échec, le client essaie l’adresse IP suivante dans le cache.
    
- Si la connexion TCP réussit, le client négocie TLS pour se connecter au bureau d’enregistrement principal sur pool01.contoso.com.
    
- Si le client tente toutes les entrées mises en cache sans connexion réussie, l’utilisateur est informé qu’aucun serveur exécutant Skype Entreprise Server n’est disponible pour le moment.
    
> [!NOTE]
> L’équilibrage de la charge DNS est différent du tourniquet (round robin) DNS (DNS RR) qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour fournir un ordre d’adresses IP différent correspondant aux serveurs d’un pool. DNS RR active en général uniquement la distribution de la charge, mais n’active pas le basculement. Par exemple, si la connexion à l’adresse IP renvoyée par les requêtes DNS A et AAAA (si vous utilisez l’adressaing IPv6) échoue, la connexion échoue. Par conséquent, le tourniquet DNS (round robin) seul est moins fiable que l’équilibrage de la charge DNS. Vous pouvez utiliser le tourniquet DNS (round robin) conjointement avec l’équilibrage de la charge DNS. 
  
L’équilibrage de la charge DNS est utilisé dans les cas suivants :
  
- Équilibrage de charge SIP de serveur à serveur sur les serveurs Edge
    
- Équilibrage de la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel.
    
- Empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage »)
    
- Équilibrage de la charge de l’ensemble du trafic client-serveur entre les clients et les serveurs Edge
    
L’équilibrage de la charge DNS ne peut pas être utilisé dans les cas suivants :
  
- Trafic web client à serveur vers les serveurs directeurs ou frontux
    
Équilibrage de la charge DNS et trafic fédéré :
  
Si plusieurs enregistrements DNS sont renvoyés par une requête DNS SRV, le service Edge d’accès sélectionne toujours l’enregistrement SRV DNS ayant la priorité numérique la plus faible et le poids numérique le plus élevé. Le document « A DNS RR for specifying the location of services (DNS SRV) » [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) spécifie que si plusieurs enregistrements DNS SRV sont définis, la priorité est d’abord utilisée, puis la pondération. Par exemple, l’enregistrement SRV DNS A a un poids de 20 et une priorité de 40 et l’enregistrement DNS SRV B a une pondération de 10 et une priorité de 50. L’enregistrement DNS SRV A avec la priorité 40 est sélectionné. Les règles suivantes s’appliquent à la sélection d’enregistrement DNS SRV :
  
- La priorité est considérée comme prioritaire. Un client DOIT tenter de contacter l’hôte cible défini par l’enregistrement DNS SRV avec la priorité numéroée la plus faible qu’il peut atteindre. Les cibles ayant la même priorité DOIVENT être essayées dans un ordre défini par le champ de pondération.
    
- Le champ de pondération spécifie une pondération relative pour les entrées ayant la même priorité. Les pondérations plus importantes doivent avoir une probabilité proportionnellement plus élevée d’être sélectionnées. Les administrateurs DNS doivent utiliser le poids 0 lorsqu’il n’y a aucune sélection de serveur à faire. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements ayant une pondération 0 ont très peu de chances d’être sélectionnés.
    
Si plusieurs enregistrements SRV DNS de même priorité et de même poids sont renvoyés, le service Edge d’accès sélectionne l’enregistrement SRV reçu en premier à partir du serveur DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Équilibrage de la charge DNS dans les pools frontaux et les pools directeurs

Vous pouvez désormais utiliser l’équilibrage de la charge DNS pour le trafic SIP dans les pools frontaux et les pools directeurs. Avec l’équilibrage de charge DNS déployé, vous devrez quand même toujours utiliser les programmes d’équilibrage de la charge matérielle pour ces pools, mais seulement pour le trafic HTTPS du client vers le serveur. Le programme d’équilibrage de la charge matérielle est utilisé pour le trafic HTTPS venant des clients sur les ports 443 et 80. 
  
Bien que le recours à des programmes d’équilibrage de la charge matérielle soit toujours nécessaire pour ces pools, leur configuration et leur administration concernera avant tout le trafic HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Équilibrage de charge DNS et prise en charge d’anciens clients et serveurs

L’équilibrage de charge DNS prend en charge leover automatique uniquement pour les serveurs exécutant Skype Entreprise Server ou Lync Server 2010, et pour les clients Lync 2013 Skype Entreprise. Les versions antérieures des clients et de Office Communications Server peuvent toujours se connecter à des pools exécutant l’équilibrage de charge DNS, mais s’ils ne parviennent pas à établir une connexion au premier serveur vers qui l’équilibrage de charge DNS les fait référencer, ils ne peuvent pas effectuer le pas vers un autre serveur du pool. 
  
En outre, si vous utilisez une Exchange de service de Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir la prise en charge de l Skype Entreprise Server équilibrage de charge DNS. Si vous utilisez une version antérieure de Exchange, vos utilisateurs n’auront pas de fonctionnalités de Exchange scénarios de la Exchange de l’utilisateur :
  
- Lecture de Enterprise messagerie vocale sur son téléphone
    
- Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange
    
Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs
<a name="BK_FE_Dir"> </a>

Le déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs vous oblige à effectuer quelques étapes supplémentaires avec les enregistrements de noms de domaine complets et les enregistrements DNS.
  
- Un pool qui utilise l’équilibrage de charge DNS doit avoir deux FQDN : le nom de pool normal utilisé par l’équilibrage de charge DNS (tel que pool01.contoso.com) et résolu en adresses IP physiques des serveurs du pool, et un autre nom de groupe pour les services Web du pool (tel que web01.contoso.com), qui se résout en adresse IP virtuelle du pool. 
    
    Dans le Générateur de topologie, si vous souhaitez déployer l’équilibrage de charge DNS pour un pool, pour créer ce FQDN supplémentaire pour les services Web du pool, vous devez cocher la case Remplacer le **FQDN** du pool de services web internes et taper le FQDN dans la page Spécifier les URL des services Web pour ce **pool.**
    
- Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.
    
    > [!CAUTION]
    > Si vous avez plusieurs serveurs frontaux ou serveurs frontaux, le FQDN des services Web externes doit être unique. Par exemple, si vous définissez le nom de groupe des services Web externes d’un serveur frontal en tant que **pool01.contoso.com,** vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de groupe des services Web externes défini pour un directeur ou un pool directeur doit être unique à partir d’un autre directeur ou pool directeur, ainsi que de tout pool frontal ou serveur frontal. Si vous décidez de remplacer les services web internes par un FQDN auto-défini, chaque FQDN doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Équilibrage de charge DNS dans les pools de serveurs Edge
<a name="BK_Edge"> </a>

Vous pouvez déployer l’équilibrage de charge DNS dans les pools de serveurs Edge. Dans ce cas, vous devez tenir compte de certaines considérations.
  
L’utilisation de l’équilibrage de charge DNS sur vos serveurs Edge entraîne une perte des capacités de basculement dans les scénarios suivants :
  
- Fédération avec les organisations qui exécutent des versions de Skype Entreprise Server publiées avant Lync Server 2010.
    
- Échange de messages instantanés avec les utilisateurs des services de messagerie instantanée publics AOL et Yahoo!, en plus des fournisseurs et serveurs XMPP, tels que Google Talk, actuellement le seul partenaire XMPP pris en charge.
    
Ces scénarios fonctionneront tant que tous les serveurs Edge dans le pool sont opérationnels, mais si un serveur Edge est indisponible, toutes les demandes envoyées à ces scénarios échoueront au lieu d’être routées vers un autre serveur Edge.
  
 Si vous utilisez la Exchange,vous devez utiliser un minimum de Exchange 2013 pour obtenir la prise en charge de l Skype Entreprise Server équilibrage de charge DNS sur Edge. Si vous utilisez une version antérieure de Exchange, vos utilisateurs distants n’auront pas de fonctionnalités de Exchange scénarios de um :
  
- Lecture de Enterprise messagerie vocale sur son téléphone
    
- Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange
    
Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.
  
Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Déploiement de l’équilibrage de charge DNS dans les pools de serveurs Edge

Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :
  
- Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le FQDN du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge du pool.
    
- Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le FQDN du service Edge de conférence Web (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence Web sur l’un des serveurs Edge du pool.
    
- Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le FQDN du service Edge audio/vidéo (par exemple, av.contoso.com) en adresse IP du service Edge A/V sur l’un des serveurs Edge du pool.
    
Pour déployer l’équilibrage de la charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A qui résout le nom de domaine complet interne du pool de serveurs Edge en adresse IP pour chaque serveur dans le pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilisation de l’équilibrage de charge DNS dans les pools de serveurs de médiation
<a name="BK_Mediation"> </a>

Vous pouvez utiliser l’équilibrage de charge DNS sur des pools de serveurs de médiation autonomes. Tout le trafic SIP et multimédia est équilibré par l’équilibrage de charge DNS.
  
Pour déployer l’équilibrage de la charge DNS sur un pool de serveurs de médiation, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, mediationpool1.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocage du trafic vers un serveur avec équilibrage de charge DNS
<a name="BK_Mediation"> </a>

Si vous utilisez l’équilibrage de charge DNS et que vous devez bloquer le trafic vers un ordinateur spécifique, il ne suffit pas de supprimer simplement les entrées d’adresse IP du FQDN du pool. Vous devez également supprimer l’entrée DNS de l’ordinateur. 
  
Notez que pour le trafic de serveur à serveur, Skype Entreprise Server utilise l’équilibrage de charge pris en charge par la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir le FQDN des serveurs de la topologie et distribuent automatiquement le trafic entre les serveurs. Pour empêcher un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie. 
