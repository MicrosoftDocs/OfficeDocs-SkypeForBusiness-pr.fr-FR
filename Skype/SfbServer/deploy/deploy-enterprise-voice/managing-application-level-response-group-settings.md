---
title: Gestion des paramètres de Response Group au niveau de l’application dans Skype pour les entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestion des paramètres de Response Group au niveau des applications, telles que les paramètres attente musicale et de rappel, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 41daedd21c5d7ea6f210594c66e3f20906ad90a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892334"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gestion des paramètres de Response Group au niveau de l’application dans Skype pour les entreprises
 
Gestion des paramètres de Response Group au niveau des applications, telles que les paramètres attente musicale et de rappel, dans Skype pour Business Server Enterprise Voice.
  
Paramètres de niveau application pour l’application Response Group incluent la configuration d’attente musicale par défaut, le fichier audio du attente musicale par défaut, la période de grâce de rappel de l’agent et la configuration de contexte d’appel. Vous pouvez définir un seul ensemble de paramètres de niveau application par pool. Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration**. Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration**.
  
L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.
  
### <a name="to-modify-response-group-application-level-settings"></a>Pour modifier les paramètres de niveau application Response Group

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis qui prennent en charge Response Group.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Exemple :
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Pour spécifier un fichier audio à utiliser comme attente musicale par défaut, vous devez d’abord importer le fichier audio. Par exemple :
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Voir aussi

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
