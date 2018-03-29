---
title: Configuration système requise pour le serveur Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Résumé : En savoir plus sur la configuration système requise pour le serveur de transport Edge dans Skype pour Business Server.'
ms.openlocfilehash: d4d195d07b13ccfc294054a811cbd6735b2431cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-system-requirements-in-skype-for-business-server-2015"></a>Configuration système requise pour le serveur Edge dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur la configuration système requise pour le serveur de transport Edge dans Skype pour Business Server.
  
Lorsqu’il s’agit de votre Skype pour le déploiement du serveur de transport Edge Server Business, ce sont des choses que vous devez faire pour l’ou les serveurs qui se trouvent dans l’environnement lui-même, ainsi que la planification de la structure de l’environnement. Pour plus d’informations sur la topologie, DNS, les certificats et les aspects de l’infrastructure, consultez la documentation se rapportant aux exigences en matière d’environnement.
  
## <a name="components"></a>Composants

Lorsque vous abordez l’environnement de serveur de transport Edge, nous allons référencer des composants, pour l’essentiel, déployés dans un réseau de périmètre (c’est à dire qu’il est dans un groupe de travail ou un domaine situé en dehors de votre Skype pour structure de domaine Business Server).
  
Tout en gardant ceci à l’esprit, voici les composants qui vous permettront de déployer correctement votre serveur Edge :
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (composants facultatifs qui, s’ils sont inclus, se trouvent sur votre réseau interne) ;
    
- [Équilibreurs de charge](system-requirements.md#LoadBalancers) (vous pouvez avoir l’équilibrage de la charge DNS ou un équilibreur de charge matériel (HUMIDIFICATION à HLB), mais pour un seul serveur Edge, il n’est pas nécessaire)
    
Ces composants sont décrits plus en détails ci-après :
  
### <a name="edge-servers"></a>Serveurs Edge
<a name="EdgeServers"> </a>

Il s’agit de la Skype des serveurs d’entreprise déployé dans votre environnement de périmètre. Leur rôle est d’envoyer et de recevoir le trafic réseau vers des utilisateurs externes pour les services offerts par votre Skype interne pour le déploiement du serveur de l’entreprise. Pour ce faire, chaque serveur de transport Edge s’exécute :
  
- **Le service Edge d’accès**: fournit un point de connexion unique et approuvée pour le trafic de protocole SIP (Session Initiation) entrant et sortant.
    
- **Serveur Edge de conférence Web service**: permet aux utilisateurs externes de participer à des conférences hébergées sur votre Skype interne pour un environnement de serveur d’entreprise.
    
- **A / V Edge service**: fait d’audio, de vidéo, de partage d’applications et utilisateurs disponibles à externe de transfert de fichier.
    
- **Le service Proxy de XMPP**: accepte et envoie des messages (XMPP) de protocole de messagerie et de présence extensible vers et à partir des partenaires fédérés de XMPP configurés.
    
Utilisateurs externes autorisés peuvent utiliser vos serveurs Edge pour vous connecter à votre Skype interne pour le déploiement du serveur de l’entreprise, mais dans le cas contraire, elles ne fournissent aucun autre accès à votre réseau interne pour tout le monde.
  
> [!NOTE]
> Les serveurs Edge sont déployés pour fournir des connexions de Skype activé pour les clients de l’entreprise et des autres serveurs Edge (dans les scénarios de fédération). Impossible de se connecter à partir d’autres types de point de terminaison client ou serveur. Le serveur de passerelle de XMPP peut autoriser les connexions avec les partenaires XMPP configurés. Mais, là encore, celles sont les seuls types de client et de la fédération qui fonctionnent. 
  
### <a name="reverse-proxies"></a>Proxys inverses
<a name="ReverseProxies"> </a>

Un serveur proxy inverse (RP) n’a aucun Skype pour le rôle de serveur de l’entreprise, mais est un composant essentiel d’un déploiement de serveur de transport Edge. Un proxy inverse permet aux utilisateurs externes :
  
- de participer à des réunions ou à des conférences à distance via des URL simples ;
    
- de télécharger le contenu des réunions ;
    
- de développer des groupes de distribution ;
    
- de obtenir un certificat utilisateur pour l’authentification basée sur un certificat client ;
    
- télécharger des fichiers à partir du serveur de carnet d’adresses, ou pour envoyer des requêtes au service d’adresse livre requête sur le Web.
    
- d’obtenir des mises à jour de logiciels clients et des périphériques.
    
Et pour les appareils mobiles :
  
- Il leur permet de détecter automatiquement les serveurs frontaux offrant des services de mobilité.
    
- Il active les notifications de transmission à partir d’Office 365 pour les périphériques mobiles.
    
Vous trouverez nos recommandations de proxy inverse en cours sur la page de [L’Infrastructure de téléphonie pour Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947483) . Par conséquent, votre proxy inverse :
  
- utiliser la sécurité TLS (Transport Layer Security) mise en œuvre dans votre environnement via les certificats publics pour se connecter aux services web externes publiés du :
    
  - Pool de directeur ou de directeur
    
  - Pool de serveur principal ou frontal avant
    
- publier des sites web internes à l’aide de certificats pour le chiffrement ou les publier de manière non chiffrée en cas de nécessité ;
    
- publier un site web hébergé en interne à l’aide d’un nom de domaine complet ;
    
- publier tout le contenu du site web hébergé. Par défaut, vous pouvez utiliser la ** / ** directive, qui est reconnue par la plupart des serveurs web pour signifier « Publier tout le contenu sur le serveur web. » Vous pouvez également modifier la directive — par exemple, **/Uwca/\***, qui signifie « publie tout le contenu du répertoire virtuel Ucwa. »
    
- exiger des connexions TLS avec les clients qui demandent du contenu à partir de votre site web publié ;
    
- accepter les certificats avec des entrées d’autres noms du sujet ;
    
- autoriser la liaison d’un certificat à une interface ou un écouteur par le biais duquel le nom de domaine complet des services web externes sera résolu. Les configurations d’écouteurs sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une même interface ;
    
- autoriser la configuration de la gestion des en-têtes d’hôtes. Souvent, l’en-tête d’hôte original envoyé par le client demandeur doit être passé en toute transparence, et non en cours de modification par le serveur proxy inverse.
    
- autoriser le pontage du trafic TLS à partir d’un port défini de manière externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Votre proxy inverse peut déchiffrer le paquet sur l’accusé de réception et puis recrypter le paquet lors de l’envoi.
    
- autoriser le pontage du trafic TCP non chiffré à partir d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080) ;
    
