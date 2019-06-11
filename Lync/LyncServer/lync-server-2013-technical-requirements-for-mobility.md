---
title: 'Lync Server 2013 : exigences techniques pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Exigences techniques pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Les utilisateurs mobiles rencontrent différents scénarios d’application mobile qui nécessitent une planification particulière. Par exemple, une personne peut commencer à utiliser une application mobile en se connectant par le biais du réseau 3G, puis basculer vers le réseau Wi-Fi d’entreprise lors de votre travail, puis revenir à la technologie 3G lorsque vous quittez le bâtiment. Vous devez planifier votre environnement pour prendre en charge ces transitions réseau et garantir une utilisation homogène de l’utilisateur. Cette section décrit les exigences d’infrastructure requises pour la prise en charge des applications mobiles et la découverte automatique des ressources de mobilité.

<div>


> [!NOTE]  
> Même si les applications mobiles peuvent également se connecter à d’autres services Lync Server 2013, la configuration requise pour envoyer toutes les demandes Web d’applications mobiles au même nom de domaine complet (FQDN) du site Web externe s’applique uniquement au service de mobilité Lync Server 2013. Les autres services de mobilité ne nécessitent pas cette configuration.



</div>

L’exigence d’affinité de cookie dans les équilibreurs de charge matérielle est considérablement réduite et vous remplacez l’affinité TCP (Transmission Control Protocol) si vous utilisez le mobile Lync fourni avec Lync Server 2013. L’affinité de cookie peut toujours être utilisée, mais les services Web ne le nécessitent plus.

<div>


> [!IMPORTANT]  
> Tout le trafic de service de mobilité passe par le proxy inverse, quelle que soit la position du point de départ (interne ou externe). Dans le cas d’un seul proxy inverse ou d’une batterie de serveurs proxy inverse, ou d’un appareil fournissant la fonction de proxy inverse, un problème peut se produire lorsque le trafic interne est egressing par le biais d’une interface et tente d’être entrant immédiatement dans la même interface. Cela entraîne souvent une violation d’une règle de sécurité appelée usurpation de paquets TCP ou simplement une usurpation d’identité. <EM>Épingler des cheveux</EM> (la sortie et la pénétration immédiate d’un paquet ou d’une série de paquets) doivent être autorisés pour que la mobilité puisse fonctionner. Une façon de résoudre ce problème consiste à utiliser un proxy inverse différent du pare-feu (la règle de prévention des intrusions doit toujours être appliquée au pare-feu, à des fins de sécurité). Le cheveux peut se produire à l’interface externe du proxy inverse au lieu de l’interface externe du pare-feu. Vous avez détecté l’usurpation d’identité au niveau du pare-feu et détendez la règle sur le proxy inverse, ce qui permet à l’cheveux de la mobilité requise.<BR>Pour définir le proxy inverse du comportement de cheveux (pas le pare-feu), utilisez les enregistrements CNAMe ou DNS (Domain Name System).



</div>

Lync Server 2013 prend en charge les services de mobilité pour les clients mobiles Lync 2010 mobile et Lync 2013. Les deux clients utilisent le service de découverte automatique Lync Server 2013 pour trouver le point d’entrée de mobilité et varient en fonction du service de mobilité utilisé. Lync 2010 mobile utilise le service de mobilité appelé *MCX*, présenté par la mise à jour cumulative pour Lync Server 2010:2011 novembre. Les clients mobiles Lync 2013 utilisent l’API Web de communications unifiées, ou *UCWA*, comme fournisseur de services de mobilité.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configuration DNS interne et externe

Les services de mobilité MCX (introduits avec la mise à jour cumulative pour Lync Server 2010: novembre 2011) et UCWA (introduits dans les mises à jour cumulatives de Lync Server 2013:2013) utilisent le système de la même manière.

