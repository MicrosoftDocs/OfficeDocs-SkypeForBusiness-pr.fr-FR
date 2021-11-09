---
title: Activation ou désactivation de la découverte de partenaires de fédération
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la découverte des domaines partenaires fédérés doit être prise en charge automatiquement.
ms.openlocfilehash: 4e425566fb0b8aa463c93f0940582487dabaae3d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830008"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Activer ou désactiver la découverte de partenaires de fédération dans Skype Entreprise Server

Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la découverte des domaines partenaires fédérés doit être prise en charge automatiquement. Utilisez la procédure de cette rubrique pour modifier cette configuration.

> [!NOTE]  
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre entreprise

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, sous **Autoriser les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Activer la découverte du domaine partenaire** pour activer ou désactiver la découverte automatique des domaines partenaires.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, [voir Activer ou désactiver la fédération et la connectivité DE messagerie instantanée publique.](enable-or-disable-federation-and-public-im-connectivity.md) Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir Gérer les domaines fédérés [SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) et Gérer les fournisseurs fédérés [SIP.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la découverte de partenaires de fédération à l’aide Windows PowerShell cmdlets

La découverte des partenaires de fédération peut être gérée à l’Windows PowerShell l'Set-CsAccessEdgeConfiguration cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Pour activer la découverte des partenaires de fédération

  - Pour activer la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à True ($True). Notez que vous devez activer le routage DNS SRV afin de changer la valeur de cette propriété.<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Pour désactiver la découverte des partenaires de fédération

  - Pour désactiver la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à False ($False).<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

