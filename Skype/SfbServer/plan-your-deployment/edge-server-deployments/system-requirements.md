---
title: Configuration requise pour le serveur Edge dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Résumé : Découvrez la configuration système requise pour le serveur Edge dans Skype entreprise Server.'
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221024"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Configuration requise pour le serveur Edge dans Skype entreprise Server
 
**Résumé :** En savoir plus sur la configuration système requise pour le serveur Edge dans Skype entreprise Server.
  
En ce qui concerne le déploiement de votre serveur Edge Skype entreprise Server, il s’agit des éléments que vous devez effectuer pour le serveur ou les serveurs qui se trouvent dans l’environnement lui-même, ainsi que la planification de la structure de l’environnement. Pour plus d’informations sur la topologie, le DNS, les certificats et d’autres problèmes liés à l’infrastructure, consultez la documentation sur les exigences environnementales.
  
## <a name="components"></a>Composants

Lors de la présentation de l’environnement de serveur Edge, nous référençons des composants qui sont, pour la plupart, déployés dans un réseau de périmètre (c’est-à-dire, soit dans un groupe de travail, soit dans un domaine qui se trouve en dehors de votre structure de domaine Skype entreprise Server).
  
Gardez cela à l’esprit qu’il s’agit des composants que vous devez garder à l’esprit pour déployer correctement votre serveur Edge :
  
