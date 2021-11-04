---
title: Activation ou désactivation de la fédération et de la connectivité PIC (Public IM Connectivity)
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: La fédération doit être prise en charge pour permettre aux utilisateurs possédant un compte auprès d’un client approuvé ou d’une organisation partenaire, y compris les domaines partenaires et les utilisateurs de fournisseurs de services de messagerie instantanée publics que vous prenez en charge, de collaborer avec des utilisateurs de votre entreprise.
ms.openlocfilehash: 7c87ad567bef1b073dae80e8bc669d6f0d52e3a6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765472"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Activer ou désactiver la fédération et la connectivité de messagerie instantanée publique dans Skype Entreprise Server

La fédération doit être prise en charge pour permettre aux utilisateurs possédant un compte auprès d’un client approuvé ou d’une organisation partenaire, y compris les domaines partenaires et les utilisateurs de fournisseurs de services de messagerie instantanée publics que vous prenez en charge, de collaborer avec des utilisateurs de votre entreprise. La fédération est également nécessaire pour utiliser un fournisseur de service Exchange hébergé afin de procurer une messagerie vocale aux utilisateurs Voix Entreprise dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tel que Microsoft Exchange Online. Une fois que vous avez établi une relation d’confiance avec ces domaines externes, vous pouvez autoriser les utilisateurs de ces domaines à accéder à votre déploiement et à participer à des communications Skype Entreprise Server réseau. Cette relation de confiance est appelée « fédération » ; elle n’est pas liée à une relation de confiance Active Directory et n’en dépend pas non plus.

Pour prendre en charge l’accès des utilisateurs de domaines fédérés, vous devez activer la fédération. Si vous activez la fédération pour votre entreprise, vous devez également préciser si vous voulez implémenter les options suivantes :

  - **Activer la découverte de domaine partenaire**   Si vous activez cette option, Skype Entreprise Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines non répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de partenaires fédérés découverts et en limitant ou bloquant ce trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés. Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations sur le contrôle de l’accès par les domaines fédérés, voir Configurer la prise en charge [des domaines externes autorisés.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)

  - **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage**    Une notification d’exclusion est envoyée aux partenaires fédérés pour les informer que l’archivage est mis en œuvre dans votre déploiement. Si vous prenez en charge l’archivage des communications externes avec des domaines de partenaires fédérés, vous devez activer la notification d’exclusion relative à l’archivage afin de prévenir les partenaires que leurs messages sont archivés.

Si plus tard, vous souhaitez empêcher temporairement ou définitivement des utilisateurs d’accéder aux domaines fédérés, vous pouvez désactiver la fédération pour votre entreprise. Suivez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés dans votre entreprise, en spécifiant notamment les options de fédération que vous souhaitez prendre en charge.

> [!NOTE]  
> L’activation de la fédération pour votre organisation signifie uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés. Les utilisateurs des domaines fédérés ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de l’accès des utilisateurs fédérés. Les utilisateurs de fournisseurs de services de messagerie instantanée publics ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de la connectivité de messagerie instantanée publique. Skype Entreprise Server ne peut pas utiliser un service Exchange hébergé pour fournir des services de répondage d’appel, Outlook Voice Access (y compris la messagerie vocale) ou de service automatique pour les utilisateurs dont les boîtes aux lettres sont situées sur un service Exchange hébergé tant que vous n’avez pas configuré une stratégie de messagerie vocale hébergée qui fournit des informations de routage. Pour plus d’informations sur la configuration des stratégies de communication avec les utilisateurs de domaines fédérés dans d’autres organisations, voir Gérer les domaines fédérés [SIP pour votre organisation.](../sip-domains/manage-sip-federated-domains-for-your-organization.md) Qui plus est, si vous souhaitez prendre en charge les communications avec des utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies à cet effet et configurer la prise en charge des différents fournisseurs de services de votre choix. Pour plus d’informations, [voir Gérer les fournisseurs fédérés SIP pour votre organisation.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre entreprise

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour votre entreprise, activez la case à cocher **Autoriser les communications avec des utilisateurs fédérés**.
    
      - Pour désactiver l’accès des utilisateurs fédérés pour votre entreprise, désactivez la case à cocher **Autoriser les communications avec des utilisateurs fédérés**.

6.  Si vous avez activé la case à cocher **Autoriser les communications avec des utilisateurs fédérés**, procédez comme suit :
    
    1.  Pour prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **Activer la découverte du domaine partenaire**.
    
    2.  Si votre entreprise prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage**.

7.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés.](../external-access-policies/configure-policies-to-control-federated-user-access.md) Pour contrôler l’accès à des domaines fédérés spécifiques, voir Configurer la prise en [charge des domaines externes autorisés.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la fédération et de la connectivité de messagerie instantanée publique à l’aide Windows PowerShell cmdlets

La fédération et la connectivité de messagerie instantanée publique peuvent également être gérées à l’aide de Windows PowerShell et de la cmdlet Set-CsAccessEdgeConfiguration public. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Pour activer la fédération et la connectivité DE MESSAGERIE INSTANTANÉE publique

  - Pour activer la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à True ($True) :<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Pour désactiver la fédération et la connectivité de messagerie instantanée publique

  - Pour désactiver la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à False ($False) :<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

