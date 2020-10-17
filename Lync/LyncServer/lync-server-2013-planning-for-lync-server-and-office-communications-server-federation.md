---
title: Planification de la Fédération de Lync Server et Office Communications Server
description: Planification de la Fédération entre Lync Server et Office Communications Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d7385b8fde27446fb0648802544a8840a0f6276
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552370"
---
# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planification de la Fédération entre Lync Server 2013 et Office Communications Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-13_

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
        > Si vous prenez en charge les clients mobiles Microsoft Lync sur Windows Phone ou Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notification par transmission ou de notification, vous devez planifier _sipfederationtls. _ TCP. &lt;&gt;Enregistrements SRV de domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync. Android et Nokia Symbian Lync mobile n’utilisent pas la notification de transmission et ne sont pas soumis à cette exigence.

        
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

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

