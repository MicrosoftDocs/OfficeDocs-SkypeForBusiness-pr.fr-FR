---
title: Activation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Après avoir configuré l’appel d’admission des appels (CAC) réseau, vous devez activer CAC appliquer les limitations de bande passante."
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228406"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Activation du contrôle d’admission des appels dans Skype Entreprise Server

Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau CAC, vous devez activer CAC appliquer les limitations de bande passante. Vous pouvez utiliser la Skype pour Business Server Control Panel pour effectuer cette opération.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Pour activer CAC à partir de la Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Global**.

4.  Dans la page **globale** , cliquez sur la configuration **globale** .
   
    > [!NOTE]  
    > Seul réseau peut être configuré pour n’importe quel Skype pour le déploiement de serveur d’entreprise, il y aura jamais plus d’une configuration réseau dans la liste. Vous ne pouvez pas renommer la configuration globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale** , activez la case à cocher **Activer le contrôle d’admission des appels** , puis cliquez sur **Valider**.

Lorsque vous cliquez sur **Valider**, vous exécutez un test de la configuration. Ferme la boîte de dialogue **Modifier les paramètres globaux** , vous revenez à la page **Global** . Vous recevrez un avertissement si des erreurs ou des incohérences sont découvertes dans la configuration de votre réseau qui l’empêche de fonctionner correctement (par exemple, si chaque région n’est pas connectée à toutes les autres régions via un itinéraire inter-région).

Si vous apportez des modifications à la configuration de votre réseau, vous pouvez exécuter à nouveau le contrôle de validation en ouvrant la configuration globale et en cliquant sur **Valider**. Vous n’avez pas besoin de désactiver CAC tout d’abord : laissez la case à cocher activée et cliquez sur **Valider**. Vous pouvez le faire à tout moment sans apporter de modifications de configuration.

## <a name="see-also"></a>Voir aussi

[Planification du contrôle d’admission des appels](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Déploiement du contrôle d’admission des appels](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
