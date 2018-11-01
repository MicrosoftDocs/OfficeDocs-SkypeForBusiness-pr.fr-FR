---
title: 'Lync Server 2013 : exigences techniques pour la mobilité'
TOCTitle: Exigences techniques pour la mobilité
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690030(v=OCS.15)
ms:contentKeyID: 49297913
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigences techniques pour la mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Les utilisateurs mobiles font face à différents scénarios d’applications mobiles qui nécessitent une planification particulière. Par exemple, il se peut que quelqu’un commence à utiliser une application mobile lors d’un déplacement en se connectant par le biais du réseau 3G, qu’il bascule vers le réseau Wi-Fi d’entreprise à son arrivée au bureau et qu’il rebascule ensuite sur le réseau 3G à sa sortie du bâtiment. Vous devez planifier votre environnement de sorte qu’il prenne en charge ce type de transition de réseau et qu’il garantisse une expérience utilisateur cohérente. Cette section décrit les exigences d’infrastructure à satisfaire pour prendre en charge des applications mobiles et la découverte automatique des ressources de mobilité.

> [!NOTE]  
> Même si les applications mobiles peuvent également se connecter à d’autres services Lync Server 2013, l’exigence relative à l’envoi de toutes les demandes web d’applications mobiles au même nom de domaine complet web externe s’applique uniquement au service de mobilité Lync Server 2013. Cette configuration n’est pas nécessaire pour les autres services de mobilité.

Les exigences en matière d’affinité de cookie dans les équilibreurs de charge matérielle sont réduites et vous pouvez la remplacer par l’affinité TCP (Transmission Control Protocol) si vous utilisez Lync Mobile fourni avec Lync Server 2013. L’affinité de cookie peut être utilisée, mais les services web ne l’exigent plus.

> [!IMPORTANT]  
> Tout le trafic du service de mobilité passe par le proxy inverse, quel que soit le point d’origine (interne ou externe). Dans le cas d’un seul proxy inverse ou d’une batterie de proxys inverses, ou d’un appareil qui fournit la fonction de proxy inverse, un problème peut survenir quand le trafic interne quitte une interface et essaie immédiatement d’entrer dans la même interface. Cela peut souvent mener à une violation de règle de sécurité appelée « usurpation d’identité de paquet TCP ». L’<em>épinglage</em> (hairpinning : sortie puis entrée immédiate d’un paquet ou d’une série de paquets) doit être autorisé pour que la mobilité fonctionne. Une solution à ce problème consiste à utiliser un proxy inverse distinct du pare-feu (la règle de prévention d’usurpation d’identité doit toujours être appliquée au niveau du pare-feu, pour des raisons de sécurité). L’épingle peut se trouver au niveau de l’interface externe du proxy inverse plutôt qu’au niveau de l’interface externe du pare-feu. Vous détectez l’usurpation d’identité au niveau du pare-feu et ignorez la règle au niveau du proxy inverse, autorisant ainsi l’épingle requise par la mobilité.<br />
Utilisez les enregistrements hôte DNS (Domain Name System) ou CNAME pour définir le proxy inverse pour le comportement d’épinglage (et non le pare-feu) dans la mesure du possible.

Lync Server 2013 prend en charge les services de mobilité pour les clients mobiles Lync 2010 Mobile et Lync 2013. Ces deux types de clients utilisent le service de découverte automatique de Lync Server 2013 pour trouver le point d’entrée de mobilité, mais diffèrent quant au service de mobilité utilisé. Lync 2010 Mobile utilise le service de mobilité appelé *Mcx* , introduit dans la Mise à jour cumulative pour Lync Server 2010 de novembre 2011. Les clients mobiles Lync 2013 utilisent l’API web de communications unifiées, ou *UCWA* , comme fournisseur de service de mobilité.

## Configuration DNS interne et externe

Les services de mobilité Mcx (introduit dans la Mise à jour cumulative pour Lync Server 2010 de novembre 2011) et UCWA (introduit dans la Mise à jour cumulative pour Lync Server 2013 de février 2013) utilisent le système DNS de la même manière.

