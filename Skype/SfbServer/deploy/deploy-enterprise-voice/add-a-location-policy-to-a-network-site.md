---
title: Ajout d’une stratégie d’emplacement à un site réseau dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement de E9-1-1 pour les sites de réseau de Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>Ajout d’une stratégie d’emplacement à un site réseau dans Skype Entreprise Server 2015
 
Affecter des stratégies d’emplacement de E9-1-1 pour les sites de réseau de Skype pour Business Server Voix Entreprise. 
  
Les exemples suivants montrent comment ajouter la stratégie d’emplacement de **Redmond** définie dans les [stratégies d’emplacement de créer dans Skype pour Business Server 2015](create-location-policies.md) à un site de réseau existant et comment créer un nouveau site de réseau qui utilise le site de **Redmond** stratégie.
  
Pour plus d’informations sur l’utilisation des sites du réseau, consultez la documentation de Communications Server Management Shell pour les applets de commande suivantes :
  
- **Nouvelle-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Ensemble-CsNetworkSite**
    
- **Supprimer-CsNetworkSite**
    
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


