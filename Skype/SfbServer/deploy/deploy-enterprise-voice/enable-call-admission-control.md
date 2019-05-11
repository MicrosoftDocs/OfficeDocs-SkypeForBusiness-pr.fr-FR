---
title: Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: ce50e11d5d8536dba6038a918a9242ad2cfd6f1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892495"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server
 
Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server Enterprise Voice. 
  
Une fois que vous avez configuré vos paramètres réseau pour le déploiement du contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels afin de mettre en œuvre vos stratégies de bande passante.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Pour activer le contrôle d’admission des appels à l’aide de Skype pour Business Server Management Shell

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Exécutez l’applet de commande Set-CsNetworkConfiguration pour activer le contrôle d’admission des appels dans votre réseau. Par exemple, exécutez :
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si vous souhaitez désactiver le contrôle d’admission des appels dans votre réseau, exécutez la commande suivante :
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Pour activer le contrôle d’admission des appels à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Global**.
    
4. Cliquez sur **Global** dans la liste, puis sélectionnez **Afficher les détails** dans le menu **Edition**.
    
5. Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**.
    
    > [!NOTE]
    > Si vous souhaitez désactiver le contrôle d’admission des appels dans tout votre déploiement, désactivez cette case à cocher. 
  
6. Cliquez sur **Valider**. 
    
## <a name="see-also"></a>Voir aussi

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
