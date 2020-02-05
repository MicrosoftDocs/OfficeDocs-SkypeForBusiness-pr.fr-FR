---
title: Créer des stratégies d’intersite réseau dans Skype entreprise Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Créer des stratégies réseau intersites, qui sont utilisées par le système de contrôle d’admission des appels voix entreprise dans Skype entreprise Server.
ms.openlocfilehash: f24d0ad289d9388c45a5dbd9a31aa60e8c41e357
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767917"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Créer des stratégies d’intersite réseau dans Skype entreprise Server
 
Créer des stratégies réseau intersites, qui sont utilisées par le système de contrôle d’admission des appels voix entreprise dans Skype entreprise Server. 
  
Une stratégie réseau intersite définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.
  
> [!IMPORTANT]
> Une stratégie inter-site réseau est requise *uniquement* s’il existe un lien croisé direct entre deux sites du réseau.
  
Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Pour créer une stratégie réseau intersite

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies réseau intersite et appliquer un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies réseau intersite pour toutes les paires de sites réseau qui présentent un lien d’accès direct.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
