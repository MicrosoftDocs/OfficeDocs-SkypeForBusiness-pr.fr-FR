---
title: Planification pour les conversations SIP, XMPP et la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planification de la Fédération SIP, de XMPP et de la messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-28_

Les serveurs Edge peuvent être configurés pour autoriser vos utilisateurs internes et externes à accéder à des contacts au niveau des organisations ou services partenaires. Les fédérations, au fur et à mesure qu’elles sont connues, peuvent fournir tout ou partie des éléments suivants aux contacts de votre organisation dans le cadre de la Fédération de partenaire ou des contacts de la Fédération du partenaire au vôtre:

  - Messagerie instantanée et présence

  - Collaboration et conférences, par exemple: conférences Web

  - Audioconférence, visioconférence ou les deux

Dans certains cas, la communication, par exemple, la messagerie instantanée et la présence d’un contact Microsoft Lync Server 2013 et d’un protocole de messagerie extensible (XMPP), est pair à pair uniquement: vous ne pouvez prendre en charge que vous et le contact fédéré. partenaire. Dans d’autres cas, comme un serveur Lync, Lync Server 2010 vers Lync Server 2013 Federation, plusieurs participants peuvent être invités à rejoindre la conversation.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Fédération Lync Server et Office Communications Server

La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications d’égal à égal et à plusieurs parties. Les conversations d’égal à égal peuvent être transmises à des conversations à plusieurs participants, ce qui permet de participer à des réunions ad hoc. Réunions (conférences Web ou conférences audiovisuelles) il est possible d’inclure les contacts au sein de votre organisation ainsi que les contacts des partenaires avec lesquels vous vous fédérer.

La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération unique. La Fédération directe nécessite que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération ainsi que le nom de domaine complet (FQDN) du serveur Edge du partenaire. Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, tous les enregistrements SRV du système de noms de domaine (DNS) requis pour la publication du serveur Edge. La terminologie de cette version était la suivante:

  - *Ouvrir la Fédération avancée*: accepter un nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge du partenaire

  - *Fédération améliorée*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour trouver le serveur Edge du partenaire.

  - *Fédération directe*: configuration du nom de domaine SIP du partenaire et du nom de domaine complet (FQDN) du serveur Edge du partenaire

  - *Liste verte du serveur*: accepter les domaines, utiliser DNS SRV pour trouver le serveur de périphérie d’un fournisseur d’hébergement ou un fournisseur de connectivité de messagerie instantanée publique

Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération pour mieux définir ce que chaque type de Fédération a réellement accompli:

  - Ouvrir la Fédération avancée a été connu sous le nom de *domaine partenaire détecté*

  - La Fédération améliorée a été connue sous le nom de *domaine partenaire autorisé*

  - La Fédération directe s’est appelée *serveur partenaire autorisé*

  - La liste verte du serveur est devenue désignée comme *fournisseur d’hébergement* et *fournisseur de messagerie instantanée publique*

Microsoft Lync Server 2010 a introduit une définition plus restreinte du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et Microsoft Office 365, et il a également été soumis à la même liste autorisée définie par le type de Fédération de domaine autorisé.