Quand vous utilisez la découverte automatique, les appareils mobiles utilisent le système DNS pour trouver les ressources. Lors de la recherche DNS, une tentative de connexion est d’abord effectuée vers le nom de domaine complet associé à l’enregistrement DNS interne (lyncdiscoverinternal. *\<internal domain name\>*). Si aucune connexion ne peut être établie à l’aide de l’enregistrement DNS interne, une tentative de connexion est effectuée à l’aide de l’enregistrement DNS externe (lyncdiscover. *\<sipdomain\>*). Un appareil mobile interne au réseau se connecte à l’URL du service de découverte automatique interne, alors qu’un appareil mobile externe au réseau se connecte à l’URL du service de découverte automatique externe. Les demandes externes passent par le proxy inverse. Le service de découverte automatique de Lync Server 2013 renvoie toutes les URL des services web correspondant au pool d’accueil de l’utilisateur, dont les URL du service de mobilité (Mcx et UCWA). Cependant, l’URL du service de mobilité interne et l’URL du service de mobilité externe sont toutes deux associées au nom de domaine complet externe des services web. Par conséquent, qu’il soit interne ou externe au réseau, un appareil mobile se connecte toujours au service de mobilité de Lync Server 2013 de manière externe, par le biais du proxy inverse.

> [!NOTE]  
> Il est important de comprendre que votre déploiement peut comporter plusieurs espaces de noms distincts pour une utilisation interne et externe. Votre nom de domaine SIP peut être différent du nom de domaine de déploiement interne. Par exemple, votre domaine SIP peut être <strong>contoso.com</strong>, alors que votre déploiement interne peut être <strong>contoso.net</strong>. Les utilisateurs se connectant à Lync Server emploieront le nom de domaine SIP, tel que <strong>john@contoso.com</strong>. Lors du traitement des services web externes (définis dans Générateur de topologie en tant que <strong>Services web externes</strong>), les noms de domaine et de domaine SIP seront cohérents, comme indiqué dans DNS. Lors du traitement des services web internes (définis dans Générateur de topologie en tant que <strong>Services web internes</strong>), le FQDN du serveur frontal, pool de serveurs frontaux, directeur ou pool de directeurs représentera le nom par défaut des services web internes. Vous pouvez remplacer le nom des services web internes. Utilisez le nom de domaine interne (et non le nom de domaine SIP) pour les services web internes, et définissez l’enregistrement A de l’hôte DNS (ou, pour IPv6, AAAA) de sorte qu’il corresponde au nom remplacé. Par exemple, le FQDN par défaut des services web internes peut être <strong>pool01.contoso.net</strong>. Un FQDN remplacé des services web internes peut être <strong>webpool.contoso.net</strong>. Ce mode de définition des services web permet de garantir l’observation des localités interne et externe de ces services (et non la localité de l’utilisateur qui s’en sert).<br />
Cependant, les services web étant définis dans Générateur de topologie et le nom des services web internes remplaçable, sous réserve de la cohérence du nom final des services Web, du certificat qui le valide et des enregistrements DNS qui le définissent, vous pouvez définir ces services web internes avec le nom de domaine de votre choix (dont celui du domaine SIP). La résolution du nom en adresse IP est déterminée par les enregistrements hôte DNS et un espace de noms cohérent.<br />
Dans le cas de cette rubrique et des exemples, le nom de domaine interne est utilisé pour illustrer la topologie et les définitions DNS.

Le diagramme suivant illustre le flux des demandes web d’applications mobiles pour le service de mobilité et le service de découverte automatique lors de l’utilisation d’une configuration DNS interne et externe.

**Flux de service de mobilité avec la découverte automatique**

![Flux de demandes de mobilité](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "Flux de demandes de mobilité")

> [!NOTE]  
> Le diagramme illustre les services web génériques. Un répertoire virtuel nommé Mobility illustre les services de mobilité Mcx et/ou UCWA. Si vous n’avez pas appliqué la mise à jour cumulative pour Lync Server 2013 de février 2013, il n’est pas certain que le répertoire virtuel Ucwa soit défini sur vos services web internes et externes. Vous aurez un répertoire virtuel de découverte automatique et peut-être un répertoire virtuel Mcx.<br />
La découverte automatique et la découverte des services fonctionnent de la même façon, quelle que soit la technologie des services de mobilité déployée.

