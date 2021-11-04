---
title: Créer des liens de région réseau dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Créez ou modifiez des liaisons de région réseau, qui sont utilisées par Voix Entreprise d’admission des appels dans Skype Entreprise Server.
ms.openlocfilehash: dd46e7d7043d7d1814b7a23ac755624af0af4c69
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775794"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Créer des liens de région réseau dans Skype Entreprise Server
 
Créez ou modifiez des liaisons de région réseau, qui sont utilisées par Voix Entreprise d’admission des appels dans Skype Entreprise Server. 
  
Les régions au sein d’un réseau sont liées par le biais d’une connectivité WAN physique. Un lien de région réseau crée un lien entre deux régions configurées pour le contrôle d’admission des appels (CAC) et définit les limites de bande passante sur le trafic audio et vidéo entre ces régions.
  
L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC et un lien entre les régions EMEA et APAC. Chacune de ces liaisons de région est limitée par la bande passante de réseau wan, comme décrit dans le tableau Informations sur la bande passante de lien de région dans l’exemple : Collecte des exigences pour le contrôle d’admission des appels [dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Pour créer des liens de région réseau à l’aide Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Exécutez la cmdlet New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés. Par exemple, exécutez :
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Pour créer des liens de région réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Lien de région**.
    
4. Cliquez sur **Nouveau**.
    
5. Sur la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.
    
6. Cliquez sur **Région réseau n° 1**, puis sur la région réseau dans la liste que vous voulez lier à la Région réseau n° 2.
    
7. Cliquez sur **Région réseau n° 2**, puis sur la région réseau dans la liste que vous voulez lier à la Région réseau n° 1.
    
8. Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante que vous souhaitez appliquer au lien de région réseau.
    
    > [!NOTE]
    > Appliquez une stratégie de bande passante uniquement si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien. 
  
9. Cliquez sur **Valider**.
    
10. Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.
    
## <a name="see-also"></a>Voir aussi

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)