- autoriser la configuration d’Authentification NTLM, Aucune authentification et Authentification directe ou accepter celles-ci.
    
Si votre serveur proxy inverse peut répondre à tous les besoins de cette liste, vous devez être judicieux d’aller, mais gardez à l’esprit nos recommandations sur le lien ci-dessus.
  
### <a name="firewalls"></a>Pare-feu
<a name="Firewalls"> </a>

Vous devez placer votre déploiement Edge derrière un pare-feu externe, mais nous vous recommandons d’activer deux pare-feu, à savoir un pare-feu externe et un pare-feu interne, situé entre l’environnement Edge et votre environnement interne. La documentation de l’ensemble de nos scénarios fait référence à deux pare-feu. Cette configuration est recommandée, car elle garantit un routage strict dans l’ensemble du réseau, tout en doublant la protection de votre réseau interne derrière le pare-feu.
  
### <a name="directors"></a>directeurs
<a name="Directors"> </a>

Ce rôle est facultatif. Il peut être un seul serveur ou un pool de serveurs exécutant le rôle de directeur. Il s’agit d’un rôle sur le Skype interne pour environnement Business Server.
  
Le directeur est un serveur de tronçon suivant interne qui reçoit le trafic SIP entrant des serveurs Edge destiné à Skype pour serveurs internes du serveur de l’entreprise. Il authentifie au préalable les requêtes entrantes et les redirige vers le pool ou le serveur central de l’utilisateur. L’authentification préalable vous permet de supprimer les requêtes des comptes d’utilisateur non identifiés.
  
Pourquoi est-ce important ? Il est une fonction importante pour un directeur pour protéger les serveurs Standard Edition Server et les serveurs frontaux ou les pools de Front-End contre le trafic malveillant, comme les attaques de déni de service (DoS). Si votre réseau est inondé de trafic d’externe non valide, le trafic s’arrête sur le directeur.
  
### <a name="load-balancers"></a>Équilibreurs de charge matérielle
<a name="LoadBalancers"> </a>

Le Skype pour Business Server 2015 est mis à l’échelle consolidés topologie de bord optimisé à des fins équilibrage pour les nouveaux déploiements de charge de DNS, et que nous recommandons. Si vous avez besoin d’une disponibilité élevée, nous vous recommandons d’utiliser un équilibreur de charge matériel pour une situation spécifique :
  
- Messagerie unifiée Exchange pour les utilisateurs distants à l’aide de la messagerie unifiée Exchange **antérieures** à Exchange 2013.
    
> [!IMPORTANT]
> Il est essentiel de noter que vous ne pouvez pas mélanger les équilibreurs de charge matérielle. Dans votre Skype pour environnement Business Server toutes les interfaces doivent utiliser DNS ou HUMIDIFICATION à HLB. 
  
> [!NOTE]
> Serveur direct de retour (DSR) NAT n’est pas pris en charge pour Skype pour Business Server 2015. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requise pour équilibrage de la charge pour serveurs de bord Edge serveurs en cours d’exécution A / V Edge service

Pour n’importe quel serveur de bord en cours d’exécution A / service de V Edge, il s’agit de la configuration requise :
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.
    
- Désactivez le nagling TCP pour la plage de ports externes 50000 à 59999.
    
- N’utilisez pas la traduction d’adresses réseau sur votre pare-feu interne ou externe.
    
- Votre interface interne bord doit se trouver sur un autre réseau que l’interface externe du serveur de transport Edge et le routage entre les deux doit être désactivé.
    
