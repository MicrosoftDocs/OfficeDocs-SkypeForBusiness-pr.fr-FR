---
title: Edge requise serveur dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Résumé : Découvrez la configuration système requise pour le serveur de périphérie dans Skype pour Business Server.'
ms.openlocfilehash: ede0f7f933f246496593519afa035f09ef402bfb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013137"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Edge requise serveur dans Skype pour Business Server
 
**Résumé :** Découvrez la configuration système requise pour le serveur de périphérie dans Skype pour Business Server.
  
Lorsqu’il s’agit de votre Skype pour le déploiement du serveur de périphérie Business Server, ce sont les éléments que vous devez faire pour l’ou les serveurs qui se trouvent dans l’environnement lui-même, ainsi que la planification de la structure de l’environnement. Pour plus d’informations sur la topologie, DNS, les certificats et les aspects de l’infrastructure, consultez la documentation se rapportant aux exigences en matière d’environnement.
  
## <a name="components"></a>Composants

Lorsque vous abordez l’environnement de serveur de transport Edge, nous allons référencer des composants, pour l’essentiel, déployés dans un réseau de périmètre (c’est à dire qu’il est dans un groupe de travail ou un domaine situé en dehors de votre Skype pour la structure de domaine Business Server).
  
Tout en gardant ceci à l’esprit, voici les composants qui vous permettront de déployer correctement votre serveur Edge :
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (composants facultatifs qui, s’ils sont inclus, se trouvent sur votre réseau interne) ;
    
