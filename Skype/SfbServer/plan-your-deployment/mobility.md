---
title: Planification de la mobilité pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planifiez votre mise en œuvre de la mobilité pour Skype pour Business Server 2015.
ms.openlocfilehash: f0d822050055ea7255786128fcaecd144f91367a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-mobility-for-skype-for-business-server-2015"></a>Planification de la mobilité pour Skype Entreprise Server 2015
 
Planifiez votre mise en œuvre de la mobilité pour Skype pour Business Server 2015.
  
Avec Skype pour Business Server 2015, vous pouvez déployer la fonctionnalité de mobilité pour fournir Skype pour la fonctionnalité Business Server 2015 sur les périphériques mobiles. Cet article fournit des détails sur la fonctionnalité de mobilité et vous aide à planifier votre déploiement.
  
La fonctionnalité de mobilité pour Skype pour Business Server 2015 est en mesure de prendre en charge les clients mobiles de Skype pour les entreprises, ainsi que les clients Lync 2010 pour revenir. Une fois qu’il est déployé, vos utilisateurs peuvent se connecter à votre Skype pour Business Server 2015 déploiement à l’aide de prises en charge iOS, Android et Windows Phone de périphériques mobiles de tirer parti des différentes fonctionnalités, y compris les fonctionnalités de Voix Entreprise. Nous avons inclus une liste partielle ci-dessous, et vous pouvez également vérifier la [comparaison des fonctionnalités client de bureau pour Skype pour entreprise](clients-and-devices/desktop-feature-comparison.md) pour plus d’informations :
  
- Envoyer et recevoir des messages
    
- Afficher les informations de présence
    
- Afficher les contacts
    
- Cliquer pour participer à une conférence
    
- Appel via le bureau
    
- Numéro unique
    
- Messagerie vocale
    
- Notification des appels manqués
    
- VoIP
    
- Vidéo des participants (H.264)
    
