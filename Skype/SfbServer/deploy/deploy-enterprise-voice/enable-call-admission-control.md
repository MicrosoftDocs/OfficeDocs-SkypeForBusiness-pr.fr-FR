---
title: Activer le contrôle d’admission des appels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Activez le contrôle d’admission des appels dans Skype entreprise Server Voice.
ms.openlocfilehash: c5fc500b4e0839b4db43bd229087b3a6bcc7e644
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767287"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Activer le contrôle d’admission des appels dans Skype entreprise Server
 
Activez le contrôle d’admission des appels dans Skype entreprise Server Voice. 
  
Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Pour activer le contrôle d’admission des appels à l’aide de Skype entreprise Server Management Shell

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Pour activer le contrôle d’admission des appels à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Global**.
    
4. Cliquez sur **Global** dans la liste, puis sélectionnez **Afficher les détails** dans le menu **Edition**.
    
5. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.
    
    > [!NOTE]
    > Si vous souhaitez désactiver le contrôle d’admission des appels dans tout votre déploiement, désactivez cette case à cocher. 
  
6. Cliquez sur **Valider**. 
    
## <a name="see-also"></a>Voir aussi

[Get-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-Csnetworkconfiguration permettent](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
