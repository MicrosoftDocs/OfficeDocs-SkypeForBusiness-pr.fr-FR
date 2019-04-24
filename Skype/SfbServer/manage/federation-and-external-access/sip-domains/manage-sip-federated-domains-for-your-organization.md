---
title: Gestion des domaines fédérés SIP pour l’organisation
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment gérer et configurer des domaines SIP que vous pouvez vous fédérer avec,
ms.openlocfilehash: 83623b41e0d9adb1e4539958344214fd2ebe0db9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199832"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gestion des domaines fédérés SIP de votre organisation dans Skype pour Business Server


Pour gérer et configurer des domaines SIP que vous pouvez vous fédérer avec, vous pouvez effectuer des opérations suivantes :

  - Créer ou modifier une liste de domaines autorisés de domaines partenaires fédérés SIP.

  - Créer ou modifier une liste des domaines bloqués de domaines fédérés SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurer la prise en charge pour les domaines externes autorisés dans Skype pour Business Server

Si vous avez configuré la prise en charge pour les partenaires fédérés, vous pouvez gérer les domaines peuvent être fédéré avec votre organisation. Vous configurez un ou plusieurs domaines externes spécifiques en tant que domaines fédérés autorisés. Pour ce faire, ajoutez chaque domaine à la liste des domaines autorisés. Même si la détection des partenaires est activée pour votre organisation, procéder ainsi si le domaine est un partenaire fédéré que pour communiquer avec plus de 1 000 utilisateurs ou devront peut-être envoyer plus de 20 messages par seconde. Si la découverte de partenaire n’est pas activée pour votre organisation, seuls les utilisateurs des domaines externes que vous ajoutez à la liste des domaines autorisés peuvent participer par messagerie instantanée et de conférence avec des utilisateurs dans votre organisation. Si vous souhaitez restreindre l’accès pour un domaine fédéré à un serveur spécifique exécutant le service Edge d’accès du partenaire fédéré, vous pouvez spécifier le nom de domaine du serveur exécutant le service Edge d’accès pour chaque domaine dans la liste des domaines autorisés.

> [!NOTE]  
> Cette procédure explique comment configurer la prise en charge pour des domaines spécifiques, mais l’implémentation de la prise en charge pour les utilisateurs fédérés également nécessite activer la prise en charge pour les utilisateurs fédérés pour votre organisation et de configurer et de contrôle, les utilisateurs peuvent appliquer des stratégies collaborer avec des utilisateurs fédérés. Pour plus d’informations sur l’activation de la prise en charge pour les utilisateurs fédérés, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md). Pour plus d’informations sur la configuration des stratégies de contrôle de fédération, voir [configurer les stratégies de contrôle des accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Pour ajouter un domaine externe à la liste des domaines autorisés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.
2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Domaines fédérés**.
4.  Dans la page **Domaines fédérés** , cliquez sur **Nouveau**, puis cliquez sur **domaine autorisé**.
5.  Dans les **Nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **nom de domaine (ou le nom de domaine complet)**, tapez le nom de domaine du partenaire fédéré.       

        > [!NOTE]  
        > Ce nom doit être unique et ne peut pas déjà exister en tant qu’un domaine autorisé pour ce serveur qui exécute le service Edge d’accès. Le nom ne peut pas dépasser 256 caractères.<BR><br>La recherche sur le nom de domaine du partenaire fédéré effectue une correspondance de suffixe. Par exemple, si vous tapez **contoso.com**, la recherche renverra également domaine **it.contoso.com**.<BR><br>Un domaine de partenaire fédéré simultanément ne peut pas être bloqué et autorisé. Skype pour Business Server les empêche de se produire afin que vous n’avez pas vos listes de synchronisation.
    
      - Si vous souhaitez restreindre l’accès de ce domaine fédéré pour les utilisateurs d’un serveur spécifique exécutant le service Edge d’accès, dans **le service Edge d’accès (FQDN)**, tapez le nom de domaine complet du serveur du domaine fédéré qui exécute le service Edge d’accès.    
      - Si vous souhaitez fournir des informations supplémentaires, dans **commentaire**, tapez les informations que vous souhaitez partager avec d’autres administrateurs système sur cette configuration.

6.  Cliquez sur **Valider**.
7.  Répétez les étapes 4 à 6 pour chaque domaine de partenaire fédéré que vous souhaitez autoriser.

Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge pour l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).

En outre, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez être en mesure de collaborer avec des utilisateurs fédérés. Pour plus d’informations, voir [configurer les stratégies de contrôle des accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurer la prise en charge pour les domaines externes bloqués dans Skype pour Business Server 

Si vous avez configuré la prise en charge pour les partenaires fédérés, vous pouvez gérer les domaines qui seront bloquées de se fédérer avec votre organisation. La liste des domaines bloqués agira comme une liste d’interdiction (liste des entrées explicites qui ne sont ne pas autorisés) et sera appliquée dans la découverte des domaines fédérés, si cette option est activée. Pour plus d’informations, voir [Activer ou désactiver la découverte des partenaires de fédération](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloquer un ou plusieurs domaines externes de se connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Pour ajouter un domaine externe à la liste des domaines bloqués

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.
2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**.
4.  Cliquez sur **Domaines fédérés**, cliquez sur **Nouveau**, puis cliquez sur **domaine bloqué**.
5.  Dans les **Nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **nom de domaine (ou le nom de domaine complet)**, tapez le nom de domaine du partenaire fédéré que vous souhaitez bloquer.

        > [!NOTE]  
        > Le nom ne peut pas dépasser 256 caractères.<BR><br>La recherche sur le nom de domaine du partenaire fédéré effectue une correspondance de suffixe. Par exemple, si vous tapez **contoso.com**, la recherche renverra également domaine **it.contoso.com**.<BR><br>Un domaine de partenaire fédéré simultanément ne peut pas être bloqué et autorisé. Skype pour Business Server les empêche de se produire afin que vous n’avez pas vos listes de synchronisation.
   
      - (Facultatif) Dans la zone **commentaire**, tapez les informations que vous souhaitez partager avec d’autres administrateurs système sur cette configuration.

6.  Cliquez sur **Valider**.
7.  Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.

Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge pour l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).

En outre, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez être en mesure de collaborer avec des utilisateurs fédérés. Pour plus d’informations, voir [configurer les stratégies de contrôle des accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Voir aussi

[Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Activation ou désactivation de la découverte de partenaires de fédération](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

