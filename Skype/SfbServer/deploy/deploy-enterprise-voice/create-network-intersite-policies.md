---
title: Créer des stratégies intersite réseau dans Skype Entreprise Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Créez des stratégies intersessants réseau, qui sont utilisées par Voix Entreprise contrôle d’admission des appels dans Skype Entreprise Server.
ms.openlocfilehash: 8e5fb020ece1762868f9d943eb2aad955903b91329d636a981e644b2e9892b67
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338752"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Créer des stratégies intersite réseau dans Skype Entreprise Server
 
Créez des stratégies intersessants réseau, qui sont utilisées par Voix Entreprise contrôle d’admission des appels dans Skype Entreprise Server. 
  
Une stratégie intersessant réseau définit des limites de bande passante entre les sites qui ont des liaisons wan directes entre eux.
  
> [!IMPORTANT]
> Une stratégie intersessant réseau n’est requise que s’il existe un lien direct entre deux sites réseau. 
  
Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque. Ces deux sites nécessitent une stratégie intersessant qui applique un profil de stratégie de bande passante approprié. L’exemple suivant applique le profil 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Pour créer une stratégie intersessant réseau

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Exécutez la cmdlet New-CsNetworkInterSitePolicy pour créer des stratégies intersessants réseau et appliquer un profil de stratégie de bande passante approprié pour deux sites qui ont un lien direct entre les sites. Par exemple, exécutez :
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Répétez l’étape 2 si nécessaire pour créer des stratégies réseau intersessants pour toutes les paires de sites réseau qui ont un lien direct.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)