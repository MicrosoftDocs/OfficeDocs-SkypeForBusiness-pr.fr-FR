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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 2478d1f0a8b09fc8d2eff0f3131ad703a3bd72bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919527"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Activer ou désactiver l’envoi d’une notification d’exclusion d’archivage aux partenaires fédérés dans Skype pour Business Server

Au moment où vous déployé vos serveurs de périphérie et activé la fédération pour votre organisation, doit avoir spécifié s’il faut automatiquement envoyer la notification d’exclusion d’archivage aux partenaires fédérés. Si vous archivez les communications externes, vous devez activer l’envoi d’une notification d’exclusion d’archivage. Utilisez la procédure de cette rubrique pour modifier cette configuration.

> [!NOTE]
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre organisation. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Pour activer ou désactiver l’envoi d’une notification d’exclusion d’archivage aux partenaires fédérés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, cliquez sur **Configuration du serveur Edge d’accès**.

4.  Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la Configuration Edge accès**, sous **Activer les communications avec les utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer l’archivage de notification d’exclusion aux partenaires fédérés** pour activer ou désactiver l’envoi de l’archivage automatique notification d’exclusion.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations sur le contrôle d’accès pour des domaines fédérés spécifiques, voir [Configure prise en charge pour les domaines externes autorisés](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la notification d’exclusion d’archivage à l’aide des applets de commande Windows PowerShell

L’utilisation de la notification d’exclusion d’archivage peut être gérée à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Pour activer la notification d’exclusion d’archivage

  - Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Pour désactiver la notification d’exclusion d’archivage

  - Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


