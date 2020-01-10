---
title: Création de liens vers les régions de réseau dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Créer ou modifier des liens de région réseau qui sont utilisés par le contrôle d’admission des appels voix entreprise dans Skype entreprise Server.
ms.openlocfilehash: 3c40488c3cbb4d5116f9b242bb198ba20f13bd58
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001734"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Création de liens vers les régions de réseau dans Skype entreprise Server
 
Créer ou modifier des liens de région réseau qui sont utilisés par le contrôle d’admission des appels voix entreprise dans Skype entreprise Server. 
  
Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique. Un lien de région réseau crée un lien entre deux régions configurées pour le contrôle d’admission des appels et définit les restrictions de bande passante sur le trafic audio et vidéo entre ces régions.
  
L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC, ainsi qu’un lien entre les régions EMEA et APAC. Chacun de ces liens de région est limité par la bande passante WAN, comme décrit dans la table des informations de bande passante pour les liaisons de zone, comme [le montre l’exemple ci-dessous : collecter les exigences de contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Pour créer des liaisons de région réseau à l’aide de Skype entreprise Server Management Shell

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés. Par exemple, exécutez :
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Pour créer des liaisons de région réseau à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
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

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
