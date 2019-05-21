---
title: Plan de mobilité pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planifiez le déploiement de votre mobilité pour Skype entreprise Server.
ms.openlocfilehash: 8b0ba8dd4ae07d3330a8ca722a1101c6b41a7cec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297322"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Plan de mobilité pour Skype entreprise Server
 
Planifiez le déploiement de votre mobilité pour Skype entreprise Server.
  
Skype entreprise Server vous permet de déployer la fonction de mobilité pour proposer une fonctionnalité de Skype entreprise Server sur les appareils mobiles. Cet article fournit des détails sur la fonctionnalité de mobilité et vous aide à planifier votre déploiement.
  
La fonctionnalité de mobilité de Skype entreprise Server est capable de prendre en charge les clients mobiles pour Skype entreprise, ainsi que les clients Lync revenons à 2010. Après le déploiement, vos utilisateurs peuvent se connecter à votre déploiement Skype entreprise Server à l’aide d’appareils mobiles iOS, Android et Windows Phone, pour tirer parti de diverses fonctionnalités, notamment les fonctionnalités d’entreprise voix. Nous avons inclus une liste partielle ci-dessous et vous pouvez également consulter la [comparaison des fonctionnalités du client de bureau pour Skype entreprise](clients-and-devices/desktop-feature-comparison.md) pour plus d’informations:
  
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
    
Tout cela est accompli par le biais de l’API Web de communications unifiées, ou UCWA. UCWA a été introduit pour la première fois dans Lync Server 2013 et est toujours utilisé avec Skype entreprise Server. Il existe une fonctionnalité supplémentaire permettant de communiquer avec les clients 2010 Lync et ce service de mobilité (MCX). Il s’agit de services gratuits, qui permettent aux clients Lync Server 2010 et 2013 ainsi qu’aux clients Skype entreprise d’accéder aux déploiements de Skype entreprise Server.
  
> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
Il est important de noter que si toutes ces fonctionnalités sont disponibles une fois la mobilité mise en œuvre, elles peuvent fonctionner différemment sur certains appareils. Nous disposons d’un site Web qui décrit les fonctionnalités qui sont compatibles avec les appareils, lors de la [comparaison des fonctionnalités du client mobile pour Skype entreprise](clients-and-devices/mobile-feature-comparison.md). Nous avons également des informations de périphériques et de systèmes d’exploitation exceptionnelles au [plan pour les clients et les appareils](clients-and-devices/clients-and-devices.md).
  
La mobilité tire une utilisation de la fonctionnalité de découverte automatique, qui permet aux clients de rechercher automatiquement les services Web de Skype entreprise Server sans que les utilisateurs aient besoin d’entrer dans une URL (ils n’ont pas besoin de les connaître). En cas de résolution de problèmes, la saisie manuelle d'URL est toujours prise en charge.
  
Les notifications de transmission sont également prises en charge, lorsque l’application Skype entreprise n’est pas en cours d’exécution en arrière-plan (ou pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan). Une notification push est envoyée à un appareil mobile lorsqu'un événement survient alors que l'application ou l'appareil est inactif. Par exemple, vous avez manqué un message instantané alors que votre téléphone était éteint, une notification push est alors envoyée (présentée sous forme de toast ou de notification, comme dans le cas d'une exécution de l'application en arrière-plan). Grâce aux notifications push, les utilisateurs ne manqueront plus aucun message instantané ni appel audio.
  
Pour plus d’informations, consultez les sections suivantes :
  
