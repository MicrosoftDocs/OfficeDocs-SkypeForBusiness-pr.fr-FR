---
title: Gestion de la configuration du serveur Edge d’accès pour votre organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer le type d’accès du fournisseur ou du domaine externe, l’accès des utilisateurs distants et l’accès anonyme aux conférences par le biais des serveurs Edge qui sont pris en charge pour votre organisation.
ms.openlocfilehash: 7308d6914f3f6d79cd217a31c0246c6f2d189516
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818345"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestion de la configuration du serveur Edge d’accès pour votre organisation

Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer le type d’accès du fournisseur ou du domaine externe, l’accès des utilisateurs distants et l’accès anonyme aux conférences par le biais des serveurs Edge qui sont pris en charge pour votre organisation.

Ces options incluent les types d’accès suivants qui peuvent être configurés par le biais de la page **configuration de Microsoft Edge** :

  - **Activer la connectivité**   de Fédération et de messagerie instantanée publique activez cette opération si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés. Ce paramètre s’applique aux fédérations SIP configurées pour les étendues globales, de sites ou d’utilisateurs sur la page de **stratégie d’accès externe** . Pour que les paramètres de Fédération s’appliquent, vous devez configurer la prise en charge de la Fédération sur les deux pages.
    
    Il existe deux options qui sont des paramètres facultatifs pour la façon dont les partenaires fédérés sont détectés, et si les exclusions de responsabilité en matière d’archivage (notification à des contacts fédérés avec lesquels vous communiquez avec votre déploiement est activée et que les communications les détails seront archivés) seront envoyés aux contacts :
    
      - **Activer la découverte**   de domaine partenaire la sélection de cette option permet la découverte automatique des domaines avec lesquels vous pouvez être fédérer. Skype entreprise Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant des partenaires fédérés détectés et en limitant ou en bloquant ce trafic en fonction de l’approbation. le niveau, le volume et les paramètres d’administration. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs des domaines que vous incluez dans la liste des domaines autorisés. Si vous sélectionnez cette option, vous pouvez spécifier que les domaines individuels doivent être bloqués ou autorisés, y compris limiter l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, voir [configurer la prise en charge des domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Envoyer un message d’exclusion d’archivage aux partenaires**   fédérés cette option permet d’envoyer un message d’exclusion d’archivage aux partenaires fédérés qui les recommandent que les détails des communications sont enregistrés. Si vous archivez des communications externes avec des domaines partenaires fédérés, vous devez activer la notification d’exclusion de responsabilité pour signaler aux partenaires que leurs messages et leurs coordonnées sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, voir [activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage au partenaire fédéré](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Activer l’accès**   des utilisateurs distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu (par exemple, des télétravailleurs et des utilisateurs qui voyagent) puissent se connecter à Skype entreprise Server. Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).

  - **Permettre aux utilisateurs anonymes d’accéder aux conférences**   activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs externes anonymes à des conférences qu’ils organisent. L’activation de ce paramètre n’autorise que les utilisateurs anonymes pour les conférences.

> [!NOTE]  
> Outre l’activation de la prise en charge de l’accès des utilisateurs externes, vous configurez également des stratégies pour contrôler l’utilisation des utilisateurs distants au sein de votre organisation avant d’avoir accès aux utilisateurs externes. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès utilisateur externe, voir gérer les stratégies [d’accès externe pour votre organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Affichage des informations de configuration de bord d’accès à l’aide des cmdlets Windows PowerShell**

  - Les informations de configuration de Microsoft Edge peuvent être consultées à l’aide de Windows PowerShell et de l’applet **de passe Get-CsAccessEdgeConfiguration** . Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 
    
    Pour afficher des informations sur l’ensemble des paramètres de configuration de Edge Access, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
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

