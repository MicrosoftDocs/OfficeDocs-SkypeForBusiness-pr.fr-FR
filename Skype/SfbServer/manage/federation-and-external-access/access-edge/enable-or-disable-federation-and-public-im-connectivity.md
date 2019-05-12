---
title: Activation ou désactivation de la fédération et de la connectivité PIC
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prise en charge de la fédération est requise pour permettre aux utilisateurs qui disposent d’un compte avec une organisation clients ou partenaires approuvé, y compris les domaines partenaires et les utilisateurs de public de messagerie instantanée (MI) fournisseur utilisateurs, pour collaborer avec des utilisateurs dans votre organisation.
ms.openlocfilehash: d82833dcd4e477e2c332c01d3d4ba2fdca5123aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896417"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Activer ou désactiver la fédération et la connectivité PIC dans Skype pour Business Server

Prise en charge de la fédération est requise pour permettre aux utilisateurs qui disposent d’un compte avec une organisation clients ou partenaires approuvé, y compris les domaines partenaires et les utilisateurs de public de messagerie instantanée (MI) fournisseur utilisateurs, pour collaborer avec des utilisateurs dans votre organisation. Fédération est également requis pour utiliser un fournisseur de service Exchange hébergé pour fournir la messagerie vocale aux utilisateurs d’Enterprise Voice dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tel que Microsoft Exchange Online. Lorsque vous avez établi une relation d’approbation avec les domaines externes, vous pouvez autoriser les utilisateurs dans les domaines pour accéder à votre déploiement et participer à Skype pour les communications de serveur d’entreprise. Cette relation d’approbation est appelée de fédération et il n’est pas lié, ou une fonction, une relation d’approbation Active Directory.

Pour prendre en charge l’accès par les utilisateurs des domaines fédérés, vous devez activer la fédération. Si vous activez la fédération pour votre organisation, vous devez également spécifier s’il faut mettre en œuvre les options suivantes :

  - **Activer la découverte du domaine partenaire**   si vous activez cette option, Skype pour Business Server utilise les enregistrements de nom de domaine DNS (Domain Name System) pour tenter de découvrir les domaines non répertoriés dans la liste des domaines autorisés, découvertes Evaluation automatiquement le trafic entrant à partir de fédérés partenaires et limitant ou bloquer ce trafic selon le niveau de confiance, la quantité de trafic et les paramètres de l’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activée uniquement pour les utilisateurs dans les domaines que vous incluez dans la liste des domaines autorisés. Si vous sélectionnez cette option, vous pouvez spécifier cette personne domaines à être bloquée ou autorisée, y compris la restriction de l’accès à un serveur spécifique exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations sur le contrôle d’accès des domaines fédérés, voir [Configure prise en charge pour les domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Envoyer une notification d’exclusion d’archivage aux partenaires fédérés**     notification d’exclusion de responsabilité est envoyée à des partenaires fédérés d’archivage dans votre déploiement est en place. Si vous prenez en charge l’archivage des communications externes avec les domaines de partenaire fédéré, vous devez activer la notification d’exclusion relative d’archivage prévenir vos partenaires que leurs messages sont archivés.

Si vous souhaitez ultérieurement à titre temporaire ou permanent empêcher l’accès par les utilisateurs des domaines fédérés, vous pouvez désactiver la fédération pour votre organisation. Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés pour votre organisation, notamment en spécifiant les options appropriées fédération soient prises en charge pour votre organisation.

> [!NOTE]  
> Activation de la fédération pour votre organisation indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés. Les utilisateurs de domaines fédérés ne peuvent pas participer à par messagerie instantanée ou des conférences dans votre organisation jusqu'à ce que vous configurez également au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés. Les utilisateurs des fournisseurs de services de messagerie instantanée publique ne peut pas participer à par messagerie instantanée ou des conférences dans votre organisation jusqu'à ce que vous configurez également au moins une stratégie pour prendre en charge la connectivité PIC. Skype pour Business Server Impossible d’utiliser un service Exchange hébergé pour le répondeur, Outlook Voice Access (y compris la messagerie vocale), ou des services de standard automatique pour les utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé jusqu'à ce que vous configurez un vocale hébergée stratégie de messagerie qui fournit des informations de routage. Pour plus d’informations sur la configuration des stratégies pour la communication avec les utilisateurs des domaines fédérés dans d’autres organisations, voir [Manage SIP federated domaines pour votre organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md). En outre, si vous souhaitez prendre en charge les communications avec les utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies pour prendre en charge et également configurer la prise en charge pour les fournisseurs de services individuels que vous souhaitez prendre en charge. Pour plus d’informations, voir [Gérer SIP federated providers pour votre organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre organisation

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Modifier la Configuration Edge accès**, effectuez l’une des options suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour votre organisation, activez la case à cocher **Activer les communications avec les utilisateurs fédérés** .
    
      - Pour désactiver l’accès des utilisateurs fédérés pour votre organisation, désactivez la case à cocher **Activer les communications avec les utilisateurs fédérés** .

6.  Si vous avez sélectionné la case à cocher **Activer les communications avec les utilisateurs fédérés** , procédez comme suit :
    
    1.  Si vous souhaitez prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **Activer la découverte du domaine partenaire** .
    
    2.  Si votre organisation prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer l’archivage de notification d’exclusion aux partenaires fédérés** .

7.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, voir [configurer les stratégies de contrôle des accès des utilisateurs fédérés](../external-access-policies/configure-policies-to-control-federated-user-access.md). Pour contrôler l’accès des domaines fédérés spécifiques, voir [Configure prise en charge pour les domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la fédération et la connectivité PIC à l’aide des applets de commande Windows PowerShell

Fédération et la connectivité PIC peuvent également être gérés à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Pour activer la fédération et la connectivité PIC

  - Pour activer la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Pour désactiver la fédération et la connectivité PIC

  - Pour désactiver la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

