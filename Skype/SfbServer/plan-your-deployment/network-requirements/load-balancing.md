---
title: Configuration requise pour l’équilibrage de charge pour Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Résumé : Passez en revue le considérations équilibrage avant la mise en œuvre de Skype pour Business Server 2015.'
ms.openlocfilehash: f0b04ca0a9a5384ea26dd45c6caf0e826c7568d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Configuration requise pour l’équilibrage de charge pour Skype Entreprise
 
**Résumé :** Passez en revue le considérations équilibrage avant la mise en œuvre de Skype pour Business Server 2015.
  
L’équilibrage de charge répartit le trafic entre les serveurs d’un pool. Si vous avez des pools de Front-End, pools de serveur de médiation ou serveur de transport Edge, vous devez déployer pour ces pools d’équilibrage de charge.
  
Skype pour Business Server prend en charge deux types de solutions pour le trafic de client à serveur d’équilibrage de la charge : équilibrage de la charge de système de nom de domaine (DNS) et matériel équilibrage de charge souvent (abrégé sous la forme d’humidification à HLB). DNS charge équilibrage offre plusieurs avantages, notamment une administration plus simple, un dépannage plus efficace et la possibilité d’isoler une grande partie de votre Skype pour le trafic de Business Server à partir de tout problème potentiel équilibreur de charge matériel.
  
Décider quelle solution d’équilibrage de charge est appropriée pour chaque pool dans votre déploiement, mais gardez à l’esprit les restrictions suivantes : 
  
- Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de charge. Vous ne pouvez pas utiliser l’équilibrage de charge DNS sur une interface et l’équilibrage de charge matérielle sur l’autre.
    
- Certains types de trafic nécessitent un programme dʼéquilibrage de charge matérielle. Par exemple, le trafic HTTP requiert un équilibrage de charge matérielle plutôt que l’équilibrage de charge DNS. Celui-ci ne fonctionne pas avec le trafic web client à serveur.
    
Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des équilibreurs de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des équilibreurs de la charge matérielle est grandement simplifiée. Par exemple, l’équilibreur de charge matérielle sera plus simple car il ne gérera que le trafic HTTP et HTTPS, alors que tous les autres protocoles seront gérés par l’équilibrage de charge DNS. Pour plus d’informations, reportez-vous à la section [Équilibrage de la charge DNS](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Pour le trafic de serveur à serveur, Skype pour Business Server utilise l’équilibrage de charge compatibles avec la topologie. Serveurs lisent les topologies dans le magasin Central de gestion afin d’obtenir les noms de domaine complets des serveurs de la topologie et les distribuer automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge. 
  
Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur. 
  
## <a name="hardware-load-balancer-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Le Skype pour Business Server mis à l’échelle consolidée bord topologie est optimisé pour l’équilibrage de charge DNS pour les nouveaux déploiements se fédérer principalement avec d’autres organisations à l’aide de Skype pour Lync Server ou un serveur d’entreprise. Si une disponibilité élevée est requise pour un des scénarios suivants, un équilibreur de charge matériel doit être utilisé sur des pools de serveur de transport Edge pour les éléments suivants : 
  
- Fédération avec les organisations qui utilisent Office Communications Server 2007 R2 ou Office Communications Server 2007
    
- Messagerie unifiée Exchange pour les utilisateurs distants à l’aide de messagerie unifiée Exchange avant Exchange 2010 avec SP1
    
- Connectivité avec les utilisateurs de messagerie instantanée publique
    
> [!IMPORTANT]
> L’utilisation de l’équilibrage de charge DNS sur une interface et de l’équilibrage de charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser l’équilibrage de charge matérielle ou l’équilibrage de charge DNS. 
  
> [!NOTE]
> Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne. 
  
> [!NOTE]
> Le retour de serveur direct (DSR) NAT n’est pas pris en charge avec Skype pour Business Server. 
  
Pour déterminer si votre équilibreur de charge matériel prend en charge les fonctionnalités nécessaires requises par Skype pour Business Server, consultez [Infrastructure de Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947483).
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V

Voici la configuration matérielle charge équilibrage requise pour les serveurs Edge A / V Edge service :
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.
    
- Désactiver nagling TCP pour la plage de ports externes de 50 000 à 59 999. 
    
- N’utilisez pas NAT sur le pare-feu interne ou externe. 
    
- L’interface interne de bord doit être sur un autre réseau que l’interface externe du serveur de transport Edge et le routage entre les deux doit être désactivé. 
    
- L’interface externe du serveur Edge A / V Edge Service doivent utiliser des adresses IP routables publiquement et aucun NAT ou port de traduction sur toutes les adresses IP externes de bord. 
    
- L’équilibreur de la charge ne doit pas modifier lʼadresse source du client.
    
### <a name="other-hardware-load-balancer-requirements"></a>Autres conditions de l’équilibreur de charge matériel

Exigences d’affinité de basée sur les cookies sont considérablement réduits dans Skype pour Business Server pour les services Web. Si vous déployez Skype pour le serveur de l’entreprise et ne conservera pas les pools de Lync Server 2010 avant les serveurs principaux ou frontaux, il est inutile persistance cookie. Toutefois, si vous temporairement ou définitivement conservez tous les pools Front-End ou de Lync Server 2010 avant les serveurs principaux, vous toujours utilisez persistance cookie tel qu’il est déployé et configuré pour Lync Server 2010. 
  
> [!NOTE]
> **Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin**, aucun impact négatif n’en résultera. 
  
Pour les déploiements qui **nʼutiliseront pas** lʼaffinité basée sur les cookies :
  
- Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur True afin de vous assurer que lʼURL dʼorigine est envoyée.
    
Pour des déploiements qui **utiliseront** lʼaffinité basée sur les cookies :
  
- Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur True afin de vous assurer que lʼURL dʼorigine est envoyée.
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée
    
> [!NOTE]
> Configurations d’équilibrage de charge matériel classique utilisent l’affinité adresse source et un minimum de 20 TCP, durée de vie de session qui est parfaite pour les clients Lync Server et Lync 2013, car l’état de session est conservé par le biais de l’utilisation du client et/ou et l’interaction de l’application. 
  
Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!CAUTION]
> Les programmes d’équilibrage de la charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de la charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 fournit les paramètres spécifiques pour cela. 
  
