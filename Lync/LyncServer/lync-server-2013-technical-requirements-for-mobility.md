---
title: 'Lync Server 2013 : configuration technique requise pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8df94773a551ee503ac435af8f31d0104dc38aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536141"
---
# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Configuration technique requise pour la mobilité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Les utilisateurs mobiles font face à différents scénarios d’applications mobiles qui nécessitent une planification particulière. Par exemple, quelqu’un peut commencer à utiliser une application mobile en se connectant via le réseau 3G, puis basculer vers le réseau d' Wi-Fi d’entreprise lorsqu’il arrive au travail, puis rebasculer vers 3G lorsqu’il quitte le bâtiment. Vous devez planifier votre environnement de sorte qu’il prenne en charge ce type de transition de réseau et qu’il garantisse une expérience utilisateur cohérente. Cette section décrit les exigences d’infrastructure dont vous devez disposer afin de prendre en charge les applications mobiles et la découverte automatique des ressources de mobilité.

<div>


> [!NOTE]  
> Bien que les applications mobiles puissent également se connecter à d’autres services Lync Server 2013, la nécessité d’envoyer toutes les demandes Web d’applications mobiles vers le même nom de domaine complet (FQDN) Web externe s’applique uniquement au service de mobilité de Lync Server 2013. Les autres services de mobilité n’ont pas besoin de cette configuration.



</div>

La configuration requise pour l’affinité des cookies dans les programmes d’équilibrage de la charge matérielle est considérablement réduite et vous pouvez utiliser l’affinité TCP (Transmission Control Protocol) si vous utilisez le service Lync mobile fourni avec Lync Server 2013. L’affinité de cookie peut toujours être utilisée, mais les services Web ne l’ont plus besoin.

<div>


> [!IMPORTANT]  
> Tout le trafic du service de mobilité passe par le proxy inverse, quel que soit son emplacement d’origine (interne ou externe). Dans le cas d’un proxy inverse unique ou d’une batterie de serveurs proxy inverse, ou d’un périphérique qui fournit la fonction de proxy inverse, un problème peut se produire lorsque le trafic interne est egressing via une interface et tente de passer immédiatement à la même interface. Cela conduit souvent à une violation de règle de sécurité connue sous le nom de « usurpation de paquets TCP » ou simplement d’usurpation d’identité. L' <EM>épinglage de cheveux</EM> (la sortie et la pénétration immédiate d’un paquet ou d’une série de paquets) doit être autorisé pour que la mobilité puisse fonctionner. Pour résoudre ce problème, vous pouvez utiliser un proxy inverse distinct du pare-feu (la règle de prévention d’usurpation d’adresses doit toujours être appliquée au niveau du pare-feu, pour des raisons de sécurité). L’épinglage peut se produire sur l’interface externe du proxy inverse au lieu de l’interface externe du pare-feu. Vous détectez l’usurpation d’identité au niveau du pare-feu et détendez la règle au proxy inverse, ce qui permet aux épinglage de la mobilité.<BR>Utilisez l’hôte DNS (Domain Name System) ou les enregistrements CNAMe pour définir le proxy inverse pour le comportement épinglage (et non le pare-feu), si possible.



</div>

Lync Server 2013 prend en charge les services de mobilité pour les clients mobiles Lync 2010 mobile et Lync 2013. Les deux clients utilisent le service de découverte automatique Lync Server 2013 pour trouver le point d’entrée de mobilité, mais ils diffèrent en fonction du service de mobilité qu’ils utilisent. Lync 2010 mobile utilise le service de mobilité appelé *MCX*, présenté avec la mise à jour cumulative pour Lync Server 2010 : novembre 2011. Les clients mobiles Lync 2013 utilisent l’API Web Unified Communications, ou *UCWA*, en tant que fournisseur de services de mobilité.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configuration DNS interne et externe

Les services de mobilité MCX (introduits avec la mise à jour cumulative pour Lync Server 2010 : novembre 2011) et UCWA (introduits dans les mises à jour cumulatives pour Lync Server 2013:2013) utilisent DNS de la même manière.

