---
title: Gestion des paramètres Response Group au niveau de l’application dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestion des paramètres Response Group au niveau de l’application, tels que les paramètres d’attente musicale et de rappel, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 7ac6b9e03f8a738baa5bb41bac858da1ce057c8b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839666"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gestion des paramètres Response Group au niveau de l’application dans Skype Entreprise
 
Gestion des paramètres Response Group au niveau de l’application, tels que les paramètres d’attente musicale et de rappel, Skype Entreprise Server Voix Entreprise.
  
Les paramètres au niveau de l’application Response Group incluent la configuration de l’attente musicale par défaut, le fichier audio d’attente musicale par défaut, la période de grâce de rappel de l’agent et la configuration du contexte de l’appel. Vous pouvez définir un seul jeu de paramètres de niveau application par pool. Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration**. Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration**.
  
L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.
  
### <a name="to-modify-response-group-application-level-settings"></a>Pour modifier les paramètres au niveau de l’application Response Group

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Par exemple :
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Pour spécifier un fichier audio à utiliser comme attente musicale par défaut, vous devez d’abord importer le fichier audio. Par exemple :
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Voir aussi

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)