---
title: Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4148cd97ec118a223e7e8b1b1e8c3825f51dbad6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-28_

Les serveurs Edge peuvent être configurés pour permettre à vos utilisateurs internes et externes d’accéder aux contacts au niveau des organisations ou des services partenaires. Ces accords partenaires, que l’on appelle « fédérations », peuvent fournir tout ou partie des fonctionnalités suivantes entre les contacts de votre organisation et ceux de la fédération partenaire :

  - Messagerie instantanée et présence

  - Collaboration et conférence (par exemple, conférence web)

  - Audioconférence, vidéoconférence ou les deux

Dans certains cas, la communication, par exemple, la messagerie instantanée et la présence entre un contact Microsoft Lync Server 2013 et un contact XMPP (extensible Messaging and Presence Protocol), est à l’égal à homologue : ne prenez en charge que vous et le contact du partenaire fédéré. Dans d’autres cas, tels qu’un Lync Server, Lync Server 2010 à la Fédération Lync Server 2013, plusieurs participants peuvent être invités à participer à la conversation.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Fédération Lync Server et Office Communications Server

La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications entre homologues et plusieurs parties. Les communications d’égal à égal peuvent devenir des conversions à plusieurs utilisateurs, ce qui permet d’organiser des réunions ad hoc. Des réunions (conférences web ou conférences audiovisuelles) peuvent être programmées pour inclure des contacts de votre organisation, ainsi que des contacts des partenaires avec lesquels vous appliquez la fédération.

La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération directe. La Fédération directe exigeait que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération et le nom de domaine complet (FQDN) du serveur Edge du partenaire. Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, dont tous les enregistrements SRV DNS (Domain Name System) requis doivent être publiés par le partenaire fédéré pour localiser leur serveur Edge. Cette version utilisait la terminologie suivante :

  - *Ouvrir la Fédération étendue*: accepter tout nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge partenaire

  - *Fédération étendue*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour rechercher le serveur Edge partenaire.

  - *Fédération directe*: configurez le nom de domaine SIP du partenaire et le nom de domaine complet (FQDN) du serveur Edge du partenaire.

  - *Liste verte du serveur*: accepter n’importe quel domaine, utiliser DNS SRV pour rechercher le serveur Edge d’un fournisseur d’hébergement ou d’un fournisseur de connectivité de messagerie instantanée publique

Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération afin de mieux définir ce que chaque type de Fédération a réellement accompli :

  - La fédération étendue ouverte a été remplacée par le *domaine partenaire découvert*.

  - La fédération étendue a été remplacée par le *domaine partenaire autorisé*.

  - La fédération directe a été remplacée par le *serveur partenaire autorisé*.

  - La liste verte du serveur a été remplacée par le *fournisseur d’hébergement* et le *fournisseur public de messagerie instantanée*.

Microsoft Lync Server 2010 a introduit une définition plus étroite du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et à Microsoft Office 365 et l’a également soumise à la même liste autorisée définie par le type de Fédération de domaine partenaire autorisé.

