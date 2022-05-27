---
title: Gestion des fournisseurs fédérés SIP pour votre organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
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
description: Découvrez comment configurer la prise en charge des utilisateurs de fournisseurs fédérés SIP.
ms.openlocfilehash: dbbf01de2c1538c0761550b073ace573cde44eb7
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676206"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gérer les fournisseurs fédérés SIP pour votre organisation dans Skype Entreprise Server

Pour configurer la prise en charge pour les utilisateurs des fournisseurs fédérés SIP, vous devez effectuer les opérations suivantes :

  - Configurez une ou plusieurs des stratégies d’accès des utilisateurs externes pour prendre en charge la communication avec les contacts de fournisseurs fédérés SIP.

  - Spécifiez les fournisseurs hébergés à prendre en charge.

  - Spécifiez les fournisseurs de messagerie instantanée publics à prendre en charge.

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Créer ou modifier des fournisseurs fédérés SIP publics dans Skype Entreprise Server

La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par les fournisseurs publics.

Skype Entreprise Server dispose de configurations de fournisseur public pour la messagerie instantanée. Chaque fournisseur public est configuré avec le nom de domaine complet du serveur Edge du fournisseur, et le niveau de vérification par défaut **Permet aux utilisateurs de communiquer uniquement avec les personnes de leur liste de contacts qui utilisent ce fournisseur**.

Par défaut, aucun des fournisseurs publics n’est activé. Terminez le travail relatif au contrat de licence et à l’approvisionnement avant d’activer les fournisseurs publics. Vous pouvez activer le fournisseur avant de terminer le travail relatif au contrat de licence et à l’approvisionnement. Les utilisateurs ne pourront pas communiquer avec leurs contacts situés chez ces fournisseurs tant que le travail préalable ne sera pas terminé. Pour plus d’informations sur les licences et l’approvisionnement des fournisseurs publics, consultez [Configurer des stratégies pour contrôler les accès des utilisateurs publics](../external-access-policies/configure-policies-to-control-public-user-access.md).

Utilisez la procédure suivante pour créer ou modifier des fournisseurs publics.


### <a name="to-create-or-edit-public-providers"></a>Pour créer ou modifier des fournisseurs publics

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.

4.  Pour créer un fournisseur public, cliquez sur **Nouveau**, puis sur **Fournisseur public**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis sur **Afficher les détails**.

6.  Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur**   La sélection de ce paramètre permet aux utilisateurs de ce fournisseur d’accéder à la messagerie instantanée.
    
      - **Nom du fournisseur :** propriété requise. Tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN) :** propriété requise. Tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez. Ces informations sont fournies par défaut et ne doivent être changées que si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.
    
      - **Niveau de vérification par défaut :** le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** limite la communication aux contacts que vous avez acceptés et qui figurent dans votre liste des contacts.
        
        La sélection du paramètre **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** supprime la restriction que vous devez avoir reçue et permet d’accepter l’invitation d’un contact. Ce paramètre n’impose pas de limite aux personnes qui peuvent vous contacter à partir du réseau du fournisseur public.

7.  Quand vous avez terminé de configurer les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Créer ou modifier des fournisseurs fédérés SIP hébergés dans Skype Entreprise Server

La connectivité de messagerie instantanée du fournisseur hébergé permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par les fournisseurs hébergés.

Chaque fournisseur hébergé est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur**.

Utilisez la procédure suivante pour créer ou modifier des fournisseurs hébergés.

### <a name="to-create-or-edit-hosted-providers"></a>Pour créer ou modifier des fournisseurs hébergés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL Administration pour ouvrir le Skype Entreprise Server Panneau de configuration. 

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.

4.  Si vous devez créer un nouveau fournisseur hébergé, cliquez sur **Nouveau**, puis sur **Fournisseur hébergé**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier**, puis sur **Afficher les détails**.

6.  Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur** Ce paramètre active les communications avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur :** propriété requise. Tapez le nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN) :** propriété requise. Tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez. Cette information doit être fournie par le fournisseur hébergée et ne doit être modifiée que si le fournisseur hébergé modifie le nom de domaine complet de son service Edge d’accès.
    
      - **Niveau de vérification par défaut :** le paramètre par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** limite la communication aux contacts que vous avez acceptés et qui figurent dans votre liste des contacts.
        
        Sélectionnez **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** pour supprimer la restriction sur la réception et l’acceptation d’invitations de contacts. Ce paramètre n’applique aucune restriction sur les personnes qui peuvent vous contacter à partir du réseau du fournisseur hébergé.

7.  Une fois que vous avez configuré les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.


## <a name="see-also"></a>Voir aussi


[Configurer des stratégies pour contrôler les accès des utilisateurs publics](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