- Affichage du contenu de la réunion (Partage de PowerPoint et de bureau/d'application)
    
Tout cela est effectué par le biais de l’API de Web de Communications unifiées, ou UCWA. UCWA a été introduit dans Microsoft Lync Server 2013, et il est en cours d’utilisation pour Skype pour Business Server 2015 aujourd'hui. Il existe une fonctionnalité supplémentaire permettant de communiquer avec les clients Lync 2010, et qui est le Service de mobilité (MCX). Il s’agit des services complémentaires, permettant de Lync Server 2010 et clients de 2013, ainsi que Skype pour les clients Business, pour accéder à Skype pour les déploiements de serveur d’entreprise avec succès.
  
> [!NOTE]
> Nous avez inclus MCX ici, mais pour être clair que ceci est pris en charge, nous envisageons cela désapprouver dans notre prochaine version, qui doit être quelque chose que vous gardez à l’esprit lors de la planification. Nous continuerons à utiliser le UCWA et de recommander des Lync 2013 et Skype pour servir des clients d’entreprise à l’avenir dans un environnement éventuelle post-MCX. 
  
Il est important de noter que toutes ces fonctionnalités sont disponibles après l’implémentation de mobilité, ils peuvent fonctionnent un peu différemment sur certains périphériques. Nous avons un site Web qui présente des fonctionnalités qui fonctionnent sur des périphériques, en [comparaison des fonctionnalités de client Mobile de Skype pour les entreprises](clients-and-devices/mobile-feature-comparison.md). Nous avons également quelques appareils et des informations de système d’exploitation à [Planifier pour les clients et les périphériques](clients-and-devices/clients-and-devices.md).
  
Mobilité rend l’utilisation de la fonctionnalité de découverte automatique fonctionnalité, qui permet aux clients de localiser automatiquement le Skype pour les services web de serveur de l’entreprise sans avoir à entrer dans les URL (ils ne doivent même savoir les) des utilisateurs. En cas de résolution de problèmes, la saisie manuelle d'URL est toujours prise en charge.
  
Les notifications de transmission sont également pris en charge, lorsque le Skype pour application métier n’est pas en cours d’exécution en arrière-plan (ou pour les périphériques mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan). Une notification push est envoyée à un appareil mobile lorsqu'un événement survient alors que l'application ou l'appareil est inactif. Par exemple, vous avez manqué un message instantané alors que votre téléphone était éteint, une notification push est alors envoyée (présentée sous forme de toast ou de notification, comme dans le cas d'une exécution de l'application en arrière-plan). Grâce aux notifications push, les utilisateurs ne manqueront plus aucun message instantané ni appel audio.
  
Pour plus d’informations, consultez les sections suivantes :
  
- [Composants de mobilité](mobility.md#MobilityComponents)
    
- [Topologies prises en charge](mobility.md#SupportedTopos)
    
- [Configuration technique requise](mobility.md#TechRequirements)
    
- [Définition de vos besoins en termes de mobilité](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Composants de mobilité
<a name="MobilityComponents"> </a>

Il existe quatre services qui composent la mobilité de Skype pour Business Server 2015 :
  
- **API web Communications unifiées (UCWA)**
    
    Fournit des services de communications en temps réel avec mobile et les clients web pour Skype pour Business Server 2015. Lorsque Skype pour Business Server est déployé, un répertoire virtuel UCWA est créé dans les services web internes et externes. Un composant virtuel dans ce répertoire virtuel qui accepte des appels de clients prenant en charge les UCWA. Les applications client communiquent via une interface de transfert (reste) de représentation d’état pour :
    
  - informations de présence
    
  - contacts
    
  - messagerie instantanée
    
  - VoIP
    
  - vidéoconférences
    
  - collaboration
    
    UCWA utilise un canal basé sur P-GET pour envoyer des événements tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
- **Service de mobilité (MCX)**
    
    Skype prend en charge les fonctionnalités de Business Server, telles que la messagerie instantanée, présence et des contacts, sur les périphériques mobiles. Le service de la mobilité est installé sur chaque serveur frontal dans chaque pool qui a conçu pour prendre en charge Skype pour la fonctionnalité de serveur de l’entreprise sur les périphériques mobiles. Lorsque vous installez Skype pour Business Server 2015 un nouveau répertoire virtuel (Mcx) est créé sous les sites internes et externes sur vos serveurs frontaux.
    
    > [!NOTE]
    > Comme indiqué précédemment, les services MCX ne seront plus disponibles dans la version ultérieure du produit. 
  
- **Service de découverte automatique**
    
    Identifie l’emplacement de l’utilisateur et permet à des périphériques mobiles et autre Skype pour entreprise aux clients de localiser des ressources (telles que les URL internes et externes pour Skype pour Business Server 2015, Services Web, l’URL de Mcx ou UCWA URL), quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôtes codés en dur (lyncdiscoverinternal pour les utilisateurs qui se trouvent sur le réseau et lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Elle prend en charge les connexions clientes qui utilisent le protocole HTTP ou HTTPS. 
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur chaque directeur dans chaque pool qui a conçu pour prendre en charge Skype pour la fonctionnalité de serveur de l’entreprise sur les périphériques mobiles. Lorsque vous installez le service, un nouveau répertoire virtuel (découverte automatique) est créé sous les sites internes et externes sur vos serveurs frontaux et les directeurs.
    
- **Service de notifications Push**
    
    Un service en nuage qui se trouve dans votre Skype pour centre de données commerciales en ligne. Sur les téléphones qui n’ont pas Skype pour client d’entreprise en cours d’exécution en arrière-plan, lorsqu’un événement se produit, notification d’un événement manquée (appelé une notification de transmission) est envoyée à l’appareil mobile à la place. Le service de la mobilité envoie une notification au service de notification d’émission (MPNS), qui l’envoie ensuite à l’appareil mobile. L'utilisateur peut alors répondre sur son téléphone pour activer l'application. Un serveur de transport Edge est requis pour cette fonctionnalité.
    
## <a name="supported-topologies"></a>Topologies prises en charge
<a name="SupportedTopos"> </a>

Nous avons le Skype suivant pris en charge pour les applications de serveur d’entreprise pour votre planification de la topologie :
  
- Édition Standard de mobilité
    
- Édition d’entreprise de mobilité
    
Vous devez être en mesure d’utiliser cette fonctionnalité avec Skype pour les serveurs de bord Business Server ou des serveurs de périphérie de Lync Server 2013.
  
Le service de mobilité est pris en charge sur les serveurs frontaux lorsque colocalisé avec le rôle de serveur de médiation, avec deux interfaces réseau, mais vous devez prendre les mesures appropriées pour configurer ces interfaces. Vous devez attribuer des adresses IP à l’interface spécifique qui communique comme le serveur de médiation et l’interface IP réseau qui communique comme le serveur frontal. Ce faire, dans le Générateur de topologie en sélectionnant l’adresse IP pour chaque service, au lieu d’utiliser la sélection **d’utiliser toutes les adresses IP configurées** par défaut.
  
## <a name="technical-requirements"></a>Configuration technique requise
<a name="TechRequirements"> </a>

Il est important de planifier les différents scénarios d’application mobile que vos utilisateurs mobiles peuvent rencontrer. Par exemple, une personne peut démarrer à l’aide d’une application mobile en dehors du travail en se connectant via un réseau de 3G, puis passez au réseau Wi-Fi d’entreprise lorsqu’ils atteignent le travail. Ils peuvent faire basculer en 4G lorsqu’ils quittent leur construction. Planification maintenant vous permettra de prendre en charge de ces transitions de réseau et de garantir une expérience utilisateur cohérente.
  
### <a name="dns-configuration"></a>Configuration DNS

Les services de mobilité, Mcx et UCWA utilisent DNS de la même manière. Grâce à la découverte automatique, les appareils mobiles utilisent le système DNS pour rechercher des ressources. Lors de la recherche DNS, une tentative de connexion est effectuée vers le nom de domaine complet associé à l’enregistrement DNS interne (lyncdiscoverinternal.[internal domain name]). Si aucune connexion ne peut être établie à l’aide de l’enregistrement DNS interne, une seconde tentative de connexion est effectuée à l’aide de l’enregistrement DNS externe (lyncdiscover.[sipdomain]). Pourquoi disposer des deux ? Un appareil mobile interne à votre réseau pourra utiliser l'URL interne de découverte automatique. Les appareils mobiles externes utiliseront l'URL externe de découverte automatique. Dans les deux cas, le service de découverte automatique renvoie toutes les URL de service Web pour le pool de domicile de l’utilisateur, qui inclut le service de mobilité (Mcx et UCWA).
  
Il est prévu que les demandes de découverte automatique externes passe par le proxy inverse, que vous avez configuré pour Skype pour Business Server 2015. Toutefois, à la fois l’URL de service de mobilité interne et l’URL du service mobilité externe associés le FQDN de Services Web externes. Par conséquent, qu’un appareil mobile soit interne ou externe à votre réseau, le périphérique se connecte toujours au Skype pour le service de serveur 2015 mobilité en externe, par le biais de votre proxy inverse.
  
> [!NOTE]
> Comme nous l’avons dit simplement, tout trafic de service de mobilité (interne et externe) passe par le biais de votre proxy inverse. Cependant, une erreur se produit parfois lorsque le trafic interne sort par une interface, pour ensuite tenter de revenir vers cette même interface. Cela peut entraîner une violation de vos règles de sécurité appelée usurpation d'identité (usurpation d’identité de paquet TCP). Vous devez autoriser **L’épinglage de cheveux** à fonction de mobilité.
  
> [!NOTE]
> Si vous êtes prêt à le faire, vous pouvez également choisir d’utiliser un proxy inverse qui est distinct de votre pare-feu (pour la sécurité à des fins, la prévention de l’usurpation d’identité doivent toujours être appliquées au niveau du pare-feu). De cette façon, l’EPINGLE peut se produire à l’interface externe de votre serveur proxy inverse, plutôt que des interface externe de votre firewall. Cela vous permet de détecter l’usurpation correctement au niveau de votre pare-feu pendant que vous assouplissez la règle à votre serveur proxy inverse, et vous obtenez votre fonctionnalité de mobilité. 
  
> [!NOTE]
> Si vous choisissez cette méthode, veillez à utiliser l’hôte DNS ou les enregistrements CNAME pour définir le proxy inverse pour le comportement d’EPINGLE (pas le pare-feu), si possible. 
  
Certains éléments devront être configurés pour prendre en charge les utilisateurs situés à l'intérieur comme l’extérieur du réseau de votre société.
  
Voici les règles applicables aux noms de domaine complets web internes et externes :
  
- nouveaux enregistrements DNS CNAME ou A (hôte, si IPv6, AAAA) pour la découverte automatique ;
    
- nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications push à travers votre réseau Wi-Fi ;
    
- Objet autres noms sur les certificats de serveur interne et proxy inversé pour la découverte automatique.
    
- Matériel de serveur principal avant équilibrage l’affinité de source de modifications de configuration.
    
Il s’agit de la configuration de topologie requise pour prendre en charge le Service de la mobilité et le Autodiscover Service :
  
- Le Front-End pool interne site web nom de domaine complet doit être distinct du Front-End pool externe site Web complet.
    
- Le nom de domaine complet web interne doit uniquement être résolu vers et accessible depuis l’intérieur du réseau d’entreprise.
    
- Le nom de domaine complet web externe doit uniquement être résolu vers et accessible depuis Internet.
    
- Pour un utilisateur à l’intérieur du réseau d’entreprise, l’URL de service de mobilité doit être traité sur le web externe, nom de domaine complet. Cette exigence est pour le service de la mobilité et s’applique uniquement à cette URL.
    
- Pour un utilisateur en dehors du réseau d’entreprise, la demande doit aller sur le web externe, nom de domaine complet du pool frontal ou directeur.
    
Si vous prenez en charge la découverte automatique, vous devrez créer les enregistrements DNS suivants pour chaque domaine SIP :
  
- un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis l'intérieur de votre réseau de votre organisation.
    
- un enregistrement DNS externe, ou public, afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.
    
L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau interne. L’URL de découverte automatique externe ne doit pas être adressable depuis l'intérieur de votre réseau. Toutefois, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité de votre client mobile ne sera probablement pas affectée, car la première tentative portera toujours sur l’URL interne.
  
### <a name="port-and-firewall-requirements"></a>Exigences relatives aux ports et aux pare-feu

Nous avons étudié la plupart des cela dans notre autre documentation, mais pour la mobilité, vous allez avoir les ports suivants ouverts sur votre réseau Wi-Fi d’entreprise si vous disposez de tous les utilisateurs hébergement sur une solution matérielle-logicielle de branche Survivable (SBA) :
  
- UcwaSipExternalListeningPort requiert le port 5088.
    
- UcwaSipPrimaryListeningPort requiert le port 5089.
    
### <a name="certificate-requirements"></a>Exigences en matière de certificats

Si vous utilisez la découverte automatique pour votre Skype pour clients mobiles d’entreprise, vous devez modifier les listes de SAN (autre nom du sujet) à vos certificats pour prendre en charge les connexions sécurisées à partir de vos clients mobiles. Si vous avez déjà des certificats sur place, vous devrez demander et affecter les nouveaux certificats avec les entrées de SAN décrites ici. Cela doit être fait pour chaque serveur frontal et le directeur (si dans votre environnement) qui exécute le service de découverte automatique. Il est également préférable de modification des que listes de SAN sur vos certificats de proxy inverse, ajout d’entrées de SAN pour chaque domaine SIP de votre organisation.
  
Ce doit être un processus simple si vous demandez les nouveaux certificats désactiver une autorité de certification interne (autorité de certification), mais les certificats publics sont plus complexes et plus coûteuses à demander de nouveau, ne pas de mentionner qu’il peut s’avérer coûteux d’ajouter un grand nombre de SIP domaines à un nouveau certificat public. Dans ce cas, il existe une approche qui est pris en charge, mais **pas recommandé**. Vous pouvez configurer votre proxy inverse pour effectuer la demande de service de découverte automatique initiale sur le port 80, utilisez HTTP, plutôt que le port 443, qui est le protocole HTTPS (et 443 est la configuration par défaut). Cette demande entrante est redirigée vers le port 8080 de votre pool frontal ou d’un directeur. De cette façon, il ne sera pas nécessaire de modifier vos certificats, car ce trafic n'utilise pas le protocole HTTPS pour les demandes. Nous voulons cependant insister sur le fait que nous ne recommandons pas cette approche, bien qu'elle fonctionnera dans votre cas.
  
### <a name="windows-and-iis-requirements"></a>Configuration requise pour Windows et les services Internet (IIS)

Comme indiqué dans notre principal article de [configuration serveur requise pour Skype pour Business Server 2015](requirements-for-your-environment/server-requirements.md) , vous devez avoir Windows Server 2012 R2 ou Windows Server 2012 pour votre Skype pour un environnement de serveur d’entreprise. Par conséquent, vous devez disposer également de IIS 8 ou IIS 8.5 pour vos besoins en termes de mobilité. Il faudra quelques modifications aux paramètres ASP.NET par défaut, mais le programme d’installation du service de mobilité est le faire automatiquement.
  
### <a name="hlb-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Si vous utilisez une topologie de Skype pour Business Server 2015 incluant une HUMIDIFICATION à HLB pour votre pool de Front-End (ce qui serait une topologie qui inclut plus d’un serveur frontal), l’externe des Services Web IPs virtuel (VIPs) pour le trafic des Services Web doivent être configuré pour la source. L'affinité source permet d'assurer l'envoi de plusieurs connexions provenant d'un seul client vers le même serveur pour maintenir l’état de la session.
  
Si vous envisagez de prendre en charge Skype pour les clients professionnels mobiles uniquement sur votre réseau Wi-Fi interne, vous devez configurer votre VIP de Services Web internes pour source comme décrit pour le VIP de Services Web externes. Dans ce cas, vous devez utiliser source_addr (ou TCP) une affinité pour le VIP de Services Web internes sur l’humidification à HLB.
  
Pour plus d’informations sur tout cela, veuillez consulter la documentation de [l’équilibrage de la charge requise pour Skype pour les entreprises](network-requirements/load-balancing.md) .
  
### <a name="reverse-proxy-requirements"></a>Exigences relatives au proxy inverse

Pour prendre en charge la découverte automatique pour Skype pour clients mobiles d’entreprise, vous devez mettre à jour la règle de publication en cours comme suit :
  
- Si vous décidez de mettre à jour les listes de SAN sur vos certificats de proxy inverse et vous utilisez HTTPS pour la demande de service de découverte automatique initiale, vous devez mettre à jour la règle de publication web pour lyncdiscover. \<sipdomain\>. Cela est généralement combinée avec la publication rul pour l’URL des Services Web externes sur le pool frontal.
    
- Si vous avez décidé d’utiliser HTTP pour la requête de service de découverte automatique initiale éviter de devoir mettre à jour le SAN liste pour vos certificats de proxy inverse (qui n’est pas recommandé), vous devrez créer une nouvelle règle de publication web pour le port HTTP/TCP 80, si il n’existe pas déjà. Si cette règle existe, mettre à jour pour inclure un lyncdiscover. \<sipdomain\> entrée.
    
## <a name="defining-your-mobility-needs"></a>Définition de vos besoins en termes de mobilité
<a name="MobilityNeeds"> </a>

Maintenant que nous avons examiné les topologies, les composants et les exigences techniques, examinons ce que votre organisation peut avoir besoin en termes d’une implémentation de la mobilité.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Souhaitez-vous utiliser la découverte automatique pour les clients mobiles Skype Entreprise ?

Nous vous recommandons vivement d'utiliser la découverte automatique. La création d'enregistrements DNS internes et externes sera requise, tel que décrit dans la section de configuration technique requise plus haut. Avec la découverte automatique, le Skype pour les clients de l’entreprise permet de rechercher automatiquement Skype pour les Services Web de 2015 Server à partir de n’importe quel endroit, sans avoir besoin d’être entré manuellement dans une URL.
  
Vous pouvez utiliser les paramètres manuels si besoin est. Ces URL devront être saisies par les utilisateurs dans leurs appareils mobiles :
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** pour l’accès externe.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** pour l’accès interne.
    
Nous vous recommandons à nouveau d'utiliser la découverte automatique. Les paramètres manuels vous seront peut-être utiles lors de la résolution de problèmes.
  
### <a name="are-you-going-to-support-push-notifications"></a>Allez-vous prendre en charge les notifications push ?

Les notifications push sont utilisées pour les applications mobiles qui prennent en charge cette fonctionnalité pour notifier un utilisateur d'un événement survenu alors que l'application était inactive. Votre serveur de transport Edge devrez ont une relation de fédération avec votre Skype en nuage pour le Service Business Server Push Notification, qui se trouve sous le Skype pour centre de données commerciales en ligne. Vous devrez exécuter un applet de commande pour activer les notifications push.
  
> [!NOTE]
> Si vous disposez de tous les utilisateurs de toujours les clients Lync Server 2010, il devra ouvrir de port 5223 TCP sortant sur votre réseau Wi-Fi d’entreprise. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Voulez-vous que tous vos utilisateurs d’accéder à toutes les fonctionnalités de mobilité, ou vous souhaitez spécifier les utilisateurs qui peuvent accéder à ces fonctionnalités à la place ?

Nous disposons d’une table pour vous aider avec certaines des fonctionnalités qui sont disponibles pour tous les utilisateurs et si elles vous définies qui fait ou non par défaut. Pour une liste complète, consultez [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Les étendues pour l'ensemble de ces fonctions sont Globale/Site/Utilisateur. 
  
|**Fonctionnalité**|**Nom du paramètre**|**Description**|**Paramètre par défaut**|
|:-----|:-----|:-----|:-----|
|Activer la mobilité  <br/> |EnableMobility  <br/> |Contrôle utilisateurs de Skype pour client mobile Business est installé dans une portée donnée. Si la stratégie est définie sur False, vos utilisateurs ne seront pas en mesure de se connecter à l'aide de leur client.  <br/> |True  <br/> |
|Voix extérieure  <br/> |EnableOutsideVoice  <br/> |Permet à un utilisateur d'utiliser l’Appel via le bureau, une fonctionnalité qui lui permet d’effectuer et de recevoir des appels à l’aide de son numéro professionnel au lieu de son numéro de téléphone mobile. Si ce paramètre est défini sur False, vos utilisateurs ne pourront pas effectuer ou recevoir d’appel à l’aide de leur numéro professionnel depuis leur téléphone mobile.  <br/> |True  <br/> |
|Activer l’audio/la vidéo IP  <br/> |EnableIPAudioVideo  <br/> |Défini sur la valeur par défaut, ce paramètre permet à un utilisateur d'utiliser VoIP pour effectuer ou recevoir des appels sur son appareil mobile. Si ce paramètre est défini sur False, vos utilisateurs ne pourront pas utiliser leur appareil mobile pour effectuer ces actions.  <br/> |True  <br/> |
|Exiger WiFi pour l’audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Détermine si un client devra passer et recevoir les appels sur VoIP sur Wi-Fi plutôt que sur le réseau de données cellulaire. Si ce paramètre est défini sur True, vos utilisateurs pourront passer et recevoir des appels VoIP uniquement lorsqu’ils sont connectés à un réseau WiFi.  <br/> |False  <br/> |
|Exiger WiFi pour la vidéo IP  <br/> |RequireWiFiForIPVideo  <br/> |Détermine si un client devra passer et recevoir les appels vidéo sur VoIP sur Wi-Fi plutôt que sur le réseau de données cellulaire. Si ce paramètre est défini sur True, vos utilisateurs pourront passer et recevoir des appels VoIP uniquement lorsqu’ils sont connectés à un réseau WiFi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Les utilisateurs qui ne sont pas activés pour Voix Entreprise doivent-ils pouvoir utiliser la fonctionnalité Cliquez pour participer afin de rejoindre des conférences ?

Pour les utilisateurs d’accéder aux fonctionnalités de mobilité et l’appel via le travail, ils doivent être activés pour la Voix Entreprise. Si ce n'est toutefois pas le cas, ils peuvent toujours participer aux conférences en cliquant sur un lien sur leur appareil mobile, mais une stratégie de voix appropriée devra leur être affectée. Vous pouvez procéder de l'une des manières suivantes :
  
- affectez une stratégie de voix spécifique pour ces utilisateurs ; ou,
    
- assurez-vous qu'une stratégie globale ou de niveau site existe et qu'elle leur est appliquée.
    
Dans un cas comme dans l'autre, la stratégie de voix que vous assignez doit avoir des enregistrements d’utilisation PSTN (Public Switched Telephone Network) et des itinéraires qui définiront les zones à partir desquelles les utilisateurs peuvent téléphoner pour rejoindre une conférence.
  
> [!NOTE]
> Les utilisateurs mobiles qui souhaitent utiliser le clic en jointure nécessitent une stratégie Voice, ainsi que les enregistrements d’utilisation de TLS connexes et les itinéraires de voix, car lorsqu’ils cliquent sur ce lien sur leurs appareils mobiles, un appel sortant à partir de Skype pour Business Server 2015 sera le résultat. 
  