Pour prendre en charge les utilisateurs mobiles internes et externes au réseau d’entreprise, vos noms de domaine complets web internes et externes doivent remplir certaines conditions. Par ailleurs, certaines conditions supplémentaires peuvent être requises, selon les fonctionnalités que vous choisissez d’implémenter :

  - nouveaux enregistrements DNS, A (hôte, si IPv6, AAAA) ou CNAME pour la découverte automatique ;

  - nouvelle règle de pare-feu, si vous souhaitez prendre en charge les notifications push à travers votre réseau Wi-Fi ;

  - autres noms du sujet sur les certificats de serveurs internes et les certificats de proxys inverses, pour la découverte automatique ;

  - la configuration du programme d’équilibrage de la charge matérielle du serveur frontal change l’affinité source.

Votre topologie doit remplir les conditions suivantes afin de prendre en charge le service de mobilité et le service de découverte automatique :

  - Le nom de domaine complet web interne du pool de serveurs frontaux doit être différent du nom de domaine complet web externe du pool de serveurs frontaux.

  - Le nom de domaine complet web interne doit uniquement être résolu vers et accessible depuis l’intérieur du réseau d’entreprise.

  - Le nom de domaine complet web externe doit uniquement être résolu vers et accessible depuis Internet.

  - Pour un utilisateur qui se trouve sur le réseau d’entreprise, l’URL du service de mobilité doit être adressée au nom de domaine complet web externe. Cette exigence concerne le service de mobilité et s’applique uniquement à cette URL.

  - Pour un utilisateur qui se trouve à l’extérieur du réseau d’entreprise, la demande doit parvenir au nom de domaine complet web externe du pool de serveurs frontaux ou du directeur.

Si vous prenez en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP :

  - un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis le réseau de votre organisation ;

  - un enregistrement DNS externe ou public afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.

L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable depuis votre réseau. Cependant, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité du client mobile ne sera sans doute pas affectée car la première tentative porte toujours sur l’URL interne.

Les enregistrements DNS peuvent être des enregistrements CNAME ou des enregistrements A (hôte, si IPv6, AAAA).

> [!NOTE]  
> Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) de différents domaines. Par conséquent, la redirection CNAME vers différents domaines n’est pas prise en charge sur le protocole HTTPS. Par exemple, un enregistrement DNS CNAME pour lyncdiscover.contoso.com qui redirige vers une adresse director.contoso.net n’est pas pris en charge sur HTTPS. Dans une telle topologie, un client d’appareil mobile doit utiliser le protocole HTTP pour la première demande, de sorte que la redirection CNAME soit résolue sur HTTP. Les demandes ultérieures utilisent ensuite le protocole HTTPS. Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication web pour le port 80 (HTTP). Pour plus d’informations, reportez-vous à « Pour créer une règle de publication web pour le port 80 » dans <a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</a>.<br />
La redirection CNAME vers le même domaine est prise en charge sur HTTPS. Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.

