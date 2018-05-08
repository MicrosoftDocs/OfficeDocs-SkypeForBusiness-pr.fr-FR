---
title: Gestion des paramètres de Response Group au niveau de l’application dans Skype Entreprise 2015
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestion des paramètres de Response Group au niveau des applications, telles que les paramètres attente musicale et de rappel, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: eaf31904958997561be056da728ff3b0b31f9d8b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business-2015"></a>Gestion des paramètres de Response Group au niveau de l’application dans Skype Entreprise 2015
 
Gestion des paramètres de Response Group au niveau des applications, telles que les paramètres attente musicale et de rappel, dans Skype pour Business Server Enterprise Voice.
  
Paramètres de niveau application pour l’application Response Group incluent la configuration d’attente musicale par défaut, le fichier audio du attente musicale par défaut, la période de grâce de rappel de l’agent et la configuration de contexte d’appel. Vous pouvez définir un seul ensemble de paramètres de niveau application par pool. Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration** . Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration** .
  
L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.
  
### <a name="to-modify-response-group-application-level-settings"></a>Pour modifier les paramètres de niveau application Response Group

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. À partir de la ligne de commande, exécutez la commande suivante :
    
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

#### 

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

