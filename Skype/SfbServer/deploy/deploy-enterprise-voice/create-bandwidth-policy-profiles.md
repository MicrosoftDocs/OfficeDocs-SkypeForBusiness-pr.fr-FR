---
title: Créer des profils de stratégie de bande passante dans Skype Entreprise Server
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Créez ou modifiez des stratégies de bande passante, qui sont utilisées Voix Entreprise contrôle d’admission des appels dans Skype Entreprise Server.
ms.openlocfilehash: ac80ebb8b61a763efc0077f267a024a21a359b5d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824844"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Créer des profils de stratégie de bande passante dans Skype Entreprise Server 
 
Créez ou modifiez des stratégies de bande passante, qui sont utilisées Voix Entreprise contrôle d’admission des appels dans Skype Entreprise Server. 
  
Des stratégies de bande passante définissent des restrictions d’utilisation de la bande passante pour des modes audio et vidéo en temps réel. Les stratégies de bande passante sont appliquées aux profils de stratégiebandwidth, qui peuvent être appliqués à plusieurs sites réseau pour le contrôle d’admission des appels.
  
Pour obtenir des instructions sur les limites de bande passante que vous devez définir dans votre déploiement cac, voir [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Les stratégies d’exemple créées lors de la procédure suivante définissent des limites pour l’ensemble du trafic audio, les sessions audio individuelles, l’ensemble du trafic vidéo et les sessions vidéo individuelles. Le profil de stratégie de bande passante « 5Mb_Link » définit par exemple les limites suivantes : 
  
- Limite audio : 2 000 Kbits/s
    
- Limite de session audio : 200 Kbits/s
    
- Limite vidéo : 1 400 Kbits/s
    
- Limite de session vidéo : 700 Kbits/s
    
> [!NOTE]
> La valeur minimum de limite de session audio est 40 Kbits/s La valeur minimum de limite de session vidéo est 100 Kbits/s 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Pour créer des profils de stratégie de bande passante à l’aide de Skype Entreprise Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**
    
2. Pour chaque profil de stratégie de bande passante que vous voulez créer, exécutez l’applet de commande New-CsNetworkBandwidthPolicyProfile. Par exemple, exécutez :
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Pour créer des profils de stratégie de bande passante à l’aide du Panneau de contrôle Skype Entreprise Server

1. Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Profil de stratégie**.
    
4. Cliquez sur **Nouveau**.
    
5. A la page **Nouveau profil de stratégie**, cliquez sur **Nom**, puis tapez un nom pour le profil de stratégie de bande passante.
    
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