- [Équilibreurs de charge](system-requirements.md#LoadBalancers) (vous pouvez avoir l’équilibrage de charge DNS ou un équilibreur de charge matérielle (HLB), mais pour un seul serveur de périphérie, il n’est pas nécessaire)
    
Ces composants sont décrits plus en détails ci-après :
  
### <a name="edge-servers"></a>Serveurs Edge
<a name="EdgeServers"> </a>

Il s’agit du Skype des serveurs d’entreprise déployés dans votre environnement de périmètre. Leur rôle consiste à envoyer et recevoir le trafic réseau aux utilisateurs externes pour les services offerts par votre Skype pour le déploiement de serveur d’entreprise interne. Pour ce faire, chaque serveur de périphérie exécute :
  
- **Service Edge d’accès**: fournit un point de connexion unique approuvé, pour le trafic de protocole SIP (Session Initiation) sortant et entrant.
    
- **Service Edge de conférence Web**: permet aux utilisateurs externes de participer à des réunions qui sont hébergées sur votre Skype pour un environnement Business Server interne.
    
- **A / V Edge service**: rend audio, vidéo, partage d’application et d’accessibles aux utilisateurs externes de transfert de fichiers.
    
- **Service Proxy XMPP**: accepte et envoie des messages (XMPP) protocole extensible de messagerie et de présence avec des partenaires fédérés XMPP configurés.
    
Les utilisateurs externes autorisés peuvent utiliser vos serveurs de périphérie pour se connecter à votre Skype pour le déploiement de serveur d’entreprise interne, mais dans le cas contraire, qu’ils ne fournissent aucune autre accès à votre réseau interne pour tout le monde.
  
> [!NOTE]
> Serveurs Edge sont déployés pour fournir des connexions pour Skype activé pour les clients d’entreprise et les autres serveurs de périphérie (dans les scénarios de fédération). Impossible de se connecter à partir d’autres types de point de terminaison client ou serveur. Le serveur de passerelle XMPP peut autoriser les connexions avec les partenaires XMPP configurés. Mais là encore, ceux sont les seuls types de client et la fédération fonctionnent. 

> [!NOTE]
> XMPP passerelles et les proxys sont disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Pour plus d’informations, voir [la fédération XMPP de migration](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Proxys inverses
<a name="ReverseProxies"> </a>

Un serveur proxy inverse (RP) n’a aucune Skype pour le rôle de serveur d’entreprise, mais il est essentiel d’un déploiement de serveur Edge. Un proxy inverse permet aux utilisateurs externes :
  
- de participer à des réunions ou à des conférences à distance via des URL simples ;
    
- de télécharger le contenu des réunions ;
    
- de développer des groupes de distribution ;
    
- de obtenir un certificat utilisateur pour l’authentification basée sur un certificat client ;
    
- télécharger des fichiers à partir du serveur de carnet d’adresses ou soumettre des requêtes au service de requête sur le Web téléchargeable adresse.
    
- d’obtenir des mises à jour de logiciels clients et des périphériques.
    
Et pour les appareils mobiles :
  
- elle leur permet de découvrir automatiquement les serveurs frontaux qui offre des services de mobilité.
    
- Il permet de notifications push à partir d’Office 365 pour les appareils mobiles.
    
Nos recommandations en cours de proxy inverse, vous pouvez trouver dans la page de [L’Infrastructure de téléphonie pour Skype pour les entreprises](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Si votre serveur proxy inverse :
  
- utiliser la sécurité TLS (Transport Layer Security) mise en œuvre dans votre environnement via les certificats publics pour se connecter aux services web externes publiés du :
    
  - Directeur ou pool directeur
    
  - Serveur frontal pool frontal ou serveur
    
- publier des sites web internes à l’aide de certificats pour le chiffrement ou les publier de manière non chiffrée en cas de nécessité ;
    
- publier un site web hébergé en interne à l’aide d’un nom de domaine complet ;
    
- publier tout le contenu du site web hébergé. Par défaut, vous pouvez utiliser la ** / ** directive, qui est reconnue par la plupart des serveurs web pour signifier « Publier tout le contenu sur le serveur web ». Vous pouvez également modifier la directive — par exemple, **/Uwca/\***, ce qui signifie « publie tout le contenu sous le répertoire virtuel Ucwa. »
    
- exiger des connexions TLS avec les clients qui demandent du contenu à partir de votre site web publié ;
    
- accepter les certificats avec des entrées d’autres noms du sujet ;
    
- autoriser la liaison d’un certificat à une interface ou un écouteur par le biais duquel le nom de domaine complet des services web externes sera résolu. Les configurations d’écouteurs sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une même interface ;
    
- autoriser la configuration de la gestion des en-têtes d’hôtes. Souvent, l’en-tête d’hôte d’origine envoyé par le client demande doit être transmis en toute transparence, au lieu d’être modifiée par le proxy inverse.
    
- autoriser le pontage du trafic TLS à partir d’un port défini de manière externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Le proxy inverse peut déchiffrer le paquet sur réception et puis renouvelez chiffrement le paquet sur l’envoi.
    
- autoriser le pontage du trafic TCP non chiffré à partir d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080) ;
    
- autoriser la configuration d’Authentification NTLM, Aucune authentification et Authentification directe ou accepter celles-ci.
    
Si votre serveur proxy inverse peut traiter tous les besoins dans cette liste, vous devez être à atteindre, mais gardez à l’esprit nos recommandations sur le lien ci-dessus.
  
### <a name="firewalls"></a>Pare-feu
<a name="Firewalls"> </a>

Vous devez placer votre déploiement Edge derrière un pare-feu externe, mais nous vous recommandons d’activer deux pare-feu, à savoir un pare-feu externe et un pare-feu interne, situé entre l’environnement Edge et votre environnement interne. La documentation de l’ensemble de nos scénarios fait référence à deux pare-feu. Cette configuration est recommandée, car elle garantit un routage strict dans l’ensemble du réseau, tout en doublant la protection de votre réseau interne derrière le pare-feu.
  
### <a name="directors"></a>directeurs
<a name="Directors"> </a>

Ce rôle est facultatif. Il peut être un serveur unique ou un pool de serveurs qui exécutent le rôle de directeur. Il est un rôle que qui se trouvent dans le Skype pour un environnement Business Server interne.
  
Le directeur est un serveur du tronçon suivant interne qui reçoit le trafic SIP entrant à partir des serveurs Edge qui est destiné à Skype pour les serveurs internes Business Server. Il authentifie au préalable les requêtes entrantes et les redirige vers le pool ou le serveur central de l’utilisateur. L’authentification préalable vous permet de supprimer les requêtes des comptes d’utilisateur non identifiés.
  
Pourquoi est-ce important ? Une fonction importante pour un directeur est de protéger les serveurs Standard Edition Server et serveurs frontaux ou pools frontaux du trafic malveillant, telles que les attaques par déni de service (DoS). Si votre réseau est réparti avec le trafic externe non valide, le trafic s’arrête au directeur.
  
### <a name="load-balancers"></a>Équilibreurs de charge matérielle
<a name="LoadBalancers"> </a>

Le Skype pour Business Server mis à l’échelle de topologie Edge consolidée est optimisé pour de nouveaux déploiements d’équilibrage de la charge DNS et nous vous recommandons ce. Si vous avez besoin d’une disponibilité élevée, nous recommandons d’utiliser un mécanisme d’équilibrage de charge pour une situation spécifique :
  
- Messagerie unifiée Exchange pour les utilisateurs distants à l’aide de la messagerie unifiée Exchange **antérieures** à Exchange 2013.
    
> [!IMPORTANT]
> Il est essentiel de noter que vous ne pouvez pas mélanger les équilibreurs de charge matérielle. Dans votre Skype pour un environnement Business Server toutes les interfaces doivent utiliser matérielle ou DNS. 
  
> [!NOTE]
> Serveur direct renvoyer NAT (DSR) n’est pas pris en charge pour Skype pour Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>conditions requises d’équilibrage de charge matérielle pour les serveurs de périphérie de serveurs Edge exécutant A / V Edge service

Pour n’importe quel serveur Edge A / service Edge v., voici la configuration requise :
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.
    
- Désactivez le nagling TCP pour la plage de ports externes 50000 à 59999.
    
- N’utilisez pas la traduction d’adresses réseau sur votre pare-feu interne ou externe.
    
- L’interface interne Edge doit se trouver sur un autre réseau que l’interface externe du serveur Edge, et routage entre elles doit être désactivé.
    
- L’interface externe de n’importe quel serveur Edge A / V Edge service doit utiliser des adresses IP routables publiquement, mais aucune NAT ou traduction de port sur une des adresses IP Edge externes.
    
#### <a name="hlb-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Skype pour Business Server ne possède pas un grand nombre de conditions d’affinité basée sur les cookies. Afin que vous n’avez pas besoin d’utiliser un cookie persistance **, sauf si** (et il s’agit de Skype pour serveur 2015 spécifiques à l’entreprise) vous devrez Lync Server 2010 Front End Servers ou pools frontaux dans votre Skype pour un environnement Business Server. Ils doivent basée l’affinité dans la méthode de configuration recommandée pour Lync Server 2010.
  
> [!NOTE]
> Si vous décidez d’activer l’affinité basée sur les cookies pour l’équilibreur de charge matérielle, cela ne posera pas problème, même si votre environnement ne l’exige pas. 
  
Si votre environnement ne requiert **pas** l’affinité basée sur les cookies :
  
- Sur la règle de publication proxy inverse pour le port 443, définissez **l’en-tête d’hôte directe** sur **True**. Cela garantit que l’URL d’origine sera transférée.
    
Pour les déploiements qui **requièrent** l’affinité basée sur les cookies :
  
- Sur la règle de publication proxy inverse pour le port 443, définissez **l’en-tête d’hôte directe** sur **True**. Cela garantit que l’URL d’origine sera transférée.
    
- Le cookie de d’équilibrage de la charge matériel **ne doit pas** être marqué httpOnly.
    
- Le cookie de d’équilibrage de la charge matériel **ne doit pas** avoir un délai d’expiration.
    
- Le cookie de d’équilibrage de la charge matériel **doit** être nommé **MS-WSMAN** (il s’agit de la valeur que les services Web prévoient et il ne peut pas être modifié).
    
- Le cookie de d’équilibrage de la charge matériel **doit** être définie dans chaque réponse HTTP pour laquelle la requête HTTP entrante n’ait un cookie, quel que soit ou non une réponse HTTP précédente sur ce même connexion TCP avait obtenu un cookie. Si votre équilibreur de charge matériel optimise cookie insert devant se produire uniquement une fois par une connexion TCP, cette optimisation **ne doit pas** être utilisé.
    
> [!NOTE]
> Il est courant pour les configurations matérielle à utiliser l’affinité source et 20 minutes TCP durée de vie de session qui convient pour Skype pour Business Server et ses clients, étant donné que l’état de session est géré par le biais de l’utilisation de client et/ou d’interaction de l’application. 
  
Si vous déployez des appareils mobiles, votre équilibreur de charge matérielle doit être capable d’équilibrer la charge de requêtes individuelles au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!IMPORTANT]
> Les programmes d’équilibrage de charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 est en mesure de vous fournir les paramètres spécifiques, si nécessaire. 
  
Voici la configuration requise matérielle pour le directeur (facultatif) et le pool frontal (obligatoire) des Services Web :
  
- Définir votre VIP de Services Web internes, persistance Source_addr (interne port 80, 443) sur votre matérielle. Pour Skype pour Business Server, persistance Source_addr signifie que plusieurs connexions provenant d’une adresse IP unique sont toujours envoyées à un serveur, pour maintenir l’état de session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre le proxy inverse et matérielle de votre pool du tronçon suivant, créez une règle pour autoriser le protocole https : le trafic sur le port 4443, à partir de votre serveur proxy inverse pour votre matérielle. L’équilibreur de charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Synthèse des conditions requises en matière d’affinité par l’équilibreur de charge matérielle

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes**|
|:-----|:-----|:-----|
|Skype pour Business Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype pour Business Web App (pour les utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype pour Business Web App (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Surveillance des ports pour les équilibreurs de charge matérielle

Vous définissez le port de surveillance sur votre équilibreurs de charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles, en raison de défaillances matérielles ou les communications. Par exemple, si le service du serveur frontal (RTCSRV) s’arrête, car le pool frontal ou serveur frontal échoue, la surveillance matérielle doit également arrêter de recevoir le trafic sur les Services Web. Vous devez implémenter la surveillance des ports sur le programme d’équilibrage de charge matérielle pour surveiller les éléments suivants pour l’interface externe de l’équilibreur de charge matérielle :
  
|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

Nous avons traité Edge Server Configuration matérielle et logicielle requise dans notre documentation [configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et la [configuration système requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) globale.
  
## <a name="collocation"></a>Colocalisation

Nous avons traité colocation du serveur de transport Edge dans notre documentation [Concepts de topologie de base pour Skype pour Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