Lorsque vous utilisez la découverte automatique, les appareils mobiles utilisent le système DNS pour localiser les ressources. Lors de la recherche DNS, une connexion est d’abord tentée vers le nom de domaine complet associé à l’enregistrement DNS interne (lyncdiscoverinternal. \<internal domain name\> ). Si une connexion ne peut pas être établie à l’aide de l’enregistrement DNS interne, une tentative de connexion se fait à l’aide de l’enregistrement DNS externe (lyncdiscover. \<sipdomain\> ). Un appareil mobile interne au réseau se connecte à l’URL du service de découverte automatique interne, alors qu’un appareil mobile externe au réseau se connecte à l’URL du service de découverte automatique externe. Les demandes de découverte automatique externe passent par le proxy inverse. Le service de découverte automatique Lync Server 2013 renvoie toutes les URL de services Web pour le pool d’accueil de l’utilisateur, y compris les URL du service de mobilité (MCX et UCWA). Toutefois, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont toutes deux associées au nom de domaine complet externe des services web. Par conséquent, qu’un appareil mobile soit interne ou externe au réseau, l’appareil se connecte toujours au service de mobilité Lync Server 2013 en externe via le proxy inverse.

<div>


> [!NOTE]  
> Il est important de comprendre que votre déploiement peut se composer de plusieurs espaces de noms distincts pour une utilisation interne et externe. Le nom de votre domaine SIP peut être différent du nom de domaine de déploiement interne. Par exemple, votre domaine SIP peut être <STRONG>contoso.com</STRONG>, tandis que votre déploiement interne peut être <STRONG>contoso.net</STRONG>. Les utilisateurs qui se connectent à Lync Server utiliseront le nom de domaine SIP, tel que <STRONG>John@contoso.com</STRONG>. Lors de l’adressage des services Web externes (définis dans le générateur de topologie en tant que <STRONG>services Web externes</STRONG>), le nom de domaine et le nom de domaine SIP sont cohérents, comme défini dans DNS. Lors de l’adressage des services Web internes (définis dans le générateur de topologie en tant que <STRONG>services Web internes</STRONG>), le nom par défaut des services Web internes sera le nom de domaine complet du serveur frontal, le pool frontal, le directeur ou le pool directeur. Vous avez la possibilité de remplacer le nom du service Web interne. Vous devez utiliser le nom de domaine interne (et non le nom de domaine SIP) pour les services Web internes et définir l’enregistrement A (ou, pour IPv6, AAAA) de l’hôte DNS pour refléter le nom remplacé. Par exemple, le nom de domaine complet des services Web internes par défaut peut être <STRONG>pool01.contoso.net</STRONG>. Un nom de domaine complet (FQDN) de services Web interne substitué peut être <STRONG>webpool.contoso.net</STRONG>. La définition des services Web de cette façon permet de s’assurer que la localité interne et externe des services, et non la localité de l’utilisateur qui les utilise, est observée.<BR>Toutefois, étant donné que les services Web sont définis dans le générateur de topologie et que le nom des services Web internes peut être remplacé, étant donné que le nom des services Web résultants, le certificat qui le valide et les enregistrements DNS qui le définissent, sont cohérents, vous pouvez définir les services Web internes avec n’importe quel nom de domaine, y compris le nom de domaine SIP, Enfin, la résolution du nom vers l’adresse IP est déterminée par les enregistrements d’hôte DNS et un espace de noms cohérent.<BR>Pour les besoins de cette rubrique et des exemples, le nom de domaine interne est utilisé pour illustrer la topologie et les définitions DNS.



</div>

Le diagramme suivant illustre le flux des demandes Web d’applications mobiles pour le service de mobilité et le service de découverte automatique lors de l’utilisation d’une configuration DNS interne et externe.

**Flux de service de mobilité à l’aide de la découverte automatique**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> Le diagramme illustre les services Web génériques. Un répertoire virtuel nommé Mobility illustre les services de mobilité MCX et/ou UCWA. Si vous n’avez pas appliqué les mises à jour cumulatives pour Lync Server 2013 : février 2013, le répertoire virtuel Ucwa est peut-être défini sur vos services Web internes et externes. Vous disposerez d’un service de découverte automatique de répertoire virtuel et vous aurez peut-être un répertoire virtuel MCX.<BR>La découverte automatique et la découverte de services fonctionnent de la même manière, quelle que soit la technologie de services de mobilité que vous avez déployée.



