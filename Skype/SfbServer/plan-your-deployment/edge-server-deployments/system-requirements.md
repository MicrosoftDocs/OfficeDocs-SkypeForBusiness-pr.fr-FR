---
title: Configuration requise pour le serveur Edge dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Résumé : en savoir plus sur la configuration système requise pour Edge Server dans Skype entreprise Server.'
ms.openlocfilehash: 01a5cce8dd1ccb85d322b6c66615d022c8d6c2df
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "34277145"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Configuration requise pour le serveur Edge dans Skype entreprise Server
 
**Résumé :** En savoir plus sur la configuration système requise pour serveur Edge dans Skype entreprise Server.
  
Dans le cadre de votre déploiement de serveur Edge Skype entreprise Server, voici ce que vous devez faire pour le ou les serveurs qui se trouvent dans l’environnement proprement dit, ainsi que pour planifier la structure de l’environnement. Pour plus d’informations sur la topologie, DNS, les certificats et les aspects de l’infrastructure, consultez la documentation se rapportant aux exigences en matière d’environnement.
  
## <a name="components"></a>Composants

Lorsque vous discutez dans l’environnement de serveur Edge, nous faisons référence à des composants qui, dans la plupart des cas, sont déployés dans un réseau de périmètre (il s’agit d’un groupe de travail ou d’un domaine extérieur à votre structure de domaine Skype entreprise Server).
  
Tout en gardant ceci à l’esprit, voici les composants qui vous permettront de déployer correctement votre serveur Edge :
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors) (composants facultatifs qui, s’ils sont inclus, se trouvent sur votre réseau interne) ;
    
- [Équilibreurs de charge](system-requirements.md#LoadBalancers) (vous pouvez disposer de l’équilibrage de charge DNS ou d’un équilibreur de charge matérielle (HLB), mais pour un serveur Edge unique, cela n’est pas nécessaire.
    
Ces composants sont décrits plus en détails ci-après :
  
### <a name="edge-servers"></a>Serveurs Edge
<a name="EdgeServers"> </a>

Il s’agit des serveurs Skype entreprise déployés dans votre environnement de périmètre. Son rôle est d’envoyer et de recevoir du trafic réseau à des utilisateurs externes pour les services offerts par votre déploiement interne de Skype entreprise Server. Pour effectuer cette opération, chaque serveur Edge s’exécute comme suit :
  
- **Service Edge d’accès**: fournit un point de connexion unique et approuvé pour le trafic SIP (Session Initiation Protocol) entrant et sortant.
    
- **Service Edge de conférence Web**: permet aux utilisateurs externes de rejoindre des réunions hébergées sur votre environnement Skype entreprise Server interne.
    
- **Service Edge A/V**: permet de rendre les fichiers audio, vidéo, de partage d’application et de transfert de fichiers accessibles aux utilisateurs externes.
    
- **Service proxy XMPP**: accepte et envoie les messages de la messagerie électronique extensible (XMPP) vers et depuis les partenaires fédérés de XMPP configurés.
    
Les utilisateurs externes autorisés peuvent utiliser votre serveur Edge pour vous connecter à votre déploiement Skype entreprise Server interne, mais ils ne fournissent pas d’autres accès à votre réseau interne pour quiconque.
  
> [!NOTE]
> Les serveurs Edge sont déployés de manière à fournir des connexions aux clients Skype entreprise et aux autres serveurs Edge activés (dans les scénarios de Fédération). Vous ne pouvez pas vous connecter à partir du client ou du type de serveurs d’un autre point de terminaison. Le serveur de passerelle XMPP peut autoriser les connexions avec les partenaires XMPP configurés. À l’exception de là, il s’agit des seuls clients et des types de Fédération qui fonctionneront. 

> [!NOTE]
> Les passerelles et les proxys XMPP sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la section migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Proxys inverses
<a name="ReverseProxies"> </a>

Un serveur proxy inverse (RP) ne possède pas de rôle Skype entreprise Server, mais est un composant essentiel d’un déploiement de serveur Edge. Un proxy inverse permet aux utilisateurs externes d’effectuer les opérations suivantes :
  
- de participer à des réunions ou à des conférences à distance via des URL simples ;
    
- de télécharger le contenu des réunions ;
    
- de développer des groupes de distribution ;
    
- de obtenir un certificat utilisateur pour l’authentification basée sur un certificat client ;
    
- Télécharger des fichiers à partir du serveur du carnet d’adresses, ou pour renvoyer des requêtes au service de requête sur le carnet d’adresses.
    
- d’obtenir des mises à jour de logiciels clients et des périphériques.
    
Et pour les appareils mobiles :
  
- elle permet aux utilisateurs finaux de détecter automatiquement les serveurs frontaux proposant des services de mobilité.
    
- Il permet d’activer les notifications de transmission d’Office 365 sur les appareils mobiles.
    
[Pour](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) plus d’informations, consultez nos recommandations en matière de proxy inverse. Par conséquent, votre proxy inverse :
  
- utiliser la sécurité TLS (Transport Layer Security) mise en œuvre dans votre environnement via les certificats publics pour se connecter aux services web externes publiés du :
    
  - Pool de directeurs ou de réalisateurs
    
  - Serveur frontal ou liste de front-end
    
- publier des sites web internes à l’aide de certificats pour le chiffrement ou les publier de manière non chiffrée en cas de nécessité ;
    
- publier un site web hébergé en interne à l’aide d’un nom de domaine complet ;
    
- publier tout le contenu du site web hébergé. Par défaut, vous pouvez utiliser la ** / **directive *, qui est reconnue par la plupart des serveurs Web, « publier tout le contenu sur le serveur Web ». Vous pouvez également modifier la directive (par exemple, * */Uwca/\\* * *), ce qui signifie « publier tout le contenu sous le répertoire virtuel Ucwa ».
    
- exiger des connexions TLS avec les clients qui demandent du contenu à partir de votre site web publié ;
    
- accepter les certificats avec des entrées d’autres noms du sujet ;
    
- autoriser la liaison d’un certificat à une interface ou un écouteur par le biais duquel le nom de domaine complet des services web externes sera résolu. Les configurations d’écouteurs sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une même interface ;
    
- autoriser la configuration de la gestion des en-têtes d’hôtes. Dans la plupart des cas, l’en-tête d’hôte d’origine envoyé par le client demandant doit être passé transparent au lieu d’être modifié par le proxy inverse.
    
- autoriser le pontage du trafic TLS à partir d’un port défini de manière externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Votre proxy inverse risque de déchiffrer le paquet en réception, puis de le rechiffrer lors de l’envoi.
    
- autoriser le pontage du trafic TCP non chiffré à partir d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080) ;
    
