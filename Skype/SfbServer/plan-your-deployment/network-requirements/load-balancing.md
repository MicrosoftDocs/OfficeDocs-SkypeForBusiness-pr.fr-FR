---
title: Configuration requise pour l’équilibrage de charge pour Skype Entreprise
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
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Résumé: prenez connaissance des considérations relatives à l’équilibrage de charge avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 2db9b7aa37f71d445feb3cfd9a09e49f44ca48f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297056"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Configuration requise pour l’équilibrage de charge pour Skype Entreprise
 
**Résumé:** Prenez connaissance des considérations relatives à l’équilibrage de charge avant d’implémenter Skype entreprise Server.
  
L’équilibrage de la charge répartit le trafic entre les serveurs d’un pool. Si vous avez des pools front-end, des pools de serveurs de médiation ou des pools de serveurs Edge, vous devez déployer l’équilibrage de charge pour ces pools.
  
Skype entreprise Server prend en charge deux types de solutions d’équilibrage de charge pour le trafic client à serveur: l’équilibrage de charge DNS (Domain Name System) et l’équilibrage de charge matérielle (souvent abrégé comme HLB). Le service d’équilibrage de la charge DNS offre plusieurs avantages: une administration plus simple, un dépannage plus efficace et la possibilité d’isoler une grande partie du trafic de votre serveur Skype entreprise par rapport aux problèmes potentiels de l’équilibrage de charge matérielle.
  
Déterminez à vous-même quelle solution d’équilibrage de charge est appropriée pour chaque pool dans votre déploiement, tout en gardant à l’esprit les restrictions suivantes: 
  
- Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de charge. Vous ne pouvez pas utiliser l’équilibrage de charge DNS sur une interface et l’équilibrage de charge matérielle sur l’autre.
    