</div>

Pour prendre en charge les utilisateurs mobiles internes et externes au réseau d’entreprise, vos noms de domaine complets web internes et externes doivent remplir certaines conditions. Par ailleurs, certaines conditions supplémentaires peuvent être requises, selon les fonctionnalités que vous choisissez d’implémenter :

  - Nouveaux enregistrements DNS, CNAMe ou A (hôte, si IPv6, AAAA), pour la découverte automatique.

  - Nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications de type transmission via votre réseau Wi-Fi.

  - Autres noms de sujet sur les certificats de serveur internes et les certificats de proxy inverse, pour la découverte automatique.

  - La configuration de l’équilibreur de charge matérielle du serveur frontal modifie l’affinité source.

Votre topologie doit répondre aux exigences suivantes pour prendre en charge le service de mobilité et le service de découverte automatique :

  - Le nom de domaine complet Web interne du pool frontal doit être différent du nom de domaine complet Web externe du pool frontal.

  - Le nom de domaine complet web interne doit uniquement être résolu vers et accessible depuis l’intérieur du réseau d’entreprise.

  - Le nom de domaine complet Web externe ne doit être résolu qu’vers et être accessible à partir d’Internet.

  - Pour un utilisateur qui se trouve sur le réseau d’entreprise, l’URL du service de mobilité doit être adressée au nom de domaine complet web externe. Cette exigence concerne le service de mobilité et s’applique uniquement à cette URL.

  - Pour un utilisateur qui se trouve à l’extérieur du réseau d’entreprise, la demande doit être adressée au nom de domaine complet Web externe du pool ou du directeur frontal.

Si vous prenez en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP :

  - Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.

  - Un enregistrement DNS externe ou public pour prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet.

L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable depuis votre réseau. Toutefois, si vous ne pouvez pas répondre à cette exigence pour l’URL externe, le client mobile n’est probablement pas affecté, car l’URL interne est toujours essayée en premier.

Les enregistrements DNS peuvent être des enregistrements CNAMe ou des enregistrements A (hôte, si IPv6, AAAA).

<div>


> [!NOTE]  
> Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) de différents domaines. Par conséquent, la redirection CNAME vers différents domaines n’est pas prise en charge sur le protocole HTTPS. Par exemple, un enregistrement DNS CNAME pour lyncdiscover.contoso.com qui redirige vers une adresse director.contoso.net n’est pas pris en charge sur HTTPS. Dans une telle topologie, un client d’appareil mobile doit utiliser le protocole HTTP pour la première demande, de sorte que la redirection CNAME soit résolue sur HTTP. Les demandes ultérieures utilisent ensuite le protocole HTTPS. Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication web pour le port 80 (HTTP). Pour plus d’informations, reportez-vous à la section « pour créer une règle de publication Web pour le port 80 » dans <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configuration du proxy inverse pour la mobilité dans Lync Server 2013</A>.<BR>La redirection CNAME vers le même domaine est prise en charge sur HTTPS. Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.



</div>

