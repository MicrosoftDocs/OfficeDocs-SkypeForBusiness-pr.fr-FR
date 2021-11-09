---
title: Créer des itinéraires interrégion réseau dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Créez ou modifiez des itinéraires interrégion réseau, qui sont utilisés par Voix Entreprise d’admission des appels dans Skype Entreprise Server.
ms.openlocfilehash: 4aa831c33049e2e77a298f96de80d9bad2d296e4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833870"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Créer des itinéraires interrégion réseau dans Skype Entreprise Server
 
Créez ou modifiez des itinéraires interrégion réseau, qui sont utilisés par Voix Entreprise d’admission des appels dans Skype Entreprise Server. 
  
Un itinéraire interrégion réseau définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels nécessite un itinéraire interrégion réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.
  
Alors que les liaisons de région définissent des restrictions de bande passante sur les connexions entre les régions, un itinéraire interrégion détermine le chemin d’accès lié que la connexion traversera d’une région à une autre.
  
Dans l’exemple de topologie, des itinéraires interrégion réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Pour créer des itinéraires interrégion réseau à l’aide Skype Entreprise Server Management Shell

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires. Par exemple, exécutez :
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > L’itinéraire interrégion réseau Amérique du Nord/APAC nécessite deux liaisons de région réseau, car il n’existe aucun lien de région réseau direct entre elles. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Pour créer des itinéraires interrégion réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Itinéraire de région**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouvel itinéraire de** région, cliquez sur **Nom,** puis tapez un nom pour l’itinéraire interrégion réseau.
    
6. Cliquez sur **Région réseau n° 1**, puis cliquez dans la liste sur une région réseau que vous souhaitez acheminer vers la région réseau n° 2.
    
7. Cliquez sur **Région réseau n° 2**, puis cliquez dans la liste sur une région réseau que vous souhaitez acheminer vers la région réseau n° 1.
    
8. Cliquez **sur Ajouter** en **dehors** du champ Liens de région réseau, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire interrégion réseau.
    
    > [!NOTE]
    > Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire. Par exemple, l’itinéraire interrégion réseau Amérique du Nord/APAC nécessite deux liaisons de région réseau, car il n’existe aucun lien de région réseau direct entre elles. 
  
9. Cliquez sur **Valider**.
    
10. Pour terminer la création d’itinéraires interrégion réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres itinéraires interrégion réseau.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)