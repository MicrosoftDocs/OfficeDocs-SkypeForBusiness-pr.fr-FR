---
title: Configuration requise pour l’équilibrage de charge pour Skype Entreprise
ms.reviewer: ''
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
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Résumé : Passez en revue le considérations relatives à équilibrage avant d’implémenter Skype pour Business Server.'
ms.openlocfilehash: a7e8e70088c83276c36334c5d9a1e3be1538ca38
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897889"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Configuration requise pour l’équilibrage de charge pour Skype Entreprise
 
**Résumé :** Passez en revue le considérations relatives à équilibrage avant d’implémenter Skype pour Business Server.
  
L’équilibrage de charge distribue le trafic entre les serveurs d’un pool. Si vous avez des pools frontaux, les pools de serveurs de médiation ou les pools de serveurs Edge, vous devez déployer l’équilibrage de charge pour ces pools.
  
Skype pour Business Server prend en charge deux types de solutions pour le trafic client-serveur d’équilibrage de charge : nom de domaine DNS (Domain Name System) de l’équilibrage de charge et souvent (abréviation comme matérielle) d’équilibrage de charge. Offre l’équilibrage de charge DNS offre plusieurs avantages, y compris de faciliter l’administration, la résolution des problèmes plus efficace et la possibilité d’isoler la majeure partie de votre Skype pour le trafic Business Server à partir de tout problème potentiel d’équilibrage de charge matériel.
  
Décider quelle solution d’équilibrage de charge est appropriée pour chaque pool dans votre déploiement, mais gardez à l’esprit les restrictions suivantes : 
  
- Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de charge. Vous ne pouvez pas utiliser l’équilibrage de charge DNS sur une interface et l’équilibrage de charge matérielle sur l’autre.
    
- Certains types de trafic nécessitent un programme dʼéquilibrage de charge matérielle. Par exemple, le trafic HTTP requiert un équilibrage de charge matérielle plutôt que l’équilibrage de charge DNS. Celui-ci ne fonctionne pas avec le trafic web client à serveur.
    
Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des équilibreurs de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des équilibreurs de la charge matérielle est grandement simplifiée. Par exemple, l’équilibreur de charge matérielle sera plus simple car il ne gérera que le trafic HTTP et HTTPS, alors que tous les autres protocoles seront gérés par l’équilibrage de charge DNS. Pour plus d’informations, voir [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Pour le trafic de serveur à serveur, Skype pour Business Server utilise l’équilibrage de charge compatibles avec la topologie. Les serveurs lire la topologie publiée dans le magasin Central de gestion pour obtenir les noms de domaine complets des serveurs de la topologie et distribuent automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge. 
  
Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur. 
  
## <a name="hardware-load-balancer-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Le Skype pour Business Server mis à l’échelle consolidée Edge topologie est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements fédération principalement avec d’autres organisations à l’aide de Skype pour Business Server ou de Lync Server. Si une haute disponibilité est requise pour les scénarios suivants, un mécanisme d’équilibrage de charge doit être utilisé sur les pools de serveurs Edge pour les éléments suivants : 
  
- Fédération avec des organisations à l’aide d’Office Communications Server 2007 R2 ou Office Communications Server 2007
    
- Messagerie unifiée Exchange pour les utilisateurs distants à l’aide de la messagerie unifiée Exchange avant d’Exchange 2010 avec SP1
    
- Connectivité avec les utilisateurs de messagerie instantanée publique
    
> [!IMPORTANT]
> L’utilisation de l’équilibrage de charge DNS sur une interface et de l’équilibrage de charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser l’équilibrage de charge matérielle ou l’équilibrage de charge DNS. 
  
> [!NOTE]
> Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne. 
  
> [!NOTE]
> Le retour de serveur direct (DSR) NAT n’est pas pris en charge avec Skype pour Business Server. 
  
Pour déterminer si votre équilibreur de charge matérielle prend en charge les fonctionnalités requises par Skype pour Business Server, consultez [Infrastructure de Skype pour les entreprises](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V

Voici la charge d’équilibrage de la configuration matérielle pour les serveurs Edge A / V Edge service :
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.
    
- Désactivez le nagling TCP pour la plage de ports externes 50 000 à 59 999. 
    
- N’utilisez pas NAT sur le pare-feu interne ou externe. 
    
- L’interface interne edge doit être sur un autre réseau que l’interface externe du serveur de transport Edge et routage entre elles doit être désactivé. 
    
- L’interface externe du serveur Edge A / V Edge Service doivent utiliser des adresses IP routables publiquement, mais aucune NAT ou traduction de port sur une des adresses IP edge externes. 
    
- L’équilibreur de la charge ne doit pas modifier lʼadresse source du client.
    
### <a name="other-hardware-load-balancer-requirements"></a>Autres conditions d’équilibrage de charge matérielle

Exigences de l’affinité basée sur les cookies sont considérablement réduits dans Skype pour Business Server pour les services Web. Si vous déployez Skype pour Business Server et conserverez pas n’importe quel Lync Server 2010 Front End Servers ou pools frontaux, il est inutile persistance basée sur les cookies. Toutefois, si vous temporairement ou définitivement conservez tout Lync Server 2010 Front End Servers ou pools frontaux, vous toujours utilisez persistance basée sur les cookies comme il est déployé et configuré pour Lync Server 2010. 
  
> [!NOTE]
> **Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin**, aucun impact négatif n’en résultera. 
  
Pour les déploiements qui **nʼutiliseront pas** lʼaffinité basée sur les cookies :
  
- Sur la règle de publication proxy inverse pour le port 4443, définissez **l’en-tête d’hôte directe** sur True. Cela garantit que l’original URL est transféré.
    
Pour des déploiements qui **utiliseront** lʼaffinité basée sur les cookies :
  
- Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur True afin de vous assurer que lʼURL dʼorigine est envoyée.
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly
    
- Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)
    
- Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée
    
> [!NOTE]
> Configurations d’équilibrage de charge matériel typique utilisent l’affinité des adresses de la source et un minimum de 20 TCP durée de vie de session qui convient pour les clients Lync Server et Lync 2013, car l’état de session est conservé par le biais de l’utilisation de client et/ou et l’interaction de l’application. 
  
Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!CAUTION]
> Si vous déployez les appareils mobiles, votre équilibreur de charge matérielle doit être en mesure de charger individuellement équilibrer chaque demande au sein d’une connexion TCP. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security).  
  
