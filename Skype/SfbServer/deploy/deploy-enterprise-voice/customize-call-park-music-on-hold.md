---
title: Personnalisation de l’attente musicale du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnaliser la mise en garde d’appels musicale dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 95e332aad7d96c366cfc73ca1bcf3f289b5f14ab
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a>Personnalisation de l’attente musicale du parcage d’appel dans Skype Entreprise 2015
 
Personnaliser la mise en garde d’appels musicale dans Skype pour Business Server Enterprise Voice.
  
Vous pouvez spécifier votre propre fichier de musique à utiliser pour une musique d’attente, plutôt que le fichier de musique par défaut fourni avec Skype pour Business Server. Pour personnaliser une musique d’attente, utilisez la cmdlet **Set-CsCallParkServiceMusicOnHoldFile** .
  
> [!NOTE]
> Si vous personnalisez l’attente musicale et que vous voulez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site qui exécute l’application de parcage d’appel. 
  
### <a name="to-customize-the-music-file"></a>Pour personnaliser le fichier de musique

1. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
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

#### 

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