- L’interface externe de n’importe quel serveur de bord en cours d’exécution A / V Edge service doit utiliser des adresses IP routables publiquement et aucun NAT ou port de traduction sur toutes les adresses IP externes de bord.
    
#### <a name="hlb-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Comme avec Lync Server 2013, Skype pour Business Server 2015 n’est plus un grand nombre d’exigences d’affinité de basé sur le cookie. Vous ne devez donc utiliser une persistance cookie **, sauf si** vous allez avoir des pools de Lync Server 2010 avant les serveurs principaux ou frontaux dans votre Skype pour environnement Business Server. Ils doivent l’affinité basée sur les cookies dans la méthode de configuration recommandée pour Lync Server 2010.
  
> [!NOTE]
> Si vous décidez d’activer l’affinité basée sur les cookies pour l’équilibreur de charge matérielle, cela ne posera pas problème, même si votre environnement ne l’exige pas. 
  
Si votre environnement ne requiert **pas** l’affinité basée sur les cookies :
  
- **Sur la règle de publication proxy inverse pour le port 443, valeur **en-tête de l’hôte vers l’avant** .** Cela garantit que l’URL d’origine sera transférée.
    
Pour les déploiements qui **requièrent** l’affinité basée sur les cookies :
  
- **Sur la règle de publication proxy inverse pour le port 443, valeur **en-tête de l’hôte vers l’avant** .** Cela garantit que l’URL d’origine sera transférée.
    
- Le cookie d’équilibreur de la charge matérielle **ne doit pas** être marquée de httpOnly.
    
- Le cookie d’équilibreur de la charge matérielle **ne doit pas** avoir un délai d’expiration.
    
- Le cookie d’équilibrage de la charge matérielle **doit** être nommé de **MS WSMAN** (il s’agit de la valeur que les services Web s’attendre, et il ne peut pas être modifié).
    
- Le cookie d’équilibrage de la charge matérielle **doit** être définie dans chaque réponse HTTP pour laquelle la demande HTTP entrante n’ont un cookie, indépendamment de si une réponse HTTP précédente sur la même connexion TCP avait obtenu un cookie. Si votre équilibreur de charge matériel optimise l’insertion de cookie seulement se produise une fois par connexion TCP, cette optimisation **ne doit pas** être utilisé.
    
> [!NOTE]
> Il est généralement utilisé pour les configurations d’humidification à HLB à utiliser l’affinité de la source et 20 minutes TCP durée de vie de session qui est parfaite pour Skype pour Business Server 2015 et ses clients, car l’état de session est maintenue par le biais de l’utilisation de client, et/ou de cette interaction de l’application. 
  
Si vous déployez des appareils mobiles, votre équilibreur de charge matérielle doit être capable d’équilibrer la charge de requêtes individuelles au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!IMPORTANT]
> Les programmes d’équilibrage de charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 est en mesure de vous fournir les paramètres spécifiques, si nécessaire. 
  
Voici les exigences d’humidification à HLB pour le directeur (facultatif) et le pool de Front-End (obligatoire) des Services Web :
  
- Pour votre VIP de Services Web internes, la valeur Source_addr, persistance (interne le port 80, 443) sur votre HUMIDIFICATION à HLB. Pour Skype pour Business Server 2015, persistance de Source_addr signifie que plusieurs connexions provenant d’une adresse IP unique sont toujours envoyées à un serveur, pour maintenir l’état de session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre votre serveur proxy inverse et d’humidification à HLB de votre pool de tronçon suivant, créez une règle pour autoriser https : le trafic sur le port 4443, à partir de votre serveur proxy inverse votre HUMIDIFICATION à HLB. L’équilibreur de charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Synthèse des conditions requises en matière d’affinité par l’équilibreur de charge matérielle

|**Emplacement de client/utilisateur**|**Exigences d’affinité de nom de domaine complet des services web externes**|**Exigences d’affinité FQSN des services web interne**|
|:-----|:-----|:-----|
|Skype pour Business Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype pour Business Web App (pour les utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype pour Business Web App (pour les utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Surveillance des ports pour les équilibreurs de charge matérielle

Vous permet de définir la surveillance de port sur votre équilibreurs de charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles, en raison d’une défaillance du matériel ou des communications. Par exemple, si le service de serveur frontal (RTCSRV) s’arrête car le pool Front-End ou de serveur frontal échoue, le contrôle d’humidification à HLB doit également cesser de recevoir le trafic sur les Services Web. Vous devez implémenter la surveillance des ports sur le programme d’équilibrage de charge matérielle pour surveiller les éléments suivants pour l’interface externe de l’équilibreur de charge matérielle :
  
|**IP/Port virtuel**|**Port de nœud**|**Moniteur d’ordinateur/nœud**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool de\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTPS  <br/> |
|\<pool de\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

Nous avons traité les exigences matérielles et logicielles de serveur de transport Edge dans notre documentation globale de la [configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) .
  
## <a name="collocation"></a>Colocalisation

Nous avons traité colocalisation de serveur de transport Edge dans notre documentation [Bases de topologie Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

