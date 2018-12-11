---
title: Gestion de la configuration du serveur Edge d’accès pour votre organisation
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir déployé un ou plusieurs serveurs de périphérie, vous devez activer les types de domaine externe ou fournisseur l’accès, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs de périphérie qui sera prise en charge pour votre organisation.
ms.openlocfilehash: 40fdbd6e728276897e4901c849dc0e2284635ecf
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222918"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestion de la configuration du serveur Edge d’accès pour votre organisation

Après avoir déployé un ou plusieurs serveurs de périphérie, vous devez activer les types de domaine externe ou fournisseur l’accès, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs de périphérie qui sera prise en charge pour votre organisation.

Ces options comprennent les types d’accès qui peuvent être configurés par le biais de la page **Configuration du serveur Edge d’accès** suivants :

  - **Activer la fédération et la connectivité PIC**   activez-le si vous souhaitez prendre en charge de l’accès des utilisateurs aux domaines de partenaire fédéré. Ce paramètre s’applique aux SIP fédération configurée pour globale, site ou utilisateur étendues dans la page **Stratégie d’accès externe** . Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.
    
    Il existe deux options qui sont des paramètres facultatifs pour les partenaires fédérés sont découverts et si l’archivage des notifications d’exclusion (notification par les contacts fédérés avec lesquelles vous communiquez que votre déploiement a l’archivage activé et que les communications plus d’informations seront archivées) sont envoyés à des contacts :
    
      - **Activer la découverte du domaine partenaire**   cette option permet la découverte automatique des domaines que vous pouvez vous fédérer avec. Skype pour Business Server utilise les enregistrements de nom de domaine DNS (Domain Name System) pour tenter de découvrir les domaines non répertoriés dans la liste des domaines autorisés, évaluer le trafic entrant provenant des partenaires fédérés découverts automatiquement et limitant ou bloquer ce trafic en fonction de gestion de la confidentialité niveau, la quantité de trafic et les paramètres de l’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activée uniquement pour les utilisateurs dans les domaines que vous incluez dans la liste des domaines autorisés. Si vous sélectionnez cette option, vous pouvez spécifier cette personne domaines à être bloquée ou autorisée, y compris la restriction de l’accès à un serveur spécifique exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, voir [Configure prise en charge pour les domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Envoyer la notification d’exclusion d’archivage aux partenaires fédérés**   cette option permet l’envoi d’un message de notification d’exclusion d’archivage aux partenaires fédérés leur indiquant que les détails de communication sont enregistrés. Si vous archivez les communications externes avec les domaines de partenaire fédéré, vous devez activer la notification d’exclusion relative d’archivage prévenir vos partenaires que leurs détails communications et les messages sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, voir [Activer ou désactiver l’envoi d’une notification d’exclusion d’archivage partenaire fédéré](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Activer l’accès des utilisateurs distants**   activer cette option si vous souhaitez que les utilisateurs situés en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, pour être en mesure de se connecter à Skype pour Business Server dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).

  - **Permettre aux utilisateurs anonymes d’accéder aux conférences**   activer cette option si vous souhaitez que les utilisateurs internes d’inviter des utilisateurs anonymes externes aux conférences qu’ils organisent. L’activation de ce paramètre permet uniquement aux utilisateurs anonymes pour les conférences.

> [!NOTE]  
> Outre l’activation de l’accès des utilisateurs externes prennent en charge, vous également configurez des stratégies de contrôle de l’utilisation de l’accès des utilisateurs distants de votre organisation avant de n’importe quel type d’accès des utilisateurs externes est accessible aux utilisateurs. Pour plus d’informations sur la création, la configuration et l’application des stratégies pour l’accès des utilisateurs externes, voir [Gérer la stratégie de l’accès externe pour votre organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Affichage des informations de configuration de serveur Edge d’accès à l’aide des applets de commande Windows PowerShell**

  - Accéder aux informations de configuration Edge peuvent être affichés à l’aide de Windows PowerShell et l’applet de commande **Get-CsAccessEdgeConfiguration** . Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 
    
    Pour afficher des informations sur tous vos paramètres de configuration de serveur Edge d’accès, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
     `Get-CsAccessEdgeConfiguration`
    
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

