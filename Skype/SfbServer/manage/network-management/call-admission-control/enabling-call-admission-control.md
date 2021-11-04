---
title: Activation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: " Après avoir configuré le réseau de contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les limites de bande passante."
ms.openlocfilehash: 723578d37d8094e53ed9e4f9505984e43b1f3b3d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750203"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Activation du contrôle d’admission des appels dans Skype Entreprise Server

Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible. Après avoir configuré le réseau CAC, vous devez l’activer pour qu’il applique les limites de bande passante. Vous pouvez utiliser le Panneau de Skype Entreprise Server pour ce faire.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Pour activer le contrôle d’accès au contrôle d’Skype Entreprise Server le Panneau de bord

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

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