- [Composants de mobilité](mobility.md#MobilityComponents)
    
- [Topologies prises en charge](mobility.md#SupportedTopos)
    
- [Configuration technique requise](mobility.md#TechRequirements)
    
- [Définition de vos besoins en termes de mobilité](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Composants de mobilité
<a name="MobilityComponents"> </a>

Il existe quatre services qui comprennent la mobilité de Skype entreprise Server:
  
- **API web Communications unifiées (UCWA)**
    
    Fournit des services pour communiquer en temps réel avec des clients mobiles et Web pour Skype entreprise Server. Lorsque Skype entreprise Server est déployé, un répertoire virtuel UCWA est créé dans les services Web internes et externes. Composant virtuel de cet annuaire virtuel qui accepte les appels provenant de clients UCWA. Les applications clientes communiquent par le biais d’une interface de transfert d’état de la présentation pour:
    
  - informations de présence
    
  - contacts
    
  - messagerie instantanée
    
  - VoIP
    
  - vidéoconférences
    
  - collaboration
    
    UCWA utilise un canal basé sur P-GET pour envoyer des événements tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
- **Service de mobilité (MCX)**
    
    Prend en charge la fonctionnalité de Skype entreprise Server, telle que la messagerie instantanée, la présence et les contacts, sur les appareils mobiles. Le service de mobilité est installé sur chaque serveur frontal de chaque liste conçue pour prendre en charge les fonctionnalités de Skype entreprise Server sur les appareils mobiles. Lors de l’installation de Skype entreprise Server 2015, un nouveau répertoire virtuel (MCX) est créé sous le site Web interne et externe sur votre serveur frontal.
    
    > [!NOTE]
    > La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
- **Service de découverte automatique**
    
    Identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et autres clients Skype entreprise de rechercher des ressources (par exemple, les URL internes et externes pour les services Web Skype entreprise Server, l’URL MCX ou l’URL UCWA), quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôtes codés en dur (lyncdiscoverinternal pour les utilisateurs qui se trouvent sur le réseau et lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Elle prend en charge les connexions clientes qui utilisent le protocole HTTP ou HTTPS. 
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur tous les directeurs de chaque liste conçue pour prendre en charge les fonctionnalités de Skype entreprise Server sur les appareils mobiles. Lorsque vous installez le service, un nouveau répertoire virtuel (découverte automatique) est créé sous les sites Web internes et externes sur vos serveurs et directeurs frontaux.
    
- **Service de notifications Push**
    
    Un service basé sur le Cloud qui se trouve dans votre centre de données Skype entreprise online. Sur les téléphones pour lesquels le client Skype entreprise s’exécute en arrière-plan alors qu’un nouvel événement se produit, la notification d’un événement manqué (appelé notification de transmission) est envoyée à la place à l’appareil mobile. Le service de mobilité envoie une notification au service de notifications de transmission (MPNS), qui l’envoie ensuite à l’appareil mobile. L'utilisateur peut alors répondre sur son téléphone pour activer l'application. Un serveur Edge est requis pour cette fonctionnalité.
    
## <a name="supported-topologies"></a>Topologies prises en charge
<a name="SupportedTopos"> </a>

Nous avons pris en charge les applications Skype entreprise Server suivantes pour votre planification topologique:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Vous devriez être en mesure d’utiliser cette fonctionnalité avec les serveurs Edge de Skype entreprise Server ou les serveurs Edge Lync Server 2013.
  
Le service de mobilité est pris en charge sur les serveurs frontaux lorsqu’il est colocalisé avec le rôle serveur de médiation, avec deux interfaces réseau, mais vous devez suivre les étapes nécessaires pour configurer ces interfaces. Vous devez attribuer des adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation et à l’interface IP réseau qui communiquera en tant que serveur frontal. Pour cela, vous pouvez sélectionner l’adresse IP correcte pour chaque service au lieu d’utiliser la sélection par défaut **utiliser toutes les adresses IP configurées** .
  
## <a name="technical-requirements"></a>Configuration technique requise
<a name="TechRequirements"> </a>

Il est important de planifier les différents scénarios d’application mobiles que vos utilisateurs mobiles peuvent rencontrer. Par exemple, une personne peut commencer à utiliser une application mobile en dehors du travail en se connectant par le biais d’un réseau 3G, puis basculez vers le réseau Wi-Fi d’entreprise lorsqu’il atteint son travail. Ils peuvent basculer vers 4G lorsque vous quittez leur bâtiment. La planification vous permettra désormais de prendre en charge ces transitions réseau et de garantir une utilisation homogène de l’utilisateur.
  
### <a name="dns-configuration"></a>Configuration DNS

Les services de mobilité MCX et UCWA utilisent la même méthode DNS. Grâce à la découverte automatique, les appareils mobiles utilisent le système DNS pour rechercher des ressources. Lors de la recherche DNS, une tentative de connexion est effectuée vers le nom de domaine complet associé à l’enregistrement DNS interne (lyncdiscoverinternal.[internal domain name]). Si aucune connexion ne peut être établie à l’aide de l’enregistrement DNS interne, une seconde tentative de connexion est effectuée à l’aide de l’enregistrement DNS externe (lyncdiscover.[sipdomain]). Pourquoi disposer des deux ? Un appareil mobile interne à votre réseau pourra utiliser l'URL interne de découverte automatique. Les appareils mobiles externes utiliseront l'URL externe de découverte automatique. Dans les deux cas, le service de découverte automatique renvoie toutes les URL de service Web pour le pool de domicile de l’utilisateur, y compris le service de mobilité (MCX et UCWA).
  
Les requêtes de découverte automatique externes sont censées traverser le proxy inverse que vous avez configuré pour Skype entreprise Server. Toutefois, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont associées au nom de domaine complet des services Web externes. Par conséquent, qu’il s’agisse d’un appareil mobile ou d’une connexion interne ou externe à votre réseau, l’appareil se connecte toujours au service de mobilité Skype entreprise Server en externe, par le biais de votre proxy inverse.
  
> [!NOTE]
> Comme nous l’avons remarqué, le trafic de service de mobilité (interne et externe) passera par votre proxy inverse. Cependant, une erreur se produit parfois lorsque le trafic interne sort par une interface, pour ensuite tenter de revenir vers cette même interface. Cela peut entraîner une violation de vos règles de sécurité appelée usurpation d'identité (usurpation d’identité de paquet TCP). Vous devez permettre aux **cheveux** d’avoir une fonction de mobilité.
  
> [!NOTE]
> Si vous êtes prêt à effectuer cette opération, vous pouvez également choisir d’utiliser un proxy inverse différent de votre pare-feu (à des fins de sécurité, la prévention de l’usurpation d’identité doit toujours être appliquée au pare-feu). De cette façon, le cheveux peut se produire à l’interface externe de votre proxy inverse, plutôt qu’à l’interface externe de votre pare-feu. Cela vous permet de détecter les tentatives d’usurpation d’identité au niveau de votre pare-feu lors de la délâchement de la règle sur votre proxy inverse, et de bénéficier de la fonctionnalité de mobilité. 
  
> [!NOTE]
> Si vous naviguez dans le routage, veillez à utiliser l’hôte DNS ou les enregistrements CNAMe pour définir le proxy inverse du comportement de cheveux (pas le pare-feu), dans la mesure du possible. 
  
Certains éléments devront être configurés pour prendre en charge les utilisateurs situés à l'intérieur comme l’extérieur du réseau de votre société.
  
Voici les règles applicables aux noms de domaine complets web internes et externes :
  
- nouveaux enregistrements DNS CNAME ou A (hôte, si IPv6, AAAA) pour la découverte automatique ;
    
- nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications push à travers votre réseau Wi-Fi ;
    
- Les autres noms d’objet des certificats de serveur internes et des certificats de proxy inverse, pour la découverte automatique.
    
- La configuration de l’équilibrage de charge matérielle du serveur frontal a changé d’affinité de source.
    
Voici les exigences de topologie nécessaires à la prise en charge du service de mobilité et du service de découverte automatique:
  
- Le nom de domaine complet (FQDN) du pool frontal doit être différent du FQDN Web de la liste frontale.
    
- Le nom de domaine complet web interne doit uniquement être résolu vers et accessible depuis l’intérieur du réseau d’entreprise.
    
- Le nom de domaine complet web externe doit uniquement être résolu vers et accessible depuis Internet.
    
- S’il s’agit d’un utilisateur au sein du réseau d’entreprise, l’URL du service de mobilité doit être adressée au FQDN Web externe. Cette obligation est appliquée au service de mobilité et ne s’applique qu’à cette URL.
    
- S’il s’agit d’un utilisateur en dehors du réseau d’entreprise, la requête doit accéder au nom de domaine complet (FQDN) Web externe du pool frontal ou du réalisateur.
    
Si vous prenez en charge la découverte automatique, vous devrez créer les enregistrements DNS suivants pour chaque domaine SIP :
  
- un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis l'intérieur de votre réseau de votre organisation.
    
- un enregistrement DNS externe, ou public, afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.
    
L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau interne. L’URL de découverte automatique externe ne doit pas être adressable depuis l'intérieur de votre réseau. Toutefois, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité de votre client mobile ne sera probablement pas affectée, car la première tentative portera toujours sur l’URL interne.
  
### <a name="port-and-firewall-requirements"></a>Exigences relatives aux ports et aux pare-feu

Nous avons parlé de la plupart de ces éléments dans notre autre documentation, mais en particulier pour la mobilité, il est préférable que les ports suivants s’ouvrent sur votre réseau Wi-Fi d’entreprise, si vous avez des utilisateurs hébergés sur une unité Survivable (SBA):
  
- UcwaSipExternalListeningPort requiert le port 5088.
    
- UcwaSipPrimaryListeningPort requiert le port 5089.
    
### <a name="certificate-requirements"></a>Exigences en matière de certificats

Si vous utilisez la fonctionnalité de découverte automatique pour vos clients mobiles Skype entreprise, vous devez modifier les listes de remplacement de l’objet SAN sur vos certificats pour prendre en charge des connexions sécurisées à partir de vos clients mobiles. Si vous avez déjà des certificats sur place, vous devez demander et affecter de nouveaux certificats avec les entrées du SAN décrites ici. Cette opération doit être réalisée pour chaque serveur frontal et directeur (dans votre environnement) qui exécute le service de découverte automatique. Nous vous conseillons également de modifier les listes SAN sur vos certificats de proxy inverse, en ajoutant des entrées SAN pour chaque domaine SIP de votre organisation.
  
Ce processus doit être simple si vous demandez la remise de nouveaux certificats à partir d’une autorité de certification interne (autorité de certification), mais les certificats publics sont plus complexes et, dans la plupart des cas, ils peuvent être plus onéreux pour ajouter de nombreux SIP. domaines vers un nouveau certificat public. Dans cette situation, il existe une approche qui est prise en charge, mais elle **n’est pas recommandée**. Vous pouvez configurer votre proxy inverse pour que la demande de service de découverte automatique initiale sur le port 80, qui utilise HTTP plutôt que le port 443, qui est HTTPs (et 443, la configuration par défaut). Cette demande entrante sera redirigée vers le port 8080 sur votre pool frontal ou directeur. De cette façon, il ne sera pas nécessaire de modifier vos certificats, car ce trafic n'utilise pas le protocole HTTPS pour les demandes. Nous voulons cependant insister sur le fait que nous ne recommandons pas cette approche, bien qu'elle fonctionnera dans votre cas.
  
### <a name="windows-and-iis-requirements"></a>Configuration requise pour Windows et les services Internet (IIS)

Vous devez disposer d’une version de Windows Server compatible pour votre environnement Skype entreprise Server. Par conséquent, vous devez disposer également de IIS 8 ou IIS 8.5 pour vos besoins en termes de mobilité. Vous devrez apporter quelques modifications aux paramètres de ASP.NET par défaut, mais le programme d’installation du service de mobilité le fera automatiquement.
  
### <a name="hlb-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Si vous utilisez une topologie pour Skype entreprise Server incluant un HLB pour votre réserve frontale (qui correspond à une topologie incluant plusieurs serveurs frontaux), il est nécessaire de configurer l’IPs virtuel des services Web externes (VIP) pour le trafic des services Web. pour source. L'affinité source permet d'assurer l'envoi de plusieurs connexions provenant d'un seul client vers le même serveur pour maintenir l’état de la session.
  
Si vous envisagez de prendre en charge des clients mobiles Skype entreprise uniquement sur votre réseau Wi-Fi interne, vous devez configurer vos VIP de services Web internes pour la source, comme décrit pour les VIP de services Web externes. Dans ce cas, vous devez utiliser l’affinité source_addr (ou TCP) pour les VIP de services Web internes sur le HLB.
  
Pour plus d’informations, reportez-vous à la documentation de [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Exigences relatives au proxy inverse

Pour prendre en charge la découverte automatique pour les clients mobiles Skype entreprise, vous devez mettre à jour la règle de publication actuelle comme suit:
  
- Si vous décidez de mettre à jour les listes de SAN sur vos certificats de proxy inverse et que vous utilisez HTTPs pour la demande de service de découverte automatique initiale, vous devez mettre à jour la règle de publication Web pour lyncdiscover. \<sipdomain\>. En règle générale, ce problème est associé au RUL de publication pour l’URL des services Web externes sur le pool frontal.
    
- Si vous avez décidé d’utiliser HTTP pour la demande initiale du service de découverte automatique pour éviter de mettre à jour la liste des SAN pour vos certificats de proxy inverse (ce que nous ne recommandons pas), vous devez créer une nouvelle règle de publication Web pour le port HTTP/TCP 80, le cas échéant. existante. S’il existe une règle, mettez-la à jour pour inclure une lyncdiscover. \<entrée\> sipdomain.
    
## <a name="defining-your-mobility-needs"></a>Définition de vos besoins en termes de mobilité
<a name="MobilityNeeds"> </a>

Maintenant que nous avons examiné les topologies, les composants et les spécifications techniques, examinons ce que votre organisation peut en faire en termes de mise en œuvre de mobilité.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Souhaitez-vous utiliser la découverte automatique pour les clients mobiles Skype Entreprise ?

Nous vous recommandons vivement d'utiliser la découverte automatique. La création d'enregistrements DNS internes et externes sera requise, tel que décrit dans la section de configuration technique requise plus haut. La découverte automatique permet aux clients Skype entreprise de retrouver automatiquement les services Web de Skype entreprise Server depuis n’importe quel emplacement, sans avoir besoin d’une URL à entrer manuellement.
  
Vous pouvez utiliser les paramètres manuels si besoin est. Ces URL devront être saisies par les utilisateurs dans leurs appareils mobiles :
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root** pour l’accès externe.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root** pour l’accès interne.
    
Nous vous recommandons à nouveau d'utiliser la découverte automatique. Les paramètres manuels vous seront peut-être utiles lors de la résolution de problèmes.
  
### <a name="are-you-going-to-support-push-notifications"></a>Allez-vous prendre en charge les notifications push ?

Les notifications push sont utilisées pour les applications mobiles qui prennent en charge cette fonctionnalité pour notifier un utilisateur d'un événement survenu alors que l'application était inactive. Votre serveur Edge doit avoir une relation de Fédération avec votre service de notifications de transmission Skype entreprise Server sur le Cloud, qui se trouve dans le centre de donnees Skype entreprise online. Vous devrez exécuter un applet de commande pour activer les notifications push.
  
> [!NOTE]
> Si vous avez des utilisateurs de Lync Server 2010, ils doivent disposer d’un port TCP 5223 ouvert sur le réseau WiFi de votre entreprise. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Souhaitez-vous que tous vos utilisateurs accèdent à toutes les fonctionnalités de mobilité ou vous souhaitez spécifier les utilisateurs qui peuvent accéder à ces fonctionnalités à la place?

Nous avons un tableau pour vous aider à effectuer certaines des fonctionnalités qui sont disponibles pour tous les utilisateurs, et qu’ils soient définis ou non par défaut. Pour obtenir une liste complète, veuillez consulter la rubrique [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Les étendues pour l'ensemble de ces fonctions sont Globale/Site/Utilisateur. 
  
|**Fonctionnalité**|**Nom du paramètre**|**Description**|**Paramètre par défaut**|
|:-----|:-----|:-----|:-----|
|Activer la mobilité  <br/> |EnableMobility  <br/> |Contrôle les utilisateurs d’une étendue donnée sur laquelle le client mobile Skype entreprise est installé. Si la stratégie est définie sur False, vos utilisateurs ne seront pas en mesure de se connecter à l'aide de leur client.  <br/> |True  <br/> |
|Voix extérieure  <br/> |EnableOutsideVoice  <br/> |Permet à un utilisateur d'utiliser l’Appel via le bureau, une fonctionnalité qui lui permet d’effectuer et de recevoir des appels à l’aide de son numéro professionnel au lieu de son numéro de téléphone mobile. Si ce paramètre est défini sur False, vos utilisateurs ne pourront pas effectuer ou recevoir d’appel à l’aide de leur numéro professionnel depuis leur téléphone mobile.  <br/> |True  <br/> |
|Activer l’audio/la vidéo IP  <br/> |EnableIPAudioVideo  <br/> |Défini sur la valeur par défaut, ce paramètre permet à un utilisateur d'utiliser VoIP pour effectuer ou recevoir des appels sur son appareil mobile. Si ce paramètre est défini sur False, vos utilisateurs ne pourront pas utiliser leur appareil mobile pour effectuer ces actions.  <br/> |True  <br/> |
|Exiger WiFi pour l’audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Détermine si un client devra passer et recevoir les appels sur VoIP sur Wi-Fi plutôt que sur le réseau de données cellulaire. Si ce paramètre est défini sur True, vos utilisateurs pourront passer et recevoir des appels VoIP uniquement lorsqu’ils sont connectés à un réseau WiFi.  <br/> |False  <br/> |
|Exiger WiFi pour la vidéo IP  <br/> |RequireWiFiForIPVideo  <br/> |Détermine si un client devra passer et recevoir les appels vidéo sur VoIP sur Wi-Fi plutôt que sur le réseau de données cellulaire. Si ce paramètre est défini sur True, vos utilisateurs pourront passer et recevoir des appels VoIP uniquement lorsqu’ils sont connectés à un réseau WiFi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Les utilisateurs qui ne sont pas activés pour Voix Entreprise doivent-ils pouvoir utiliser la fonctionnalité Cliquez pour participer afin de rejoindre des conférences ?

Pour que les utilisateurs puissent accéder aux fonctionnalités de mobilité et aux appels via le bureau, ils doivent être activés pour voix entreprise. Si ce n'est toutefois pas le cas, ils peuvent toujours participer aux conférences en cliquant sur un lien sur leur appareil mobile, mais une stratégie de voix appropriée devra leur être affectée. Vous pouvez procéder de l'une des manières suivantes :
  
- affectez une stratégie de voix spécifique pour ces utilisateurs ; ou,
    
- assurez-vous qu'une stratégie globale ou de niveau site existe et qu'elle leur est appliquée.
    
Dans un cas comme dans l'autre, la stratégie de voix que vous assignez doit avoir des enregistrements d’utilisation PSTN (Public Switched Telephone Network) et des itinéraires qui définiront les zones à partir desquelles les utilisateurs peuvent téléphoner pour rejoindre une conférence.
  
> [!NOTE]
> Les utilisateurs mobiles qui souhaitent utiliser le Cliquer pour participer peuvent utiliser une stratégie vocale, ainsi que les enregistrements d’utilisation RTC et les itinéraires vocaux correspondants, car lorsque ces derniers cliquent sur le lien sur leur appareil mobile, un appel sortant de Skype entreprise Server est obtenu. 
  

