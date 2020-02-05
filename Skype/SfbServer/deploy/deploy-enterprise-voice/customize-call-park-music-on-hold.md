---
title: Personnalisation du parc d’appels en attente dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnalisez le parc d’appels en attente dans Skype entreprise Server Voice.
ms.openlocfilehash: 61c82a9ba6c817eb3c61e93ae28d76208855e089
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767737"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Personnalisation du parc d’appels en attente dans Skype entreprise
 
Personnalisez le parc d’appels en attente dans Skype entreprise Server Voice.
  
Vous pouvez spécifier votre propre fichier audio à utiliser pour la musique lors de la mise en attente, au lieu du fichier de musique par défaut fourni avec Skype entreprise Server. Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Si vous personnalisez de la musique pendant l’attente et que vous souhaitez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site exécutant l’application de parc d’appels. 
  
### <a name="to-customize-the-music-file"></a>Pour personnaliser le fichier de musique

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez :
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Utilisez l’applet de commande **Get-CsService** pour identifier le service. Pour plus d’informations, consultez la rubrique [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    L’exemple ci-dessous montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous forme de tableau d’octets et l’affecter à une variable. Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel. Pour plus d’informations, consultez la rubrique [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
