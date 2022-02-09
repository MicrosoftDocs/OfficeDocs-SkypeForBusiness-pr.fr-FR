---
title: Planifier la mobilité pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planifiez votre implémentation de Mobility for Skype Entreprise Server.
ms.openlocfilehash: a86f9ed4c3c41a1afa60a3f8181307589b0ce678
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400278"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planifier la mobilité pour Skype Entreprise Server
 
Planifiez votre implémentation de Mobility for Skype Entreprise Server.
  
Avec Skype Entreprise Server, vous pouvez déployer la fonctionnalité de mobilité pour fournir Skype Entreprise Server fonctionnalités sur les appareils mobiles. Cet article fournit des détails sur la fonctionnalité mobilité et vous aide à planifier votre déploiement.
  
La fonctionnalité de mobilité Skype Entreprise Server est en mesure de prendre en charge les clients mobiles pour Skype Entreprise, ainsi que les clients Lync qui remontent à 2010. Une fois qu’il est déployé, vos utilisateurs peuvent se connecter à votre déploiement Skype Entreprise Server à l’aide d’appareils mobiles iOS, Android et Windows Phone pris en charge pour tirer parti de différentes fonctionnalités, y compris les fonctionnalités Voix Entreprise. Nous avons inclus une liste partielle ci-dessous, et vous pouvez également consulter la comparaison des fonctionnalités du [client](clients-and-devices/desktop-feature-comparison.md) de bureau Skype Entreprise pour plus d’informations :
  
- Envoyer et recevoir des messages
    
- Afficher la présence
    
- Afficher les contacts
    
- Cliquez pour participer à une conférence
    
- Appel via le travail
    
- Portée du nombre unique
    
- Messagerie vocale
    
- Notification d’appel manqué
    
- Voix sur IP (VoIP)
    
- Vidéo du participant (H.264)
    
- Affichage du contenu de réunion (partage PowerPoint bureau/application)
    
Tout cela est réalisé par le biais de l’API web communications unifiées ou UCWA. UCWA a été introduit pour la première fois dans Lync Server 2013 et est toujours en cours d’utilisation pour Skype Entreprise Server. Il existe une fonctionnalité supplémentaire pour communiquer avec les clients Lync 2010, à l’aide du service de mobilité (MCX). Ces services complémentaires permettent aux clients Lync Server 2010 et 2013, ainsi qu’aux clients Skype Entreprise, d’accéder Skype Entreprise Server déploiements.
  
> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
Il est important de noter que même si toutes ces fonctionnalités sont disponibles une fois la mobilité implémentée, elles peuvent fonctionner un peu différemment sur certains appareils. Nous avons un site web qui décrit les fonctionnalités qui fonctionnent sur quels appareils, à l’adresse de comparaison des fonctionnalités de [client mobile pour Skype Entreprise](clients-and-devices/mobile-feature-comparison.md). Nous avons également d’excellentes informations sur les appareils et le système d’exploitation [sur la façon de planifier les clients et les appareils](clients-and-devices/clients-and-devices.md).
  
La mobilité utilise la fonctionnalité de découverte automatique, qui permet aux clients de localiser automatiquement les services web Skype Entreprise Server sans que les utilisateurs n’ont besoin d’entrer d’URL (ils n’ont même pas besoin de les connaître). Si vous devez résoudre certains problèmes, l’entrée manuelle des URL est toujours prise en charge.
  
Les notifications Push sont également pris en charge lorsque l’application Skype Entreprise n’est pas en cours d’exécution en arrière-plan (ou pour les appareils mobiles qui ne sont pas pris en charge par les applications qui s’exécutent en arrière-plan). Une notification Push est envoyée à un appareil mobile à propos d’un événement qui se produit lorsque l’appareil ou l’application est inactif. Un bon exemple est l’absence d’un message instantané lorsque votre téléphone n’est pas actif, ce qui entraînerait l’envoi d’une notification Push (présentée comme un toast ou une notification, comme lorsque l’application s’exécute en arrière-plan). Avec les notifications Push, les utilisateurs ne manqueront pas les messages instantanés ou les appels vocaux.
  
