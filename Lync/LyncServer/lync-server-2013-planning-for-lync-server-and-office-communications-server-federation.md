---
title: "Planif. pour la fédération de Lync Server et Office Communications Server"
TOCtitle: "Planif. pour la fédération de Lync Server et Office Communications Server"
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205335(v=OCS.15)
ms:contentKeyID: 49298852
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification pour la fédération de Lync Server et Office Communications Server

 

_**Dernière rubrique modifiée :** 2013-02-13_

La fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications d’égal à égal et à plusieurs utilisateurs. Les communications d’égal à égal peuvent devenir des conversions à plusieurs utilisateurs, ce qui permet d’organiser des réunions ad hoc. Des réunions (conférences web ou conférences audiovisuelles) peuvent être programmées pour inclure des contacts de votre organisation, ainsi que des contacts des partenaires avec lesquels vous appliquez la fédération.

D’abord apparue dans Microsoft Office Live Communications Server 2005, la fédération prenait en charge un seul type de fédération, la fédération directe. Cette dernière nécessitait de connaître le domaine SIP (Session Initiation Protocol) du partenaire de fédération, ainsi que le nom de domaine complet du serveur Edge du partenaire. Live Communications Server 2005 avec SP1 a introduit des types de fédération supplémentaires, qui nécessitaient tous la publication des enregistrements SRV DNS (Domain Name System) par le partenaire fédéré pour localiser leur serveur Edge. Cette version utilisait la terminologie suivante :

  - *fédération étendue ouverte* : accepter tout nom de domaine SIP et utiliser les enregistrements SRV DNS pour localiser le serveur Edge du partenaire ;

  - *fédération étendue* : configurer le nom de domaine SIP du partenaire comme partenaire de fédération pour votre organisation et utiliser les enregistrements SRV DNS pour rechercher le serveur Edge du partenaire ;

  - *fédération directe* : configurer le nom de domaine SIP du partenaire et le nom de domaine complet du serveur Edge du partenaire ;

  - *liste verte du serveur* : accepter tout domaine, utiliser les enregistrements SRV DNS pour rechercher le serveur Edge d’un fournisseur d’hébergement ou d’un fournisseur de connectivité PIC (Public IM Connectivity).

Dans Microsoft Office Communications Server 2007, les types de fédération ont été renommés afin de mieux définir ce que chaque type de fédération réalise :

  - La fédération étendue ouverte a été remplacée par le *domaine partenaire découvert*.

  - La fédération étendue a été remplacée par le *domaine partenaire autorisé*.

  - La fédération directe a été remplacée par le *serveur partenaire autorisé*.

  - La liste verte du serveur a été remplacée par le *fournisseur d’hébergement* et le *fournisseur public de messagerie instantanée*.

Microsoft Lync Server 2010 a inclus une définition plus restreinte du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et Microsoft Office 365 et lui a appliqué la même liste verte définie par le type de fédération de domaine partenaire autorisé.

L’activation de la fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server utilise les serveurs Edge et les proxys inverses pour appliquer les règles et les domaines partenaires autorisés que vous définissez. Du point de vue de la planification, la fédération avec un autre serveur Lync Server, Office Communications Server nécessite les actions suivantes :

  - activation de la fédération dans le générateur de topologies. Pour plus d’informations, voir la rubrique [Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

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

## Dans cette section

  - [Résumé des certificats - Fédération SIP, fédération XMPP et messagerie instantanée publique](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Résumé des ports - Fédération SIP, fédération XMPP et messagerie instantanée publique](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Résumé des enregistrements DNS - Fédération SIP, fédération XMPP et messagerie instantanée publique](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

