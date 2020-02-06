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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: la connectivité de messagerie instantanée ublic permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs de services de messagerie instantanée publics.
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818305"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs publics dans Skype entreprise Server

La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée fournis par des fournisseurs de services de messagerie instantanée publics. Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs publics peuvent collaborer avec des utilisateurs de Skype entreprise Server internes. La connectivité de messagerie instantanée publique est une fonctionnalité ajoutée qui repose sur la configuration de votre déploiement et de vos utilisateurs. Ce service dépend également de la configuration du service auprès du fournisseur de messagerie instantanée publique. 

Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, au niveau du site et de l’utilisateur. Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de Skype entreprise Server est le suivant : la stratégie de l’utilisateur (la plus influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.

Dans le cas d’invitations de messagerie instantanée, la réponse dépend du logiciel client. La requête est acceptée sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (autrement dit, les paramètres du client de l’utilisateur **autorisent** et **bloquent** les listes). Par ailleurs, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés de tous les utilisateurs qui ne figurent pas dans sa liste **verte** .



> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs publics, même si vous n’avez pas activé la Fédération pour votre organisation. Toutefois, les stratégies que vous configurez ne s’appliquent que lorsque la Fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir [activation ou désactivation de l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md). Par ailleurs, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype entreprise Server et qui sont configurés pour utiliser cette stratégie. Pour plus d’informations sur la spécification des utilisateurs publics qui peuvent se connecter à Skype entreprise Server, voir [affecter une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md).


Utilisez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou de plusieurs fournisseurs de messagerie instantanée publics.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Pour configurer une stratégie d’accès externe pour prendre en charge l’accès public aux utilisateurs

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale de manière à prendre en charge l’accès public aux utilisateurs, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**. Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnablePublicUsers** pour une stratégie utilisateur qui autorise les communications pour les utilisateurs publics).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès public aux utilisateurs de la stratégie, activez la case à cocher **activer les communications avec les utilisateurs publics** .
    
      - Pour désactiver l’accès public aux utilisateurs de la stratégie, décochez la case **activer les communications avec les utilisateurs publics** .

7.  Cliquez sur **Valider**.

Pour activer l’accès public aux utilisateurs, vous devez également activer la prise en charge de la Fédération au sein de votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Skype entreprise Server](configure-policies-to-control-federated-user-access.md).

S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs publics que vous souhaitez pouvoir collaborer avec des utilisateurs publics. 


## <a name="see-also"></a>Voir aussi

[Gestion des fournisseurs fédérés SIP pour l’organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