L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server utilise les serveurs Edge et les proxys inverses pour appliquer les règles et les domaines partenaires que vous définissez. Du point de vue de la planification, la Fédération avec d’autres Lync Server, Office Communications Server requiert les éléments suivants :

  - activation de la fédération dans le générateur de topologies. Pour plus d’informations, reportez-vous à la rubrique relative au déploiement Configuration de la [Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - détermination de vos conditions pour la découverte des domaines fédérés :
    
      - <span></span>  
        Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge et du nom de domaine du partenaire, ou du nom de domaine en ligne, qui est entré dans le panneau de configuration Lync Server, **Fédération et accès externe**, **domaines fédérés SIP**. Créez une **nouvelle** stratégie ou **modifiez** une stratégie existante pour autoriser ou bloquer les domaines par nom de domaine complet.
        
        <div>
        

        > [!WARNING]
        > La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible d’échouer si le partenaire modifie l’adresse IP de son serveur Edge.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez fournir le <STRONG>nom de domaine (ou FQDN)</STRONG> pour Microsoft Lync Online et microsoft 365 ou Office 365. Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server, vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG> .

        
        </div>
    
      - <span></span>  
        Pour la Fédération des partenaires découverts, où les partenaires peuvent découvrir votre serveur Edge, vous créez un enregistrement SRV dans votre DNS externe- \_ sipfederationtls. \_ tcp.contoso.com – qui pointe vers le port 5061 et l’enregistrement d’hôte (A) de votre serveur Edge
        
        <div>
        

        > [!IMPORTANT]
        > Si vous prenez en charge les clients mobiles Microsoft Lync sur Windows Phone ou Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notification par transmission ou de notification, vous devez planifier _sipfederationtls. _tcp. &lt;&gt;Enregistrements SRV de domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync. Android et Nokia Symbian Lync mobile n’utilisent pas la notification de transmission et ne sont pas soumis à cette exigence.

        
        </div>

  - configuration des stratégies d’accès des utilisateurs externes pour la prise en charge des domaines fédérés.

  - ouverture des ports de pare-feu pour le protocole SIP (Session Initiation Protocol), les conférences web et audiovisuelles pour prendre en charge la fédération ou les contacts que vous activez. Pour plus d’informations, reportez-vous à la rubrique : [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Les informations suivantes vous aideront à définir les exigences en matière de certificat, de port/protocole et de DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.

La planification des certificats, des exigences de pare-feu et de port/protocole et des exigences DNS est généralement un processus direct si vous avez planifié ou déployé vos serveurs Edge Microsoft Lync Server 2013. Étant donné que la Fédération est une fonctionnalité supplémentaire qui utilise le serveur Edge existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement du serveur Edge. Vous devez utiliser les tableaux suivants pour déterminer si vos conditions sont satisfaites et apporter des modifications au port/protocole et au DNS le cas échéant.

<div>


> [!IMPORTANT]
> Si vous disposez d’un pool de serveurs Edge et que vous vous fédérer avec des partenaires Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou des programmes d’équilibrage de la charge matérielle sur les côtés internes et externes des serveurs Edge. Si vous vous fédérer avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de la charge matérielle fournira une prise en charge du basculement en cas de serveur Edge. Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de la charge DNS. Les serveurs Edge partenaires vont établir une communication avec le premier serveur Edge de votre pool qui répond. En cas de défaillance du serveur Edge, la communication ne bascule pas automatiquement.



</div>

Les certificats requis sont généralement satisfaits via la planification des certificats pour le serveur Edge choisi ou le plan de serveur Edge mis en pool.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Connectivité de messagerie instantanée publique

La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants :

  - Contacts Messenger

  - Yahoo\! contacts

  - Contacts AOL (America Online)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement aux utilisateurs de la connectivité PIC de Microsoft Lync public (PIC) n’est plus disponible pour l’achat de contrats de nouvelle ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service (la date exacte doit toujours être fixée, mais pas avant le 2013 juin).</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement mensuel, mensuelle, nécessaire pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !. Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent qui n’est pas renouvelé.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes via la messagerie instantanée et la voix.</P></LI></UL>



</div>

Cette classe de fédération nécessite les considérations de planification suivantes :

  - Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio/vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée. Vos serveurs Edge doivent répondre à des exigences spécifiques en matière de port et de protocole. Pour plus d’informations, reportez-vous à [la rubrique determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La messagerie instantanée Yahoo n’a pas de configuration spécifique, à l’exception de celles généralement utilisées dans la planification et le déploiement du serveur Edge standard qui fournit la Fédération.

  - Pour America Online, le certificat de serveur Edge attribué au service Edge d’accès a une utilisation améliorée de la clé (EKU) par le client.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Fédération XMPP (extensible Messaging and Presence Protocol)

Les versions précédentes de Lync Server et Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP. Dans Microsoft Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité. La fonctionnalité XMPP est installée en deux parties : un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.

Le déploiement et la configuration de XMPP sont abordés dans le déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) vous prévoyez de prendre en charge XMPP dans votre organisation en définissant des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout d’enregistrements DNS. Les rubriques suivantes de cette section résument les informations dont vous aurez besoin pour planifier la Fédération XMPP pour votre déploiement.

<div>


> [!IMPORTANT]
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

<div>


> [!IMPORTANT]
> La Fédération XMPP n’est pas prise en charge pour les utilisateurs hébergés sur les Survivable Branch Appliances. Cela s’applique à la fois aux informations de présence et à l’échange de messages INSTANTANÉs.



</div>

</div>

<div id="sectionSection3" class="section">

Les rubriques suivantes contiennent des conseils pour définir des certificats, des ports de pare-feu et des entrées DNS pour les types de scénarios de Fédération pris en charge.

  - <span></span>  
    [Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gérer la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

