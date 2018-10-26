---
title: "Lync Server 2013 : Gest. de la conf. du serveur Edge d’accès pour votre org."
TOCTitle: Gestion de la configuration du serveur Edge d’accès pour votre organisation
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ552443(v=OCS.15)
ms:contentKeyID: 49296057
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Cette rubrique fait partie de la documentation préliminaire. Elle est susceptible d’être modifiée au cours des prochaines mises à jour. Les rubriques vides apparaissent sous la forme d’espaces réservés.

Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types de domaine externe ou d’accès (des fournisseurs, des utilisateurs distants et des utilisateurs anonymes) aux conférences via le serveurs Edge qui sera pris en charge pour votre organisation.

Ces options couvrent les types d’accès suivants configurables via la page **Configuration du serveur Edge d’accès**  :

  - **Activer la fédération et la connectivité PIC** Activez cette option si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines de partenaires fédérés. Cette option s’applique à la fédération SIP et à la fédération XMPP configurées globalement, pour un site ou un utilisateur dans la page **Stratégie d’accès externe** . Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.
    
    Il existe deux options facultatives concernant le mode de découverte des partenaires fédérés et l’envoi ou non d’une notification d’exclusion (notification indiquant aux contacts fédérés, avec lesquels vous communiquez, que l’archivage est activé sur votre déploiement et que les détails des communications seront archivés) aux contacts
    
      - **Activer la découverte du domaine partenaire** Sélectionnez cette option pour activer la découverte automatique des domaines auxquels vous pouvez vous fédérer. Lync Server 2013 utilise les enregistrements DNS (Domain Name System) pour découvrir les domaines non répertoriés dans la liste des domaines autorisés, ce qui lui permet d’évaluer automatiquement le trafic entrant provenant des partenaires fédérés et de limiter ou de bloquer ce trafic selon le niveau de confiance, le volume du trafic et les paramètres de l’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs dans les domaines que vous incluez à la liste des domaines autorisés. Que vous sélectionniez ou non cette option, vous pouvez spécifier les domaines à bloquer ou autoriser et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, reportez-vous à [Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** Sélectionnez cette option pour activer l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés afin de leur indiquer que les détails des communications sont enregistrés. Si vous archivez des communications externes avec des domaines de partenaires fédérés, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage pour indiquer aux partenaires que leurs messages et communications sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, reportez-vous à [Définition de la configuration requise pour l’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Activer l’accès des utilisateurs distants** Activez cette option si vous souhaitez que les utilisateurs de votre organisation se trouvant hors de votre pare-feu, tels que des utilisateurs qui travaillent à distance et des utilisateurs se déplaçant beaucoup, puissent se connecter à Lync Server. Pour plus d’informations, reportez-vous à [Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Activer l’accès utilisateur anonyme aux conférences** Activez cette option si vous souhaitez que les utilisateurs internes puissent inviter des utilisateurs anonymes externes aux conférences qu’ils organisent. Si vous activez cette option, seuls les utilisateurs anonymes seront autorisés à accéder aux conférences. Pour configurer les modalités de conférence et les options qui définiront les possibilités offertes aux utilisateurs concernant les conférences et l’inclusion des utilisateurs anonymes, reportez-vous à [Créer ou modifier l’expérience utilisateur de conférence pour un site ou un groupe d’utilisateurs](https://technet.microsoft.com/fr-fr/library/gg429715\(v=ocs.15\)) et [Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous pouvez également configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs distants dans votre organisation avant que tout autre type d’accès externe soit disponible aux utilisateurs. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, reportez-vous à <a href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Gestion de la stratégie d’accès externe dans Lync Server 2013</a>.

**Affichage des informations de configuration du serveur Edge d’accès à l’aide des Windows PowerShell commandes d’applet**

  - Il est possible d’afficher ces informations via Windows PowerShell et la commande d’applet **Get-CsAccessEdgeConfiguration**. Elle peut être exécutée à partir du Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Pour consulter les informations sur tous les paramètres de configuration du serveur Edge d’accès, tapez la commande suivante dans Lync Server Management Shell puis appuyez sur Entrée :
    
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

## Dans cette section

  - [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

