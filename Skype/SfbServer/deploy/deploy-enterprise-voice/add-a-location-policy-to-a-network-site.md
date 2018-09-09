---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement E9-1-1 aux sites du réseau dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e8ff532d66531cbe92ca661d9eaa5780e5b9f56c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885741"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server
 
Affecter des stratégies d’emplacement E9-1-1 aux sites du réseau dans Skype pour Business Server Enterprise Voice. 
  
Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans les [stratégies d’emplacement créer Skype pour Business Server](create-location-policies.md) à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **Redmond** .
  
Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :
  
- **Nouvelle-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Pour affecter une stratégie d’emplacement à un site réseau existant

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez les applets de commande suivantes pour modifier un site réseau existant.
    
    Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Pour affecter une stratégie d’emplacement à un nouveau site réseau

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande suivante pour créer un nouveau site réseau.
    
    Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