Pour plus d’informations, nous avons les sections suivantes :
  
- [Composants de mobilité](mobility.md#MobilityComponents)
    
- [Topologies prises en charge](mobility.md#SupportedTopos)
    
- [Exigences techniques](mobility.md#TechRequirements)
    
- [Définition de vos besoins en matière de mobilité](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Composants de mobilité
<a name="MobilityComponents"> </a>

Il existe quatre services qui comprennent la mobilité pour Skype Entreprise Server :
  
- **API web Unified Communications (UCWA)**
    
    Fournit des services pour les communications en temps réel avec les clients mobiles et web pour Skype Entreprise Server. Lorsque Skype Entreprise Server est déployé, un répertoire virtuel UCWA est créé dans les services web internes et externes. Composant virtuel dans ce répertoire virtuel qui accepte les appels de clients activés pour UCWA. Les applications clientes communiquent sur une interface REST (Representational State Transfer) pour :
    
  - présence
    
  - contacts
    
  - messagerie instantanée
    
  - VoIP
    
  - vidéoconférence
    
  - collaboration
    
    UCWA utilise un canal P-GET pour envoyer des événements, tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
- **Service de mobilité (MCX)**
    
    Prend en charge Skype Entreprise Server fonctionnalités de messagerie instantanée, de présence et de contacts, sur les appareils mobiles. Le service de mobilité est installé sur chaque serveur frontal de chaque pool destiné à prendre en charge les fonctionnalités Skype Entreprise Server sur les appareils mobiles. Lorsque vous installez Skype Entreprise Server 2015, un nouveau répertoire virtuel (Mcx) est créé sous les sites web internes et externes sur vos serveurs frontux.
    
    > [!NOTE]
    > La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
- **Service de découverte automatique**
    
    Identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et autres clients Skype Entreprise de localiser des ressources (telles que les URL internes et externes pour les services web Skype Entreprise Server, l’URL Mcx ou l’URL UCWA) quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôtes codés en dur (lyncdiscoverinternal pour les utilisateurs au sein du réseau, lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Il prend en charge les connexions clientes qui utilisent http ou HTTPS. 
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur chaque directeur de chaque pool destiné à prendre en charge les fonctionnalités de Skype Entreprise Server sur les appareils mobiles. Lorsque vous installez le service, un nouveau répertoire virtuel (découverte automatique) est créé sous les sites web internes et externes sur vos serveurs frontux et directeurs.
    
- **Service de notification Push**
    
    Service basé sur le cloud qui se trouve dans votre centre de données Skype Entreprise Online. Sur les téléphones qui n’ont pas de client Skype Entreprise en cours d’exécution en arrière-plan, lorsqu’un nouvel événement se produit, la notification d’un événement manqué (appelé notification Push) est envoyée à l’appareil mobile à la place. Le service de mobilité envoie une notification au service de notification push (MPNS), qui l’envoie ensuite à l’appareil mobile. L’utilisateur peut ensuite répondre à la notification sur son appareil mobile pour activer l’application. Un serveur Edge est requis pour cette fonctionnalité.
    
## <a name="supported-topologies"></a>Topologies prises en charge
<a name="SupportedTopos"> </a>

Nous avons pris en charge les applications Skype Entreprise Server suivantes pour la planification de votre topologie :
  
- Mobility Édition Standard
    
- Mobilité Êdition Entreprise
    
Vous devriez être en mesure d’utiliser cette fonctionnalité Skype Entreprise Server serveurs Edge ou Lync Server 2013.
  
Le service de mobilité est pris en charge sur les serveurs frontaux lorsqu’il est coqueté avec le rôle serveur de médiation, avec deux interfaces réseau, mais vous devez prendre les mesures appropriées pour configurer ces interfaces. Vous devez affecter des adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation et à l’interface IP réseau qui communiquera en tant que serveur frontal. Vous pouvez le faire dans le Générateur de topologie en sélectionnant l’adresse IP correcte pour chaque service, au lieu d’utiliser la sélection par défaut Utiliser toutes les **adresses IP** configurées.
  
## <a name="technical-requirements"></a>Exigences techniques
<a name="TechRequirements"> </a>

Il est important de planifier les différents scénarios d’application mobile que vos utilisateurs mobiles peuvent rencontrer. Par exemple, une personne peut commencer à utiliser une application mobile en dehors du travail en se connectant via un réseau 3G, puis basculer vers le réseau Wi-Fi d’entreprise lorsqu’elle atteint le travail. Ils peuvent basculer vers la 4G lorsqu’ils quittent leur bâtiment. La planification maintenant vous permettra de prendre en charge ces transitions réseau et de garantir une expérience utilisateur cohérente.
  
### <a name="dns-configuration"></a>Configuration du DNS

Les services de mobilité Mcx et UCWA utilisent DNS de la même manière. Avec la découverte automatique, les appareils mobiles utilisent DNS pour localiser des ressources. Lors de la recherche DNS, une tentative de connexion au FQDN associée à l’enregistrement DNS interne (lyncdiscoverinternal.[ nom de domaine interne]). Si l’enregistrement DNS interne ne peut pas être utilisé pour établir cette connexion, une deuxième tentative de connexion est tentée, cette fois vers l’enregistrement DNS externe (lyncdiscover.[ sipdomain]). Pourquoi en avoir deux ? Un appareil mobile interne à votre réseau pourra utiliser l’URL de découverte automatique interne. Les appareils mobiles externes utiliseront l’URL de découverte automatique externe. Dans les deux cas, le service de découverte automatique retourne toutes les URL de service Web pour le pool d’accueil de l’utilisateur, qui inclut le service de mobilité (Mcx et UCWA).
  
Il est prévu que les demandes de découverte automatique externes passeront par le proxy inverse que vous avez configuré pour Skype Entreprise Server. Toutefois, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont associées au FQDN des services web externes. Par conséquent, qu’un appareil mobile soit interne ou externe à votre réseau, il se connecte toujours au service Skype Entreprise Server Mobility en externe, via votre proxy inverse.
  
> [!NOTE]
> Comme nous venons de le noter, tout le trafic du service de mobilité (interne et externe) passe par votre proxy inverse. Mais parfois, un problème survient lorsque le trafic interne quitte une interface, uniquement pour essayer de revenir sur la même interface. Cela peut enfreindre vos règles de sécurité d’usurpation d’usurpation (officiellement appelée usurpation de paquetS TCP). Vous devez autoriser l’épinglage **des épingles** à avoir la fonction Mobilité.
  
> [!NOTE]
> Si vous êtes prêt à le faire, vous pouvez également choisir d’utiliser un proxy inverse distinct de votre pare-feu (à des fins de sécurité, la prévention de l’usurpation d’identification doit toujours être appliquée à votre pare-feu). Ainsi, l’épingle peut se produire dans l’interface externe de votre proxy inverse, plutôt que dans l’interface externe de votre pare-feu. Cela vous permet de détecter l’usurpation correctement au niveau de votre pare-feu pendant que vous relâchez la règle au niveau de votre proxy inverse et que vous obtenez votre fonctionnalité de mobilité. 
  
> [!NOTE]
> Si vous utilisez cet itinéraire, n’oubliez pas d’utiliser l’hôte DNS ou les enregistrements CNAME pour définir le proxy inverse pour le comportement d’épingle (et non le pare-feu), si possible. 
  
Vous devez configurer certains éléments pour prendre en charge les utilisateurs à l’intérieur et à l’extérieur de votre réseau d’entreprise.
  
Voici les règles pour les FQDN web internes et externes :
  
- Nouveaux enregistrements DNS CNAME ou A (hôte, si IPv6, AAAA) pour la découverte automatique.
    
- Nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications Push via Wi-Fi réseau.
    
- Autres noms du sujet sur les certificats de serveur interne et les certificats de proxy inverse, pour la découverte automatique.
    
- La configuration avec équilibrage de la charge matérielle du serveur frontal modifie l’affinité de la source.
    
Voici la topologie requise pour prendre en charge le service de mobilité et le service de découverte automatique :
  
- Le FQDN web interne du pool frontal doit être distinct du FQDN web externe du pool frontal.
    
- Le FQDN web interne doit uniquement résoudre et être accessible à partir du réseau d’entreprise.
    
- Le FQDN web externe doit uniquement résoudre et être accessible à partir d’Internet.
    
- Pour un utilisateur au sein du réseau d’entreprise, l’URL du service de mobilité doit être adressée au nom de domaine complet web externe. Cette exigence concerne le service de mobilité et s’applique uniquement à cette URL.
    
- Pour un utilisateur en dehors du réseau d’entreprise, la demande doit être au nom de groupe web externe du pool frontal ou du directeur.
    
Si vous prise en charge la découverte automatique, vous devez effectuer les enregistrements DNS suivants pour chaque domaine SIP :
  
- Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent depuis l’intérieur du réseau de votre organisation.
    
- Un enregistrement DNS externe ou public pour prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet.
    
L’URL de découverte automatique interne ne doit pas être adressaçable depuis l’extérieur de votre réseau interne. L’URL de découverte automatique externe ne doit pas être adressaçable à partir de votre réseau. Toutefois, si cela n’est pas possible pour l’URL externe, vos fonctionnalités de client mobile ne seront probablement pas affectées, car l’URL interne sera toujours essayée en premier.
  
### <a name="port-and-firewall-requirements"></a>Exigences en matière de port et de pare-feu

Nous avons abordé la plupart de ces questions dans notre autre documentation, mais en particulier pour la mobilité, vous souhaitez que les ports suivants s’ouvrent sur votre réseau Wi-Fi d’entreprise si vous avez des utilisateurs sur un Survivable Branch Appliance (SBA) :
  
- UcwaSipExternalListeningPort requiert 5088.
    
- UcwaSipPrimaryListeningPort requiert 5089.
    
### <a name="certificate-requirements"></a>Spécifications des certificats

Si vous utilisez la découverte automatique pour vos clients mobiles Skype Entreprise, vous devez modifier les listes SAN (autre nom du sujet) sur vos certificats pour prendre en charge les connexions sécurisées à partir de vos clients mobiles. Si vous avez déjà des certificats en place, vous devez demander et affecter de nouveaux certificats avec les entrées SAN décrites ici. Cette étape doit être effectuée pour chaque serveur frontal et directeur (si votre environnement) exécute le service de découverte automatique. Nous vous recommandons également de modifier les listes SAN sur vos certificats de proxy inverse, en ajoutant des entrées SAN pour chaque domaine SIP de votre organisation.
  
Ce processus doit être simple si vous demandez les nouveaux certificats à une autorité de certification interne, mais les certificats publics sont plus complexes et potentiellement beaucoup plus coûteux à demander, sans compter qu’il peut être coûteux d’ajouter un grand nombre de domaines SIP à un nouveau certificat public. Dans ce cas, il existe une approche prise en charge, mais **non recommandée**. Vous pouvez configurer votre proxy inverse pour effectuer la demande initiale du service de découverte automatique sur le port 80, qui utilisera HTTP, plutôt que le port 443, qui est HTTPS (et 443 est la configuration par défaut). Cette demande entrante sera redirigée vers le port 8080 sur votre pool frontal ou directeur. En faisant cela, vous n’aurez pas besoin d’apporter de modifications de certificat, car ce trafic n’utilise pas HTTPS pour les demandes. Mais là encore, nous ne le recommandons pas, bien que cela fonctionne pour vous.
  
### <a name="windows-and-iis-requirements"></a>Windows et IIS

Vous devez avoir une version Windows Server prise en charge pour Skype Entreprise Server environnement. Par conséquent, vous devez également avoir IIS 8 ou IIS 8.5 pour vos besoins de mobilité. Certaines modifications devront être apportées aux paramètres de ASP.NET par défaut, mais le programme d’installation du service de mobilité le fera automatiquement.
  
### <a name="hlb-requirements"></a>Conditions requises pour l’programme d’programme d

Si vous utilisez une topologie pour Skype Entreprise Server qui inclut un programme d’lb de hlb pour votre pool frontal (qui serait une topologie comprenant plusieurs serveurs frontaux), les adresses IPS virtuelles (VIP) des services web externes pour le trafic des services Web doivent être configurées pour la source. L’affinité source permet de s’assurer que plusieurs connexions à partir d’un seul client sont envoyées au même serveur pour maintenir l’état de session.
  
Si vous envisagez de prendre en charge Skype Entreprise clients mobiles uniquement sur votre réseau Wi-Fi interne, vous devez configurer vos adresses VIP internes des services web pour la source, comme décrit pour les adresses VIP des services web externes. Dans ce cas, vous devez utiliser l’affinité source_addr (ou TCP) pour les adresses IP ip ip (VIP) des services web internes sur l’programme d’programmes d’hlb.
  
Pour plus d’informations sur tout cela, consultez les conditions requises pour l’équilibrage de [charge Skype Entreprise](network-requirements/load-balancing.md) documentation.
  
### <a name="reverse-proxy-requirements"></a>Exigences relatives au proxy inverse

Pour prendre en charge la découverte automatique pour Skype Entreprise clients mobiles, vous devez mettre à jour la règle de publication actuelle comme suit :
  
- Si vous décidez de mettre à jour les listes SAN sur vos certificats de proxy inverse et que vous utilisez HTTPS pour la demande initiale du service de découverte automatique, vous devez mettre à jour la règle de publication web pour lyncdiscover.\<sipdomain\> Cela est généralement combiné avec la rul de publication pour l’URL des services web externes sur le pool frontal.
    
- Si vous avez décidé d’utiliser HTTP pour la demande initiale du service de découverte automatique afin d’éviter d’avoir à mettre à jour la liste SAN pour vos certificats de proxy inverse (ce que nous ne recommandons pas), vous devrez créer une règle de publication web pour le port HTTP/TCP 80, s’il n’en existe pas déjà une. Si cette règle existe, mettez-la à jour pour inclure un lyncdiscover.\<sipdomain\> entrée.
    
## <a name="defining-your-mobility-needs"></a>Définition de vos besoins en matière de mobilité
<a name="MobilityNeeds"> </a>

Maintenant que nous avons examiné les topologies, les composants et les exigences techniques, examinons ce dont votre organisation peut avoir besoin en termes d’implémentation de la mobilité.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Souhaitez-vous utiliser la découverte automatique pour Skype Entreprise clients mobiles ?

Nous vous recommandons vivement d’utiliser la découverte automatique. Il nécessitera la création de nouveaux enregistrements DNS internes et externes, comme documenté dans la section Technical Requirements ci-dessus. Avec la découverte automatique, les clients Skype Entreprise peuvent localiser automatiquement les services web Skype Entreprise Server à partir de n’importe quel emplacement, sans qu’il soit nécessaire d’entrer manuellement une URL.
  
Vous pouvez utiliser les paramètres manuels si nécessaire. Ces URL doivent être entrées par les utilisateurs sur leurs appareils mobiles :
  
- **\<ExtPoolFQDN\>https:///Autodiscover/autodiscoverservice.svc/Root** pour l’accès externe.
    
- **\<IntPoolFQDN\>https:///Autodiscover/autodiscoverservice.svc/Root** pour l’accès interne.
    
Là encore, nous vous recommandons d’utiliser la découverte automatique. Vous trouverez peut-être des paramètres manuels utiles à des fins de dépannage.
  
### <a name="are-you-going-to-support-push-notifications"></a>Allez-vous prendre en charge les notifications Push ?

Les notifications Push sont utilisées pour les applications mobiles qui utilisent cette fonctionnalité pour informer un utilisateur des événements alors que l’application n’est pas active. Votre serveur Edge doit avoir une relation de fédération avec votre service de notification push Skype Entreprise Server basé sur le cloud, qui se trouve dans le centre de données Skype Entreprise Online. Vous devez exécuter une cmdlet pour activer les notifications Push.
  
> [!NOTE]
> Si des personnes utilisent encore des clients Lync Server 2010, elles auront besoin du port TCP 5223 pour ouvrir le trafic sortant sur votre réseau WiFi d’entreprise. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Voulez-vous que tous vos utilisateurs accèdent à toutes les fonctionnalités de mobilité ou spécifiez-vous plutôt les utilisateurs qui peuvent accéder à ces fonctionnalités ?

Nous avons un tableau pour vous aider avec certaines des fonctionnalités disponibles pour tous les utilisateurs, et pour savoir si elles sont définies de cette façon ou non par défaut. Pour obtenir la liste complète, consultez [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Les étendues de toutes ces fonctionnalités sont Global/Site/User. 
  
|**Fonctionnalité**|**Nom du paramètre**|**Description**|**Paramètre par défaut**|
|:-----|:-----|:-----|:-----|
|Activer la mobilité  <br/> |EnableMobility  <br/> |Contrôle les utilisateurs dans une étendue donnée qui ont installé Skype Entreprise client mobile. Si la stratégie est définie sur False, vos utilisateurs ne pourront pas se connecter avec leur client.  <br/> |Vrai  <br/> |
|Voix extérieure  <br/> |EnableOutsideVoice  <br/> |Permet à un utilisateur d’utiliser l’appel via le lieu de travail, ce qui permet aux utilisateurs d’envoyer et de recevoir des appels à l’aide de leur numéro de travail au lieu de leur numéro de téléphone mobile. Si elle est définie sur False, vos utilisateurs ne pourront pas effectuer ou recevoir d’appels sur leur téléphone mobile lors de l’utilisation de leur numéro de téléphone professionnels.  <br/> |Vrai  <br/> |
|Activer l’audio et la vidéo IP  <br/> |EnableIPAudioVideo  <br/> |Définie sur la valeur par défaut, elle permet à un utilisateur d’utiliser voIP pour effectuer ou recevoir des appels téléphoniques ou vidéo sur son appareil mobile. Si la qualité est False, vos utilisateurs ne pourront pas utiliser leur appareil mobile pour faire l’une ou l’autre de ces choses.  <br/> |Vrai  <br/> |
|Exiger le WiFi pour l’audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Définit si un client doit effectuer et recevoir des appels via VoIP sur WiFi au lieu d’un réseau de données cellulaire. Si la valeur est True, vos utilisateurs pourront uniquement effectuer et recevoir des appels VoIP lorsqu’ils sont connectés via wi-fi.  <br/> |Faux  <br/> |
|Exiger le WiFi pour la vidéo IP  <br/> |RequireWiFiForIPVideo  <br/> |Définit si un client doit effectuer et recevoir des appels vidéo sur WiFi au lieu d’un réseau de données cellulaire. Si la valeur est True, vos utilisateurs pourront uniquement effectuer et recevoir des appels VoIP lorsqu’ils sont connectés via wi-fi.  <br/> |Faux  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Les utilisateurs qui ne sont pas activés pour Voix Entreprise peuvent-ils utiliser Click to Join pour participer à des conférences ?

Pour que les utilisateurs accèdent aux fonctionnalités de mobilité et d’appel via le travail, ils doivent être activés pour Voix Entreprise. Toutefois, même s’ils ne sont pas activés, ils peuvent toujours participer à des conférences en cliquant sur un lien sur leur appareil mobile, mais uniquement s’ils ont une stratégie de voix appropriée qui leur est affectée. Vous pouvez :
  
- affecter une stratégie de voix spécifique à ces utilisateurs, ou,
    
- assurez-vous qu’une stratégie globale ou une stratégie au niveau du site existe et qu’elle s’applique à ces stratégies.
    
Dans les deux cas, la stratégie de voix que vous affectez doit avoir des enregistrements d’utilisation du réseau téléphonique commuté (PSTN) et des itinéraires qui définissent l’endroit où vos utilisateurs pourront composer un numéro pour participer à des conférences.
  
> [!NOTE]
> Les utilisateurs mobiles qui souhaitent utiliser Click to Join nécessitent une stratégie de voix, ainsi que les enregistrements d’utilisation PSTN et les itinéraires de voix associés, car lorsqu’ils cliquent sur ce lien sur leurs appareils mobiles, un appel sortant de Skype Entreprise Server en résulte. 
