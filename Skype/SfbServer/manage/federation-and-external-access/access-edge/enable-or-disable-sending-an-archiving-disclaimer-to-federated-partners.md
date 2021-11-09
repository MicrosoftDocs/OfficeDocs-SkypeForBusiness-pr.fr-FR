---
title: Activation ou désactivation de l’envoi d’une notification d’exclusion aux partenaires fédérés relative à l’archivage
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
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
description: Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Skype Entreprise Server.
ms.openlocfilehash: cbdfe6a53df73c5af3ef8d4b07b1bd2a4fc27a0a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861351"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Skype Entreprise Server

Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la notification d’exclusion relative à l’archivage doit être automatiquement envoyée aux partenaires fédérés. Si vous archivez des communications externes, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage. Utilisez la procédure de cette rubrique pour modifier cette configuration.

> [!NOTE]
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Pour activer ou désactiver l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, sous **Autoriser les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** pour activer ou désactiver l’envoi automatique d’une notification d’exclusion relative à l’archivage.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations sur le contrôle d’accès pour des domaines fédérés spécifiques, voir Configurer la prise en charge des [domaines externes autorisés.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la clause d’exclusion de responsabilité d’archivage à l’aide Windows PowerShell cmdlets

L’utilisation de la clause d’exclusion de responsabilité d’archivage peut être gérée à l’aide Windows PowerShell et de la cmdlet Set-CsAccessEdgeConfiguration'archivage. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Pour activer la clause d’exclusion de responsabilité d’archivage

  - Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Pour désactiver la clause d’exclusion de responsabilité d’archivage

  - Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