Lorsque vous utilisez la découverte automatique, les appareils mobiles utilisent le DNS pour localiser les ressources. Lors de la recherche DNS, une connexion est d’abord tentée vers le nom de domaine complet associé à l’enregistrement DNS\< interne (lyncdiscoverinternal. nom\>de domaine interne). Si une connexion ne peut pas être effectuée à l’aide de l’enregistrement DNS interne, une connexion est tentée via l’enregistrement DNS\< externe (lyncdiscover). sipdomain\>). Un appareil mobile qui est interne au réseau se connecte à l’URL du service de découverte automatique interne et un appareil mobile extérieur au réseau se connecte à l’URL du service de découverte automatique externe. Les requêtes de découverte automatique externes passent par le proxy inverse. Le service de découverte automatique Lync Server 2013 renvoie toutes les URL de services Web pour le pool de domicile de l’utilisateur, y compris les URL de service de mobilité (MCX et UCWA). Toutefois, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont associées au nom de domaine complet des services Web externes. Par conséquent, qu’il s’agisse d’un appareil mobile ou d’une connexion externe, l’appareil se connecte toujours au service de mobilité Lync Server 2013 en externe via le proxy inverse.

<div>


> [!NOTE]  
> Il est important de comprendre que votre déploiement peut être composé de plusieurs espaces de noms distincts pour une utilisation interne et externe. Le nom de votre domaine SIP doit être différent du nom de domaine de déploiement interne. Par exemple, votre domaine SIP est susceptible d’être <STRONG>contoso.com</STRONG>, alors que votre déploiement interne est susceptible d’être <STRONG>contoso.net</STRONG>. Les utilisateurs qui se connectent à Lync Server utilisent le nom de domaine SIP (par exemple, <STRONG>John@contoso.com</STRONG>). Lorsque vous répondez aux services Web externes (définis dans le générateur de topologie comme <STRONG>services Web externes</STRONG>), le nom de domaine et le nom de domaine SIP sont cohérents, comme défini dans DNS. Lors de l’adressage des services Web internes (définis dans le générateur de topologie comme <STRONG>services Web internes</STRONG>), le nom par défaut des services Web internes sera le nom de domaine complet du serveur frontal, du pool frontal, du réalisateur ou du pool de réalisateurs. Vous avez la possibilité de remplacer le nom des services Web internes. Vous devez utiliser le nom de domaine interne (et non le nom de domaine SIP) pour les services Web internes et définir l’enregistrement DNS A (ou, pour IPv6, AAAA) pour refléter le nom substitué. Par exemple, le nom de domaine complet des services Web internes par défaut est <STRONG>pool01.contoso.net</STRONG>. Un nom de domaine complet (FQDN) de services Web interne substitué est susceptible d’être <STRONG>webpool.contoso.net</STRONG>. Le fait de définir les services Web de cette manière permet de s’assurer que la localité interne et externe des services, et non celle de l’utilisateur qui les utilise, est observée.<BR>Toutefois, étant donné que les services Web sont définis dans le générateur de topologie et que le nom des services Web interne peut être substitué, tant que le nom des services Web résultant, le certificat qui les valide et les enregistrements DNS qui le définissent, sont cohérents, vous pouvez définir le services Web internes avec n’importe quel nom de domaine (y compris le nom de domaine SIP) que vous souhaitez. Enfin, la résolution du nom à l’adresse IP est déterminée par les enregistrements d’hôte DNS et un espace de noms cohérent.<BR>Pour les besoins de cette rubrique et ces exemples, le nom de domaine interne est utilisé pour illustrer la topologie et les définitions DNS.



</div>

Le diagramme suivant illustre le flux des requêtes Web d’applications mobiles pour le service de mobilité et pour le service de découverte automatique lors de l’utilisation d’une configuration DNS interne et externe.

**Flux de service de mobilité avec la découverte automatique**

