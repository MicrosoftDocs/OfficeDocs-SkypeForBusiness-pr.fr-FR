---
title: 'Lync Server 2013 : Composant Serveur de médiation'
TOCTitle: Composant Serveur de médiation
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398399(v=OCS.15)
ms:contentKeyID: 49297281
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composant Serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Vous devez déployer le serveur de médiation de Lync Server 2013 si vous déployez la charge de travail Voix Entreprise. Cette section décrit les fonctionnalités et topologies de base, les dépendances et les directives de planification.

Le serveur de médiation convertit la signalisation et, dans certaines configurations, les données multimédia entre votre infrastructure interne Voix Entreprise de Lync Server 2013 et une passerelle RTC ou une jonction SIP (Session Initiation Protocol). Du côté de Lync Server 2013, le serveur de médiation est à l’écoute sur une seule adresse de transport MTLS (Mutual TLS). Du côté de la passerelle, le serveur de médiation est à l’écoute sur tous les ports d’écoute associés aux jonctions définies dans le document de topologie. Toutes les passerelles qualifiées doivent prendre en charge le protocole TLS mais peuvent aussi activer le protocole TCP. Le protocole TCP est pris en charge pour les passerelles qui ne prennent pas en charge le protocole TLS.

Si vous disposez aussi d’un autocommutateur public (PBX) dans votre environnement, le serveur de médiation gère les appels entre les utilisateurs Voix Entreprise et l’autocommutateur public. Si votre système PBX est de type IP-PBX, vous pouvez créer une connexion SIP directe entre le système PBX et le serveur de médiation. Si votre système PBX est de type PBX TDM (multiplexage temporel), vous devez aussi déployer une passerelle RTC entre le serveur de médiation et le système PBX.

Le serveur de médiation est colocalisé avec le serveur frontal par défaut. Le serveur de médiation peut aussi être déployé dans un pool autonome pour des raisons de performances ou pour le déploiement d’une jonction SIP. Dans ce dernier cas de figure, le pool autonome est fortement recommandé.

Si vous déployez des connexions SIP directes sur une passerelle RTC qualifiée prenant en charge la déviation du trafic multimédia et l’équilibrage de charge DNS, un pool de serveurs de médiation autonome n’est pas nécessaire, car les passerelles qualifiées sont capables d’équilibrer la charge DNS sur un pool de serveurs de médiation et d’accepter du trafic en provenance de n’importe quel serveur de médiation au sein d’un pool.

Nous vous recommandons également de colocaliser le serveur de médiation sur un pool de serveurs frontaux après avoir déployé des systèmes IP-PBX ou vous être connecté au contrôleur SBC d’un fournisseur de serveur de téléphonie Internet si l’une des conditions suivantes est remplie :

  - Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

  - Le système IP-PBX ne prend pas en charge la déviation du trafic multimédia mais le pool de serveurs frontaux chargé d’héberger le serveur de médiation peut gérer le transcodage vocal des appels non concernés par la déviation du trafic multimédia.

L’outil de planification Microsoft Lync Server 2013 peut servir à évaluer si le pool de serveurs frontaux sur lequel s‘effectuera la colocalisation du serveur de médiation peut gérer la charge. Si votre environnement ne satisfait pas les conditions requises, vous devez déployer un pool de serveurs de médiation autonome.

Les principales fonctions du serveur de médiation sont les suivantes :

  - Chiffrement et déchiffrement SRTP sur Lync Server

  - Conversion SIP sur TCP (pour les passerelles non compatibles TLS) vers SIP sur mutual TLS

  - Conversion des flux de données multimédias entre Lync Server et l’homologue de passerelle du serveur de médiation

  - Connexion des clients situés hors du réseau aux composants ICE internes, ce qui permet aux données multimédias de traverser les convertisseurs d’adresses réseau (NAT) et les pare-feu

  - Rôle d’intermédiaire pour les flux d’appels non pris en charge par une passerelle, tels que les appels de travailleurs distants sur un client Voix Entreprise

  - Dans les déploiements qui incluent la jonction SIP, collaboration avec le fournisseur de services de jonction SIP pour fournir la prise en charge RTC, de sorte qu’il ne soit plus nécessaire de disposer d’une passerelle RTC

La figure suivante illustre les protocoles de signalisation et de données multimédias utilisés par le serveur de médiation lors de la communication avec une passerelle RTC de base et l’infrastructure Voix Entreprise.

**Protocoles de signalisation et de données multimédias utilisés par le serveur de médiation**

![Diagramme de protocoles de serveur de médiation](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramme de protocoles de serveur de médiation")

> [!NOTE]  
> Si vous utilisez TCP ou RTP/RTCP (au lieu de SRTP ou SRTCP) sur le réseau entre la passerelle RTC et le serveur de médiation, nous vous conseillons de prendre les mesures nécessaires pour garantir la sécurité et la confidentialité des données sur le réseau.

## Dans cette section

  - [Jonction M:N dans Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Instructions de déploiement du serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