- autoriser la configuration d’Authentification NTLM, Aucune authentification et Authentification directe ou accepter celles-ci.
    
Si votre proxy inverse est en mesure de répondre à tous les besoins de cette liste, vous devriez être assuré, mais n’oubliez pas nos recommandations sur le lien fourni ci-dessus.
  
### <a name="firewalls"></a>Pare-feu
<a name="Firewalls"> </a>

Vous devez placer votre déploiement Edge derrière un pare-feu externe, mais nous vous recommandons d’activer deux pare-feu, à savoir un pare-feu externe et un pare-feu interne, situé entre l’environnement Edge et votre environnement interne. La documentation de l’ensemble de nos scénarios fait référence à deux pare-feu. Cette configuration est recommandée, car elle garantit un routage strict dans l’ensemble du réseau, tout en doublant la protection de votre réseau interne derrière le pare-feu.
  
### <a name="directors"></a>directeurs
<a name="Directors"> </a>

Ce rôle est facultatif. Il peut s’agir d’un serveur unique ou d’un ensemble de serveurs exécutant le rôle directeur. Il s’agit d’un rôle déterminé dans l’environnement interne Skype entreprise Server.
  
Le directeur est un serveur interne tronçon suivant qui reçoit le trafic SIP entrant provenant des serveurs Edge destinés à des serveurs internes Skype entreprise Server. Il authentifie au préalable les requêtes entrantes et les redirige vers le pool ou le serveur central de l’utilisateur. L’authentification préalable vous permet de supprimer les requêtes des comptes d’utilisateur non identifiés.
  
Pourquoi est-ce important ? Dans le cadre d’un réalisateur, il est important de protéger les serveurs Standard Edition et les serveurs frontaux ou les listes frontales du trafic malveillant, par exemple pour les attaques par déni de service (DoS). Si votre réseau est inondé de trafic externe non valide, le trafic s’arrête au directeur.
  
### <a name="load-balancers"></a>Équilibreurs de charge matérielle
<a name="LoadBalancers"> </a>

La topologie de périphérie consolidée de Skype entreprise Server est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements et nous vous recommandons de procéder comme suit. Si vous avez besoin d’une haute disponibilité, nous vous recommandons d’utiliser un équilibrage de charge matérielle pour une situation spécifique :
  
- Exchange UM pour les utilisateurs distants utilisant la messagerie unifiée Exchange **avant** Exchange 2013.
    
> [!IMPORTANT]
> Il est essentiel de noter que vous ne pouvez pas mélanger les équilibreurs de charge matérielle. Dans votre environnement Skype entreprise Server, toutes les interfaces doivent utiliser DNS ou HLB. 
  
> [!NOTE]
> Le service de traduction d’adresses réseau (DSR) direct Server n’est pas pris en charge par Skype entreprise Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Configuration requise pour le service d’équilibrage de la charge matérielle pour les serveurs Edge serveur Edge exécutant le service Edge A/V

Pour tout serveur Edge exécutant le service Edge A/V, vous devez disposer des éléments suivants :
  
- Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.
    
- Désactivez le nagling TCP pour la plage de ports externes 50000 à 59999.
    