![cdb96424-96f2-4ABF-88d7-1d32d1010ffd] (images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4ABF-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> Le diagramme illustre des services Web génériques. Un répertoire virtuel intitulé mobilité représente les services de mobilité MCX et/ou UCWA. Si vous n’avez pas appliqué les mises à jour cumulatives pour Lync Server 2013: février 2013, il est possible que vous n’ayez pas ou non le répertoire virtuel Ucwa défini sur vos services Web internes et externes. Vous aurez une découverte automatique d’annuaire virtuelle et vous aurez peut-être un répertoire virtuel MCX.<BR>La découverte automatique et la découverte de services fonctionnent de la même manière, quelle que soit la technologie de services de mobilité déployée.



</div>

Pour prendre en charge les utilisateurs mobiles à l’intérieur et à l’extérieur du réseau d’entreprise, vos noms de domaine complets internes et externes doivent respecter certaines conditions préalables. De plus, il est possible que vous deviez respecter d’autres exigences, en fonction des fonctionnalités que vous choisissez d’implémenter:

  - Nouveaux enregistrements DNS, CNAMe ou A (hôte, s’il s’agit du protocole IPv6, AAAA) pour la découverte automatique.

  - nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications push à travers votre réseau Wi-Fi ;

  - Les autres noms d’objet des certificats de serveur internes et des certificats de proxy inverse, pour la découverte automatique.

  - Configuration de l’équilibrage de charge matérielle du serveur frontal

Votre topologie doit respecter les exigences suivantes pour prendre en charge le service de mobilité et le service de découverte automatique:

  - Le nom de domaine complet (FQDN) du pool frontal doit être différent du FQDN Web de la liste frontale.

  - Le nom de domaine complet (FQDN) du site Web interne ne doit être résolu qu’à l’intérieur du réseau d’entreprise.

  - Le nom de domaine complet (FQDN) Web externe doit uniquement être résolu et être accessible à partir d’Internet.

  - Pour un utilisateur se trouvant à l’intérieur du réseau d’entreprise, l’URL du service de mobilité doit être adressée au FQDN Web externe. Cette obligation est appliquée au service de mobilité et ne s’applique qu’à cette URL.

  - S’il s’agit d’un utilisateur qui se trouve en dehors du réseau d’entreprise, la requête doit se trouver dans le nom de domaine complet (FQDN) Web externe de la liste du pool frontal ou du réalisateur.

Si vous prenez en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP:

  - Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent au sein du réseau de votre organisation.

  - Un enregistrement DNS externe ou public permettant de prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet.

L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable à partir de votre réseau. Toutefois, si vous ne pouvez pas respecter cette exigence pour l’URL externe, le client mobile n’est probablement pas affecté, car l’URL interne est toujours essayée en premier.

Les enregistrements DNS peuvent être des enregistrements CNAMe ou un (hôte, si vous avez des enregistrements IPv6, AAAA).

<div>


> [!NOTE]  
> Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) provenant de différents domaines. Par conséquent, la redirection CNAMe vers différents domaines n’est pas prise en charge sur HTTPs. Par exemple, un enregistrement CNAMe DNS pour lyncdiscover.contoso.com qui redirige vers une adresse de director.contoso.net n’est pas pris en charge sur HTTPs. Dans le cas d’une telle topologie, un client d’appareil mobile doit utiliser HTTP pour la première demande, de sorte que la redirection CNAMe soit résolue via HTTP. Les requêtes suivantes utilisent alors HTTPs. Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication Web pour le port 80 (HTTP). Pour plus d’informations, reportez-vous à la section «pour créer une règle de publication Web pour le port 80» dans <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configuration du proxy inverse pour la mobilité dans Lync Server 2013</A>.<BR>La redirection CNAMe vers le même domaine est prise en charge sur HTTPs. Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.



</div>

