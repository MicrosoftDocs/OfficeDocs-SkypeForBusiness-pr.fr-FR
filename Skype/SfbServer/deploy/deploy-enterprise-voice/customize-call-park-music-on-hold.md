---
title: Personnalisation de l’attente musicale du parc d’appel dansSkype pour les entreprises
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnalisez la musique d’attente musicale du parc Skype Entreprise Server Voix Entreprise.
---

# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personnalisation de l’attente musicale du parc d’appel dansSkype pour les entreprises
 
Personnalisez la musique d’attente musicale du parc Skype Entreprise Server Voix Entreprise.
  
Vous pouvez spécifier votre propre fichier de musique à utiliser pour l’attente musicale, au lieu du fichier de musique par défaut qui est Skype Entreprise Server. Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Si vous personnalisez l’attente musicale et que vous souhaitez la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site qui exécute l’application de parcage d’appel. 
  
### <a name="to-customize-the-music-file"></a>Pour personnaliser le fichier de musique

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Exécuter : 
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilisez l’applet de commande **Get-CsService** pour identifier le service. Pour plus d’informations, [voir Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps). 
  
    L’exemple suivant montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous la forme d’un tableau d’octets et l’affecter à une variable. Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel. Pour plus d’informations, [voir Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)