- N’utilisez pas la traduction d’adresses réseau sur votre pare-feu interne ou externe.
    
- Votre interface interne Edge doit être située sur un autre réseau que votre interface externe serveur Edge, et le routage entre ces derniers doit être désactivé.
    
- L’interface externe de tout serveur de périphérie exécutant le service Edge A/V doit utiliser des adresses IP routables publiques et aucune traduction NAT ou de port sur l’une des adresses IP externes Edge.
    
#### <a name="hlb-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Skype entreprise Server ne possède pas de nombreuses exigences d’affinités basées sur des cookies. Par conséquent, si vous n’avez pas besoin d’utiliser une persistance basée sur les cookies **, sauf** (et ce n’est pas le cas pour Skype entreprise Server 2015), vous envisagez d’utiliser des serveurs frontaux ou des listes frontales Lync Server 2010 dans votre environnement Skype entreprise Server. Ils ont besoin d’une affinité basée sur les cookies dans la méthode de configuration recommandée pour Lync Server 2010.
  
> [!NOTE]
> Si vous décidez d’activer l’affinité basée sur les cookies pour l’équilibreur de charge matérielle, cela ne posera pas problème, même si votre environnement ne l’exige pas. 
  
Si votre environnement ne requiert **pas** l’affinité basée sur les cookies :
  
- Sur la règle de publication de proxy inverse pour le port 443, définissez **Forward Header Header** sur **true**. Cela garantit que l’URL d’origine sera transférée.
    
Pour les déploiements qui **requièrent** l’affinité basée sur les cookies :
  
- Sur la règle de publication de proxy inverse pour le port 443, définissez **Forward Header Header** sur **true**. Cela garantit que l’URL d’origine sera transférée.
    
- Le cookie d’équilibrage de charge matérielle **ne doit pas** être marqué en tant que httpOnly.
    
- Le cookie d’équilibrage de charge matérielle **ne doit pas** avoir d’heure d’expiration.
    
- Le cookie de l’équilibrage de charge matérielle **doit** être appelé **MS-WSMan** (il s’agit de la valeur attendue par les services Web et ne peut pas être modifié).
    
- Le cookie d’équilibrage de charge matérielle **doit** être défini dans chaque réponse HTTP pour laquelle la requête http entrante n’a pas de cookie, qu’il s’agisse d’une réponse http précédente ou d’un cookie. Si le système d’équilibrage de la charge matérielle optimise la fonction d’insertion de cookie pour une seule fois par connexion TCP, cette optimisation ne **doit pas** être utilisée.
    
> [!NOTE]
> Il est courant de faire en sorte que les configurations HLB utilisent la durée de vie de la session par affinité source et de 20 minutes dans le cadre de la session du serveur Skype entreprise Server, car l’état de session est maintenu par le biais de l’utilisation du client et/ou de l’interaction avec les applications. 
  
Si vous déployez des appareils mobiles, votre équilibreur de charge matérielle doit être capable d’équilibrer la charge de requêtes individuelles au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!IMPORTANT]
> Les programmes d’équilibrage de charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 est en mesure de vous fournir les paramètres spécifiques, si nécessaire. 
  
Voici la configuration requise pour HLB pour le directeur (facultatif) et les services Web de pool frontal (requis) :
  
- Pour vos VIP de services Web internes, définissez persistance de Source_addr (port interne 80, 443) sur votre HLB. Dans le cas de Skype entreprise Server, la persistance de Source_addr implique que plusieurs connexions venant d’une seule adresse IP sont toujours envoyées à un serveur pour conserver l’état de la session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre votre proxy inverse et le HLB du pool de sauts suivant, créez une règle pour autoriser https : trafic sur le port 4443, de votre proxy inverse vers votre HLB. L’équilibreur de charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Synthèse des conditions requises en matière d’affinité par l’équilibreur de charge matérielle

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes**|
|:-----|:-----|:-----|
|Skype entreprise Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype entreprise Web App (utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype entreprise Web App (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Surveillance des ports pour les équilibreurs de charge matérielle

Vous définissez le contrôle de port sur vos équilibreurs de charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles en raison d’une défaillance matérielle ou de communication. Par exemple, si le service serveur frontal (RTCSRV) s’arrête en raison d’un dysfonctionnement du serveur frontal ou du pool frontal, la surveillance de HLB doit également arrêter la réception du trafic sur les services Web. Vous devez implémenter la surveillance des ports sur le programme d’équilibrage de charge matérielle pour surveiller les éléments suivants pour l’interface externe de l’équilibreur de charge matérielle :
  
|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>du pool  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>du pool  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucune  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

Nous avons couvert la configuration matérielle et logicielle requise pour Microsoft Edge Server et la configuration requise pour Skype [entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et la [Configuration système requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Colocalisation

Nous avons couvert la colocalisation du serveur Edge dans nos notions de base sur la [topologie de Skype entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

