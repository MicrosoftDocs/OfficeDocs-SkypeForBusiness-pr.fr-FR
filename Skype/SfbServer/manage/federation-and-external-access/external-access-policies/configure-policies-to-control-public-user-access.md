---
title: Configuration des stratégies pour contrôler l’accès des utilisateurs publics
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par les fournisseurs de services de messagerie instantanée publics.
ms.openlocfilehash: 2482270d27843b546246e11fb1bcadcc45c900da
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774954"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs publics dans Skype Entreprise Server

La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par les fournisseurs de services de messagerie instantanée publics. Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs publics peuvent collaborer avec des utilisateurs Skype Entreprise Server internes. La connectivité de messagerie instantanée publique est une fonctionnalité ajoutée qui s’appuie sur la configuration de votre déploiement et des utilisateurs. Cela dépend également de la mise en service du service au niveau du fournisseur de messagerie instantanée public. 

Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, du site et des utilisateurs. Skype Entreprise Server de stratégie appliquées à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Dans le cas des invitations de messagerie instantanée, la réponse dépend du logiciel client. La demande est acceptée, sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (c’est-à-dire les paramètres figurant dans les listes **Autoriser** et **Bloquer**). De plus, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés des utilisateurs qui ne figurent pas dans sa liste **Autoriser**.



> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs publics, même si vous n’avez pas activé la fédération pour votre organisation. Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants.](../access-edge/enable-or-disable-remote-user-access.md) En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs activés pour Skype Entreprise Server et configurés pour utiliser la stratégie. Pour plus d’informations sur la spécification des utilisateurs publics qui peuvent se Skype Entreprise Server, voir Affecter une stratégie d’accès des utilisateurs [externes.](assign-an-external-user-access-policy.md)


Effectuez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou plusieurs fournisseurs de messagerie instantanée publics.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Pour configurer une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs publics

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs publics, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui autorise les communications des utilisateurs publics).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs publics pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs publics**.
    
      - Pour désactiver l’accès des utilisateurs publics pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs publics**.

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs publics, vous devez aussi activer la prise en charge de la fédération dans votre organisation. Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès](configure-policies-to-control-federated-user-access.md)des utilisateurs fédérés dans Skype Entreprise Server .

S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs publics que vous souhaitez autoriser à collaborer avec les utilisateurs publics. 


## <a name="see-also"></a>Voir aussi

[Gestion des fournisseurs fédérés SIP pour l’organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
