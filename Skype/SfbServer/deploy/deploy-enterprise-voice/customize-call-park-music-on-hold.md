---
title: Personnaliser une musique de parcage d’appel d’attente inSkype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnaliser la mise en garde d’appels musicale dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e3d1ccdf70278173bf5a3a448e5330a24879d117
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895432"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personnaliser une musique de parcage d’appel d’attente inSkype pour les entreprises
 
Personnaliser la mise en garde d’appels musicale dans Skype pour Business Server Enterprise Voice.
  
Vous pouvez spécifier votre propre fichier de musique à utiliser pour une musique d’attente, plutôt que le fichier de musique par défaut fourni avec Skype pour Business Server. Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Si vous personnalisez l’attente musicale et que vous voulez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site qui exécute l’application de parcage d’appel. 
  
### <a name="to-customize-the-music-file"></a>Pour personnaliser le fichier de musique

1. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Exécutez :
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilisez l’applet de commande **Get-CsService** pour identifier le service. Pour plus d’informations, voir [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    L’exemple ci-dessous montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous forme de tableau d’octets et l’affecter à une variable. Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel. Pour plus d’informations, voir [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
