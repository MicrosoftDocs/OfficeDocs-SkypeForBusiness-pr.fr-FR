---
title: Gestion des fournisseurs fédérés SIP pour l’organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment configurer la prise en charge des utilisateurs de fournisseurs fédérés SIP.
ms.openlocfilehash: ee16ec8953a722a86838f710fdf92cb9b2ce5f36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303962"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gestion des fournisseurs fédérés SIP pour votre organisation dans Skype entreprise Server

Pour configurer la prise en charge des utilisateurs de fournisseurs fédérés SIP, vous devez procéder comme suit:

  - Configuration d’une ou plusieurs stratégies d’accès des utilisateurs externes pour la prise en charge de la communication avec les contacts du fournisseur fédéré SIP

  - Spécifier les fournisseurs hébergés que vous voulez prendre en charge

  - Spécifier les fournisseurs de messagerie instantanée publics que vous voulez prendre en charge

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Créer ou modifier des fournisseurs fédérés SIP publics dans Skype entreprise Server

La connectivité de messagerie instantanée publique permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs publics.

Skype entreprise Server dispose de configurations de fournisseur public pour la messagerie instantanée. Chaque fournisseur public est configuré à l’aide du nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes figurant sur leur liste de contacts qui utilisent ce fournisseur**.

Comme paramètre par défaut, aucun des fournisseurs publics n’est activé. Vous devez compléter le contrat de licence et le fonctionnement de la mise en service avant d’activer les fournisseurs publics. Vous pouvez activer le fournisseur avant d’effectuer les tâches de gestion des licences et de mise en service. Les utilisateurs ne seront pas en mesure de communiquer avec les contacts de ces fournisseurs tant que la configuration requise ne sera pas effectuée. Pour plus d’informations sur la gestion des licences et la mise en service des fournisseurs publics, voir [configurer des stratégies pour contrôler les accès publiques aux utilisateurs](../external-access-policies/configure-policies-to-control-public-user-access.md).

Utilisez la procédure suivante pour créer ou modifier des fournisseurs publics.


### <a name="to-create-or-edit-public-providers"></a>Pour créer ou modifier des fournisseurs publics

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **fournisseurs fédérés SIP**.

4.  Si vous avez besoin de créer un nouveau fournisseur public, cliquez sur **nouveau** , puis cliquez sur **fournisseur public**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **modifier**, puis sur **afficher les détails**.

6.  Dans la page **modifier le fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants:
    
      - **Activer les communications avec ce fournisseur**   sélectionnez ce paramètre active la messagerie instantanée avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur:**   une propriété requise, tapez le nom du fournisseur tel qu’il sera reflété dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN):**   une propriété requise, tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez. Ces informations sont fournies en tant qu’élément par défaut et ne doivent être changées que si le fournisseur public apporte une modification au FQDN du service Edge d’accès au fournisseur public.
    
      - **Niveau de vérification par défaut:**   le paramètre par défaut, **permettre aux utilisateurs de communiquer avec des personnes de la liste de contacts qui utilisent ce fournisseur** , limite les communications aux contacts que vous avez acceptés et qui se trouvent dans votre liste de contacts.
        
        Sélectionner **permettre aux utilisateurs de communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction que vous devez avoir reçu et accepté une invitation de contact. Ce paramètre ne limite pas les personnes qui peuvent vous contacter à partir du réseau du fournisseur public.

7.  Lorsque vous avez configuré les paramètres, cliquez sur **valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Créer ou modifier des fournisseurs fédérés SIP hébergés dans Skype entreprise Server

La connectivité de messagerie instantanée du fournisseur hébergé permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs de services de messagerie instantanée proposés par des fournisseurs hébergés.

Chaque fournisseur hébergé est configuré à l’aide du nom de domaine complet du serveur Edge du fournisseur, et le niveau de vérification par défaut **permet aux utilisateurs de communiquer uniquement avec des personnes de leur liste de contacts qui utilisent ce fournisseur**.

Utilisez la procédure suivante pour créer ou modifier des fournisseurs hébergés.

### <a name="to-create-or-edit-hosted-providers"></a>Pour créer ou modifier des fournisseurs hébergés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **fournisseurs fédérés SIP**.

4.  Si vous avez besoin de créer un nouveau fournisseur hébergé, cliquez sur **nouveau** , puis cliquez sur **fournisseur hébergé**.

5.  Si vous avez besoin de modifier une entrée de la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **modifier**, puis sur **afficher les détails**.

6.  Dans la page **modifier le fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants:
    
      - **Activer les communications avec ce fournisseur**   sélectionnez ce paramètre active les communications avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur:**   une propriété requise, tapez le nom du fournisseur tel qu’il sera reflété dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN):**   une propriété requise, tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez. Ces informations doivent être fournies par le fournisseur hébergé et ne doivent être changées que si le fournisseur hébergé apporte une modification au FQDN du service Edge d’accès au fournisseur hébergé.
    
      - **Niveau de vérification par défaut:**   le paramètre par défaut, **permettre aux utilisateurs de communiquer avec des personnes de la liste de contacts qui utilisent ce fournisseur** , limite les communications aux contacts que vous avez acceptés et qui se trouvent dans votre liste de contacts.
        
        Sélectionner **permettre aux utilisateurs de communiquer avec tout le monde à l’aide de ce fournisseur** supprime la restriction que vous devez avoir reçu et accepté une invitation de contact. Ce paramètre ne limite pas qui peut vous contacter à partir du réseau du fournisseur hébergé.

7.  Lorsque vous avez configuré les paramètres, cliquez sur **valider** pour enregistrer ou cliquez sur **Annuler** pour ignorer vos modifications.


## <a name="see-also"></a>Voir aussi


[Configurer des stratégies pour contrôler les accès public aux utilisateurs](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

