---
title: Conditions requises pour le système du serveur Edge dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Résumé : Découvrez la requise pour le serveur Edge dans Skype Entreprise Server.'
ms.openlocfilehash: bc8a6666f46d093c9f3d2da41f2663c79e94ddf3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622156"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Conditions requises pour le système du serveur Edge dans Skype Entreprise Server
 
**Résumé :** Découvrez la demande système requise pour le serveur Edge dans Skype Entreprise Server.
  
En ce qui concerne le déploiement de votre serveur Edge Skype Entreprise Server, voici les choses que vous devez faire pour le ou les serveurs se trouver dans l’environnement lui-même, ainsi que la planification de la structure de l’environnement. Pour plus d’informations sur la topologie, le DNS, les certificats et d’autres problèmes d’infrastructure, consultez la documentation relative aux exigences environnementales.
  
## <a name="components"></a>Composants

Lorsque vous discutez de l’environnement de serveur Edge, nous référons les composants qui sont, pour la plupart, déployés dans un réseau de périmètre (c’est-à-dire qu’ils se trouveraient dans un groupe de travail ou un domaine en dehors de votre structure de domaine Skype Entreprise Server).
  
En gardant cela à l’esprit, voici les composants que vous devrez garder à l’esprit pour déployer correctement votre edge :
  