Pour plus d’informations sur les enregistrements DNS requis pour votre scénario, reportez-vous à [Synthèse DNS - Découverte automatique dans Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

## Exigences relatives aux ports et aux pare-feu

Si vous prenez en charge les notifications push et souhaitez que les appareils mobiles Apple reçoivent des notifications push par le biais de votre réseau Wi-Fi, vous devez également ouvrir le port 5223 sur votre réseau Wi-Fi d’entreprise. Il s’agit d’un port TCP sortant utilisé par le service APNS (Apple Push Notification Service). L’appareil mobile initie la connexion. Pour plus d’informations, reportez-vous à [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ht6175?viewlocale=fr_fr)

> [!WARNING]  
> Un appareil Apple utilisant le client Lync 2013 Mobile ne nécessite pas de notifications push.

Notez que si un utilisateur est hébergé sur un Survivable Branch Appliance (SBA), les ports suivants sont requis :

  - UcwaSipExternalListeningPort requiert le port 5088

  - UcwaSipPrimaryListeningPort requiert le port 5089

Pour plus d’informations et des instructions sur les exigences liées aux ports et aux protocoles de découverte automatique, reportez-vous à [Synthèse des ports - Découverte automatique dans Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

## Exigences en matière de certificats

Si vous prenez en charge la découverte automatique pour les clients mobiles Lync, vous devez modifier la liste des autres noms de sujet sur les certificats de manière à prendre en charge les connexions sécurisées établies à partir de clients mobiles. Vous devez demander et affecter de nouveaux certificats, en ajoutant les entrées d’autres noms de sujet comme décrit dans cette section, pour chaque serveur frontal et directeur qui exécute le service de découverte automatique. L’approche recommandée consiste à modifier également les listes d’autres noms de sujet sur les certificats pour vos proxys inverses. Vous devez ajouter des entrées d’autres noms de sujet pour chaque domaine SIP de votre organisation.

La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple, mais l’ajout de plusieurs entrées d’autres noms du sujet à des certificats publics utilisés par le proxy inverse peut être une opération coûteuse. Si vous avez de nombreux domaines SIP, ce qui rend l’ajout d’autres noms du sujet très coûteux, vous pouvez configurer le proxy inverse de sorte qu’il effectue la demande initiale du service de découverte automatique sur le port 80 à l’aide du protocole HTTP, plutôt que sur le port 443 à l’aide du protocole HTTPS (configuration par défaut). La demande est alors redirigée vers le port 8080 sur le directeur ou le pool de serveurs frontaux. Lorsque vous publiez la demande initiale du service de découverte automatique sur le port 80, il n’est pas nécessaire de modifier les certificats pour le proxy inverse car la demande utilise le protocole HTTP plutôt que HTTPS. Cette approche est prise en charge mais non recommandée.

## Exigences relatives aux services Internet (IIS)

Nous vous recommandons d’utiliser les services Internet (IIS) 7.5, les services Internet (IIS) 8.0 ou les services Internet (IIS) 8.5 pour la mobilité. Le programme d’installation du service de mobilité définit des indicateurs dans ASP.NET afin d’améliorer les performances. Les services Internet (IIS) 7.5 sont installés par défaut sur Windows Server 2008 R2, les services Internet (IIS) 8.0 sur Windows Server 2012 et les services Internet (IIS) 8.5 sur Windows Server 2012 R2. Le programme d’installation du service de mobilité modifie automatiquement les paramètres ASP.NET.

## Exigences relatives au programme d’équilibrage de la charge matérielle

Sur l’équilibreur de la charge matérielle qui prend en charge le pool de serveurs frontaux, les adresses IP virtuelles des services web externes pour le trafic des services web doivent être configurées pour la source. L’affinité source aide à s’assurer que plusieurs connexions issues d’un même client sont envoyées à un seul serveur pour maintenir l’état de la session. Pour plus d’informations sur les exigences relatives à l’affinité, reportez-vous à [Configuration requise pour l’équilibrage de charge dans Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Si vous envisagez de prendre en charge les clients mobiles Lync uniquement sur votre réseau Wi-Fi interne, vous devez configurer les adresses IP virtuelles des services web internes pour la source comme décrit pour les adresses IP virtuelles des services web externes. Dans ce cas, vous devez utiliser source\_addr (ou TCP) pour les adresses IP virtuelles des services web internes sur l’équilibreur de la charge matérielle. Pour plus d’informations, reportez-vous à [Configuration requise pour l’équilibrage de charge dans Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

## Exigences relatives au proxy inverse

Si vous prenez en charge la découverte automatique pour les clients mobiles Lync, vous devez mettre à jour la règle de publication actuelle comme suit :

  - Si vous décidez de mettre à jour les listes d’autres noms du sujet sur les certificats de proxy inverse et d’utiliser le protocole HTTPS pour la demande initiale de découverte automatique, vous devez mettre à jour la règle de publication web pour lyncdiscover. *\<sipdomain\>*. En règle générale, elle est associée à la règle de publication pour l’URL externe des services web sur le pool de serveurs frontaux.

  - Si vous décidez d’utiliser HTTP pour la demande initiale du service de découverte automatique afin de ne pas être obligé de mettre à jour la liste des autres noms du sujet sur les certificats de proxy inverse, vous devez créer une règle de publication web pour le port HTTP/TCP 80, si elle n’existe pas déjà. S’il existe déjà une règle pour HTTP/TCP 80, vous pouvez mettre à jour la règle de façon à inclure l’entrée lyncdiscover. *\<sipdomain\>*.

