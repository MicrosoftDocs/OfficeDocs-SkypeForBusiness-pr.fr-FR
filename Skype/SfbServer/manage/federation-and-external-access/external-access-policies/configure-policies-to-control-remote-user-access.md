---
title: Configuration des stratégies pour contrôler l’accès des utilisateurs distants
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs Skype Entreprise Server internes. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau global, du site et de l’utilisateur.
ms.openlocfilehash: 6131163d83078f3aa1b9e4c1380a0596cac0837c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384292"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Skype Entreprise Server

Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs Skype Entreprise Server internes. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau global, du site et de l’utilisateur. Les stratégies de site remplacent la stratégie globale, et les stratégies utilisateur remplacent les stratégies de site et globale. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir [Managing federation and external access to Skype Entreprise Server](../managing-federation-and-external-access.md). Skype Entreprise Server de stratégie appliquées à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs distants, même si vous n’avez pas activé l’accès des utilisateurs distants pour votre organisation. Toutefois, les stratégies que vous configurez sont effectives uniquement quand vous activez l’accès des utilisateurs distants pour votre organisation. En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs distants, la stratégie s’applique uniquement aux utilisateurs activés pour Skype Entreprise Server et configurés pour utiliser la stratégie. Pour plus d’informations sur la spécification des utilisateurs qui peuvent se Skype Entreprise Server à partir d’emplacements distants, voir [Affecter une stratégie](assign-an-external-user-access-policy.md) d’accès des utilisateurs externes.

Utilisez la procédure suivante pour configurer chaque stratégie d’accès externe que vous comptez utiliser pour contrôle l’accès des utilisateurs distants.


> [!NOTE]  
> Cette procédure décrit comment configurer une stratégie uniquement pour activer les communications avec les utilisateurs distants, mais chaque stratégie que vous configurez pour prendre en charge l’accès des utilisateurs distants peut également configurer l’accès des utilisateurs fédérés et des utilisateurs publics. Pour plus d’informations sur la configuration des stratégies de prise en charge des utilisateurs fédérés, voir [Configure policies to control federated user access in Skype Entreprise Server](configure-policies-to-control-federated-user-access.md). Pour plus d’informations sur la configuration des stratégies de prise en charge des utilisateurs publics, voir Gérer les fournisseurs [fédérés SIP pour votre organisation dans Skype Entreprise Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Pour configurer une stratégie d’accès externe permettant de prendre en charge l’accès des utilisateurs distants

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs distants, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableRemoteUsers** pour une stratégie utilisateur qui permet les communications des utilisateurs distants).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des opérations suivantes :
    
      - Afin d’activer l’accès des utilisateurs distants pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs distants**.
    
      - Afin de désactiver l’accès des utilisateurs distants pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs distants**.

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs distants, vous devez aussi activer la prise en charge de l’accès des utilisateurs distants dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver la fédération et la connectivité DE messagerie instantanée publique](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à se connecter à distance. Pour plus d’informations, voir [Affecter une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md).