- Certains types de trafic nécessitent un programme dʼéquilibrage de charge matérielle. Par exemple, le trafic HTTP requiert un équilibrage de charge matérielle plutôt que l’équilibrage de charge DNS. Celui-ci ne fonctionne pas avec le trafic web client à serveur.
    
Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des équilibreurs de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des équilibreurs de la charge matérielle est grandement simplifiée. Par exemple, l’équilibreur de charge matérielle sera plus simple car il ne gérera que le trafic HTTP et HTTPS, alors que tous les autres protocoles seront gérés par l’équilibrage de charge DNS. Pour plus d’informations, voir [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Pour le trafic de serveur à serveur, Skype entreprise Server utilise l’équilibrage de charge prenant en charge la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge. 
  
Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur. 
  
## <a name="hardware-load-balancer-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

La topologie de périphérie consolidée de Skype entreprise Server est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements qui se fédère principalement avec d’autres organisations à l’aide de Skype entreprise Server ou de Lync Server. S’il est nécessaire de disposer d’une haute disponibilité pour l’un des scénarios suivants, un équilibreur de charge matérielle doit être utilisé sur les pools de serveurs Edge pour les éléments suivants: 
  
- Fédération avec des organisations qui utilisent Office Communications Server 2007 R2 ou Office Communications Server 2007
    
- Messagerie unifiée Exchange pour les utilisateurs distants utilisant la messagerie unifiée Exchange antérieure à Exchange 2010 avec SP1
    
- Connectivité avec les utilisateurs de messagerie instantanée publique
    
> [!IMPORTANT]
> L’utilisation de l’équilibrage de charge DNS sur une interface et de l’équilibrage de charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser l’équilibrage de charge matérielle ou l’équilibrage de charge DNS. 
  
> [!NOTE]
> Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne. 
  
> [!NOTE]
> Le moteur de traduction d’adresses du serveur direct (DSR) n’est pas pris en charge avec Skype entreprise Server. 
  
Pour savoir si votre équilibreur de charge matérielle prend en charge les fonctionnalités nécessaires requises par Skype entreprise Server, voir [infrastructure pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V

Vous trouverez ci-après les exigences relatives à l’équilibrage de charge matérielle pour les serveurs Edge exécutant le service Edge A/V:
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.
    
- Désactivez TCP nagling pour la plage de ports externes 50 000-59 999. 
    
- N’utilisez pas NAT sur le pare-feu interne ou externe. 
    
- L’interface interne Edge doit être située sur un autre réseau que l’interface externe du serveur Edge et le routage entre ces derniers doit être désactivé. 
    
- L’interface externe du serveur de périphérie exécutant le service Edge A/V doit utiliser les adresses IP routables publiquement et aucune traduction NAT ou de port sur les adresses IP externes du bord. 
    
- L’équilibreur de la charge ne doit pas modifier lʼadresse source du client.
    
### <a name="other-hardware-load-balancer-requirements"></a>Autres exigences de l’équilibrage de charge matérielle

Les exigences d’affinité basées sur les cookies sont considérablement réduites dans Skype entreprise Server pour les services Web. Si vous déployez Skype entreprise Server et ne conservera aucun serveur frontal ou pool frontal Lync Server 2010, vous n’avez pas besoin d’une persistance basée sur les cookies. Toutefois, si vous conservez temporairement ou définitivement tout serveur frontal ou pool frontal de Lync Server 2010, vous utiliserez quand même le niveau de persistance de cookie tel qu’il sera déployé et configuré pour Lync Server 2010. 
  
> [!NOTE]
> **Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin**, aucun impact négatif n’en résultera. 
  
Pour les déploiements qui **nʼutiliseront pas** lʼaffinité basée sur les cookies :
  
- Sur la règle de publication de proxy inverse pour le port 4443, définissez **Forward Header Header** sur true. Cela permet de s’assurer que l’URL d’origine est transférée.
    
Pour des déploiements qui **utiliseront** lʼaffinité basée sur les cookies :
  
- Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur True afin de vous assurer que lʼURL dʼorigine est envoyée.
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée
    
> [!NOTE]
> Les configurations standard du programme d’équilibrage de la charge matérielle utilisent l’affinité adresse source et une durée de vie de session de 20 minutes, qui convient aux clients Lync Server et Lync 2013, car l’état de session est maintenu par le biais de l’utilisation du client et/ou de l’interaction avec l’application. 
  
Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!CAUTION]
> Si vous déployez des appareils mobiles, votre dispositif d’équilibrage de la charge matérielle doit être en mesure de charger individuellement chaque demande au sein d’une connexion TCP. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security).  
  