- [Serveurs de périphérie](system-requirements.md#EdgeServers)
    
- [Proxys inverses](system-requirements.md#ReverseProxies)
    
- [Pare-feu](system-requirements.md#Firewalls)
    
- [Directeurs](system-requirements.md#Directors) (facultatifs et s’ils sont inclus, ils se trouveront sur votre réseau interne)
    
- [Les équilibreurs de](system-requirements.md#LoadBalancers) charge (vous pouvez avoir un équilibrage de charge DNS ou un équilibrage de la charge matérielle, mais pour un serveur Edge unique, cela n’est pas nécessaire)
    
Nous avons plus de détails sur chacun de ces éléments ci-dessous :
  
### <a name="edge-servers"></a>Serveurs de périphérie
<a name="EdgeServers"> </a>

Il s’Skype Entreprise serveurs déployés dans votre environnement de périmètre. Leur rôle consiste à envoyer et recevoir du trafic réseau vers des utilisateurs externes pour les services offerts par votre déploiement Skype Entreprise Server interne. Pour ce faire, chaque serveur Edge exécute :
  
- **Service Edge d’accès**: fournit un point de connexion unique approuvé pour le trafic SIP (Session Initiation Protocol) entrant et sortant.
    
- **Service Edge** de conférence web : permet aux utilisateurs externes de participer à des réunions hébergées sur votre environnement Skype Entreprise Server interne.
    
- **Service Edge A/V :** met l’audio, la vidéo, le partage d’application et le transfert de fichiers à la disposition des utilisateurs externes.
    
- **Service proxy XMPP**: accepte et envoie des messages XMPP (Extensible Messaging and Presence Protocol) vers et depuis des partenaires fédérés XMPP configurés.
    
Les utilisateurs externes autorisés peuvent utiliser vos serveurs Edge pour se connecter à votre déploiement Skype Entreprise Server interne, mais dans le cas contraire, ils ne fournissent aucun autre accès à votre réseau interne pour qui que ce soit.
  
> [!NOTE]
> Les serveurs Edge sont déployés pour fournir des connexions pour les clients Skype Entreprise activés et d’autres serveurs Edge (dans les scénarios de fédération). Vous ne pouvez pas vous connecter à partir d’autres types de serveur ou de client de point de fin. Le serveur de passerelle XMPP peut autoriser les connexions avec des partenaires XMPP configurés. Mais là encore, il s’agit des seuls types de client et de fédération qui fonctionneront. 

> [!NOTE]
> Les passerelles et les proxies XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.
  
### <a name="reverse-proxies"></a>Proxys inverses
<a name="ReverseProxies"> </a>

Un serveur proxy inverse (RP) n’a Skype Entreprise Server rôle principal, mais il s’agit d’un composant essentiel d’un déploiement de serveur Edge. Un proxy inverse permet aux utilisateurs externes de :
  
- se connecter à des réunions ou des conférences rendez-vous à l’aide d’URL simples.
    
- télécharger le contenu de la réunion.
    
- développer des groupes de distribution.
    
- obtenir des certificats basés sur l’utilisateur pour l’authentification basée sur les certificats clients
    
- téléchargez des fichiers à partir du serveur de carnet d’adresses ou envoyez des requêtes au service de requête Web du carnet d’adresses.
    
- obtenir des mises à jour du logiciel client et du logiciel de périphérique.
    
Et pour les appareils mobiles :
  
- Il leur permet de découvrir automatiquement les serveurs frontaux offrant des services de mobilité.
    
- il active les notifications Push à partir Microsoft 365 ou Office 365 aux appareils mobiles.
    
Nos recommandations actuelles en matière de proxy inverse sont présentes dans la page Infrastructure de téléphonie [Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md) web. Votre proxy inverse :
  
- doit être en mesure d’utiliser le TLS (Transport Layer Security) introduit dans votre environnement via des certificats publics pour se connecter aux services Web externes publiés de :
    
  - Directeur ou pool directeur
    
  - Serveur frontal ou pool frontal
    
- doit être en mesure de publier des sites Web internes à l’aide de certificats pour le chiffrement, ou de les publier sur un moyen non chiffré, si nécessaire.
    
- doit être en mesure de publier un site web hébergé en interne en externe à l’aide d’un nom de domaine complet ( FQDN).
    
- doit pouvoir publier tout le contenu de votre site web hébergé. Par défaut, vous pouvez utiliser la directive _ qui est reconnue par la plupart des serveurs web pour signifier « Publier tout le contenu **/\\** sur le serveur web ». Vous pouvez également modifier la directive( par exemple, _*/Uwca/ ***), ce qui signifie « Publier tout le contenu sous le répertoire virtuel \\ Ucwa ».
    
- doit exiger des connexions TLS avec les clients qui demandent du contenu à partir de votre site web publié.
    
- doit accepter les certificats avec des entrées SAN (autre nom de sujet).
    
- doit être en mesure d’autoriser la liaison d’un certificat à un listener ou une interface par le biais de laquelle le FQDN des services web externes sera résolu. Les configurations d’écoute sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une seule interface.
    
- doit autoriser la configuration de la gestion des en-têtes d’hôte. Souvent, l’en-tête d’hôte d’origine envoyé par le client demandeur doit être transmis de manière transparente, au lieu d’être modifié par le proxy inverse.
    
- autoriser le pontage du trafic TLS d’un port défini en externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Votre proxy inverse peut déchiffrer le paquet lors de la réception, puis le recrypter lors de l’envoi.
    
- autoriser le pontage du trafic TCP non chiffré d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080).
    
- doit autoriser la configuration ou l’acceptation de l’authentification NTLM, aucune authentification et l’authentification directe.
    
Si votre proxy inverse peut répondre à tous les besoins de cette liste, vous devriez pouvoir y aller, mais n’oubliez pas nos recommandations sur le lien fourni ci-dessus.
  
### <a name="firewalls"></a>Pare-feu
<a name="Firewalls"> </a>

Vous devez placer votre déploiement Edge derrière un pare-feu externe, mais nous vous recommandons d’avoir deux pare-feu, un externe et un interne entre l’environnement Edge et votre environnement interne. Toute notre documentation dans nos scénarios aura deux pare-feu. Nous recommandons deux pare-feu, car il assure un routage strict d’un bord réseau à l’autre et double la protection du pare-feu pour votre réseau interne.
  
### <a name="directors"></a>Directeurs
<a name="Directors"> </a>

Il s’agit d’un rôle facultatif. Il peut s’agit d’un serveur unique ou d’un pool de serveurs exécutant le rôle directeur. Il s’agit d’un rôle trouvé dans l’environnement Skype Entreprise Server interne.
  
Le directeur est un serveur de saut suivant interne qui reçoit le trafic SIP entrant des serveurs Edge destinés aux serveurs Skype Entreprise Server internes. Il authentifier préalablement les demandes entrantes et les redirige vers le pool ou le serveur d’accueil d’un utilisateur. Cette pré-authentication vous permet de déposer des demandes de comptes d’utilisateur non identifiés.
  
Pourquoi cela importe-t-il ? Une fonction importante pour un directeur consiste à protéger les serveurs Édition Standard et les serveurs frontaux ou les pools frontaux contre le trafic malveillant, tel que les attaques par déni de service. Si votre réseau est submergé par du trafic externe non valide, le trafic s’arrête au niveau du directeur.
  
### <a name="load-balancers"></a>Équilibreurs de charge
<a name="LoadBalancers"> </a>

L Skype Entreprise Server topologie Edge consolidée mise à l’échelle est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements, et nous vous recommandons de le faire. Si vous avez besoin d’une haute disponibilité, nous vous recommandons d’utiliser un programme d’équilibrage de la charge matérielle pour une situation spécifique :
  
- Exchange Um for remote users using Exchange UM **prior** to Exchange 2013.
    
> [!IMPORTANT]
> Il est essentiel de noter que vous ne pouvez pas combiner des équilibreurs de charge. Dans votre environnement Skype Entreprise Server, toutes les interfaces doivent utiliser DNS ou HLB. 
  
> [!NOTE]
> La nat de retour direct du serveur (DSR) n’est pas prise en charge pour Skype Entreprise Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>Configuration requise pour l’équilibrage de la charge matérielle pour les serveurs Edge des serveurs Edge exécutant le service Edge A/V

Pour n’importe quel serveur Edge exécutant le service Edge A/V, voici les conditions requises :
  
- Désactiver le nagling TCP pour les ports internes et externes 443 (le nagling est le processus de combinaison de plusieurs petits paquets en un seul paquet plus grand pour une transmission plus efficace).
    
- Désactiver le nagling TCP pour la plage de ports externes 50000 - 59999.
    
- N’utilisez pas nat sur vos pare-feu internes ou externes.
    
- Votre interface interne Edge doit se trouver sur un autre réseau que votre interface externe de serveur Edge, et le routage entre elles doit être désactivé.
    
- L’interface externe d’un serveur Edge exécutant le service Edge A/V doit utiliser des adresses IP publiquement routables et aucune traduction nat ou de port sur l’une des adresses IP externes Edge.
    
#### <a name="hlb-requirements"></a>Conditions requises pour l’programme d’programme d

Skype Entreprise Server n’a pas beaucoup d’exigences d’affinité basée sur les cookies. Par conséquent, vous n’avez pas besoin d’utiliser une persistance basée sur les cookies, sauf **si** (et c’est spécifique à Skype Entreprise Server 2015) vous allez avoir des serveurs frontux ou des pools frontux Lync Server 2010 dans votre environnement Skype Entreprise Server. Ils doivent avoir une affinité basée sur les cookies dans la méthode de configuration recommandée pour Lync Server 2010.
  
> [!NOTE]
> Si vous décidez d’activer l’affinité basée sur les cookies pour votre programme d’hlb, cela ne pose aucun problème, même si votre environnement n’en a pas besoin. 
  
Si votre environnement **n’a pas besoin d’affinité** basée sur les cookies :
  
- Sur la règle de publication du proxy inverse pour le port 443, définissez l’en-tête d’hôte **Forward** sur **True**. Cela garantit le forwarded de l’URL d’origine.
    
Pour les déploiements **qui ont besoin d’affinité** basée sur les cookies :
  
- Sur la règle de publication du proxy inverse pour le port 443, définissez l’en-tête d’hôte **Forward** sur **True**. Cela garantit le forwarded de l’URL d’origine.
    
- Le cookie de l’équilibreur de **charge matérielle ne doit pas** être marqué httpOnly.
    
- Le cookie de l’équilibreur de charge **matérielle ne doit pas** avoir de délai d’expiration.
    
- Le **cookie** de l’équilibreur de la charge matérielle doit être nommé **MS-WSMAN** (il s’agit de la valeur à attendre des services Web et ne peut pas être modifiée).
    
- Le **cookie** du programme d’équilibrage de la charge matérielle doit être définie dans chaque réponse HTTP pour laquelle la demande HTTP entrante n’a pas de cookie, qu’une réponse HTTP précédente sur cette même connexion TCP a obtenu ou non un cookie. Si votre programme d’équilibrage de la charge matérielle optimise l’insertion des cookies pour qu’elle ne se produise qu’une seule fois par connexion TCP, cette optimisation ne **doit pas** être utilisée.
    
> [!NOTE]
> Il est courant que les configurations hLB utilisent l’affinité source et la durée de vie des sessions TCP de 20 minutes, ce qui est bien pour Skype Entreprise Server et ses clients, car l’état de session est maintenu par le biais de l’utilisation du client et/ou de l’interaction de l’application. 
  
Si vous déployez des appareils mobiles, votre programme d’équilibrage de la charge réseau doit pouvoir équilibrer la charge des demandes individuelles au sein d’une session TCP (en fait, vous devez être en mesure d’équilibrer la charge d’une demande individuelle en fonction de l’adresse IP cible).
  
> [!IMPORTANT]
> Les HLB F5 ont une fonctionnalité appelée OneConnect. Il garantit que chaque demande au sein d’une connexion TCP est individuellement équilibrée. Si vous déployez des appareils mobiles, assurez-vous que votre fournisseur DLB prend en charge les mêmes fonctionnalités. Les dernières applications mobiles iOS nécessitent TLS version 1.2. Si vous avez besoin d’en savoir plus, F5 fournit des paramètres spécifiques pour ce faire. 
  
Voici les exigences en matière d’programme d’programme d’hlb pour les services Web du directeur (facultatif) et du pool frontal (obligatoire) :
  
- Pour vos adresses VIP des services web internes, Source_addr persistance (port interne 80, 443) sur votre hLB. Par Skype Entreprise Server, Source_addr persistance signifie que plusieurs connexions provenant d’une seule adresse IP sont toujours envoyées à un seul serveur, pour maintenir l’état de session.
    
- Utilisez un délai d’inactivité TCP de 1 800 secondes.
    
- Sur le pare-feu entre votre proxy inverse et l’équilibrez le hLB de votre pool de sauts suivant, créez une règle pour autoriser le trafic https: sur le port 4443, de votre proxy inverse vers votre équilibrez le matériel. Votre hLB doit être configuré pour écouter sur les ports 80, 443 et 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Résumé des exigences en matière d’affinité hLB

|**Emplacement du client/de l’utilisateur**|**Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes**|**Conditions requises pour l’affinité du FQSN des services web internes**|
|:-----|:-----|:-----|
|Application Web Skype Entreprise (utilisateurs internes et externes)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Application Web Skype Entreprise (utilisateurs externes uniquement)  <br/> Appareil mobile (utilisateurs internes et externes)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
|Application Web Skype Entreprise (utilisateurs internes uniquement)  <br/> Appareil mobile (non déployé)  <br/> |Aucune affinité  <br/> |Affinité des adresses sources  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Surveillance des ports pour les programmes d’HLB

Vous définissez la surveillance des ports sur vos programmes d’équilibrage de la charge matérielle pour déterminer à quel moment des services spécifiques ne sont plus disponibles en raison d’une défaillance matérielle ou de communication. Par exemple, si le service de serveur frontal (RTCSRV) s’arrête en raison de l’échec du serveur frontal ou du pool frontal, la surveillance de l’programme d’programmes d’émission de programmes d’émission de programmes d’urgence doit également cesser de recevoir du trafic sur les services Web. Vous devez implémenter la surveillance des ports sur le programme d’programmes d’ergonomie pour surveiller les opérations suivantes pour votre interface externe HLB :
  
|**IP/Port virtuel**|**Port de nœud**|**Nœud Ordinateur/Écran**|**Profil de persistance**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucun  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Serveur frontal  <br/> 5061  <br/> |Aucun  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

Nous avons couvert la configuration matérielle et logicielle requise pour le serveur Edge dans notre configuration requise globale pour Skype Entreprise Server [2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et la configuration système requise pour [Skype Entreprise Server 2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="collocation"></a>C collocation

Nous avons abordé la cocation des serveurs Edge dans notre documentation de base sur la [topologie Skype Entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.
