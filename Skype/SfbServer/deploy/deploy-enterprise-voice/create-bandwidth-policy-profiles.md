---
title: Créer des profils de stratégie de bande passante dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Créer ou modifier des stratégies de bande passante, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server.
ms.openlocfilehash: 26f0e81d4f148888b9c8f61b774dcd476bd102d5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223514"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Créer des profils de stratégie de bande passante dans Skype pour Business Server 
 
Créer ou modifier des stratégies de bande passante, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server. 
  
Des stratégies de bande passante définissent des restrictions d’utilisation de la bande passante pour des modes audio et vidéo en temps réel. Stratégies de bande passante sont appliqués tobandwidth profils de stratégie, qui peuvent être appliquées à plusieurs sites réseau pour le contrôle d’admission des appels.
  
Pour connaître les limites de bande passante que vous devez dans votre déploiement CAC, voir [planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Les stratégies d’exemple créées lors de la procédure suivante définissent des limites pour l’ensemble du trafic audio, les sessions audio individuelles, l’ensemble du trafic vidéo et les sessions vidéo individuelles. Le profil de stratégie de bande passante « 5Mb_Link » définit par exemple les limites suivantes : 
  
- Limite audio : 2 000 Kbits/s
    
- Limite de session audio : 200 Kbits/s
    
- Limite vidéo : 1 400 Kbits/s
    
- Limite de session vidéo : 700 Kbits/s
    
> [!NOTE]
> La valeur minimum de limite de session audio est 40 Kbits/s. La valeur minimum de limite de session vidéo est 100 Kbits/s. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Pour créer des profils de stratégie de bande passante à l’aide de Skype pour Business Server Management Shell

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Pour chaque profil de stratégie de bande passante que vous voulez créer, exécutez l’applet de commande New-CsNetworkBandwidthPolicyProfile. Par exemple, exécutez :
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Pour créer des profils de stratégie de bande passante à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Profil de stratégie**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouveau profil de stratégie**, cliquez sur **Nom**, puis tapez un nom pour le profil de stratégie de bande passante.
    
6. Cliquez sur **Limite audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions audio combinées.
    
7. Cliquez sur **Limite de session audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session audio individuelle.
    
8. Cliquez sur **Limite vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions vidéo combinées.
    
9. Cliquez sur **Limite de session vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session vidéo individuelle.
    
10. En option, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce profil de stratégie de bande passante.
    
11. Cliquez sur **Valider**.
    
12. Pour finir de créer des profils de stratégie de bande passante pour votre topologie, répétez les étapes 4 à 11 avec des paramètres pour d’autres profils de stratégie de bande passante.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
