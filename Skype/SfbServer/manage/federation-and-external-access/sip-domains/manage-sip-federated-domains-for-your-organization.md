---
title: Gestion des domaines fédérés SIP pour votre organisation
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: Découvrez comment gérer et configurer des domaines SIP avec qui vous pouvez vous fédérer,
ms.openlocfilehash: 0c79141a491f713c1a6858d6703fc3fac55d5b20
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386642"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gérer les domaines fédérés SIP pour votre organisation dans Skype Entreprise Server


Pour gérer et configurer des domaines SIP avec lesquels vous pouvez vous fédérer, vous pouvez effectuer les opérations suivantes :

  - créer ou modifier une liste de domaines partenaires fédérés SIP autorisés ;

  - créer ou modifier une liste de domaines fédérés SIP bloqués.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurer la prise en charge des domaines externes autorisés dans Skype Entreprise Server

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez décider des domaines qui sont autorisés à se fédérer avec votre organisation. Vous devez configurer un ou plusieurs domaines externes spécifiques en tant que domaines fédérés autorisés. Pour ce faire, ajoutez chaque domaine à la liste des domaines autorisés. Même si la découverte de partenaire est activée pour votre organisation, effectuez cette opération si le domaine est un partenaire fédéré qui devra peut-être communiquer avec plus de 1 000 de vos utilisateurs ou envoyer plus de 20 messages par seconde. Si la découverte de partenaire est désactivée pour votre organisation, seuls les utilisateurs des domaines externes que vous ajoutez à la liste des domaines autorisés peuvent utiliser la messagerie instantanée et les services de conférence avec les utilisateurs de votre organisation. Si vous souhaitez limiter l’accès d’un domaine fédéré à un serveur spécifique qui exécute le service Edge d’accès du partenaire fédéré, vous pouvez spécifier le nom de domaine du serveur exécutant le service Edge d’accès pour chaque domaine présent dans la liste des domaines autorisés.

> [!NOTE]  
> Cette procédure décrit la façon de configurer la prise en charge de domaines spécifiques, mais l’implémentation de la prise en charge des utilisateurs fédérés nécessite également d’activer la prise en charge des utilisateurs fédérés pour votre organisation, mais aussi de configurer et d’appliquer des stratégies permettant de spécifier les utilisateurs qui sont autorisés à collaborer avec les utilisateurs fédérés. Pour plus d’informations sur l’activation de la prise en charge des utilisateurs fédérés, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md). Pour plus d’informations sur la configuration des stratégies de contrôle de la fédération, voir [Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Pour ajouter un domaine externe à la liste des domaines autorisés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Domaines fédérés**.
4.  Dans la page **Domaines fédérés**, cliquez sur **Nouveau**, puis sur **Domaine autorisé**.
5.  Dans **Nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **Nom de domaine complet (ou FQDN)**, tapez le nom de domaine du partenaire fédéré.       

        > [!NOTE]  
        > Ce nom doit être unique et ne doit pas déjà exister en tant que domaine autorisé pour ce serveur exécutant le service Edge d’accès. Il peut contenir jusqu’à 256 caractères.<BR><br>La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez **contoso.com**, la recherche renverra également le domaine **it.contoso.com**.<BR><br>Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé. Skype Entreprise Server empêche cela de se produire afin que vous n’avez pas à synchroniser vos listes.
    
      - Si vous souhaitez restreindre l’accès pour ce domaine fédéré aux utilisateurs d’un serveur spécifique qui exécute le service Edge d’accès, dans **Service Edge d’accès (FQDN)**, tapez le nom de domaine complet du serveur de domaine fédéré exécutant le service Edge d’accès.    
      - Si vous souhaitez fournir des informations supplémentaires, dans **Commentaire**, tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.

6.  Cliquez sur **Valider**.
7.  Répétez les étapes 4 à 6 pour chaque domaine de partenaire fédéré que vous souhaitez autoriser.

Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).

De plus, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés. Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurer la prise en charge des domaines externes bloqués dans Skype Entreprise Server 

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines qui n’auront pas accès à la fédération au sein de votre organisation. La liste des domaines bloqués sert de liste rouge (liste d’entrées explicites qui doivent être interdites) et s’applique à la découverte des domaines fédérés, si cette option est activée. Pour plus d’informations, voir [Activer ou désactiver la découverte des partenaires de fédération](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Empêchez un ou plusieurs domaines externes de se connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Pour ajouter un domaine externe à la liste des domaines bloqués

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**.
4.  Cliquez sur **Domaines fédérés**, sur **Nouveau**, puis sur **Domaine bloqué**.
5.  Dans **Nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **Nom de domaine complet (ou FQDN)**, tapez le nom de domaine du partenaire fédéré que vous souhaitez bloquer.

        > [!NOTE]  
        > Il peut contenir jusqu’à 256 caractères.<BR><br>La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez **contoso.com**, la recherche renverra également le domaine **it.contoso.com**.<BR><br>Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé. Skype Entreprise Server empêche cela de se produire afin que vous n’avez pas à synchroniser vos listes.
   
      - (Facultatif) Dans **Commentaire**, tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.

6.  Cliquez sur **Valider**.
7.  Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.

Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).

De plus, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés. Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Voir aussi

[Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Activation ou désactivation de la découverte de partenaires de fédération](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

