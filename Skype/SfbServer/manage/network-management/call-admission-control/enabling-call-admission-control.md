---
title: Activation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Après avoir configuré le réseau CAC (Call Admission Control), vous devez activer le CAC pour appliquer les limitations de bande passante."
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817533"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Activation du contrôle d’admission des appels dans Skype Entreprise Server

Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau CAC, vous devez activer le CAC pour appliquer les limitations de bande passante. Pour cela, vous pouvez utiliser le panneau de configuration Skype entreprise Server.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Pour activer le CAC dans le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **Global**.

4.  Dans la page **Global** , cliquez sur configuration **globale** .
   
    > [!NOTE]  
    > Un seul réseau peut être configuré pour n’importe quel déploiement de Skype entreprise Server, de sorte qu’il ne reste jamais plus d’une configuration réseau dans la liste. Vous ne pouvez pas renommer la configuration globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le paramètre global** , activez la case à cocher **activer le contrôle d’admission des appels** , puis cliquez sur **valider**.

Lorsque vous cliquez sur **valider**, vous effectuez un test de la configuration. La boîte de dialogue **modifier les paramètres globaux** se ferme et vous permet de revenir à la page **globale** . Vous recevez un avertissement en cas d’erreurs ou d’éventuelles incohérences détectées dans votre configuration réseau qui empêche celle-ci de fonctionner correctement (par exemple, si chaque région n’est pas connectée à une autre région par le biais d’un itinéraire interrégion).

Si vous apportez des modifications à la configuration de votre réseau, vous pouvez exécuter de nouveau le contrôle de validation en ouvrant la configuration globale et en cliquant sur **valider**. Vous n’avez pas besoin de désactiver le CAC d’abord : laissez la case à cocher activée, puis cliquez sur **valider**. Vous pouvez le faire à tout moment sans apporter de modifications à la configuration.

## <a name="see-also"></a>Voir aussi

[Planification du contrôle d’admission des appels](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Déploiement du contrôle d’admission des appels](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
