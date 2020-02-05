---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype entreprise Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Attribuez des stratégies d’emplacement E9-1-1 aux sites réseau dans Skype entreprise Server Voice.
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768277"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Ajouter une stratégie d’emplacement à un site réseau dans Skype entreprise Server
 
Attribuez des stratégies d’emplacement E9-1-1 aux sites réseau dans Skype entreprise Server Voice. 
  
Les exemples suivants montrent comment ajouter la stratégie d’emplacement de **Redmond** définie dans [créer des stratégies d’emplacement dans Skype entreprise Server](create-location-policies.md) à un site réseau existant et comment créer un site réseau qui utilise la politique de localisation de **Redmond** .
  
Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Pour affecter une stratégie d’emplacement à un site réseau existant

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez les applets de commande suivantes pour modifier un site réseau existant.
    
    Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Pour affecter une stratégie d’emplacement à un nouveau site réseau

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande suivante pour créer un nouveau site réseau.
    
    Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