> [!CAUTION]
> Pour plus d’informations sur les équilibreurs de charge matérielle tiers, consultez [Infrastructure de Skype pour les entreprises](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :
  
- Pour les adresses IP virtuelles (VIP) des services web internes, définissez la persistance Source_addr (port interne 80, 443) sur l’équilibreur de la charge matérielle. Pour Skype pour Business Server, persistance Source_addr signifie que plusieurs connexions provenant d’une adresse IP unique sont toujours envoyées à un serveur pour gérer l’état de session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre le proxy inverse et d’équilibrage de charge matérielle du pool du tronçon suivant, créez une règle pour autoriser le protocole https : le trafic sur le port 4443, à partir du proxy inverse pour le matériel équilibreur de charge. L’équilibreur de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes**|
|:-----|:-----|:-----|
|Lync Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (pour les utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Lync Web App (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Surveillance des ports pour les programmes d’équilibrage de la charge matérielle

Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication. Par exemple, si le service du serveur frontal (RTCSRV) s’arrête, car le pool frontal ou serveur frontal échoue, la surveillance matérielle doit également arrêter de recevoir le trafic sur les Services Web. Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :
  
**Pool d’utilisateur de serveur frontal - Interface interne HLB**

|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>-int_mco_443_vs web  <br/> 443  <br/> |443  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTPS  <br/> |
|\<pool\>-int_mco_80_vs web  <br/> 80  <br/> |80  <br/> |Serveur frontal  <br/> 5061  <br/> |Source  <br/> |HTTP  <br/> |
   
**Pool d’utilisateur de serveur frontal - Interface externe HLB**

|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

Skype pour Business Server Active DNS équilibrage de charge, une solution logicielle qui permet de réduire la surcharge administrative liée à équilibrage de charge sur votre réseau. Équilibrage de charge DNS répartit le trafic réseau qui est unique à Skype pour le serveur d’entreprise, telles que le trafic SIP et le trafic multimédia.
  
Si vous déployez l’équilibrage de charge DNS, l’administration de votre organisation une surcharge pour les équilibreurs de charge matérielle est réduite. En outre, la résolution des problèmes complexes de problèmes liés à une mauvaise configuration des équilibreurs de charge pour le trafic SIP seront éliminé. Vous pouvez également empêcher les connexions serveur afin que vous puissiez prendre des serveurs en mode hors connexion. Équilibrage de charge DNS s’assure également que les problèmes d’équilibrage de charge matériels n’affectent pas les éléments du trafic SIP tels que le routage des appels de base.

Le diagramme suivant illustre un exemple qui inclut les deux interne et l’équilibrage de charge DNS externe : 
  
**Diagramme réseau Edge utilisant des adresses IPv4 publiques**

![exemple de diagramme réseau DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Si vous utilisez l’équilibrage de charge DNS, vous pourrez également les équilibreurs de charge matérielle moindre coût que si vous avez utilisé les équilibreurs de charge matérielle pour tous les types de trafic d’achat. Vous devez utiliser des équilibreurs de charge qui se sont écoulées qualification interopérabilité test avec Skype pour Business Server. Pour plus d’informations sur les tests d’interopérabilité d’équilibrage de la charge, voir [Les partenaires d’équilibrage de la charge Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). Il le contenu s’applique à Skype Business Server.
  
Équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools directeurs et pools de serveurs de médiation autonomes.
  
Équilibrage de charge DNS est généralement implémenté au niveau de l’application. L’application (par exemple, un client exécutant Skype pour les entreprises), essaie de se connecter à un serveur dans un pool en se connectant à une des adresses IP retournées par le DNS A et AAAA (si l’adressage IPv6 est utilisé) enregistrent la requête pour le nom de domaine complet (FQDN) du pool. 
  
Par exemple, s’il existe trois serveurs frontaux dans un pool appelé pool01.contoso.com, les éléments suivants se produit :
  
- Les clients Skype pour les entreprises en cours d’exécution de requête DNS pour pool01.contoso.com. La requête renvoie trois IP addresses et met en mémoire cache comme suit (pas nécessairement dans cet ordre) :
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Le client tente d’établir une connexion de protocole TCP (Transmission Control) à une des adresses IP. En cas d’échec, le client tente de l’adresse IP suivante dans le cache.
    
- Si la connexion TCP aboutit, le client négocie le protocole TLS pour se connecter au serveur d’inscriptions principal sur pool1.contoso.com.
    
- Si le client essaie toutes les entrées mises en cache sans que la connexion échoue, l’utilisateur est informé qu’aucun serveur exécutant Skype pour Business Server n’est disponibles pour le moment.
    
> [!NOTE]
> L’équilibrage de charge basée sur DNS est différente de DNS (round robin) (RR DNS) qui fait généralement référence à équilibrage en se basant sur le DNS afin de fournir un ordre différent de IP addresses correspondant aux serveurs d’un pool. Généralement DNS RR uniquement permet de charge la distribution, mais ne pas activer le basculement. Par exemple, si la connexion à une adresse IP renvoyée par le DNS A et AAAA (si vous utilisez l’adressage IPv6) requête échoue, la connexion échoue. Par conséquent, DNS round robin par lui-même est moins fiable que l’équilibrage de charge basée sur DNS. Vous pouvez utiliser DNS l’équilibrage de charge round robin conjointement avec le système DNS. 
  
Équilibrage de charge DNS est utilisé pour les éléments suivants :
  
- Serveur-serveur SIP pour les serveurs de périphérie d’équilibrage de la charge
    
- Applications de Services d’applications de Communications unifiées (UCAS) telles que conférence automatique Attendant, Response Group et parcage d’appel d’équilibrage de la charge
    
- Empêcher les nouvelles connexions aux applications UCAS (également appelé « drainage »)
    
- Tout le trafic de client à serveur entre les clients et serveurs de périphérie d’équilibrage de la charge
    
Équilibrage de charge DNS ne peut pas être utilisé pour les éléments suivants :
  
- Trafic web client à serveur pour les serveurs frontaux ou directeur
    
Le trafic fédéré et de l’équilibrage de charge DNS :
  
Si plusieurs enregistrements DNS sont retournés par une requête SRV DNS, le serveur Edge d’accès service choisit toujours le DNS SRV enregistrer la priorité numérique et poids numérique le plus élevé. « A DNS RR pour spécifier l’emplacement des services (DNS SRV) » de documents Internet Engineering Task Force [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) Spécifie que s’il existe plusieurs enregistrements SRV DNS pour les enregistrements définis, priorité de la première utilisation, puis poids. Par exemple, l’enregistrement SRV DNS A a une épaisseur de 20 et une priorité de 40 et de l’enregistrement DNS SRV B a une épaisseur de 10 et la priorité de 50. Enregistrement DNS SRV A priorité 40 est sélectionnée. Les règles suivantes s’appliquent à la sélection des enregistrements DNS SRV :
  
- Priorité est traitée en premier. Un client doit essayer de contacter l’hôte cible définie par l’enregistrement DNS SRV avec la priorité numérotée la plus faible que possible. Cibles de même priorité doivent être faites dans un ordre défini par le champ poids.
    
- Le champ Poids spécifie une épaisseur relative pour les entrées avec la même priorité. Poids du plus grandes convient proportionnellement probabilité d’être sélectionnés. Les administrateurs DNS doivent utiliser poids 0 en l’absence de toute sélection de serveur à faire. En présence d’enregistrements contenant des pondérations supérieures à 0, les enregistrements avec poids 0 doivent avoir un très petit risque d’être sélectionnés.
    
Si plusieurs enregistrements SRV DNS avec la même priorité et poids sont renvoyés, le service Edge d’accès sélectionne l’enregistrement SRV qui a été reçu tout d’abord à partir du serveur DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS équilibrage de charge sur directeur Pools frontaux et les Pools

Vous pouvez utiliser DNS équilibrage de charge pour le trafic SIP sur les pools frontaux et directeurs. Avec équilibrage de charge DNS déployé, vous devez toujours utiliser également les équilibreurs de charge matérielle pour ces pools, mais uniquement pour le trafic HTTPS de client à serveur. L’équilibrage de charge matérielle est utilisé pour le trafic HTTPS à partir de clients sur les ports 443 et 80. 
  
Bien que vous devez toujours équilibreurs de charge matérielle pour ces pools, leur configuration et administration sera principalement pour le trafic HTTPS, les administrateurs des équilibreurs de charge matérielle sont familiarisés pour.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS équilibrage de charge et prise en charge d’anciens Clients et serveurs

Équilibrage de la prise en charge le basculement automatique uniquement pour les serveurs exécutant Skype pour Business Server ou Microsoft Lync Server 2010 et pour Lync 2013 et Skype pour les clients d’entreprise de charge DNS. Versions antérieures d’Office Communications Server et les clients peuvent toujours se connecter à des pools d’équilibrage de charge DNS, mais si elles ne peuvent pas établir de connexion sur le premier serveur que l’équilibrage de charge DNS fait référence aux, ils ne peuvent pas basculer vers un autre serveur du pool . 
  
En outre, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir un support pour Skype pour l’équilibrage de charge DNS de serveur d’entreprise. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs disposent pas des fonctions de basculement pour ces scénarios de messagerie unifiée Exchange :
  
- Lecture de leur messagerie vocale d’entreprise sur leur téléphone
    
- Transfert d’appels à partir d’un standard automatique Exchange UM
    
Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Déploiement DNS équilibrage de charge sur directeur Pools frontaux et les Pools
<a name="BK_FE_Dir"> </a>

Déploiement de DNS équilibrage de charge sur les pools frontaux et directeurs vous oblige à effectuer quelques étapes supplémentaires avec les enregistrements DNS et les noms de domaine complets.
  
- Un pool qui utilise l’équilibrage de charge DNS doit avoir deux noms de domaine complets : le nom de domaine complet qui est utilisé par le système DNS du pool régulière équilibrage de charge (par exemple, pool01.contoso.com) et correspond à des adresses IP physique des serveurs du pool et un autre nom de domaine complet Web du pool services (tels que web01.contoso.com), qui est résolu en adresse IP virtuelle du pool. 
    
    Dans le Générateur de topologie, si vous souhaitez déployer DNS équilibrage de charge pour un pool, pour créer ce nom de domaine complet supplémentaire pour les services Web du pool vous devez activez la case à cocher **nom de domaine complet du pool de Services Web internes de substitution** et tapez le nom de domaine complet, dans le **spécifier l’URL de Services Web Ce Pool** page.
    
- Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de charge DNS, vous devez configurer le DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2 et ainsi de suite). Vous devez inclure uniquement les adresses IP des serveurs qui sont actuellement déployés.
    
    > [!CAUTION]
    > Si vous avez plus d’un pool frontal ou serveur frontal des services Web externes nom de domaine complet doit être unique. Par exemple, si vous définissez les nom de domaine complet d’un serveur frontal des services Web externes comme **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également les directeurs, nom de domaine complet défini pour n’importe quel directeur des services Web externe ou pool directeur doit être unique à partir de n’importe quelle autre directeur ou directeur du pool ainsi qu’un pool frontal ou un serveur frontal. Si vous décidez de remplacer les services web internes avec un nom de domaine complet automatiquement défini, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou un pool directeur.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>DNS équilibrage de charge sur Pools de serveurs Edge
<a name="BK_Edge"> </a>

Vous pouvez déployer DNS équilibrage de charge sur pools de serveurs Edge. Si vous procédez ainsi, vous devez être informé de certaines considérations.
  
Avec DNS équilibrage de charge sur vos serveurs Edge entraîne une perte des capacités de basculement dans les scénarios suivants :
  
- Fédération avec des organisations qui exécutent des versions de Skype pour Business Server antérieures à Lync Server 2010.
    
- Échange de messages instantanés avec les utilisateurs des services de messagerie instantanée publique (IM) AOL et Yahoo!, en plus des fournisseurs basés sur XMPP et des serveurs, tels que Google Talk, actuellement le seul partenaire XMPP pris en charge.
    
Ces scénarios fonctionnera tant que tous les serveurs Edge du pool sont en cours d’exécution, mais si un serveur de périphérie n’est pas disponible, toutes les demandes pour ces scénarios qui lui sont envoyés échoue, au lieu de routage vers un autre serveur de transport Edge.
  
 Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2013 pour obtenir une assistance pour Skype pour Business Server DNS équilibrage de charge sur Edge. Si vous utilisez une version antérieure d’Exchange, les utilisateurs distants n’aura plus de capacités de basculement pour ces scénarios de messagerie unifiée Exchange :
  
- Lecture de leur messagerie vocale d’entreprise sur leur téléphone
    
- Transfert d’appels à partir d’un standard automatique Exchange UM
    
Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.
  
L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Déploiement DNS équilibrage de charge sur Pools de serveurs Edge

Pour déployer DNS équilibrage de charge sur l’interface externe de votre pool de serveurs Edge, vous devez les entrées DNS suivantes :
  
- Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès (par exemple, Access.contoso.com) à l’adresse IP du service Edge d’accès sur un des serveurs de périphérie dans le pool.
    
- Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge de conférence Web (par exemple, webconf.contoso.com) à l’adresse IP du service Edge de conférence Web sur un des serveurs de périphérie dans le pool.
    
- Pour le service Edge Audio/vidéo, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge Audio/vidéo (par exemple, av.contoso.com) à l’adresse IP a / V Edge de service sur un des serveurs de périphérie dans le pool.
    
Pour déployer DNS équilibrage de charge sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A, qui résout le nom de domaine complet interne du pool de serveur de transport Edge à l’adresse IP de chaque serveur du pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>À l’aide du DNS équilibrage de charge sur les Pools de serveurs de médiation
<a name="BK_Mediation"> </a>

Vous pouvez utiliser DNS équilibrage de charge sur les pools de serveurs de médiation autonomes. Tout le trafic SIP et multimédia est équilibré à l’équilibrage de charge DNS.
  
Pour déployer DNS équilibrage de charge dans un pool de serveurs de médiation, vous devez configurer le DNS pour résoudre le nom de domaine complet (par exemple, mediationpool1.contoso.com) du pool pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2 et ainsi de suite).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocage du trafic vers un serveur avec équilibrage de charge DNS
<a name="BK_Mediation"> </a>

Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur. 
  
Notez que pour le trafic de serveur à serveur, Skype pour Business Server utilise l’équilibrage de charge compatibles avec la topologie. Les serveurs lire la topologie publiée dans le magasin Central de gestion pour obtenir les noms de domaine complets des serveurs de la topologie et distribuent automatiquement le trafic entre les serveurs. Pour bloquer un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie. 
  

