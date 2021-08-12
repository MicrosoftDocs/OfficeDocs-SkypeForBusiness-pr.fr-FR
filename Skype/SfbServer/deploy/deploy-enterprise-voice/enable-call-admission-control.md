---
title: Activer le contrôle d’admission des appels dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Activez le contrôle d’admission des appels Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 65c9ea2e4732ca4c2c069479826f353a9a2dabf82d6eee35c6feaf1c14391ddd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281197"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Activer le contrôle d’admission des appels dans Skype Entreprise Server
 
Activez le contrôle d’admission des appels Skype Entreprise Server Voix Entreprise. 
  
Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Pour activer le contrôle d’admission des appels à l’aide Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Pour activer le contrôle d’admission des appels à l’Skype Entreprise Server panneau de commande

1. Ouvrez Skype Entreprise Server panneau de contrôle.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Global**.
    
4. Cliquez sur **Global** dans la liste, puis sélectionner **Afficher les détails** dans le menu **Edition**.
    
5. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.
    
    > [!NOTE]
    > Si vous souhaitez désactiver le contrôle d’admission des appels à travers votre déploiement, désactivez cette case à cocher. 
  
6. Cliquez sur **Valider**. 
    
## <a name="see-also"></a>Voir aussi

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)