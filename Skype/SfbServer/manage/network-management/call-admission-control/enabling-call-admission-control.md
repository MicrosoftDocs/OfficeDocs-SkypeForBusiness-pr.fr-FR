---
title: Activation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Après avoir configuré le réseau de contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les limites de bande passante."
ms.openlocfilehash: 090b19282ce85289b0e79e09d58646c5bf5e81e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118573"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Activation du contrôle d’admission des appels dans Skype Entreprise Server

Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau CAC, vous devez l’activer pour qu’il applique les limites de bande passante. Pour ce faire, vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Pour activer le contrôle d’accès au contrôle d’accès à partir du Panneau de contrôle Skype Entreprise Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Global**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**.
   
    > [!NOTE]  
    > Un seul réseau peut être configuré pour un déploiement Skype Entreprise Server, il n’y aura donc jamais plus d’une configuration réseau dans la liste. Il n’est pas possible de renommer la configuration Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**, puis cliquez sur **Valider**.

Lorsque vous cliquez sur **Valider**, un test de la configuration est exécuté. La boîte de dialogue **Modifier la configuration globale** se ferme et vous retournez à la page **Globale**. Vous obtiendrez un message d’avertissement si des erreurs ou des incohérences, qui empêcheront la configuration du réseau de fonctionner correctement, sont détectées (par exemple, si chaque région n’est pas connectée aux autres régions via un itinéraire interrégion).

Si vous modifiez la configuration du réseau, vous pouvez exécuter de nouveau la vérification de validation. Pour cela, ouvrez la configuration globale et cliquez sur **Valider**. Vous n’avez pas besoin de désactiver d’abord le CAC : ne désactivez pas la case à cocher et cliquez sur **Valider**. Vous pouvez lancer la vérification à tout moment même si vous ne modifiez pas la configuration.

## <a name="see-also"></a>Voir aussi

[Planifier le contrôle d’admission des appels](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Déploiement du contrôle d’admission des appels](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](/powershell/module/skype/Remove-CsNetworkConfiguration)