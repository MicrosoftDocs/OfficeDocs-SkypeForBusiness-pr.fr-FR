---
title: Créer des stratégies inter-sites réseau dans Skype pour Business Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Créer des stratégies inter-sites, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server réseau.
ms.openlocfilehash: 455caaf624c463bdb1c32ca8fbce70c88626c774
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892964"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Créer des stratégies inter-sites réseau dans Skype pour Business Server
 
Créer des stratégies inter-sites, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server réseau. 
  
Une stratégie réseau intersite définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.
  
> [!IMPORTANT]
> Une stratégie réseau intersite est requis *uniquement* s’il existe un lien d’accès direct entre deux sites réseau.
  
Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Pour créer une stratégie réseau intersite

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies réseau intersite et appliquer un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies réseau intersite pour toutes les paires de sites réseau qui présentent un lien d’accès direct.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
