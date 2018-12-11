---
title: Activation ou désactivation de la découverte de partenaires de fédération
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Au moment où vous déployé vos serveurs de périphérie et activé la fédération pour votre organisation, doit avoir spécifié s’il faut prendre en charge la découverte automatique des domaines de partenaire fédéré.
ms.openlocfilehash: afa022ae1a52124c3dabaf788de8308ba9834227
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222848"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Activer ou désactiver la découverte des partenaires de fédération dans Skype pour Business Server

Au moment où vous déployé vos serveurs de périphérie et activé la fédération pour votre organisation, doit avoir spécifié s’il faut prendre en charge la découverte automatique des domaines de partenaire fédéré. Utilisez la procédure de cette rubrique pour modifier cette configuration.

> [!NOTE]  
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre organisation. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, cliquez sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Modifier la Configuration Edge accès**, sous **Activer les communications avec les utilisateurs fédérés**, activez ou désactivez la case à cocher **Activer la découverte du domaine partenaire** pour activer ou désactiver la découverte automatique des domaines partenaires.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, voir [Activer ou désactiver la fédération et la connectivité PIC](enable-or-disable-federation-and-public-im-connectivity.md). Pour plus d’informations sur le contrôle d’accès pour des domaines fédérés spécifiques, voir [Gérer SIP des domaines fédérés](../sip-domains/manage-sip-federated-domains-for-your-organization.md) et [Gérer SIP fournisseurs fédérés](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la détection des partenaires de fédération à l’aide des applets de commande Windows PowerShell

Découverte des partenaires de fédération peut être gérée à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Pour activer la découverte des partenaires de fédération

  - Pour activer la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur True ($True). Notez que vous devez activer DNS SRV routage afin de modifier la valeur de cette propriété.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Pour désactiver la découverte des partenaires de fédération

  - Pour désactiver la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à False ($False) :
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

