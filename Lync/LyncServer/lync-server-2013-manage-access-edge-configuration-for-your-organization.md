---
title: 'Lync Server 2013 : gestion de la configuration du serveur Edge d’accès pour votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c62e5b03057f09d7489a413456e432e8e08799b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534547"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Gérer la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Cette documentation est préliminaire et sujette à modification. Des rubriques vides sont incluses comme espaces réservés.

Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès au domaine externe ou au fournisseur, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.

Ces options couvrent les types d’accès suivants configurables via la page **Configuration du serveur Edge d’accès** :

  - **Activer la Fédération et la connectivité PIC**     Activez-le si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés. Cette option s’applique à la fédération SIP et à la fédération XMPP configurées globalement, pour un site ou un utilisateur dans la page **Stratégie d’accès externe**. Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.
    
    Il existe deux options facultatives concernant le mode de découverte des partenaires fédérés et l’envoi ou non d’une notification d’exclusion (notification indiquant aux contacts fédérés, avec lesquels vous communiquez, que l’archivage est activé sur votre déploiement et que les détails des communications seront archivés) aux contacts
    
      - **Activer la découverte**     du domaine partenaire La sélection de cette option active la découverte automatique des domaines avec lesquels vous pouvez fédérer. Lync Server 2013 utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant en provenance des partenaires fédérés découverts et en limitant ou bloquant le trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés. Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, reportez-vous à la rubrique [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Envoyer la clause d’exclusion de responsabilité d’archivage aux partenaires fédérés**     La sélection de cette option permet d’envoyer un message de notification d’exclusion d’archivage aux partenaires fédérés qui les avertit que les communications sont enregistrées. Si vous archivez des communications externes avec des domaines de partenaires fédérés, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage pour indiquer aux partenaires que leurs messages et communications sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, reportez-vous à [la rubrique définition de la configuration requise pour l’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Activer l’accès**     des utilisateurs distants Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, puissent se connecter à Lync Server. Pour plus d’informations, consultez la rubrique [activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Autoriser les utilisateurs anonymes à accéder aux conférences**     Activez cette option si vous souhaitez que les utilisateurs internes invitent les utilisateurs anonymes externes à des conférences qu’ils organisent. Si vous activez cette option, seuls les utilisateurs anonymes seront autorisés à accéder aux conférences. Pour configurer l’expérience de conférence et les options qui définissent comment et ce que vos utilisateurs peuvent faire avec des conférences et pour l’inclusion des utilisateurs anonymes, consultez les détails de la rubrique [créer ou modifier l’expérience utilisateur de conférence pour un site ou des utilisateurs](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) et des [paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous pouvez également configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs distants dans votre organisation avant que tout autre type d’accès externe ne soit disponible aux utilisateurs. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestion de la stratégie d’accès externe dans Lync Server 2013</A>.



</div>

**Affichage des informations de configuration du serveur Edge d’accès à l’aide des applets de commande Windows PowerShell**

  - Les informations de configuration du serveur Edge d’accès peuvent être affichées à l’aide de Windows PowerShell et de la cmdlet **Get-CsAccessEdgeConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Pour afficher des informations sur tous les paramètres de configuration du serveur Edge d’accès, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsAccessEdgeConfiguration
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
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

  - [Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Activer ou désactiver l’accès des utilisateurs anonymes dans Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

