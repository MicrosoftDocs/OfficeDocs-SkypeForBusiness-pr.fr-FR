---
title: Créer des liens de région réseau dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Créer ou modifier des liens de région réseau, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server.
ms.openlocfilehash: f184e18da816bae693fd209a97704681240538e7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965428"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Créer des liens de région réseau dans Skype pour Business Server
 
Créer ou modifier des liens de région réseau, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server. 
  
Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique. Un lien de région réseau crée un lien entre deux régions configurées pour le contrôle d’admission des appels et définit les restrictions de bande passante sur le trafic audio et vidéo entre ces régions.
  
L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC, ainsi qu’un lien entre les régions EMEA et APAC. Chacun de ces liens de région est limité par la bande passante du WAN, comme décrit dans la table d’informations sur la bande passante de lien de région dans [exemple : collecte des conditions requises pour le contrôle d’admission des appels dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Pour créer des liens de région réseau à l’aide de Skype pour Business Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés. Par exemple, exécutez :
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Pour créer des liens de région réseau à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Lien de région**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.
    
6. Cliquez sur **Région réseau n° 1**, puis, dans la liste, cliquez sur la région réseau à lier à la Région réseau n° 2.
    
7. Cliquez sur **Région réseau n° 2**, puis, dans la liste, cliquez sur la région réseau à lier à la Région réseau n° 1.
    
8. Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante à appliquer au lien de région réseau.
    
    > [!NOTE]
    > N’appliquez une stratégie de bande passante que si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien. 
  
9. Cliquez sur **Valider**.
    
10. Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.
    
## <a name="see-also"></a>Voir aussi

[Nouvelle-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)