- [Serveurs de périphérie](system-requirements.md#EdgeServers)
    
- [Proxys inverses](system-requirements.md#ReverseProxies)
    
- [Pare-feu](system-requirements.md#Firewalls)
    
- [Directeurs](system-requirements.md#Directors) (ceux-ci sont facultatifs et, s’ils sont inclus, ils se trouvent sur votre réseau interne)
    
- [Équilibreurs de charge](system-requirements.md#LoadBalancers) (vous pouvez avoir un équilibrage de la charge DNS ou un équilibreur de la charge matérielle (charge matérielle), mais pour un serveur Edge unique, cela n’est pas nécessaire)
    
Vous trouverez plus d’informations sur chacun de ces éléments ci-dessous :
  
### <a name="edge-servers"></a>Serveurs de périphérie
<a name="EdgeServers"> </a>

Il s’agit des serveurs Skype entreprise déployés dans votre environnement de périmètre. Leur rôle est d’envoyer et de recevoir du trafic réseau vers des utilisateurs externes pour les services offerts par votre déploiement Skype entreprise Server interne. Pour effectuer cette opération correctement, chaque serveur Edge exécute les opérations suivantes :
  
- **Service Edge d’accès**: fournit un point de connexion unique et approuvé pour le trafic SIP (Session Initiation Protocol) entrant et sortant.
    
- **Service Edge de conférence Web**: permet aux utilisateurs externes de participer à des réunions hébergées sur votre environnement Skype entreprise Server interne.
    
- **Service Edge A/V**: rend l’audio, la vidéo, le partage d’application et le transfert de fichiers accessibles aux utilisateurs externes.
    
- **Service proxy XMPP**: accepte et envoie les messages XMPP (extensible Messaging and Presence Protocol) vers et depuis les partenaires fédérés XMPP configurés.
    
Les utilisateurs externes autorisés peuvent utiliser vos serveurs Edge pour se connecter à votre déploiement interne de Skype entreprise Server, mais ils ne fournissent pas d’autre accès à votre réseau interne pour personne.
  
> [!NOTE]
> Les serveurs Edge sont déployés pour fournir des connexions pour les clients Skype entreprise et les autres serveurs Edge activés (dans les scénarios de Fédération). Vous ne pouvez pas vous connecter à partir de types de client ou de serveur de point de terminaison. Le serveur de passerelle XMPP peut autoriser les connexions avec les partenaires XMPP configurés. Mais encore une fois, il s’agit du seul type de client et de Fédération qui fonctionnera. 

> [!NOTE]
> Les passerelles XMPP et les proxys sont disponibles dans Skype entreprise Server 2015, mais ne sont plus pris en charge dans Skype entreprise Server 2019. Pour plus d’informations, consultez la rubrique migration de la [Fédération XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Proxys inverses
<a name="ReverseProxies"> </a>

Un serveur de proxy inverse n’a pas de rôle Skype entreprise Server, mais est un composant essentiel d’un déploiement de serveur Edge. Un proxy inverse permet aux utilisateurs externes de :
  
- Connectez-vous à des réunions ou à des conférences rendez-vous à l’aide d’URL simples.
    
- Télécharger le contenu de la réunion.
    
- Développez groupes de distribution.
    
- obtenir des certificats utilisateur pour l’authentification basée sur un certificat client
    
- Téléchargez des fichiers à partir du serveur de carnet d’adresses ou envoyez des requêtes au service de requête Web du carnet d’adresses.
    
- obtenir les mises à jour du client et du logiciel du périphérique.
    
Et pour les appareils mobiles :
  
- il leur permet de découvrir automatiquement les serveurs frontaux offrant des services de mobilité.
    
- Il active les notifications de type transmission de Microsoft 365 ou Office 365 sur les appareils mobiles.
    
Nos recommandations de proxy inverse actuelles sont disponibles sur la page [téléphonie de l’infrastructure de téléphonie pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Pour votre proxy inverse :
  
- il doit être en mesure d’utiliser le protocole TLS (Transport Layer Security) introduit dans votre environnement via des certificats publics pour se connecter aux services Web externes publiés de :
    
  - Directeur ou pool directeur
    
  - Serveur frontal ou pool frontal
    
- doit pouvoir publier des sites Web internes à l’aide de certificats pour le chiffrement, ou les publier sur des moyens non chiffrés, si nécessaire.
    
- il doit être en mesure de publier un site Web hébergé en interne de façon externe à l’aide d’un nom de domaine complet (FQDN).
    
- doit être en mesure de publier tout le contenu de votre site Web hébergé. Par défaut, vous pouvez utiliser la **/\\** directive *, qui est reconnue par la plupart des serveurs Web comme signifiant « publier tout le contenu sur le serveur Web ». Vous pouvez également modifier la directive (par exemple, * */Uwca/ \\ * * *), ce qui signifie « publier tout le contenu sous le répertoire virtuel Ucwa ».
    
- doit exiger des connexions TLS avec des clients qui demandent du contenu à partir de votre site Web publié.
    
- doit accepter les certificats avec des entrées SAN.
    
- doit être en mesure d’autoriser la liaison d’un certificat à un écouteur ou à une interface par le biais duquel le nom de domaine complet des services Web externes est résolu. Les configurations de l’écouteur sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une seule interface.
    
- doit autoriser la configuration de la gestion des en-têtes d’hôte. Souvent, l’en-tête d’hôte d’origine envoyé par le client demandeur doit être passé de manière transparente, au lieu d’être modifié par le proxy inverse.
    
- doit autoriser le pontage du trafic TLS à partir d’un port défini de manière externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Votre proxy inverse peut déchiffrer le paquet lors de sa réception, puis le rechiffrer lors de l’envoi.
    
- doit autoriser le pontage du trafic TCP non chiffré à partir d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080).
    
- doit autoriser la configuration ou l’acceptation de l’authentification NTLM, aucune authentification et authentification directe.
    
Si votre proxy inverse peut répondre à tous les besoins de cette liste, vous devez être prudent, mais gardez à l’esprit nos recommandations sur le lien fourni ci-dessus.
  
### <a name="firewalls"></a>Pare-feu
<a name="Firewalls"> </a>

Vous devez placer votre déploiement Edge derrière un pare-feu externe, mais nous vous recommandons d’avoir deux pare-feu, un externe et un interne entre l’environnement de périmètre et votre environnement interne. Toutes les informations de notre documentation comportent deux pare-feu. Nous vous recommandons d’utiliser deux pare-feu, car cela garantit un routage strict entre l’un et l’autre réseau, et double la protection du pare-feu de votre réseau interne.
  
### <a name="directors"></a>Directeurs
<a name="Directors"> </a>

Il s’agit d’un rôle facultatif. Il peut s’agir d’un serveur unique ou d’un pool de serveurs exécutant le rôle directeur. Il s’agit d’un rôle de l’environnement interne Skype entreprise Server.
  
Le directeur est un serveur de tronçon suivant interne qui reçoit le trafic SIP entrant des serveurs Edge destinés aux serveurs internes Skype entreprise Server. Il procède à l’authentification préalable des demandes entrantes et les redirige vers le serveur ou le pool d’accueil d’un utilisateur. Cette préauthentification vous permet de supprimer les demandes de comptes d’utilisateur non identifiés.
  
Pourquoi cela est-il important ? Une fonction importante pour un directeur est de protéger les serveurs Standard Edition et les serveurs frontaux ou les pools frontaux contre le trafic malveillant, tels que les attaques par déni de service (DoS). Si votre réseau est inondé avec du trafic externe non valide, le trafic s’arrête au niveau du directeur.
  
### <a name="load-balancers"></a>Équilibreurs de charge
<a name="LoadBalancers"> </a>

La topologie Edge consolidée mise à l’ampleur de Skype entreprise Server est optimisée pour l’équilibrage de charge DNS pour de nouveaux déploiements, et nous vous recommandons de le faire. Si vous avez besoin d’une haute disponibilité, nous vous recommandons d’utiliser un programme d’équilibrage de la charge matérielle pour une situation spécifique :
  
- Messagerie unifiée Exchange pour les utilisateurs distants qui utilisent la messagerie unifiée Exchange **avant** Exchange 2013.
    
> [!IMPORTANT]
> Il est essentiel de noter que vous ne pouvez pas mélanger des programmes d’équilibrage de charge. Dans votre environnement Skype entreprise Server, toutes les interfaces doivent utiliser DNS ou charge matérielle. 
  
> [!NOTE]
> Le protocole NAT DSR (direct Server Return) n’est pas pris en charge pour Skype entreprise Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Configuration requise du programme d’équilibrage de la charge matérielle pour les serveurs Edge serveurs Edge exécutant le service Edge A/V

Pour tout serveur Edge exécutant le service Edge A/V, les conditions requises sont les suivantes :
  
- Désactivez le nagling TCP pour les ports internes et externes 443 (nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul et même paquet plus volumineux pour une transmission plus efficace).
    
- Désactivez le nagling TCP pour la plage de ports externes 50000-59999.
    
- N’utilisez pas la traduction d’adresses réseau sur vos pare-feu interne ou externe.
    
- Votre interface interne Edge doit se trouver sur un autre réseau que l’interface externe de votre serveur Edge, et le routage entre elles doit être désactivé.
    
- L’interface externe de n’importe quel serveur de périphérie exécutant le service Edge A/V doit utiliser des adresses IP publiquement routables et aucune traduction d’adresses réseau ou NAT sur les adresses IP externes du serveur Edge.
    
#### <a name="hlb-requirements"></a>Configuration requise pour charge matérielle

Skype entreprise Server n’a pas de nombreuses exigences en matière d’affinité basée sur les cookies. Par conséquent, vous n’avez pas besoin d’utiliser une persistance basée sur les cookies **, sauf si** (et cela est spécifique à Skype entreprise Server 2015), vous allez disposer de serveurs frontaux ou de pools frontaux Lync Server 2010 dans votre environnement Skype entreprise Server. Elles auraient besoin d’une affinité basée sur les cookies dans la méthode de configuration recommandée pour Lync Server 2010.
  
> [!NOTE]
> Si vous décidez d’activer l’affinité basée sur les cookies pour votre charge matérielle, il n’y aura pas de problème, même si votre environnement n’en a pas besoin. 
  
Si votre environnement **n’a pas** besoin d’une affinité basée sur les cookies :
  
- Sur la règle de publication de proxy inverse pour le port 443, définissez l' **en-tête** de l’hôte de transfert sur **true**. Cela permet de s’assurer que l’URL d’origine est transférée.
    
Pour les déploiements **qui nécessitent** une affinité basée sur les cookies :
  
- Sur la règle de publication de proxy inverse pour le port 443, définissez l' **en-tête** de l’hôte de transfert sur **true**. Cela permet de s’assurer que l’URL d’origine est transférée.
    
- Le cookie de l’équilibreur de la charge matérielle **ne doit pas** être marqué httpOnly.
    
- Le cookie de l’équilibreur de la charge matérielle **ne doit pas** avoir de délai d’expiration.
    
- Le cookie de l’équilibreur de la charge matérielle **doit** être nommé **MS-WSMan** (il s’agit de la valeur attendue par les services Web et il ne peut pas être modifié).
    
- Le cookie de l’équilibreur de la charge matérielle **doit** être défini dans chaque réponse HTTP pour laquelle la demande http entrante n’a pas de cookie, qu’une réponse http précédente sur la même connexion TCP avait été un cookie. Si votre programme d’équilibrage de la charge matérielle optimise l’insertion de cookies pour ne se produire qu’une seule fois par connexion TCP, cette optimisation **ne doit pas** être utilisée.
    
> [!NOTE]
> Il est courant pour les configurations charge matérielle d’utiliser l’affinité source et la durée de vie de la session TCP de 20 minutes, ce qui est parfait pour Skype entreprise Server et ses clients, car l’état de session est conservé par le biais de l’utilisation du client et/ou de l’interaction de l’application. 
  
Si vous déployez des appareils mobiles, votre charge matérielle doit pouvoir équilibrer la charge des demandes individuelles au cours d’une session TCP (en effet, vous devez pouvoir équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).
  
> [!IMPORTANT]
> F5 équilibreurs possèdent une fonctionnalité appelée OneConnect. Elle garantit que chaque demande au sein d’une connexion TCP est équilibrée individuellement. Si vous déployez des appareils mobiles, assurez-vous que votre fournisseur charge matérielle prend en charge la même fonctionnalité. Les applications mobiles iOS les plus récentes requièrent TLS version 1,2. Pour en savoir plus, la touche F5 fournit des paramètres spécifiques. 
  
Voici les conditions requises pour le charge matérielle (facultatif) et les services Web de pool frontal (requis) :
  
- Pour les adresses IP virtuelles des services Web internes, définissez Source_addr persistance (port interne 80, 443) sur votre charge matérielle. Pour Skype entreprise Server, Source_addr persistance signifie que plusieurs connexions provenant d’une seule adresse IP sont toujours envoyées à un serveur, afin de maintenir l’état de la session.
    
- Utilisez un délai d’inactivité TCP de 1800 secondes.
    
- Sur le pare-feu entre votre proxy inverse et les charge matérielle de votre pool de tronçon suivant, créez une règle pour autoriser le trafic https : sur le port 4443, de votre proxy inverse vers votre charge matérielle. Votre charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Résumé des exigences en matière d’affinité charge matérielle

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Exigences en matière d’affinité des services Web FQSN**|
|:-----|:-----|:-----|
|Skype entreprise Web App (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype entreprise Web App (utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Skype entreprise Web App (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Surveillance des ports pour équilibreurs

Vous définissez la surveillance des ports sur vos programmes d’équilibrage de la charge matérielle afin de déterminer si des services spécifiques ne sont plus disponibles, en raison d’une défaillance matérielle ou de communication. Par exemple, si le service de serveur frontal (RTCSRV) s’arrête en raison de l’échec du serveur frontal ou du pool frontal, la surveillance charge matérielle doit également cesser de recevoir du trafic sur les services Web. Vous devez implémenter la surveillance des ports sur le charge matérielle pour surveiller les éléments suivants pour votre interface externe charge matérielle :
  
|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs de pool \>  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucun  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs de pool \>  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucun  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

Nous avons couvert la configuration matérielle et logicielle requise pour le serveur Edge dans notre [configuration serveur totale requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et la [Configuration système requise pour la documentation de skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Colocalisation

Nous avons couvert la colocalisation des serveurs Edge dans nos [concepts de base de topologie pour Skype entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