L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server fait appel aux serveurs Edge et aux proxys inverses pour appliquer les règles et domaines de partenaires autorisés que vous définissez. Du point de vue de la planification, la Fédération avec un autre serveur Lync Server et Office Communications Server nécessite les éléments suivants:

  - Activez la Fédération dans le générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique déploiement Configuration de la Fédération [SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Déterminez la configuration requise pour la découverte de domaines fédérés:
    
      - <span></span>  
        Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge du partenaire et du nom de domaine ou du nom de domaine en ligne, qui est entré dans le panneau de configuration de Lync Server, la **Fédération et l’accès externe**, **SIP Domaines fédérés**. Créez une **** stratégie ou **Modifiez** une stratégie existante pour autoriser ou bloquer des domaines en utilisant un nom de domaine complet.
        
        <div>
        

        > [!WARNING]
        > La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible de ne pas pouvoir échouer en cas de changement d’adresse IP de son serveur Edge par le partenaire.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez indiquer le <STRONG>nom de domaine (ou le nom de domaine complet (FQDN)</STRONG> de Microsoft Lync Online, Microsoft Office 365. Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Pour la Fédération de partenaires découverte, où les partenaires peuvent découvrir votre serveur Edge, vous devez créer un enregistrement SRV dans \_votre DNS externe-sipfederationtls. \_TCP.contoso.com: qui pointe vers le port 5061 et l’hôte (A) du serveur de périphérie
        
        <div>
        

        > [!IMPORTANT]
        > Si vous prenez en charge des clients mobiles Microsoft Lync sur un appareil Windows Phone ou un Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notifications de transmission ou le service de notifications d’émission, vous devez planifier _sipfederationtls. _ TCP. &lt;Enregistrements SRV&gt; du domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync. Android et Nokia Symbian Lync mobile n’utilisent pas de notifications de transmission et ne sont pas soumis à cette obligation.

        
        </div>

  - Configurer des stratégies d’accès des utilisateurs externes pour prendre en charge des domaines fédérés

  - Ouvrez les ports de pare-feu pour le protocole SIP (Session Initiation Protocol), la conférence Web et l’audio/visuel pour accepter la ou les personnes que vous activez. Pour plus d’informations, reportez-vous à: [identification des exigences de port et de pare-feu externes pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Les informations suivantes vous permettront de définir le certificat, le port/protocole et les exigences DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.

La planification des certificats, de la configuration requise pour le pare-feu et du port/protocole et des exigences DNS est généralement un processus direct de transfert si vous avez planifié ou déployé vos serveurs Microsoft Lync Server 2013 Edge. Dans la mesure où la Fédération est une fonctionnalité supplémentaire qui utilise le serveur de périphérie existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement de serveur Edge. Vous devez utiliser les tableaux suivants pour vérifier que vos exigences sont remplies et apporter des modifications au port/protocole et au DNS en conséquence.

<div>


> [!IMPORTANT]
> Si vous avez un pool de serveurs Edge et que vous effectuez une Fédération avec Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou les équilibreurs de charge matérielle sur les côtés internes et externes des serveurs de périphérie. Si vous vous fédérationz avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de charge matérielle fournira une prise en charge du basculement en cas de serveur Edge. Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de charge DNS. Les serveurs Edge du partenaire établiront une communication avec le premier serveur Edge de votre pool qui répond. Si ce serveur Edge tombe en panne, la communication ne bascule pas automatiquement.



</div>

Les exigences en matière de certificats sont généralement satisfaites par le cadre de la planification de certificats pour le serveur Edge ou le plan de serveur Edge sélectionné.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Connectivité de messagerie instantanée publique

La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants:

  - Contacts Messenger

  - Yahoo!\! contacts

  - Contacts AOL (America Online)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>À compter du 1er septembre 2012, la licence de l’abonnement à l’utilisateur de la connectivité PIC (Public IM Connectivity) de Microsoft Lync n’est plus disponible pour l’achat de contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service (la date exacte doit toujours être décidée, mais pas avant le 2013 juin).</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par utilisateur et par mois requise pour la Fédération de Lync Server ou d’Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, qui n’est pas renouvelé.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste, ce qui permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes par messagerie instantanée et vocale.</P></LI></UL>



</div>

Cette classe de Fédération exige les considérations en matière de planification suivantes:

  - Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio et vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée. Vos serveurs Edge doivent répondre à des exigences de port et de protocole spécifiques. Pour plus d’informations, reportez-vous à [la rubrique déterminer la configuration requise 2013 pour le pare-feu A](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - Le service de messagerie instantanée Yahoo n’est soumis à aucune configuration unique, autre que celles généralement utilisées dans le cadre de la planification et du déploiement du serveur de périphérie standard qui fournit la Fédération.

  - America Online nécessite que votre certificat de serveur Edge attribué au service Edge d’accès possède une utilisation améliorée de la clé par le client.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Fédération des protocoles de messagerie extensible et de présence

Les versions précédentes de Lync Server et d’Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP. Dans Microsoft Lync Server 2013, la fonctionnalité XMPP peut être déployée en tant que fonctionnalité. La fonctionnalité XMPP est installée en deux parties: un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.

Le déploiement et la configuration de XMPP sont abordés dans le déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) que vous envisagez de prendre en charge XMPP au sein de votre organisation en définissant des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout de DNS registres. Les rubriques suivantes de cette section résument les informations dont vous avez besoin pour planifier la Fédération XMPP pour votre déploiement.

<div>


> [!IMPORTANT]
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

<div>


> [!IMPORTANT]
> La Fédération XMPP n’est pas prise en charge pour les utilisateurs hébergés sur des appareils de succursales survivables. Cela s’applique aussi bien aux informations de présence qu’à l’échange de messages INSTANTANÉs.



</div>

</div>

<div id="sectionSection3" class="section">

Les rubriques suivantes contiennent des recommandations pour la définition de certificats, de ports de pare-feu et d’entrées DNS pour les types de scénarios de Fédération pris en charge.

  - <span></span>  
    [Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Résumé de port-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Résumé DNS-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