> [!CAUTION]
> Pour plus d’informations sur les équilibreurs de charge matériels tiers, voir [Infrastructure de Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947483). 
  
La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :
  
- Pour les adresses IP virtuelles (VIP) des services web internes, définissez la persistance Source_addr (port interne 80, 443) sur l’équilibreur de la charge matérielle. Pour Skype pour Business Server, Source_addr persistance signifie que plusieurs connexions provenant d’une adresse IP unique sont toujours envoyées à un serveur pour gérer l’état de session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre le proxy inverse et l’équilibreur de charge matériel du pool du tronçon suivant, créez une règle pour autoriser https : le trafic sur le port 4443, à partir du proxy inverse pour le matériel de l’équilibreur de charge. L’équilibreur de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle

|**Emplacement de client/utilisateur**|**Exigences d’affinité de nom de domaine complet des services web externes**|**Exigences d’affinité de nom de domaine complet des services web interne**|
|:-----|:-----|:-----|
|(Les utilisateurs internes et externes) de Lync Web App  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (pour les utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (pour les utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Surveillance des ports pour les programmes d’équilibrage de la charge matérielle

Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication. Par exemple, si le service de serveur frontal (RTCSRV) s’arrête car le pool Front-End ou de serveur frontal échoue, le contrôle d’humidification à HLB doit également cesser de recevoir le trafic sur les Services Web. Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :
  
**Pool d’utilisateur de serveur frontal - Interface interne d’humidification à HLB**

|**IP/Port virtuel**|**Port de nœud**|**Moniteur d’ordinateur/nœud**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool de\>int_mco_443_vs-web  <br/> 443  <br/> |443  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTPS  <br/> |
|\<pool de\>int_mco_80_vs-web  <br/> 80  <br/> |80  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTP  <br/> |
   
**Pool d’utilisateur de serveur frontal - Interface externe d’humidification à HLB**

|**IP/Port virtuel**|**Port de nœud**|**Moniteur d’ordinateur/nœud**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool de\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTPS  <br/> |
|\<pool de\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype pour Business Server Active DNS équilibrage de charge, une solution logicielle qui permet de réduire considérablement la surcharge administrative liée à équilibrage de charge sur votre réseau. L’équilibrage de la charge DNS équilibre le trafic réseau qui est unique à Skype pour le serveur de l’entreprise, tels que le trafic SIP et le trafic multimédia.
  
Si vous déployez DNS équilibrage de la charge réseau, administration de votre organisation charge pour les équilibreurs de charge matériels sera réduite. De plus, le travail ardu de dépannage qu’imposent les problèmes découlant d’une mauvaise configuration des programmes d’équilibrage de la charge pour le trafic SIP sera évité. Vous pouvez aussi empêcher les connexions serveur afin de mettre les serveurs hors connexion. L’équilibrage de la charge DNS permet également d’éviter que des problèmes liés aux programmes d’équilibrage de la charge matérielle n’aient une incidence sur des éléments du trafic SIP, notamment le routage de base des appels.
  
En optant pour l’équilibrage de la charge DNS, vous pouvez aussi acheter des programmes d’équilibrage de la charge matérielle moins chers que ceux proposés pour tous les types de trafic. Vous devez utiliser des équilibreurs de charge qui ont passé qualification interopérabilité test avec Skype pour Business Server. Pour plus d’informations sur le test de l’interopérabilité équilibreur de charge, consultez [Les partenaires équilibreur de charge Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). Le contenu il s’applique à Skype Business Server.
  
L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools directeurs et les pools de serveurs de médiation autonomes.
  
L’équilibrage de la charge DNS est généralement mis en œuvre au niveau de l’application. Essaie de l’application (par exemple, un client utilisant Skype pour entreprise), pour se connecter à un serveur dans un pool en vous connectant à une des adresses IP renvoyées par le DNS A et AAAA (si l’adressage IPv6 est utilisé) enregistrent la requête pour le nom de domaine pleinement qualifié (FQDN) du pool. 
  
Si par exemple, il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, voilà ce qui se produit :
  
- Clients exécutant Skype pour les entreprises de requête DNS pour pool01.contoso.com. La requête renvoie trois IP résout et met en mémoire cache comme suit (pas nécessairement dans l’ordre indiqué) :
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Le client tente d’établir une connexion TCP à l’une des adresses IP. En cas d’échec, le client essaie l’adresse IP suivante dans le cache.
    
- Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.
    
- Si le client essaie toutes les entrées mises en cache sans établir une connexion, l’utilisateur est informé qu’aucun serveur exécutant Skype pour Business Server n’est disponibles pour le moment.
    
> [!NOTE]
> L’équilibrage de la charge DNS est différent du tourniquet (round robin) DNS (DNS RR), qui fait généralement référence à l’équilibrage de charge en s’appuyant sur DNS pour fournir un ordre d’adresses IP différent correspondant aux serveurs d’un pool. DNS RR active en général uniquement la distribution de la charge, mais n’active pas le basculement. Par exemple, si la connexion à l’adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue. Par conséquent, le tourniquet DNS (round robin) seul est moins fiable que l’équilibrage de la charge DNS. Vous pouvez utiliser le tourniquet DNS (round robin) conjointement avec l’équilibrage de la charge DNS. 
  
L’équilibrage de la charge DNS est utilisé dans les cas suivants :
  
- Équilibrage de la charge du trafic SIP vers les serveurs Edge
    
- Équilibrage de la charge des applications des services d’applications de communications unifiées (UCAS) telles que le Standard automatique de conférence, Response Group et le parcage d’appel.
    
- Empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage »)
    
- Équilibrage de la charge de l’ensemble du trafic client-serveur entre les clients et les serveurs Edge
    
L’équilibrage de la charge DNS ne peut pas être utilisé dans les cas suivants :
  
- Trafic web de client à serveur vers serveurs frontaux ou directeurs
    
Équilibrage de la charge DNS et trafic fédéré :
  
Si plusieurs enregistrements DNS sont retournées par une requête DNS SRV, Edge d’accès service sélectionne toujours le DNS SRV enregistrer avec la priorité numérique la plus faible et le poids numérique le plus élevé. L’Internet Engineering Task Force « A DNS RR for specifying the location of services (DNS SRV) » du document [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) Spécifie que s’il existe plusieurs DNS SRV enregistrements définis, priorité est utilisée tout d’abord, puis le poids. Par exemple, l’enregistrement DNS SRV A ayant un poids de 20 et une priorité de 40 et de l’enregistrement DNS SRV B a un poids de 10 et priorité de 50. Un enregistrement de DNS SRV priorité 40 est sélectionné. Les règles suivantes s’appliquent à la sélection des enregistrements DNS SRV :
  
- La priorité est prise en compte en premier. Un client DOIT tenter de contacter l’hôte cible défini par l’enregistrement SRV DNS ayant le chiffre de priorité le plus faible parmi ceux qu’il peut joindre. Pour les cibles ayant la même priorité, la tentative de connexion DOIT être effectuée en fonction d’un ordre défini par le champ de poids.
    
- Le champ de poids spécifie un poids relatif pour les entrées de même priorité. Les poids plus élevés DOIVENT présenter une probabilité de sélection proportionnellement plus élevée. Administrateurs DNS doivent utiliser des poids 0 en l’absence de toute sélection de serveur à effectuer. En présence d’enregistrements contenant des poids supérieurs à 0, les enregistrements de poids nul doivent avoir une chance très faible d’être sélectionnés.
    
Si plusieurs enregistrements SRV DNS de même priorité et de même poids sont renvoyés, le service Edge d’accès sélectionne l’enregistrement SRV qui a été reçu en premier en provenance du serveur DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Équilibrage de la charge DNS dans les pools frontaux et les pools directeurs

Vous pouvez désormais utiliser l’équilibrage de la charge DNS pour le trafic SIP dans les pools frontaux et les pools directeurs. Avec l’équilibrage de charge DNS déployé, vous devrez quand même toujours utiliser les programmes d’équilibrage de la charge matérielle pour ces pools, mais seulement pour le trafic HTTPS du client vers le serveur. Le programme d’équilibrage de la charge matérielle est utilisé pour le trafic HTTPS venant des clients sur les ports 443 et 80. 
  
Bien que le recours à des programmes d’équilibrage de la charge matérielle soit toujours nécessaire pour ces pools, leur configuration et leur administration concernera avant tout le trafic HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Équilibrage de charge DNS et prise en charge d’anciens clients et serveurs

Basculement automatique de contrepartie prend en charge uniquement pour les serveurs exécutant Skype pour Business Server ou de Microsoft Lync Server 2010 et Lync 2013 et Skype pour les clients de l’entreprise de charger DNS. Les versions antérieures d’Office Communications Server et les clients peuvent toujours se connecter aux pools de l’équilibrage de la charge DNS en cours d’exécution, mais si elles ne peuvent pas établir de connexion au premier serveur que l’équilibrage de la charge DNS fait référence à, ils ne peuvent pas basculer sur un autre serveur dans le pool . 
  
En outre, si vous utilisez Exchange UM, vous devez utiliser un minimum d’Exchange 2010 SP1 pour obtenir un support pour Skype pour l’équilibrage de la charge DNS de serveur d’entreprise. Si vous utilisez une version précédente d’Exchange, vos utilisateurs ne disposeront pas des fonctionnalités de basculement pour les scénarios de messagerie unifiée Exchange suivants :
  
- Lecture de leur messagerie vocale Entreprise sur leur téléphone
    
- Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange
    
Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs
<a name="BK_FE_Dir"> </a>

Le déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs vous oblige à effectuer quelques étapes supplémentaires avec les enregistrements de noms de domaine complets et les enregistrements DNS.
  
- Un pool par l’équilibrage de la charge DNS doit avoir deux noms de domaine complets : le nom de domaine complet est utilisé par le serveur DNS du pool régulière équilibrage de charge (par exemple, pool01.contoso.com) et correspond à l’IPs physique des serveurs dans le pool, et un autre nom de domaine complet Web du pool services (tels que web01.contoso.com), qui est résolue en une adresse IP virtuelle du pool. 
    
    Dans le Générateur de topologies, si vous souhaitez déployer DNS équilibrage de charge pour un pool, pour créer ce nom de domaine complet supplémentaire pour les services Web du pool vous devez sélectionner la case à cocher **nom de domaine complet du pool Override interne des Services Web** et tapez le nom de domaine complet dans le **de spécifier les URL de Services Web pour Ce Pool** page.
    
- Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.
    
    > [!CAUTION]
    > Si vous avez plus d’un pool frontal ou serveur frontal des services Web externes du nom de domaine complet doit être unique. Par exemple, si vous définissez les nom de domaine complet d’un serveur frontal des services Web externes comme **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou un serveur frontal. Si vous déployez également les directeurs, les externes FQDN défini pour n’importe quel directeur de services Web ou directeur pool doit être unique à partir de n’importe quel autre directeur ou directeur du pool ainsi qu’un pool frontal ou un serveur frontal. Si décider de remplacer les services web interne avec un nom de domaine complet définis par l’utilisateur, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou un directeur.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Équilibrage de charge DNS dans les pools de serveurs Edge
<a name="BK_Edge"> </a>

Vous pouvez déployer l’équilibrage de charge DNS dans les pools de serveurs Edge. Dans ce cas, vous devez tenir compte de certaines considérations.
  
L’utilisation de l’équilibrage de charge DNS sur vos serveurs Edge entraîne une perte des capacités de basculement dans les scénarios suivants :
  
- Fédération avec les entreprises qui exécutent des versions de Skype pour Business Server antérieure à Lync Server 2010.
    
- Échange de messages instantanés avec les utilisateurs de services de messagerie instantanée publique (messagerie instantanée) AOL et Yahoo!, en plus des fournisseurs XMPP et des serveurs, tels que Google Talk, actuellement le seul partenaire XMPP pris en charge.
    
Ces scénarios fonctionneront tant que tous les serveurs Edge dans le pool sont opérationnels, mais si un serveur Edge est indisponible, toutes les demandes envoyées à ces scénarios échoueront au lieu d’être routées vers un autre serveur Edge.
  
 Si vous utilisez Exchange UM, vous devez utiliser un minimum de Exchange 2013 pour obtenir un support pour Skype pour équilibrage de Business serveur DNS sur les bords. Si vous utilisez une version précédente d’Exchange, vos utilisateurs distants ne disposeront pas des fonctionnalités de basculement pour les scénarios de messagerie unifiée Exchange suivants :
  
- Lecture de leur messagerie vocale Entreprise sur leur téléphone
    
- Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange
    
Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.
  
Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Déploiement de l’équilibrage de charge DNS dans les pools de serveurs Edge

Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :
  
- Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge dans le pool.
    
- Pour le service Edge de conférence web, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge de conférence web (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence web sur l’un des serveurs Edge dans le pool.
    
- Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Audio/vidéo (par exemple, av.contoso.com) à l’adresse IP de l’A / V Edge service sur l’un des serveurs Edge dans le pool.
    
Pour déployer l’équilibrage de la charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A qui résout le nom de domaine complet interne du pool de serveurs Edge en adresse IP pour chaque serveur dans le pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilisation de l’équilibrage de charge DNS dans les pools de serveurs de médiation
<a name="BK_Mediation"> </a>

Vous pouvez utiliser l’équilibrage de charge DNS sur des pools de serveurs de médiation autonomes. Tout le trafic SIP et multimédia est équilibré par l’équilibrage de charge DNS.
  
Pour déployer l’équilibrage de la charge DNS sur un pool de serveurs de médiation, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, mediationpool1.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocage du trafic vers un serveur avec équilibrage de charge DNS
<a name="BK_Mediation"> </a>

Si vous utilisez l’équilibrage de la charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également supprimer l’entrée DNS associée à l’ordinateur. 
  
Notez que pour le trafic de serveur à serveur, Skype pour Business Server utilise l’équilibrage de charge compatibles avec la topologie. Serveurs lisent les topologies dans le magasin Central de gestion afin d’obtenir les noms de domaine complets des serveurs de la topologie et les distribuer automatiquement le trafic entre les serveurs. Pour bloquer la réception du trafic serveur à serveur pour un serveur, vous devez supprimer le serveur de la topologie. 
  

