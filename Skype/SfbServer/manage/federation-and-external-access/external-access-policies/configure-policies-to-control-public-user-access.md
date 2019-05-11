---
title: Configuration des stratégies de contrôle d’accès des utilisateurs publics
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: la connectivité de messagerie instantanée public permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs de services de messagerie instantanée publique.
ms.openlocfilehash: 6cccef5de36b733e1af13092137bf0a35e843b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920438"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurer des stratégies de contrôle d’accès des utilisateurs publics dans Skype pour Business Server

Connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs de services de messagerie instantanée publique. Vous configurez une ou plusieurs stratégies d’accès utilisateur externe au contrôle si les utilisateurs publics peuvent collaborer avec Skype interne pour les utilisateurs Business Server. Messagerie instantanée publique est une fonctionnalité supplémentaire qui repose sur la configuration de votre déploiement et d’utilisateurs. Cela dépend également la mise en service du service au niveau du fournisseur de messagerie instantanée publique. 

Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, site et au niveau utilisateur. Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre. Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins). Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.

Dans le cas des invitations de messagerie instantanée, la réponse dépend du logiciel client. La demande est acceptée, sauf si les expéditeurs externes sont bloqués explicitement par une règle configurée par l’utilisateur (autrement dit, les paramètres dans le client de l’utilisateur **Autoriser** les listes **rouges** ). En outre, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés des utilisateurs qui ne figurent pas dans sa liste **verte** .



> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs publics, même si vous n’avez pas activé la fédération pour votre organisation. Toutefois, les stratégies que vous configurez sont en effet que lorsque vous avez activée pour votre organisation de fédération. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md). En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype pour Business Server et configurés pour utiliser la stratégie. Pour plus d’informations sur la spécification des utilisateurs publics qui peuvent se connecter à Skype pour Business Server, voir [attribuer une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).


Utilisez la procédure suivante pour configurer une stratégie pour prendre en charge l’accès par les utilisateurs d’un ou plusieurs fournisseurs de messagerie instantanée publics.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Pour configurer une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs publics

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe** , effectuez l’une des options suivantes :
    
      - Pour configurer la stratégie globale pour prendre en charge l’accès des utilisateurs publics, cliquez sur la stratégie globale, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **Nouveau**, puis cliquez sur **stratégie de Site**. Dans **Sélectionner un Site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis cliquez sur **stratégie de l’utilisateur**. Dans la **Nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique quel utilisateur concernés par cette stratégie (par exemple, **EnablePublicUsers** pour une stratégie d’utilisateur qui permet les communications des utilisateurs publics).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations de la stratégie dans la zone **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès des utilisateurs publics pour la stratégie, activez la case à cocher **Activer les communications avec des utilisateurs publics** .
    
      - Pour désactiver l’accès des utilisateurs publics pour la stratégie, désactivez la case à cocher **Activer les communications avec des utilisateurs publics** .

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs publics, vous devez également activer la prise en charge pour la fédération dans votre organisation. Pour plus d’informations, voir [configurer les stratégies de contrôle d’un accès utilisateur dans Skype pour Business Server fédéré](configure-policies-to-control-federated-user-access.md).

S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie pour les utilisateurs publics que vous souhaitez être en mesure de collaborer avec des utilisateurs publics. 


## <a name="see-also"></a>Voir aussi

[Gestion des fournisseurs fédérés SIP pour l’organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
