---
title: Activation ou désactivation de la découverte de partenaires de fédération
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Au moment où vous avez déployé vos serveurs de périphérie et la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez prendre en charge la découverte automatique des domaines partenaires fédérés.
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818395"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Activer ou désactiver la découverte de partenaires de Fédération dans Skype entreprise Server

Au moment où vous avez déployé vos serveurs de périphérie et la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez prendre en charge la découverte automatique des domaines partenaires fédérés. Suivez la procédure décrite dans cette rubrique pour modifier cette configuration.

> [!NOTE]  
> La procédure suivante suppose que vous avez déjà activé la Fédération pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir [activation ou désactivation de l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **configuration de Microsoft Edge Access**.

4.  Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.

5.  Dans **modification**de la configuration d’un point d’accès, sous **activer les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **activer la découverte** automatique du domaine pour activer ou désactiver la découverte automatique des domaines partenaires.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Skype entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs fédérés. Pour plus d’informations, voir [activer ou désactiver la connectivité de Fédération et de messagerie instantanée publique](enable-or-disable-federation-and-public-im-connectivity.md). Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir [gérer les domaines fédérés SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) et gérer les [fournisseurs fédérés SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la découverte de partenaires de Fédération à l’aide d’applets de cmdlet Windows PowerShell

La découverte des partenaires de Fédération peut être gérée à l’aide de Windows PowerShell et de l’applet de la cmdlet Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Pour activer la découverte des partenaires de Fédération

  - Pour activer la découverte des partenaires de Fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur True ($true). Notez que vous devez activer le routage DNS SRV pour pouvoir modifier cette valeur de propriété.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Pour désactiver la découverte des partenaires de Fédération

  - Pour désactiver la découverte des partenaires de Fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur false ($false) :
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

