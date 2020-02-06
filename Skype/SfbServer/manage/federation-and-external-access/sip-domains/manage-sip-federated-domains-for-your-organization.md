---
title: Gestion des domaines fédérés SIP pour l’organisation
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: Découvrez comment gérer et configurer des domaines SIP avec lesquels vous pouvez être fédérer.
ms.openlocfilehash: af014c6c24d3655612846e97cfa7ff5c7b9c816b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818235"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gestion des domaines fédérés SIP pour votre organisation dans Skype entreprise Server


Pour gérer et configurer des domaines SIP avec lesquels vous êtes fédérer, vous pouvez procéder comme suit :

  - Créer ou modifier une liste de domaines autorisés de domaines partenaires fédérés SIP.

  - Créez ou modifiez la liste des domaines bloqués des domaines fédérés SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configuration de la prise en charge des domaines externes autorisés dans Skype entreprise Server

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines spécifiques qu’il est possible de fédérer avec votre organisation. Vous pouvez configurer un ou plusieurs domaines externes spécifiques en tant que domaines fédérés autorisés. Pour ce faire, ajoutez chaque domaine à la liste des domaines autorisés. Même si la découverte des partenaires est activée pour votre organisation, procédez comme suit si le domaine est un partenaire fédéré qui peut avoir besoin de communiquer avec plus de 1 000 ou si vous avez besoin d’envoyer plus de 20 messages par seconde. Si la découverte de partenaire n’est pas activée pour votre organisation, seuls les utilisateurs de domaines externes que vous ajoutez à la liste des domaines autorisés peuvent participer à la messagerie instantanée et à la Conférence avec les utilisateurs de votre organisation. Si vous souhaitez limiter l’accès d’un domaine fédéré à un serveur spécifique exécutant le service Edge d’accès du partenaire fédéré, vous pouvez spécifier le nom de domaine du serveur exécutant le service Edge d’accès pour chaque domaine dans la liste des domaines autorisés.

> [!NOTE]  
> Cette procédure vous explique comment configurer la prise en charge des domaines spécifiques, mais que l’implémentation de la prise en charge des utilisateurs fédérés nécessite également l’activation de la prise en charge des utilisateurs fédérés pour votre organisation et la configuration et l’application de stratégies pour contrôler les utilisateurs qui peuvent collaborer avec des utilisateurs fédérés. Pour plus d’informations sur l’activation de la prise en charge des utilisateurs fédérés, voir [activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md). Pour plus d’informations sur la configuration des stratégies pour contrôler la Fédération, voir [configurer des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Pour ajouter un domaine externe à la liste des domaines autorisés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.
2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **domaines fédérés**.
4.  Sur la page **domaines fédérés** , cliquez sur **nouveau**, puis cliquez sur **domaine autorisé**.
5.  Dans **nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **nom de domaine (ou nom de domaine complet)**, tapez le nom du domaine du partenaire fédéré.       

        > [!NOTE]  
        > Ce nom doit être unique et ne peut pas déjà exister en tant que domaine autorisé pour ce serveur exécutant le service Edge d’accès. Le nom ne peut pas contenir plus de 256 caractères.<BR><br>La recherche du nom de domaine du partenaire fédéré effectue une correspondance de suffixe. Par exemple, si vous tapez **contoso.com**, la recherche renverra également le domaine **it.contoso.com**.<BR><br>Un domaine de partenaire fédéré ne peut pas être bloqué et autorisé simultanément. Skype entreprise Server empêche cela d’avoir lieu de sorte que vous n’ayez pas à synchroniser vos listes.
    
      - Si vous voulez limiter l’accès à ce domaine fédéré aux utilisateurs d’un serveur spécifique exécutant le service Edge d’accès (FQDN), tapez le nom de domaine complet **(FQDN)** du serveur du domaine fédéré exécutant le service Edge d’accès.    
      - Si vous voulez fournir des informations supplémentaires, dans **commenter**, tapez les informations que vous voulez partager avec d’autres administrateurs système sur cette configuration.

6.  Cliquez sur **Valider**.
7.  Répétez les étapes 4 à 6 pour chaque domaine partenaire fédéré que vous souhaitez autoriser.

Pour autoriser l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de l’accès des utilisateurs fédérés au sein de votre organisation. Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).

Par ailleurs, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md)

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurer la prise en charge des domaines externes bloqués dans Skype entreprise Server 

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines qui seront bloqués par votre organisation. Si cette option est activée, la liste des domaines bloqués fera office de liste de blocage (liste d’entrées explicites qui ne seront pas autorisées) et sera appliquée dans découverte de domaine fédéré. Pour plus d’informations, voir [activer ou désactiver la découverte des partenaires de Fédération](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloquer un ou plusieurs domaines externes pour vous connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Pour ajouter un domaine externe à la liste des domaines bloqués

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.
2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3.  Dans la barre de navigation de gauche, cliquez sur **accès des utilisateurs externes**.
4.  Cliquez sur **domaines fédérés**, sur **nouveau**, puis sur **domaine bloqué**.
5.  Dans **nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **nom de domaine (ou nom de domaine complet)**, tapez le nom du domaine de partenaire fédéré que vous souhaitez bloquer.

        > [!NOTE]  
        > Le nom ne peut pas contenir plus de 256 caractères.<BR><br>La recherche du nom de domaine du partenaire fédéré effectue une correspondance de suffixe. Par exemple, si vous tapez **contoso.com**, la recherche renverra également le domaine **it.contoso.com**.<BR><br>Un domaine de partenaire fédéré ne peut pas être bloqué et autorisé simultanément. Skype entreprise Server empêche cela d’avoir lieu de sorte que vous n’ayez pas à synchroniser vos listes.
   
      - Facultatif Dans **Commentaire**, tapez les informations que vous voulez partager avec d’autres administrateurs système sur cette configuration.

6.  Cliquez sur **Valider**.
7.  Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.

Pour autoriser l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de l’accès des utilisateurs fédérés au sein de votre organisation. Pour plus d’informations, voir [activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).

Par ailleurs, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md)


## <a name="see-also"></a>Voir aussi

[Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Activation ou désactivation de la découverte de partenaires de fédération](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

