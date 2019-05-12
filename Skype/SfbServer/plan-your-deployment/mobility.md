---
title: Planifier pour la mobilité Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planifier votre implémentation de la mobilité pour Skype pour Business Server.
ms.openlocfilehash: e981f7d9ac22739dc38bc48e574d96670536594b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907205"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planifier pour la mobilité Skype pour Business Server
 
Planifier votre implémentation de la mobilité pour Skype pour Business Server.
  
Avec Skype pour Business Server, vous pouvez déployer la fonctionnalité de mobilité pour fournir Skype pour la fonctionnalité Business Server sur les appareils mobiles. Cet article fournit des détails sur la fonctionnalité de mobilité et vous aide à planifier votre déploiement.
  
La fonctionnalité de mobilité pour Skype pour Business Server est en mesure de prendre en charge les clients mobiles pour Skype pour les entreprises, ainsi que les clients Lync en revenant à 2010. Une fois qu’il est déployé, les utilisateurs peuvent se connecter à votre Skype pour Business Server à l’aide de déploiement prises en charge des e/s, les appareils mobiles Android et Windows Phone pour tirer parti des différentes fonctionnalités, y compris les fonctionnalités Enterprise Voice. Nous avons inclus une liste partielle ci-dessous, et vous pouvez également consulter la [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](clients-and-devices/desktop-feature-comparison.md) pour plus d’informations :
  
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
    
Tout cela se fait par le biais du Unified Communications Web API ou UCWA. UCWA a été initialement introduite dans Lync Server 2013, et il est en cours d’utilisation pour Skype pour Business Server. Il existe une fonctionnalité supplémentaire pour communiquer avec les clients Lync 2010, et qui est le Service de mobilité (MCX). Il s’agit des services gratuits, permettant de Lync Server 2010 et clients 2013, ainsi que Skype pour les clients professionnels, pour accéder aux Skype pour les déploiements de serveur d’entreprise avec succès.
  
> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
Il est important de noter que toutes ces fonctionnalités sont disponibles après l’implémentation de mobilité, ils peuvent fonctionnent un peu différemment sur certains appareils. Nous avons un site Web qui traite des fonctionnalités qui fonctionnent sur des périphériques, en [comparaison des fonctionnalités de client Mobile pour Skype pour les entreprises](clients-and-devices/mobile-feature-comparison.md). Nous avons également certains appareils et les informations du système d’exploitation à [planifier les clients et périphériques](clients-and-devices/clients-and-devices.md).
  
Mobilité fait usage de la découverte automatique fonctionnalité, qui permet aux clients de localiser automatiquement Skype pour les services web Business Server sans que les utilisateurs qui ont besoin d’entrer dans les URL (ils ne ne sont pas même besoin de connaître leur). En cas de résolution de problèmes, la saisie manuelle d'URL est toujours prise en charge.
  
Les notifications Push sont également prises en charge, pour lorsque le Skype pour l’application de gestion n’est pas en cours d’exécution en arrière-plan (ou pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan). Une notification push est envoyée à un appareil mobile lorsqu'un événement survient alors que l'application ou l'appareil est inactif. Par exemple, vous avez manqué un message instantané alors que votre téléphone était éteint, une notification push est alors envoyée (présentée sous forme de toast ou de notification, comme dans le cas d'une exécution de l'application en arrière-plan). Grâce aux notifications push, les utilisateurs ne manqueront plus aucun message instantané ni appel audio.
  
Pour plus d’informations, consultez les sections suivantes :
  
