---
title: "Plan. pour les féd. SIP, XMPP et la mess. inst. publ. dans Lync Server 2013"
TOCtitle: "Plan. pour les féd. SIP, XMPP et la mess. inst. publ. dans Lync Server 2013"
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204825(v=OCS.15)
ms:contentKeyID: 49296941
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification pour la fédération SIP, la fédération XMPP et la messagerie instantanée publique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-28_

Les serveurs Edge peuvent être configurés pour permettre à vos utilisateurs internes et externes de toucher des contacts au sein d’organisations ou de services partenaires. Ces accords partenaires, que l’on appelle « fédérations », peuvent fournir tout ou partie des fonctionnalités suivantes entre les contacts de votre organisation et ceux de la fédération partenaire :

  - Messagerie instantanée et présence

  - Collaboration et conférence (par exemple, conférence web)

  - Audioconférence, vidéoconférence ou les deux

Dans certains cas, les communications entre un contact Microsoft Lync Server 2013 et un contact XMPP (Extensible Messaging and Presence Protocol) sont des communications strictement d’égal à égal (notamment dans le cadre de la messagerie instantanée et de la présence), où seule la communication entre vous et le contact du partenaire fédéré est prise en charge. Dans d’autres cas, notamment dans le cadre d’une fédération entre Lync Server, Lync Server 2010 et Lync Server 2013, plusieurs participants peuvent être invités à se joindre à la conversation.

## Fédération Lync Server et Office Communications Server

La fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications d’égal à égal et à plusieurs utilisateurs. Les communications d’égal à égal peuvent devenir des conversions à plusieurs utilisateurs, ce qui permet d’organiser des réunions ad hoc. Des réunions (conférences web ou conférences audiovisuelles) peuvent être programmées pour inclure des contacts de votre organisation, ainsi que des contacts des partenaires avec lesquels vous appliquez la fédération.

D’abord apparue dans Microsoft Office Live Communications Server 2005, la fédération prenait en charge un seul type de fédération, la fédération directe. Cette dernière nécessitait de connaître le domaine SIP (Session Initiation Protocol) du partenaire de fédération, ainsi que le nom de domaine complet du serveur Edge du partenaire. Live Communications Server 2005 avec SP1 a introduit des types de fédérations supplémentaires, qui nécessitaient tous la publication des enregistrements SRV DNS (Domain Name System) par le partenaire fédéré pour localiser leur serveur Edge. Cette version utilisait la terminologie suivante :

  - *fédération étendue ouverte* : accepter tout nom de domaine SIP et utiliser les enregistrements SRV DNS pour localiser le serveur Edge du partenaire ;

  - *fédération étendue* : configurer le nom de domaine SIP du partenaire comme partenaire de fédération pour votre organisation et utiliser les enregistrements SRV DNS pour rechercher le serveur Edge du partenaire ;

  - *fédération directe* : configurer le nom de domaine SIP du partenaire et le nom de domaine complet du serveur Edge du partenaire ;

  - *liste verte du serveur* : accepter tout domaine, utiliser les enregistrements SRV DNS pour rechercher le serveur Edge d’un fournisseur d’hébergement ou d’un fournisseur de connectivité PIC (Public IM Connectivity).

Dans Microsoft Office Communications Server 2007, les types de fédérations ont été renommés afin de mieux définir ce que chaque type de fédération réalise :

  - La fédération étendue ouverte a été remplacée par le *domaine partenaire découvert*.

  - La fédération étendue a été remplacée par le *domaine partenaire autorisé*.

  - La fédération directe a été remplacée par le *serveur partenaire autorisé*.

  - La liste verte du serveur a été remplacée par le *fournisseur d’hébergement* et le *fournisseur public de messagerie instantanée*.

Microsoft Lync Server 2010 a inclus une définition plus restreinte du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et Microsoft Office 365 et lui a appliqué la même liste verte définie par le type de fédération de domaine partenaire autorisé.

