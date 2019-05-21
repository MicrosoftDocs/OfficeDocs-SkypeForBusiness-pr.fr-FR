---
title: Créer des itinéraires réseau interrégionals dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Créez ou modifiez des itinéraires interrégions réseau qui sont utilisés par le contrôle d’admission des appels vocaux d’entreprise dans Skype entreprise Server.
ms.openlocfilehash: aec289143e2b6dd54e2b52cfc231239fe5d73b7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286368"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Créer des itinéraires réseau interrégionals dans Skype entreprise Server
 
Créez ou modifiez des itinéraires interrégions réseau qui sont utilisés par le contrôle d’admission des appels vocaux d’entreprise dans Skype entreprise Server. 
  
Un itinéraire interrégion réseau définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels nécessite un itinéraire interrégion réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.
  
Alors que les liens de région définissent les limitations de bande passante sur les connexions entre les régions, un itinéraire interrégion détermine le chemin lié emprunté par la connexion pour aller d’une région à l’autre.
  
Dans l’exemple de topologie, les itinéraires interrégion réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Pour créer des itinéraires interrégions du réseau à l’aide de Skype entreprise Server Management Shell

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires. Par exemple, exécutez :
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > L’itinéraire interrégion réseau Amérique du Nord/APAC nécessite deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Pour créer des itinéraires interrégions du réseau à l’aide de Skype entreprise Server panneau de configuration

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Itinéraire de région**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouvel itinéraire de région**, cliquez sur **Nom**, puis tapez un nom pour l’itinéraire interrégion réseau.
    
6. Cliquez sur **Région réseau n° 1**, puis, dans la liste, cliquez sur une région réseau à router vers la région réseau n° 2.
    
7. Cliquez sur **Région réseau n° 2**, puis, dans la liste, cliquez sur une région réseau à router vers la région réseau n° 1.
    
8. Cliquez sur **Ajouter** en regard du champ **Liens de région réseau**, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire interrégion réseau.
    
    > [!NOTE]
    > Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire. Par exemple, l’itinéraire interrégion réseau Amérique du Nord/APAC nécessite deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles. 
  
9. Cliquez sur **Valider**.
    
10. Pour terminer la création des itinéraires interrégion réseau pour votre topologie, répétez les étapes 4 à 9 en spécifiant les paramètres correspondant à d’autres itinéraires interrégion réseau.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
