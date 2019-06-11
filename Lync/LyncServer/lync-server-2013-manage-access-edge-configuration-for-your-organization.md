---
title: 'Lync Server 2013 : Gestion de la configuration du serveur Edge d’accès pour votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05d2bcca7836bd451b2535fb02c350facd7fc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Il s’agit d’une documentation préliminaire susceptible d’être modifiée. Des rubriques vides sont incluses sous forme d’espaces réservés.

Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer le type d’accès du fournisseur ou du domaine externe, l’accès des utilisateurs distants et l’accès anonyme aux conférences par le biais des serveurs Edge qui sont pris en charge pour votre organisation.

Ces options incluent les types d’accès suivants qui peuvent être configurés par le biais de la page **configuration de Microsoft Edge** :

  - **Activer la connectivité**   de Fédération et de messagerie instantanée publique activez cette opération si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés. Ce paramètre s’applique aussi bien aux fédérations SIP et XMPP qu’aux fédérations qui sont configurées pour les étendues de site ou d’utilisateur globales sur la page de **stratégie d’accès externe** . Pour que les paramètres de Fédération s’appliquent, vous devez configurer la prise en charge de la Fédération sur les deux pages.
    
    Il existe deux options qui sont des paramètres facultatifs pour la façon dont les partenaires fédérés sont détectés, et si les exclusions de responsabilité en matière d’archivage (notification à des contacts fédérés avec lesquels vous communiquez avec votre déploiement est activée et que les communications les détails seront archivés) seront envoyés aux contacts
    
      - **Activer la découverte**   de domaine partenaire la sélection de cette option permet la découverte automatique des domaines avec lesquels vous pouvez être fédérer. Lync Server 2013 utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés identifiés et en limitant ou en bloquant ce trafic en fonction du niveau de confiance. le volume et les paramètres d’administration. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs des domaines que vous incluez dans la liste des domaines autorisés. Si vous sélectionnez cette option, vous pouvez spécifier que les domaines individuels doivent être bloqués ou autorisés, y compris limiter l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Envoyer un message d’exclusion d’archivage aux partenaires**   fédérés cette option permet d’envoyer un message d’exclusion d’archivage aux partenaires fédérés qui les recommandent que les détails des communications sont enregistrés. Si vous archivez des communications externes avec des domaines partenaires fédérés, vous devez activer la notification d’exclusion de responsabilité pour signaler aux partenaires que leurs messages et leurs coordonnées sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, voir [définir vos exigences d’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Activer l’accès**   des utilisateurs distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu (par exemple, des télétravailleurs et des utilisateurs qui voyagent) puissent se connecter à Lync Server. Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Permettre aux utilisateurs anonymes d’accéder aux conférences**   activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs externes anonymes à des conférences qu’ils organisent. L’activation de ce paramètre n’autorise que les utilisateurs anonymes pour les conférences. Pour configurer l’utilisation des conférences et les options qui déterminent la façon dont les utilisateurs peuvent faire des conférences et l’inclusion d’utilisateurs anonymes, voir les détails de la rubrique [créer ou modifier l’interface utilisateur des conférences pour un site ou des utilisateurs](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) et [ Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Outre l’activation de la prise en charge de l’accès des utilisateurs externes, vous configurez également des stratégies pour contrôler l’utilisation des utilisateurs distants au sein de votre organisation avant d’avoir accès aux utilisateurs externes. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès utilisateur externe, voir <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gérer une stratégie d’accès externe dans Lync Server 2013</A>.



</div>

**Affichage des informations de configuration de bord d’accès à l’aide des cmdlets Windows PowerShell**

  - Les informations de configuration de Microsoft Edge peuvent être consultées à l’aide de Windows PowerShell et de l’applet **de passe Get-CsAccessEdgeConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».
    
    Pour afficher des informations sur l’ensemble des paramètres de configuration de Microsoft Edge, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsAccessEdgeConfiguration
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