L’activation de la fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server utilise les serveurs Edge et les proxys inverses pour appliquer les règles et les domaines partenaires autorisés que vous définissez. Du point de vue de la planification, la fédération avec un autre serveur Lync Server, Office Communications Server nécessite les actions suivantes :

  - activation de la fédération dans le générateur de topologies. Pour plus d’informations, voir [Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - détermination de vos conditions pour la découverte des domaines fédérés :
    
      -   
        Pour la configuration manuelle de la fédération, vous devez disposer du nom de domaine complet du serveur Edge du partenaire et du nom de domaine, ou du nom de domaine en ligne (entré dans le Panneau de configuration Lync Server, **Fédération et accès externe**, **Domaines fédérés SIP**). Créez une **nouvelle** stratégie ou **modifiez** une stratégie existante pour autoriser ou bloquer les domaines par nom de domaine complet.
        
        > [!WARNING]  
        > La configuration manuelle du serveur Edge d’un partenaire de fédération peut échouer si le partenaire modifie l’adresse IP de son serveur Edge.        
        > [!NOTE]  
        > Pour les <strong>nouveaux domaines fédérés SIP</strong>, vous devez fournir le <strong>nom de domaine (ou nom de domaine complet)</strong> pour Microsoft Lync Online, Microsoft Office 365. Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server, vous devez également fournir un <strong>service Edge d’accès (nom de domaine complet)</strong>.    
      -   
        Pour la fédération des partenaires découverts via laquelle les partenaires peuvent découvrir votre serveur Edge, vous pouvez créer un enregistrement SRV dans votre DNS externe (\_sipfederationtls.\_tcp.contoso.com) qui pointe vers le port 5061 et l’enregistrement hôte (A) de votre serveur Edge.
        
        > [!IMPORTANT]  
        > Si vous prenez en charge les clients Microsoft Lync Mobile sur Windows Phone, iPhone, iPad ou d’autres appareils d’Apple et utilisez le service de notifications Push ou le service de notifications Push, vous devez planifier les enregistrements SRV _sipfederationtls._tcp. <em>&lt;domaine SIP&gt;</em> pour chaque domaine SIP pour lequel vous avez des clients Lync Mobile. Android et Nokia Symbian Lync Mobile n’utilisent pas les notifications push et ne sont pas soumis à cette condition.

  - configuration des stratégies d’accès des utilisateurs externes pour la prise en charge des domaines fédérés.

  - ouverture des ports de pare-feu pour le protocole SIP (Session Initiation Protocol), les conférences web et audiovisuelles pour prendre en charge la fédération ou les contacts que vous activez. Pour plus d’informations, voir [Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

Les informations suivantes vous aideront à définir les conditions relatives au certificat, au port/protocole et au DNS pour la fédération avec Microsoft Lync Server 2013 et Lync Server 2010.

La planification des conditions relatives au certificat, au pare-feu, au port/protocole et au DNS constitue généralement un processus simple si vous avez planifié ou déployé vos serveurs EdgeMicrosoft Lync Server 2013. Comme la fédération est une fonctionnalité supplémentaire qui utilise le serveur Edge existant, les conditions de planification sont généralement satisfaites par la planification et le déploiement du serveur Edge. Vous devez utiliser les tableaux suivants pour déterminer si vos conditions sont satisfaites et apporter des modifications au port/protocole et au DNS le cas échéant.

> [!IMPORTANT]  
> Si vous disposez d’un pool de serveurs Edge et utilisez la fédération avec des partenaires Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de la charge DNS ou des programmes d’équilibrage de la charge matérielle sur les côtés internes et externes des serveurs Edge. Si vous utilisez la fédération avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de la charge matérielle prendra en charge le basculement dans le cas d’un serveur Edge. Office Communications Server 2007 et Office Communications Server 2007 R2 ne sont pas compatibles avec l’équilibrage de la charge DNS. Les serveurs Edge du partenaire établiront la communication avec le premier serveur Edge dans votre pool qui répond. Si ce serveur Edge échoue, la communication ne bascule pas automatiquement.

Les conditions relatives au certificat sont généralement satisfaites via la planification des certificats pour votre serveur Edge choisi ou votre plan de serveur Edge mis en pool.

## Prise en charge de la connectivité PIC (Public IM Connectivity)

La Connectivité PIC (Public IM Connectivity) est une classe de fédération configurée pour permettre à vos utilisateurs internes et externes de Lync Server 2013 d’ajouter des contacts à partir des applications suivantes :

  - Contacts Messenger

  - Contacts Yahoo\!

  - Contacts AOL (America Online)

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync PIC USL (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service (la date exacte reste à déterminer, mais l’arrêt du service n’interviendra pas avant juin 2013).</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent ne sera pas renouvelé.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


Cette classe de fédération nécessite les considérations de planification suivantes :

  - Les utilisateurs de Windows Live Messenger peuvent communiquer avec l’audio/la vidéo d’égal-à-égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée. Vos serveurs Edge doivent respecter des exigences de port et de protocole spécifiques. Pour plus d’informations, voir [Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La messagerie instantanée Yahoo n’a aucune exigence spécifique autre que celles typiquement utilisées dans la planification et le déploiement d’un serveur Edge classique qui fournit la fédération.

  - America Online demande à ce que votre certificat serveur Edge attribué au service Edge d’accès ait une utilisation améliorée de la clé (EKU).

## Fédération XMPP (Extensible Messaging and Presence Protocol)

Les versions précédentes de Lync Server et Office Communications Server fournissaient une passerelle XMPP qui pouvait être déployée sur un rôle serveur séparé afin de permettre la fédération avec les déploiements XMPP. Dans Microsoft Lync Server 2013, XMPP peut être déployé comme une fonctionnalité. La fonctionnalité XMPP est installée en deux parties : un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.

Le déploiement et la configuration de XMPP sont décrits dans [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Pour prendre en charge XMPP au sein de votre organisation, vous devez prévoir la définition des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout d’enregistrements DNS. Les rubriques suivantes de cette section résument les informations nécessaires pour prévoir la fédération XMPP pour votre déploiement.

> [!IMPORTANT]  
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tiers pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

> [!IMPORTANT]  
> La fédération XMPP n’est pas prise en charge pour les utilisateurs qui sont hébergés sur des Survivable Branch Appliances. Ceci s’applique à la fois aux informations de présence et à l’échange de messages instantanés.

Les rubriques suivantes incluent des instructions pour la définition des certificats, des ports de pare-feu et des entrées DNS pour les types de scénarios de fédération pris en charge.

  -   
    [Résumé des certificats - Fédération SIP, fédération XMPP et messagerie instantanée publique](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  -   
    [Résumé des ports - Fédération SIP, fédération XMPP et messagerie instantanée publique](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  -   
    [Résumé des enregistrements DNS - Fédération SIP, fédération XMPP et messagerie instantanée publique](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

## Voir aussi

#### Tâches

[Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  

#### Concepts

[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Autres ressources

[Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

