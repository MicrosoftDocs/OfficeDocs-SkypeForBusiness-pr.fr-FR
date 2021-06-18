---
title: Ajouter une stratégie d’emplacement à un site réseau dans Skype Entreprise Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Affecter des stratégies d’emplacement E9-1-1 à des sites réseau dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804274"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Ajouter une stratégie d’emplacement à un site réseau dans Skype Entreprise Server
 
Affecter des stratégies d’emplacement E9-1-1 à des sites réseau dans Skype Entreprise Server Voix Entreprise. 
  
Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans Créer des stratégies d’emplacement dans [Skype](create-location-policies.md) Entreprise Server à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **de Redmond.**
  
Pour plus d’informations sur l’working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Pour affecter une stratégie d’emplacement à un site réseau existant

1. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**
    
2. Exécutez les applets de commande suivantes pour modifier un site réseau existant.
    
    Affectez la stratégie d’emplacement balisé **Redmond** à un site réseau existant nommé **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Pour affecter une stratégie d’emplacement à un nouveau site réseau

1. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**
    
2. Exécutez l’applet de commande suivante pour créer un nouveau site réseau.
    
    Créez un nouveau site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


