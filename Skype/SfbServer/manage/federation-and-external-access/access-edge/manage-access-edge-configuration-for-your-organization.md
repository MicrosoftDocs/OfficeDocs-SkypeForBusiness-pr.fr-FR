---
title: Gestion de la configuration du serveur Microsoft Edge d’accès pour votre organisation
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès de domaine ou de fournisseur externe, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.
ms.openlocfilehash: ff152ea25bbea750815e0619ce521ede8d8d7203
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860091"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Gestion de la configuration du serveur Microsoft Edge d’accès pour votre organisation

Après avoir déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès de domaine ou de fournisseur externe, l’accès des utilisateurs distants et l’accès des utilisateurs anonymes aux conférences via les serveurs Edge qui seront pris en charge pour votre organisation.

Ces options couvrent les types d’accès suivants configurables via la page **Configuration du serveur Edge d’accès** :

  - **Activer la fédération et la connectivité DE MESSAGERIE INSTANTANÉE publique**   Activez-le si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines des partenaires fédérés. Ce paramètre s’applique à la fédération SIP configurée pour les étendues globale, de site ou utilisateur dans la page Stratégie **d’accès** externe. Pour appliquer les paramètres de fédération, vous devez configurer la prise en charge de la fédération sur les deux pages.
    
    Il existe deux options qui sont facultatives pour la façon dont les partenaires fédérés sont découverts et si les notifications d’exclusion de responsabilité d’archivage (notification aux contacts fédérés avec qui vous communiquez que l’archivage est activé dans votre déploiement et que les détails des communications seront archivés) seront envoyés aux contacts :
    
      - **Activer la découverte de domaine partenaire**   La sélection de cette option permet la découverte automatique des domaines avec qui vous pouvez vous fédérer. Skype Entreprise Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines non répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés découverts et en limitant ou bloquant ce trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés. Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations, voir [Configurer la prise en charge des domaines externes autorisés.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)
    
      - **Envoyer une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés**   La sélection de cette option permet l’envoi d’un message de clause d’exclusion de responsabilité d’archivage aux partenaires fédérés qui les informe que les détails des communications sont enregistrés. Si vous archivez des communications externes avec des domaines de partenaires fédérés, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage pour indiquer aux partenaires que leurs messages et communications sont archivés par votre déploiement. Pour plus d’informations sur l’archivage, voir Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité [d’archivage au partenaire fédéré.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **Activer l’accès des utilisateurs distants**   Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui sont en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs en déplacement, puissent se connecter à Skype Entreprise Server. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants.](enable-or-disable-remote-user-access.md)

  - **Permettre aux utilisateurs anonymes d’accéder aux conférences**   Activez cette option si vous souhaitez que les utilisateurs internes invitent des utilisateurs anonymes externes aux conférences qu’ils organisent. Si vous activez cette option, seuls les utilisateurs anonymes seront autorisés à accéder aux conférences.

> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous pouvez également configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs distants dans votre organisation avant que tout autre type d’accès externe ne soit disponible aux utilisateurs. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir Gérer la stratégie d’accès [externe pour votre organisation.](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**Affichage des informations de configuration du edge d’accès Windows PowerShell cmdlets**

  - Les informations de configuration du edge d’accès peuvent être vues à l’aide de Windows PowerShell et de l’cmdlet **Get-CsAccessEdgeConfiguration.** Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 
    
    Pour afficher des informations sur tous vos paramètres de configuration du service Edge d’accès, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
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

