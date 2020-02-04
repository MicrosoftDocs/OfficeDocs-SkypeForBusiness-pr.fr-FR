---
title: Planification de Lync Server et de la Fédération du serveur Office Communications Server
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
ms.openlocfilehash: 015f824ff2b8510559a7bd4910be76321d44d242
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planification de Lync Server 2013 et de la Fédération Office Communications Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-13_

La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications d’égal à égal et à plusieurs parties. Les conversations d’égal à égal peuvent être transmises à des conversations à plusieurs participants, ce qui permet de participer à des réunions ad hoc. Réunions (conférences Web ou conférences audiovisuelles) il est possible d’inclure les contacts au sein de votre organisation ainsi que les contacts des partenaires avec lesquels vous vous fédérer.

La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération unique. La Fédération directe nécessite que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération ainsi que le nom de domaine complet (FQDN) du serveur Edge du partenaire. Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, tous les enregistrements SRV du système de noms de domaine (DNS) requis pour la publication du serveur Edge. La terminologie de cette version était la suivante :

  - *Ouvrir la Fédération avancée*: accepter un nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge du partenaire

  - *Fédération améliorée*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour trouver le serveur Edge du partenaire.

  - *Fédération directe*: configuration du nom de domaine SIP du partenaire et du nom de domaine complet (FQDN) du serveur Edge du partenaire

  - *Liste verte du serveur*: accepter les domaines, utiliser DNS SRV pour trouver le serveur de périphérie d’un fournisseur d’hébergement ou un fournisseur de connectivité de messagerie instantanée publique

Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération pour mieux définir ce que chaque type de Fédération a réellement accompli :

  - Ouvrir la Fédération avancée a été connu sous le nom de *domaine partenaire détecté*

  - La Fédération améliorée a été connue sous le nom de *domaine partenaire autorisé*

  - La Fédération directe s’est appelée *serveur partenaire autorisé*

  - La liste verte du serveur est devenue désignée comme *fournisseur d’hébergement* et *fournisseur de messagerie instantanée publique*

Microsoft Lync Server 2010 a introduit une définition plus restreinte du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et Microsoft Office 365, et il a également été soumis à la même liste autorisée définie par le type de Fédération de domaine autorisé.

L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server fait appel aux serveurs Edge et aux proxys inverses pour appliquer les règles et domaines de partenaires autorisés que vous définissez. Du point de vue de la planification, la Fédération avec un autre serveur Lync Server et Office Communications Server nécessite les éléments suivants :

  - Activez la Fédération dans le générateur de topologie. Pour plus d’informations, reportez-vous à la rubrique déploiement Configuration de la Fédération [SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Déterminez la configuration requise pour la découverte de domaines fédérés :
    
      - <span></span>  
        Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge du partenaire et du nom de domaine ou du nom de domaine en ligne, qui est entré dans le panneau de configuration de Lync Server, la **Fédération et l’accès externe**, les **domaines fédérés SIP**. Créez une stratégie ou **Modifiez** une stratégie existante pour autoriser ou bloquer des domaines en **utilisant un nom** de domaine complet.
        
        <div>
        

        > [!WARNING]
        > La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible de ne pas pouvoir échouer en cas de changement d’adresse IP de son serveur Edge par le partenaire.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez indiquer le <STRONG>nom de domaine (ou le nom de domaine complet (FQDN)</STRONG> de Microsoft Lync Online, Microsoft Office 365. Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Pour la Fédération de partenaires découverte, où les partenaires peuvent découvrir votre serveur Edge, vous devez créer un enregistrement SRV dans \_votre DNS externe-sipfederationtls. \_TCP.contoso.com : qui pointe vers le port 5061 et l’hôte (A) du serveur de périphérie
        
        <div>
        

        > [!IMPORTANT]
        > Si vous prenez en charge des clients mobiles Microsoft Lync sur un appareil Windows Phone ou un Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notifications de transmission ou le service de notifications de transmission, vous devez planifier _sipfederationtls. _tcp. &lt;Enregistrements SRV&gt; du domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync. Android et Nokia Symbian Lync mobile n’utilisent pas de notifications de transmission et ne sont pas soumis à cette obligation.

        
        </div>

  - Configurer des stratégies d’accès des utilisateurs externes pour prendre en charge des domaines fédérés

  - Ouvrez les ports de pare-feu pour le protocole SIP (Session Initiation Protocol), la conférence Web et l’audio/visuel pour accepter la ou les personnes que vous activez. Pour plus d’informations, reportez-vous à : [identification des exigences de port et de pare-feu externes pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Les informations suivantes vous permettront de définir le certificat, le port/protocole et les exigences DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.

La planification des certificats, de la configuration requise pour le pare-feu et du port/protocole et des exigences DNS est généralement un processus direct de transfert si vous avez planifié ou déployé vos serveurs Microsoft Lync Server 2013 Edge. Dans la mesure où la Fédération est une fonctionnalité supplémentaire qui utilise le serveur de périphérie existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement de serveur Edge. Vous devez utiliser les tableaux suivants pour vérifier que vos exigences sont remplies et apporter des modifications au port/protocole et au DNS en conséquence.

<div>


> [!IMPORTANT]
> Si vous avez un pool de serveurs Edge et que vous effectuez une Fédération avec Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou les équilibreurs de charge matérielle sur les côtés internes et externes des serveurs de périphérie. Si vous vous fédérationz avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de charge matérielle fournira une prise en charge du basculement en cas de serveur Edge. Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de charge DNS. Les serveurs Edge du partenaire établiront une communication avec le premier serveur Edge de votre pool qui répond. Si ce serveur Edge tombe en panne, la communication ne bascule pas automatiquement.



</div>

Les exigences en matière de certificats sont généralement satisfaites par le cadre de la planification de certificats pour le serveur Edge ou le plan de serveur Edge sélectionné.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Résumé de port-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Résumé DNS-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