> [!CAUTION]
> Pour plus d’informations sur les équilibreurs de charge matérielle tierce, voir [infrastructure pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :
  
- Pour les adresses IP virtuelles (VIP) des services web internes, définissez la persistance Source_addr (port interne 80, 443) sur l’équilibreur de la charge matérielle. Pour Skype entreprise Server, la persistance de Source_addr implique que plusieurs connexions venant d’une seule adresse IP sont toujours envoyées à un serveur pour conserver l’état de la session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre le proxy inverse et le service d’équilibrage de charge matérielle du pool de sauts suivant, créez une règle pour autoriser https: trafic sur le port 4443, à partir du proxy inverse vers l’équilibrage de charge matérielle. L’équilibreur de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes**|
|:-----|:-----|:-----|
|Lync Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Surveillance des ports pour les programmes d’équilibrage de la charge matérielle

Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication. Par exemple, si le service serveur frontal (RTCSRV) s’arrête en raison d’un dysfonctionnement du serveur frontal ou du pool frontal, la surveillance de HLB doit également arrêter la réception du trafic sur les services Web. Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :
  
**Pool d’utilisateurs du serveur frontal-interface interne de HLB**

|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<site\>Web de pool-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTPS  <br/> |
|\<site\>Web de pool-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTP  <br/> |
   
**Pool d’utilisateurs du serveur frontal-interface externe HLB**

|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>du pool  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>du pool  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

Le service d’équilibrage de charge DNS de Skype entreprise Server peut réduire considérablement la surcharge d’administration de votre réseau. L’équilibrage de charge DNS équilibre le trafic réseau propre à Skype entreprise Server, comme le trafic SIP et le trafic multimédia.
  
Si vous déployez l’équilibrage de charge DNS, la surcharge d’administration de votre organisation pour les équilibreurs de charge matérielle est réduite. Par ailleurs, le dépannage complexe des problèmes liés à la configuration incompatibilité des équilibreurs de charge pour le trafic SIP sera éliminé. Vous pouvez également empêcher les connexions au serveur pour pouvoir mettre en ligne des serveurs. L’équilibrage de charge DNS vérifie également que les problèmes liés à l’équilibrage de charge matérielle n’affectent pas les éléments du trafic SIP tels que le routage des appels de base.

Le schéma suivant illustre un exemple incluant l’équilibrage de charge DNS interne et externe: 
  
**Diagramme réseau Edge utilisant des adresses IPv4 publiques**

![exemple de diagramme réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Si vous utilisez l’équilibrage de charge DNS, vous pouvez également être en mesure d’acheter des équilibreurs de charge matérielle économiques que si vous utilisiez les équilibreurs de charge matérielle pour tous les types de trafic. Vous devez utiliser des équilibreurs de charge qui ont passé des tests de compétences d’interopérabilité avec Skype entreprise Server. Pour plus d’informations sur la vérification de l’interopérabilité de l’équilibrage de charge, consultez la rubrique partenaires de l’équilibrage de [charge Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). Le contenu s’applique à Skype entreprise Server.
  
Le service d’équilibrage de la charge DNS est pris en charge pour les pools front-end, les pools de serveurs Edge, les pools de directeurs et les pools de serveurs de médiation autonome
  
L’équilibrage de charge DNS est généralement implémenté au niveau de l’application. L’application (par exemple, un client exécutant Skype entreprise) essaie de se connecter à un serveur dans un pool en vous connectant à l’une des adresses IP renvoyées à partir de l’adresse DNS A et de la requête d’enregistrement de noms de domaine complets (si l’adressage IPv6 est utilisé). 
  
Par exemple, s’il existe trois serveurs front end dans un pool intitulé pool01.contoso.com, les informations suivantes se produisent:
  
- Clients exécutant la requête DNS de Skype entreprise pour pool01.contoso.com. La requête renvoie trois adresses IP et les met en cache comme suit (pas nécessairement dans cet ordre):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Le client tente d’établir une connexion TCP (Transmission Control Protocol) vers l’une des adresses IP. En cas d’échec, le client tente l’adresse IP suivante dans le cache.
    
- Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.
    
- Si le client tente d’accéder à toutes les entrées du cache sans connexion réussie, l’utilisateur est prévenu qu’aucun serveur exécutant Skype entreprise Server n’est disponible pour le moment.
    
> [!NOTE]
> Le service d’équilibrage de charge DNS est différent de l’équilibrage de charge DNS (RR) qui fait généralement référence à l’équilibrage de charge en fonction du système DNS, qui fournit un ordre différent d’adresses IP correspondant aux serveurs d’un pool. En règle générale, le RR DNS active uniquement la distribution de charge, mais n’autorise pas le basculement. Par exemple, si la connexion à une adresse IP renvoyée par la requête DNS A et AAAA (si vous utilisez l’adressage IPv6) échoue, la connexion échoue. C’est la raison pour laquelle le tourniquet DNS est plutôt moins fiable que le service d’équilibrage de charge DNS. Vous pouvez utiliser le tourniquet DNS conjointement avec l’équilibrage de charge DNS. 
  
L’équilibrage de charge DNS est utilisé pour les éléments suivants:
  
- Équilibrage de la charge de serveur à serveur SIP aux serveurs de périphérie
    
- Les applications UCAS (Unified Communications application Services) de répartition de charge telles que le standard automatique des conférences, le groupe de réponse et le parc d’appels
    
- Interdiction de nouvelles connexions aux applications UCAS (également appelées «drainage»)
    
- Équilibrage de la charge de tout le trafic client à serveur entre les clients et les serveurs de périphérie
    
L’équilibrage de charge DNS ne peut pas être utilisé pour les éléments suivants:
  
- Trafic Web de client à serveur vers le directeur ou les serveurs frontaux
    
Équilibrage de charge DNS et trafic fédéré:
  
Si plusieurs enregistrements DNS sont renvoyés par une requête DNS SRV, le service Edge d’accès sélectionne toujours l’enregistrement SRV DNS avec la priorité numérique la plus basse et la pondération numérique la plus élevée. Le document «Engineering Task Task» «un RR DNS pour spécifier l’emplacement de services (DNS SRV)» [RFC 2782, RR SRV](https://www.ietf.org/rfc/rfc2782.txt) spécifie que, si plusieurs enregistrements DNS SRV sont définis, la priorité est d’abord utilisée, puis l’épaisseur. Par exemple, l’enregistrement SRV DNS a a une épaisseur de 20 et une priorité de 40 et de l’enregistrement SRV DNS B a une épaisseur de 10 et de Priority 50. L’enregistrement SRV DNS A avec la priorité 40 est sélectionnée. Les règles suivantes s’appliquent à la sélection d’enregistrements SRV DNS:
  
- Priority est considéré comme premier. Un client doit tenter de contacter l’hôte cible défini par l’enregistrement SRV DNS dont la priorité numéro faible peut être atteinte. Les cibles de même priorité doivent être essayées dans un ordre défini par le champ pondération.
    
- Le champ poids spécifie une pondération relative pour les entrées ayant la même priorité. Le plus grand nombre de pondérations doit être proportionnel à la sélection. Les administrateurs DNS doivent utiliser le poids 0 quand il n’y a pas de sélection de serveur à effectuer. En présence d’enregistrements contenant des pondérations supérieures à 0, les enregistrements de poids 0 doivent avoir une très petite chance d’être sélectionnés.
    
Si plusieurs enregistrements SRV DNS ayant une priorité et un poids identiques sont retournés, le service Edge d’accès sélectionne l’enregistrement SRV reçu en premier du serveur DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Équilibrage de charge DNS pour les pools front-end et les pools de directeurs

Vous pouvez utiliser l’équilibrage de charge DNS pour le trafic SIP sur les listes frontales et les pools de Director. Après le déploiement de l’équilibrage de charge DNS, vous devez également utiliser des équilibreurs de charge matérielle pour ces pools, mais uniquement pour le trafic HTTPs de client à serveur. L’équilibrage de charge matérielle est utilisé pour le trafic HTTPs des clients sur les ports 443 et 80. 
  
Même si vous avez encore besoin d’équilibreurs de charge matérielle pour ces pools, leur configuration et leur administration s’adresseront essentiellement au trafic HTTPs, que les administrateurs des équilibreurs de charge matérielle sont habitués.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Équilibrage de charge DNS et prise en charge de clients et de serveurs plus anciens

L’équilibrage de charge DNS prend en charge le basculement automatique uniquement pour les serveurs exécutant Skype entreprise Server ou Lync Server 2010, ainsi que pour les clients Lync 2013 et Skype entreprise. Les versions antérieures de clients et d’Office Communications Server peuvent toujours se connecter aux pools exécutant l’équilibrage de charge DNS, mais, si elles ne peuvent pas établir une connexion au premier serveur auquel l’équilibrage de charge DNS fait référence, elles ne peuvent pas basculer sur un autre serveur du pool. . 
  
Par ailleurs, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir de l’aide sur l’équilibrage de charge DNS de Skype entreprise Server. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs ne disposent pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange:
  
- Lecture de leurs messages vocaux d’entreprise sur leur téléphone
    
- Transfert d’appels à partir d’un standard automatique de messagerie unifiée Exchange
    
Tous les autres scénarios Exchange UM fonctionnent correctement.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Déploiement de l’équilibrage de charge DNS pour les pools front-end et les pools de directeurs
<a name="BK_FE_Dir"> </a>

Le déploiement de l’équilibrage de charge DNS pour les pools principaux et les pools de directeurs nécessite que vous effectuiez quelques étapes supplémentaires avec les noms de domaine complets et les enregistrements DNS.
  
- Un pool qui utilise l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) du pool standard utilisés par l’équilibrage de charge DNS (par exemple, pool01.contoso.com), et est résolu sur l’IPs physique des serveurs du pool et un autre nom de domaine complet pour les services Web du pool (par exemple, web01.contoso.com), qui est résolue en adresse IP virtuelle du pool. 
    
    Dans le générateur de topologie, si vous voulez déployer l’équilibrage de charge DNS pour un pool, pour créer ce nom de domaine complet supplémentaire pour les services Web du pool, vous devez activer la case à cocher Remplacer le FQDN de la **liste des services Web internes** , puis taper le nom de domaine complet (FQDN) dans **spécifier les URL des services Web pour Cette** page de réserve.
    
- Pour prendre en charge le FQDN utilisé par l’équilibrage de charge DNS, vous devez configurer le système DNS pour résoudre le nom de domaine complet (par exemple, pool01.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Vous ne devez inclure que les adresses IP des serveurs actuellement déployés.
    
    > [!CAUTION]
    > Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Équilibrage de charge DNS sur les pools de serveurs Edge
<a name="BK_Edge"> </a>

Vous pouvez déployer l’équilibrage de charge DNS sur les pools de serveurs de périphérie. Dans le cas contraire, vous devez tenir compte de certaines considérations.
  
L’utilisation de l’équilibrage de charge DNS sur votre serveur Edge entraîne une perte de fonctionnalité de basculement dans les cas suivants:
  
- Fédération avec des organisations qui utilisent des versions de Skype entreprise Server mises en service avant Lync Server 2010.
    
- Échangez des messages instantanés avec des utilisateurs de services de messagerie instantanée publique AOL et Yahoo!, en plus des fournisseurs et des serveurs utilisant la fonction de messagerie instantanée, tels que Google Talk, pour le moment, le seul partenaire XMPP pris en charge.
    
Ces scénarios fonctionneront tant que tous les serveurs Edge du pool seront opérationnels, mais si un serveur Edge n’est pas disponible, toutes les demandes de ces scénarios qui y sont envoyés échoueront au lieu d’être routés vers un autre serveur Edge.
  
 Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum d’Exchange 2013 pour obtenir une prise en charge de l’équilibrage de charge DNS de Skype entreprise Server sur Edge. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs distants ne disposent pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange:
  
- Lecture de leurs messages vocaux d’entreprise sur leur téléphone
    
- Transfert d’appels à partir d’un standard automatique de messagerie unifiée Exchange
    
Tous les autres scénarios Exchange UM fonctionnent correctement.
  
L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Déploiement de l’équilibrage de charge DNS sur les pools de serveurs de périphérie

Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes:
  
- Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge du pool.
    
- Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet (par exemple, webconf.contoso.com) de l’adresse IP du service Edge de conférence Web sur l’un des serveurs Edge du pool.
    
- Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (par exemple, av.contoso.com) de l’adresse IP du service Edge A/V sur l’un des serveurs Edge du pool.
    
Pour déployer l’équilibrage de charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A, qui résout le nom de domaine complet (FQDN) du pool de serveurs Edge, à l’adresse IP de chaque serveur du pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation
<a name="BK_Mediation"> </a>

Vous pouvez utiliser l’équilibrage de charge DNS sur les pools de serveurs de médiation autonomes. Le trafic SIP et de média est équilibré par l’équilibrage de charge DNS.
  
Pour déployer l’équilibrage de charge DNS sur un pool de serveurs de médiation, vous devez configurer le DNS pour résoudre le nom de domaine complet (par exemple, mediationpool1.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocage du trafic vers un serveur avec l’équilibrage de charge DNS
<a name="BK_Mediation"> </a>

Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur. 
  
Notez que pour le trafic serveur à serveur, Skype entreprise Server utilise l’équilibrage de charge prenant en charge la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Pour empêcher un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie. 
  