Pour plus d’informations sur les enregistrements DNS requis pour votre scénario, voir [synthèse DNS-découverte automatique dans Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Configuration requise pour les ports et les pare-feu

Si vous prenez en charge les notifications de transmission et que les appareils mobiles Apple reçoivent des notifications de transmission sur votre réseau Wi-Fi, vous devez également ouvrir le port 5223 sur votre réseau Wi-Fi d’entreprise. Le port 5223 est un port TCP sortant utilisé par le service de notifications de type Apple (APNS). L’appareil mobile initialise la connexion. Pour plus d’informations [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) , reportez-vous à.

<div>


> [!WARNING]  
> Un appareil Apple utilisant le client mobile Lync 2013 ne nécessite pas de notifications de transmission.



</div>

Notez que si un utilisateur est hébergé sur une unité de branchement survivant (SBA), les ports suivants sont nécessaires:

  - UcwaSipExternalListeningPort nécessite le port 5088

  - UcwaSipPrimaryListeningPort nécessite le port 5089

Pour obtenir des informations supplémentaires et des conseils sur la configuration requise pour les ports et les protocoles de découverte automatique, voir [synthèse des ports-découverte automatique dans Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Conditions requises pour les certificats

Si vous prenez en charge la découverte automatique pour les clients mobiles Lync, vous devez modifier les listes nom de remplacement de l’objet sur les certificats pour prendre en charge les connexions sécurisées à partir des clients mobiles. Pour chaque serveur frontal et directeur exécutant le service de découverte automatique, vous devez demander et affecter de nouveaux certificats, en ajoutant les entrées de nom de remplacement de l’objet décrite dans cette section. L’approche recommandée consiste à modifier également les listes d’autres noms d’objet sur les certificats de vos proxys inversés. Vous devez ajouter des entrées de nouveau nom d’objet pour chaque domaine SIP de votre organisation.

La réémission de certificats à l’aide d’une autorité de certification interne correspond généralement à un processus simple, mais l’ajout de plusieurs entrées de nom de remplacement de sujet à des certificats publics utilisés par le proxy inverse peut être coûteux. Si vous avez un grand nombre de domaines SIP, le fait d’ajouter des noms de remplacement d’objet très coûteux, vous pouvez configurer le proxy inverse pour que la demande de service de découverte automatique initiale soit mise sur le port 80 à l’aide du protocole HTTP, au lieu du port 443 utilisant HTTPs (configuration par défaut). La requête est alors redirigée vers le port 8080 du réalisateur ou du pool frontal. Lorsque vous publiez la demande initiale du service de découverte automatique sur le port 80, vous n’avez pas besoin de modifier des certificats pour le proxy inverse, car la requête utilise HTTP au lieu de HTTPs. Cette approche est prise en charge, mais nous vous le déconseillons.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Configuration requise pour Internet Information Services (IIS)

Nous vous recommandons d’utiliser les 7,5 IIS, IIS 8,0 ou IIS 8,5 pour la mobilité. Le programme d’installation de service de mobilité définit des indicateurs dans ASP.NET pour améliorer les performances. IIS 7,5 est installé par défaut sur Windows Server 2008 R2, IIS 8,0 est installé sur Windows Server 2012 et IIS 8,5 est installé sur Windows Server 2012 R2. Le programme d’installation de service de mobilité modifie automatiquement les paramètres de ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Sur l’équilibrage de charge matérielle qui prend en charge le pool frontal, l’IPs virtuel pour les services Web externes (VIP) pour le trafic de services Web doit être configuré pour la source. L’affinité source permet de s’assurer que plusieurs connexions à partir d’un client unique sont envoyées à un serveur pour gérer l’état de la session. Pour plus d’informations sur les exigences d’affinité, voir [exigences d’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Si vous envisagez de prendre en charge des clients mobiles Lync uniquement sur votre réseau Wi-Fi interne, vous devez configurer les VIP de services Web internes pour la source, comme décrit pour les VIP de services Web externes. Dans ce cas, nous vous conseillons\_d’utiliser l’affinité source (ou TCP) pour les VIP de services Web internes sur le système d’équilibrage de charge matérielle. Pour plus d’informations, voir [exigences d’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Configuration requise du proxy inverse

Si vous prenez en charge la découverte automatique pour les clients mobiles Lync, vous devez mettre à jour la règle de publication actuelle comme suit:

  - Si vous décidez de mettre à jour les listes d’autres noms d’objet sur les certificats proxy inverse et d’utiliser HTTPs pour la demande de service de découverte automatique initiale, vous devez mettre à jour la règle de publication Web pour lyncdiscover. \<sipdomain\>. En règle générale, ce problème est associé à la règle de publication pour l’URL des services Web externes sur le pool frontal.

  - Si vous décidez d’utiliser HTTP pour la demande initiale de service de découverte automatique afin que vous n’ayez pas besoin de mettre à jour la liste des autres noms de sujet sur les certificats proxy inverse, vous devez créer une nouvelle règle de publication Web pour le port HTTP/TCP 80, s’il n’en existe pas. Si une règle pour HTTP/TCP 80 existe déjà, vous pouvez mettre à jour cette règle pour inclure le lyncdiscover. \<entrée\> sipdomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

