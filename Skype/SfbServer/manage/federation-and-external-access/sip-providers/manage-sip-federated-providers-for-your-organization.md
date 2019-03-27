---
title: Gestion des fournisseurs fédérés SIP pour l’organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment configurer la prise en charge pour les utilisateurs de SIP des fournisseurs fédérés.
ms.openlocfilehash: 1259ae9d2dfd7d829caaa6dba714f0876b5500c4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899672"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gérer les fournisseurs fédérés SIP de votre organisation dans Skype pour Business Server

Pour configurer la prise en charge pour les utilisateurs de SIP des fournisseurs fédérés, vous devez effectuer les opérations suivantes :

  - Configurez une ou plusieurs stratégies d’accès utilisateur externe pour prendre en charge la communication avec des contacts fédérés SIP fournisseur

  - Spécifiez les fournisseurs hébergés que vous souhaitez prendre en charge

  - Spécifier les fournisseurs de messagerie instantanée publics que vous souhaitez prendre en charge

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Créer ou modifier des fournisseurs fédérés SIP publics dans Skype pour Business Server

Connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par les fournisseurs publics.

Skype pour Business Server possède des configurations de fournisseur public pour la messagerie instantanée. Chaque fournisseur public est configuré avec le nom de domaine complet de serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec des personnes dans leur liste de Contacts qui utilisent ce fournisseur**.

Par défaut, aucun des fournisseurs publics sont activés. Vous devez effectuer le contrat de licence et de mise en service du travail avant d’activer les fournisseurs publics. Vous pouvez activer le fournisseur avant la fin de la gestion des licences et de mise en service du travail. Les utilisateurs ne pourront pas communiquer avec des contacts sur les fournisseurs jusqu'à ce que le travail requis est terminé. Pour plus d’informations sur la gestion des licences et la configuration des fournisseurs publics, consultez [configurer les stratégies pour contrôler l’accès des utilisateurs publics](../external-access-policies/configure-policies-to-control-public-user-access.md).

Utilisez la procédure suivante pour créer ou modifier des fournisseurs publics.


### <a name="to-create-or-edit-public-providers"></a>Pour créer ou modifier des fournisseurs publics

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **fédération et accès externe**, puis cliquez sur **Fournisseurs fédérés SIP**.

4.  Si vous avez besoin créer un nouveau fournisseur Public, cliquez sur **Nouveau** , puis sur **fournisseur Public**.

5.  Si vous devez modifier une entrée de la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier un fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur**   ce paramètre permet de messagerie instantanée avec des utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur :**   une propriété requise, le type du nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge (FQDN) d’accès :**   propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez. Ces informations fournies sous la forme d’un élément par défaut et doivent être modifiées seulement si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.
    
      - **Niveau de vérification par défaut :**   le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes à leur liste de Contacts qui utilisent ce fournisseur** permet de limiter la communication à des contacts que vous avez accepté et se trouvent dans votre liste de contacts.
        
        Sélectionnez **Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction, vous devez avoir reçu et accepté une invitation à un contact. Ce paramètre ne limite pas qui peuvent vous contacter à partir du réseau du fournisseur public.

7.  Lorsque vous avez la définition des paramètres, cliquez sur **Valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Créer ou modifier des fournisseurs fédérés SIP hébergés dans Skype pour Business Server

Hébergée (IM) connectivité permet aux utilisateurs de votre organisation pour utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée fournis par des fournisseurs hébergés de messagerie instantanée de fournisseur.

Chaque fournisseur hébergé est configuré avec le nom de domaine complet de serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec des personnes dans leur liste de Contacts qui utilisent ce fournisseur**.

Utilisez la procédure suivante pour créer ou modifier des fournisseurs hébergés.

### <a name="to-create-or-edit-hosted-providers"></a>Pour créer ou modifier des fournisseurs hébergés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **fédération et accès externe**, puis cliquez sur **Fournisseurs fédérés SIP**.

4.  Si vous avez besoin créer un nouveau fournisseur hébergé, cliquez sur **Nouveau** , puis sur **fournisseur hébergé**.

5.  Si vous devez modifier une entrée de la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier un fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur**   ce paramètre active les communications avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur :**   une propriété requise, le type du nom du fournisseur tel qu’il apparaîtra dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge (FQDN) d’accès :**   propriété obligatoire, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez. Ces informations doivent être fournies par le fournisseur hébergé et doivent être modifiées seulement si le fournisseur hébergé modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur hébergé.
    
      - **Niveau de vérification par défaut :**   le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes à leur liste de Contacts qui utilisent ce fournisseur** permet de limiter la communication à des contacts que vous avez accepté et se trouvent dans votre liste de contacts.
        
        Sélectionnez **Autoriser les utilisateurs à communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction, vous devez avoir reçu et accepté une invitation à un contact. Ce paramètre ne limite pas qui peuvent vous contacter à partir du réseau du fournisseur hébergé.

7.  Lorsque vous avez la définition des paramètres, cliquez sur **Valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.


## <a name="see-also"></a>Voir aussi


[Configurer des stratégies pour contrôler l’accès des utilisateurs publics](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