Pour plus d’informations sur les enregistrements DNS requis pour votre scénario, reportez-vous à la rubrique [DNS Summary-Autodiscover dans Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Exigences relatives aux ports et aux pare-feu

Si vous prenez en charge les notifications push et souhaitez que les appareils mobiles Apple reçoivent des notifications push par le biais de votre réseau Wi-Fi, vous devez également ouvrir le port 5223 sur votre réseau Wi-Fi d’entreprise. Il s’agit d’un port TCP sortant utilisé par le service APNS (Apple Push Notification Service). L’appareil mobile établit la connexion. Pour plus d’informations, reportez-vous à [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .

<div>


> [!WARNING]  
> Un appareil Apple utilisant le client mobile Lync 2013 ne requiert pas de notifications de type transmission.



</div>

Notez que si un utilisateur est hébergé sur un Survivable Branch Appliance (SBA), les ports suivants sont requis :

  - UcwaSipExternalListeningPort nécessite le port 5088

  - UcwaSipPrimaryListeningPort nécessite le port 5089

Pour obtenir des informations et des instructions supplémentaires sur les exigences de port et de protocole pour la découverte automatique, voir [port Summary-Autodiscover dans Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Exigences en matière de certificats

Si vous prenez en charge la découverte automatique pour les clients mobiles Lync, vous devez modifier la liste des autres noms de sujet sur les certificats de manière prendre en charge les connexions sécurisées établies à partir de clients mobiles. Pour chaque serveur frontal et directeur qui exécute le service de découverte automatique, vous devez demander et affecter de nouveaux certificats, en ajoutant les entrées de l’autre nom du sujet décrites dans cette section. L’approche recommandée consiste à modifier également les listes d’autres noms de sujet sur les certificats pour vos proxys inverses. Vous devez ajouter des entrées d’autres noms de sujet pour chaque domaine SIP de votre organisation.

La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple, mais l’ajout de plusieurs entrées d’autres noms de sujet à des certificats publics utilisés par le proxy inverse peut être une opération coûteuse. Si vous avez de nombreux domaines SIP, ce qui rend l’ajout d’autres noms de sujet très coûteux, vous pouvez configurer le proxy inverse de sorte qu’il effectue la demande initiale du service de découverte automatique sur le port 80 à l’aide du protocole HTTP, plutôt que sur le port 443 à l’aide du protocole HTTPS (configuration par défaut). La demande est ensuite redirigée vers le port 8080 du directeur ou du pool frontal. Lorsque vous publiez la demande initiale du service de découverte automatique sur le port 80, il n’est pas nécessaire de modifier les certificats pour le proxy inverse car la demande utilise le protocole HTTP plutôt que HTTPS. Cette approche est prise en charge, mais il n’est pas recommandé de l’utiliser.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Exigences relatives aux services Internet (IIS)

Nous vous recommandons d’utiliser IIS 7,5, IIS 8,0 ou IIS 8,5 pour la mobilité. Le programme d’installation du service de mobilité définit des indicateurs dans ASP.NET pour améliorer les performances. IIS 7,5 est installé par défaut sur Windows Server 2008 R2, IIS 8,0 est installé sur Windows Server 2012 et IIS 8,5 est installé sur Windows Server 2012 R2. Le programme d’installation du service de mobilité modifie automatiquement les paramètres ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Exigences relatives au programme d’équilibrage de la charge matérielle

Sur le programme d’équilibrage de la charge matérielle qui prend en charge le pool frontal, les adresses IP virtuelles des services Web externes pour le trafic des services Web doivent être configurées pour la source. L’affinité source permet de s’assurer que plusieurs connexions provenant d’un seul client sont envoyées à un serveur pour maintenir l’état de la session. Pour plus d’informations sur les exigences en matière d’affinité, voir [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Si vous envisagez de prendre en charge les clients mobiles Lync uniquement sur votre réseau Wi-Fi interne, vous devez configurer les VIP des services Web internes pour la source comme décrit pour les VIP de services Web externes. Dans ce cas, vous devez utiliser l' \_ affinité source (ou TCP) pour les adresses IP virtuelles des services Web internes sur le programme d’équilibrage de la charge matérielle. Pour plus d’informations, reportez-vous à [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Exigences relatives au proxy inverse

Si vous prenez en charge la découverte automatique pour les clients mobiles Lync, vous devez mettre à jour la règle de publication actuelle comme suit :

  - Si vous décidez de mettre à jour les listes des autres noms du sujet sur les certificats de proxy inverse et d’utiliser le protocole HTTPs pour la demande de service de découverte automatique initiale, vous devez mettre à jour la règle de publication Web pour lyncdiscover. \<sipdomain\> . En règle générale, il est combiné à la règle de publication pour l’URL des services Web externes sur le pool frontal.

  - Si vous décidez d’utiliser le protocole HTTP pour la demande de service de découverte automatique initiale afin de ne pas avoir à mettre à jour la liste des autres noms du sujet sur les certificats de proxy inverse, vous devez créer une nouvelle règle de publication Web pour le port HTTP/TCP 80, s’il n’en existe pas déjà un. Si une règle pour le protocole HTTP/TCP 80 existe déjà, vous pouvez mettre à jour cette règle pour inclure le lyncdiscover.\<sipdomain\> rubrique.

</div>

</div>

<span> </span>

</div>

</div>

</div>