- [Composants de mobilité](mobility.md#MobilityComponents)
    
- [Topologies prises en charge](mobility.md#SupportedTopos)
    
- [Configuration technique requise](mobility.md#TechRequirements)
    
- [Définition de vos besoins en termes de mobilité](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Composants de mobilité
<a name="MobilityComponents"> </a>

Il existe quatre services qui composent la mobilité pour Skype pour Business Server :
  
- **API web Communications unifiées (UCWA)**
    
    Fournit des services pour les communications en temps réel avec mobile et les clients web pour Skype pour Business Server. Lorsque Skype pour Business Server est déployé, un répertoire virtuel UCWA créé dans les services web internes et externes. Composant virtuel dans ce répertoire virtuel qui accepte les appels de clients prenant en charge UCWA. Les applications clientes communiquent via une interface representational state transfer (REST) pour :
    
  - informations de présence
    
  - contacts
    
  - messagerie instantanée
    
  - VoIP
    
  - vidéoconférences
    
  - collaboration
    
    UCWA utilise un canal basé sur P-GET pour envoyer des événements tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
- **Service de mobilité (MCX)**
    
    Prend en charge Skype pour les fonctionnalités du serveur d’entreprise, telles que la messagerie instantanée, présence et contacts, sur les appareils mobiles. Le service de mobilité est installé sur chaque serveur frontal dans chaque pool qui est destiné à prendre en charge Skype pour la fonctionnalité Business Server sur les appareils mobiles. Lorsque vous installez Skype pour Business Server 2015 un nouveau répertoire virtuel (Mcx) est créé sous les sites internes et externes sur vos serveurs frontaux.
    
    > [!NOTE]
    > Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
- **Service de découverte automatique**
    
    Identifie l’emplacement de l’utilisateur et Active les appareils mobiles et autres Skype pour les clients d’entreprise rechercher des ressources (par exemple, les URL internes et externes pour Skype pour Business Server Web Services, l’URL Mcx ou une URL UCWA) quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôtes codés en dur (lyncdiscoverinternal pour les utilisateurs qui se trouvent sur le réseau et lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Elle prend en charge les connexions clientes qui utilisent le protocole HTTP ou HTTPS. 
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur chaque directeur dans chaque pool qui est destiné à prendre en charge Skype pour la fonctionnalité Business Server sur les appareils mobiles. Lorsque vous installez le service, un nouveau répertoire virtuel (découverte automatique) est créé sous les sites internes et externes sur vos serveurs frontaux et les directeurs.
    
- **Service de notifications Push**
    
    Un service en nuage qui se trouve dans votre Skype pour le centre de données métiers en ligne. Sur les téléphones qui n’ont pas Skype pour client d’entreprise en cours d’exécution en arrière-plan, lorsqu’un événement se produit, notification d’un événement manqué (appelé une notification push) est envoyée à l’appareil mobile à la place. Le service de mobilité envoie une notification au service de notification push (MPNS), qui envoie ensuite à l’appareil mobile. L'utilisateur peut alors répondre sur son téléphone pour activer l'application. Un serveur de périphérie est requis pour cette fonctionnalité.
    
## <a name="supported-topologies"></a>Topologies prises en charge
<a name="SupportedTopos"> </a>

Nous avons le Skype suivant pris en charge pour les applications Business Server pour votre planification de la topologie :
  
- Mobilité Standard Edition
    
- Mobilité Enterprise Edition
    
Vous devez être en mesure d’utiliser cette fonctionnalité avec Skype pour les serveurs de périphérie Business Server ou des serveurs de périphérie Lync Server 2013.
  
Le service de mobilité est pris en charge sur les serveurs frontaux lorsque colocalisé avec le rôle de serveur de médiation, avec deux interfaces réseau, mais vous devez prendre des mesures appropriées pour configurer ces interfaces. Vous devez attribuer des adresses IP à l’interface spécifique qui communique en tant que le serveur de médiation et l’interface réseau IP qui communique en tant que serveur frontal. Vous pouvez faire ceci dans le Générateur de topologie en sélectionnant l’adresse IP pour chaque service, au lieu d’utiliser la sélection **d’utiliser toutes les adresses IP configurées** par défaut.
  
## <a name="technical-requirements"></a>Configuration technique requise
<a name="TechRequirements"> </a>

Il est important de planifier les différents scénarios applications mobiles de que vos utilisateurs mobiles peuvent rencontrer. Par exemple, une personne peut démarrer à l’aide d’une application mobile à l’extérieur de travail en vous connectant via un réseau 3 G, puis basculer vers le réseau d’entreprise Wi-Fi lorsqu’ils atteignent le travail. Ils peuvent basculent vers 4G quittant leur création. Planification maintenant vous autorisera à prendre en charge ces transitions réseau et garantir une expérience utilisateur cohérente.
  
### <a name="dns-configuration"></a>Configuration DNS

Les services de mobilité Mcx et UCWA utilisent DNS de la même manière. Grâce à la découverte automatique, les appareils mobiles utilisent le système DNS pour rechercher des ressources. Lors de la recherche DNS, une tentative de connexion est effectuée vers le nom de domaine complet associé à l’enregistrement DNS interne (lyncdiscoverinternal.[internal domain name]). Si aucune connexion ne peut être établie à l’aide de l’enregistrement DNS interne, une seconde tentative de connexion est effectuée à l’aide de l’enregistrement DNS externe (lyncdiscover.[sipdomain]). Pourquoi disposer des deux ? Un appareil mobile interne à votre réseau pourra utiliser l'URL interne de découverte automatique. Les appareils mobiles externes utiliseront l'URL externe de découverte automatique. Dans les deux cas, le service de découverte automatique renvoie toutes les URL de service Web pour le pool d’accueil de l’utilisateur, qui inclut le service de mobilité (Mcx et UCWA).
  
Il est prévu que les demandes de découverte automatique externes passe par le proxy inverse, que vous avez configuré pour Skype pour Business Server. Toutefois, l’URL interne du service de mobilité et de l’URL externe du service de mobilité associés avec le nom complet des Services Web externes. Par conséquent, qu’un appareil mobile soit internes ou externes à votre réseau, le périphérique toujours se connecte à la Skype Business Server service de mobilité en externe, par le biais de votre serveur proxy inverse.
  
> [!NOTE]
> Comme nous l’avons dit uniquement, tout trafic de service de mobilité (interne et externe) passe en revue votre proxy inverse. Cependant, une erreur se produit parfois lorsque le trafic interne sort par une interface, pour ensuite tenter de revenir vers cette même interface. Cela peut entraîner une violation de vos règles de sécurité appelée usurpation d'identité (usurpation d’identité de paquet TCP). Vous devez autoriser **L’épinglage cheveux** pour que la fonction de mobilité.
  
> [!NOTE]
> Si vous êtes prêt pour ce faire, vous pouvez également choisir d’utiliser un proxy inverse séparé de votre pare-feu (pour la sécurité à des fins, prévention de l’usurpation d’identité doivent toujours être appliquées au niveau du pare-feu). Ainsi, la « hairpin » peut se produire au niveau de l’interface externe de votre serveur proxy inverse, plutôt que d’interface externe de votre pare-feu. Cela vous permet de détecter l’usurpation correctement à votre pare-feu pendant que vous assouplissez la règle à votre serveur proxy inverse, vous obtenez votre fonctionnalité de mobilité. 
  
> [!NOTE]
> Si vous passez cet itinéraire, veillez à utiliser l’hôte DNS ou les enregistrements CNAME pour définir le proxy inverse pour le comportement hairpin (pas le pare-feu), si possible. 
  
Certains éléments devront être configurés pour prendre en charge les utilisateurs situés à l'intérieur comme l’extérieur du réseau de votre société.
  
Voici les règles applicables aux noms de domaine complets web internes et externes :
  
- nouveaux enregistrements DNS CNAME ou A (hôte, si IPv6, AAAA) pour la découverte automatique ;
    
- nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications push à travers votre réseau Wi-Fi ;
    
- Objet noms de sujet sur les certificats de serveurs internes et les certificats de proxy inverse, pour la découverte automatique.
    
- Charge de matériel serveur frontal équilibrée l’affinité source de modifications de configuration.
    
Il s’agit de la configuration de topologie requise pour prendre en charge le Service de mobilité et le Autodiscover Service :
  
- Le Front-End web interne nom de domaine complet doit être différent du web externe du pool frontal nom de domaine complet.
    
- Le nom de domaine complet web interne doit uniquement être résolu vers et accessible depuis l’intérieur du réseau d’entreprise.
    
- Le nom de domaine complet web externe doit uniquement être résolu vers et accessible depuis Internet.
    
- Pour un utilisateur à l’intérieur du réseau d’entreprise, l’URL du service de mobilité doit être traité au nom de domaine complet web externe. Cette condition est pour le service de mobilité et s’applique uniquement à cette URL.
    
- Pour un utilisateur en dehors du réseau d’entreprise, la demande doit parvenir au nom de domaine complet du directeur ou pool frontal web externe.
    
Si vous prenez en charge la découverte automatique, vous devrez créer les enregistrements DNS suivants pour chaque domaine SIP :
  
- un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis l'intérieur de votre réseau de votre organisation.
    
- un enregistrement DNS externe, ou public, afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.
    
L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau interne. L’URL de découverte automatique externe ne doit pas être adressable depuis l'intérieur de votre réseau. Toutefois, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité de votre client mobile ne sera probablement pas affectée, car la première tentative portera toujours sur l’URL interne.
  
### <a name="port-and-firewall-requirements"></a>Exigences relatives aux ports et aux pare-feu

Nous avons abordé la plupart de ce dans notre autre documentation, mais pour la mobilité, vous allez est important que les ports suivants ouverts sur votre réseau d’entreprise Wi-Fi si vous disposez de tous les utilisateurs hébergement sur un serveur Survivable Branch Appliance (SBA) :
  
- UcwaSipExternalListeningPort requiert le port 5088.
    
- UcwaSipPrimaryListeningPort requiert le port 5089.
    
### <a name="certificate-requirements"></a>Exigences en matière de certificats

Si vous utilisez la découverte automatique pour votre Skype pour clients mobiles d’entreprise, vous devez modifier les listes SAN (autre nom du sujet) sur vos certificats pour prendre en charge les connexions sécurisées à partir de vos clients mobiles. Si vous avez déjà des certificats sur place, vous devrez demander et assigner des nouveaux certificats avec les entrées SAN décrites ici. Cela vous devrez être effectuée pour chaque serveur frontal et un directeur (si dans votre environnement) qui exécute le service de découverte automatique. Il est également préférable de modification des que listes de SAN sur vos certificats de proxy inverse, ajout d’entrées SAN pour chaque domaine SIP dans votre organisation.
  
Ce doit être un processus très simple si vous demandez les nouveau certificats désactiver une autorité de certification interne (autorité de certification), mais les certificats publics sont beaucoup plus coûteuses à demander de nouveau, ne pas de mentionner qu'il peut s’avérer coûteuse ajouter un grand nombre de SIP et plus complexes domaines à un nouveau certificat public. Dans cette situation, il existe une approche est prise en charge, mais **non recommandée**. Vous pouvez configurer votre serveur proxy inverse pour rendre la demande initiale du service de découverte automatique sur le port 80, qui utilise HTTP, plutôt que le port 443, qui est le protocole HTTPS (et 443 est la configuration par défaut). Cette requête entrante s’affichera et le port 8080 sur votre directeur ou votre pool frontal. De cette façon, il ne sera pas nécessaire de modifier vos certificats, car ce trafic n'utilise pas le protocole HTTPS pour les demandes. Nous voulons cependant insister sur le fait que nous ne recommandons pas cette approche, bien qu'elle fonctionnera dans votre cas.
  
### <a name="windows-and-iis-requirements"></a>Configuration requise pour Windows et les services Internet (IIS)

Vous devez disposer d’une version prise en charge de Windows Server pour votre Skype pour un environnement de serveur d’entreprise. Par conséquent, vous devez disposer également de IIS 8 ou IIS 8.5 pour vos besoins en termes de mobilité. Il faudra quelques modifications aux paramètres ASP.NET par défaut, mais le programme d’installation du service de mobilité sera le faire automatiquement.
  
### <a name="hlb-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Si vous utilisez une topologie pour Skype pour Business Server qui comporte un matérielle pour votre pool frontal (qui doit être n’importe quelle topologie qui comprend plus d’un serveur frontal), l’externe des Services Web IP virtuelles (VIP) pour le trafic des Services Web doivent être configurés pour la source. L'affinité source permet d'assurer l'envoi de plusieurs connexions provenant d'un seul client vers le même serveur pour maintenir l’état de la session.
  
Si vous envisagez de prendre en charge Skype pour les clients mobiles Business uniquement sur votre réseau Wi-Fi interne, vous devez configurer votre VIP de Services Web internes pour source comme indiqué pour VIP de Services Web externes. Dans ce cas, vous devez utiliser source_addr (ou TCP) affinité pour le VIP de Services Web internes sur le HLB.
  
Pour plus d’informations, reportez-vous à la documentation de [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Exigences relatives au proxy inverse

Afin de prendre en charge la découverte automatique Skype pour clients mobiles d’entreprise, vous devrez mettre à jour la règle de publication actuelle comme suit :
  
- Si vous décidez de mettre à jour les listes de SAN sur vos certificats de proxy inverse et vous utilisez le protocole HTTPS pour la demande de service de découverte automatique initiale, vous devez mettre à jour la règle de publication web pour lyncdiscover. \<sipdomain\>. Il est généralement associé à la publication rul pour l’URL des Services Web externes sur le pool frontal.
    
- Si vous avez décidé d’utiliser le protocole HTTP pour la demande de service de découverte automatique initiale éviter d’avoir à mettre à jour le SAN liste pour vos certificats de proxy inverse (qui n’est pas recommandé), vous devez créer une nouvelle règle de publication web pour le port HTTP/TCP 80, si il n’existe pas déjà. Si cette règle existe, mettre à jour pour inclure un lyncdiscover. \<sipdomain\> entrée.
    
## <a name="defining-your-mobility-needs"></a>Définition de vos besoins en termes de mobilité
<a name="MobilityNeeds"> </a>

Maintenant que nous avons passé en revue les topologies, les composants et les exigences techniques, examinons ce que votre organisation peut avoir besoin en termes d’une implémentation de mobilité.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Souhaitez-vous utiliser la découverte automatique pour les clients mobiles Skype Entreprise ?

Nous vous recommandons vivement d'utiliser la découverte automatique. La création d'enregistrements DNS internes et externes sera requise, tel que décrit dans la section de configuration technique requise plus haut. Avec la détection automatique, la Skype pour les clients d’entreprise permet de rechercher automatiquement Skype pour les Services Web Business Server à partir de n’importe quel emplacement, sans avoir besoin d’une URL doit être saisi au manuellement.
  
Vous pouvez utiliser les paramètres manuels si besoin est. Ces URL devront être saisies par les utilisateurs dans leurs appareils mobiles :
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** pour l’accès externe.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** pour l’accès interne.
    
Nous vous recommandons à nouveau d'utiliser la découverte automatique. Les paramètres manuels vous seront peut-être utiles lors de la résolution de problèmes.
  
### <a name="are-you-going-to-support-push-notifications"></a>Allez-vous prendre en charge les notifications push ?

Les notifications push sont utilisées pour les applications mobiles qui prennent en charge cette fonctionnalité pour notifier un utilisateur d'un événement survenu alors que l'application était inactive. Votre serveur Edge devrez ont une relation de fédération avec votre Skype basée sur le cloud pour Business Server Service de notifications Push, qui se trouve sur la Skype pour le centre de données métiers en ligne. Vous devrez exécuter un applet de commande pour activer les notifications push.
  
> [!NOTE]
> Si vous avez tout le monde toujours à l’aide de clients Lync Server 2010, il doit ouvrir le port 5223 de TCP sortant sur votre réseau d’entreprise Wi-Fi. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Voulez-vous que tous les utilisateurs l’accès à toutes les fonctionnalités de mobilité, ou vous souhaitez spécifier les utilisateurs pouvant accéder à ces fonctionnalités à la place ?

Nous disposons d’une table à l’aide de certaines des fonctionnalités qui sont disponibles pour tous les utilisateurs et si qu’ils sont réglés qui fait ou non par défaut. Pour obtenir une liste complète, veuillez consulter la rubrique [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Les étendues pour l'ensemble de ces fonctions sont Globale/Site/Utilisateur. 
  
|**Fonctionnalité**|**Nom du paramètre**|**Description**|**Paramètre par défaut**|
|:-----|:-----|:-----|:-----|
|Activer la mobilité  <br/> |EnableMobility  <br/> |Contrôle dans une étendue donnée, les utilisateurs qui disposent de Skype pour clients mobiles Business installé. Si la stratégie est définie sur False, vos utilisateurs ne seront pas en mesure de se connecter à l'aide de leur client.  <br/> |True  <br/> |
|Voix extérieure  <br/> |EnableOutsideVoice  <br/> |Permet à un utilisateur d'utiliser l’Appel via le bureau, une fonctionnalité qui lui permet d’effectuer et de recevoir des appels à l’aide de son numéro professionnel au lieu de son numéro de téléphone mobile. Si ce paramètre est défini sur False, vos utilisateurs ne pourront pas effectuer ou recevoir d’appel à l’aide de leur numéro professionnel depuis leur téléphone mobile.  <br/> |True  <br/> |
|Activer l’audio/la vidéo IP  <br/> |EnableIPAudioVideo  <br/> |Défini sur la valeur par défaut, ce paramètre permet à un utilisateur d'utiliser VoIP pour effectuer ou recevoir des appels sur son appareil mobile. Si ce paramètre est défini sur False, vos utilisateurs ne pourront pas utiliser leur appareil mobile pour effectuer ces actions.  <br/> |True  <br/> |
|Exiger WiFi pour l’audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Détermine si un client devra passer et recevoir les appels sur VoIP sur Wi-Fi plutôt que sur le réseau de données cellulaire. Si ce paramètre est défini sur True, vos utilisateurs pourront passer et recevoir des appels VoIP uniquement lorsqu’ils sont connectés à un réseau WiFi.  <br/> |False  <br/> |
|Exiger WiFi pour la vidéo IP  <br/> |RequireWiFiForIPVideo  <br/> |Détermine si un client devra passer et recevoir les appels vidéo sur VoIP sur Wi-Fi plutôt que sur le réseau de données cellulaire. Si ce paramètre est défini sur True, vos utilisateurs pourront passer et recevoir des appels VoIP uniquement lorsqu’ils sont connectés à un réseau WiFi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Les utilisateurs qui ne sont pas activés pour Voix Entreprise doivent-ils pouvoir utiliser la fonctionnalité Cliquez pour participer afin de rejoindre des conférences ?

Pour que les utilisateurs ont accès aux fonctionnalités de mobilité et l’appel via le bureau, ils doivent être activés pour Enterprise Voice. Si ce n'est toutefois pas le cas, ils peuvent toujours participer aux conférences en cliquant sur un lien sur leur appareil mobile, mais une stratégie de voix appropriée devra leur être affectée. Vous pouvez procéder de l'une des manières suivantes :
  
- affectez une stratégie de voix spécifique pour ces utilisateurs ; ou,
    
- assurez-vous qu'une stratégie globale ou de niveau site existe et qu'elle leur est appliquée.
    
Dans un cas comme dans l'autre, la stratégie de voix que vous assignez doit avoir des enregistrements d’utilisation PSTN (Public Switched Telephone Network) et des itinéraires qui définiront les zones à partir desquelles les utilisateurs peuvent téléphoner pour rejoindre une conférence.
  
> [!NOTE]
> Les utilisateurs mobiles qui souhaitent utiliser la fonctionnalité Cliquez pour participer nécessitent une stratégie de voix, ainsi que les enregistrements d’utilisation PSTN connexes et les itinéraires de communications vocales, car lorsqu’ils cliquent sur ce lien sur leurs appareils mobiles, un appel à partir de Skype pour Business Server sera le résultat. 
  

