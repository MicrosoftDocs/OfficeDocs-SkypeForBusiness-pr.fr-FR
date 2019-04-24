---
title: Supprimer une collection existante de paramètres de configuration jonction SIP dans Skype pour Business Server
ms.reviewer: ''
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Résumé : Découvrez comment supprimer une collection de paramètres de configuration de jonction à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: da86cbaf45afa47de580c02ab74e3b0b9bb344bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223154"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Supprimer une collection existante de paramètres de configuration jonction SIP dans Skype pour Business Server
 
**Résumé :** Découvrez comment supprimer une collection de paramètres de configuration de jonction à l’aide de la Skype pour le panneau de configuration serveur Business.
  
Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :
  
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
    
- les conditions dans lesquelles les paquets RTCP sont envoyés ;
    
- si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.
    
Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. Cette collection de paramètres globale ne peuvent pas être supprimée. Toutefois, vous pouvez utiliser la Skype pour le panneau de configuration serveur Business ou l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) « réinitialiser » les propriétés dans la collection globale à leurs valeurs par défaut. Par exemple, si vous avez défini la propriété Enable3pccRefer la valeur True, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer est rétabli à sa valeur par défaut False.
  
Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle RTC individuelle). Ces paramètres personnalisés peuvent être supprimés. Lors de la suppression de ces paramètres personnalisés, tenez compte des points suivants :
  
- Si vous supprimez des paramètres étendus à un service, la jonction SIP (Session Initiation Protocol) gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.
    
- Si vous supprimez des paramètres étendus à un site, les jonctions SIP (Session Initiation Protocol) gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration de jonction avec Skype pour le panneau de configuration serveur Business

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales** , puis cliquez sur **Configuration de jonction**.
    
2. Sous l’onglet **Configuration de la jonction**, sélectionnez la collection de paramètres de configuration de jonction SIP (Session Initiation Protocol) à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée et cliquez sur les autres collections à supprimer.
    
3. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
    
4. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
    
5. Dans la boîte de dialogue **Skype pour Business Server le panneau de configuration** , cliquez sur **OK**.
    
6. If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. Lorsque la boîte de dialogue **Skype pour le panneau de configuration serveur Business** s’affiche, cliquez sur **OK**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Suppression des paramètres de Configuration de jonction à l’aide de Skype pour les applets de commande Business Server Management Shell

Vous pouvez supprimer les paramètres de configuration de jonction à l’aide de Skype pour Business Server Management Shell et l’applet de commande **Remove-CsTrunkConfiguration** . Vous pouvez exécuter cette applet de commande que ce soit par le Skype pour Business Server Management Shell ou d’une session à distance de Skype pour Business Server Management Shell.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Pour supprimer une collection de paramètres spécifiée

- La commande ci-dessous supprime les paramètres de configuration de jonction appliqués au site Redmond :
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Pour supprimer toutes les collections appliquées dans l’étendue du site

- Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée

- La commande ci-dessous supprime tous les paramètres de configuration de jonction pour lesquels la déviation du trafic multimédia est activée :
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .
  

