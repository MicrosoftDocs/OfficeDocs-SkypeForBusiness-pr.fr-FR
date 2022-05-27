---
title: Gestion de la configuration du serveur Microsoft Edge d’accès pour votre organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès au domaine ou au fournisseur externe, l’accès utilisateur à distance et l’accès utilisateur anonyme aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674596"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestion de la configuration du serveur Microsoft Edge d’accès pour votre organisation

Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès au domaine ou au fournisseur externe, l’accès utilisateur à distance et l’accès utilisateur anonyme aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.

Ces options couvrent les types d’accès suivants configurables via la page **Configuration du serveur Edge d’accès** :

  - **Activer la fédération et la connectivité de messagerie instantanée publique**   Activez cette option si vous souhaitez prendre en charge l’accès utilisateur aux domaines de partenaires fédérés. Ce paramètre s’applique à la fédération SIP configurée pour les étendues globales, de site ou d’utilisateur sur la page **Stratégie d’accès externe** . Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.
    
    Il existe deux options qui sont des paramètres facultatifs pour la façon dont les partenaires fédérés sont découverts, et si l’archivage des exclusions de responsabilité (notification aux contacts fédérés avec lesquels vous communiquez avec lequel l’archivage de votre déploiement est activé et que les détails des communications seront archivés) sera envoyé aux contacts :
    
      - **Activer la découverte de domaine de partenaire**   La sélection de cette option permet la découverte automatique des domaines avec lequel vous pouvez fédérer. Skype Entreprise Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines non répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés découverts et en limitant ou en bloquant ce trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés. Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, consultez [Configurer la prise en charge des domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).
    
      - **Envoyer une exclusion de responsabilité d’archivage à des partenaires fédérés**   La sélection de cette option permet d’envoyer un message d’exclusion de responsabilité d’archivage aux partenaires fédérés qui leur indiquent que les détails des communications sont enregistrés. Si vous archivez des communications externes avec des domaines de partenaires fédérés, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage pour indiquer aux partenaires que leurs messages et communications sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, consultez [Activer ou désactiver l’envoi d’une exclusion de responsabilité d’archivage au partenaire fédéré](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

  - **Activer l’accès utilisateur distant**   Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs en déplacement, puissent se connecter à Skype Entreprise Server. Pour plus d’informations, consultez [Activer ou désactiver l’accès utilisateur distant](enable-or-disable-remote-user-access.md).

  - **Permettre aux utilisateurs anonymes d’accéder aux conférences**   Activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs anonymes externes aux conférences qu’ils organisent. Si vous activez cette option, seuls les utilisateurs anonymes seront autorisés à accéder aux conférences.

> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous pouvez également configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs distants dans votre organisation avant que tout autre type d’accès externe ne soit disponible aux utilisateurs. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, consultez [Gérer la stratégie d’accès externe pour votre organisation](../external-access-policies/manage-external-access-policy-for-your-organization.md).

**Affichage des informations de configuration Access Edge à l’aide d’applets de commande Windows PowerShell**

  - Les informations de configuration Access Edge peuvent être affichées à l’aide de Windows PowerShell et de l’applet de commande **Get-CsAccessEdgeConfiguration**. Cette applet de commande peut être exécutée à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 
    
    Pour afficher des informations sur tous vos paramètres de configuration Access Edge, tapez la commande suivante dans le Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
     `Get-CsAccessEdgeConfiguration`
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
    Identité : global<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery : False<br/>
    EnableArchivingDisclaimer : False<br/>
    EnableUserReplicator : True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner : 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored : 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage : 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

