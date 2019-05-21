---
title: Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280214"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Activation ou désactivation de l’envoi d’une exclusion d’archivage aux partenaires fédérés dans Skype entreprise Server

Lors du déploiement de vos serveurs de périphérie et de la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez envoyer automatiquement l’exclusion de responsabilité aux partenaires fédérés. Si vous archivez des communications externes, vous devez autoriser l’envoi d’une exclusion de responsabilité d’archivage. Suivez la procédure décrite dans cette rubrique pour modifier cette configuration.

> [!NOTE]
> La procédure suivante suppose que vous avez déjà activé la Fédération pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir [activation ou désactivation de l’accès des utilisateurs](enable-or-disable-remote-user-access.md)distants.


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Pour activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage aux partenaires fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **configuration de Microsoft Edge Access**.

4.  Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modification de la configuration d’Access Edge**, sous **activer les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer un courrier électronique d’envoi aux partenaires fédérés** pour activer ou désactiver l’envoi automatique de l’archivage relative.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Skype entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs fédérés. Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir [configurer la prise en charge des domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’exclusion de responsabilité de l’archivage à l’aide d’applets de cmdlet Windows PowerShell

L’utilisation de la clause d’exclusion de responsabilité d’archivage peut être gérée à l’aide de Windows PowerShell et de l’applet de passe Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Pour activer le démenti d’archivage

  - Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Pour désactiver la clause d’exclusion de responsabilité d’archivage

  - Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


