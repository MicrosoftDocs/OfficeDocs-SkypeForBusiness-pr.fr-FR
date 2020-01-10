---
title: Gestion des paramètres du groupe de réponse au niveau de l’application dans Skype entreprise
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestion des paramètres du groupe de réponse au niveau de l’application, tels que les paramètres de musique et de rappel, dans Skype entreprise Server voix entreprise.
ms.openlocfilehash: 4c5964d84e5fb84bf1c20c3e43bb0cc4aa25ae17
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001274"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gestion des paramètres du groupe de réponse au niveau de l’application dans Skype entreprise
 
Gestion des paramètres du groupe de réponse au niveau de l’application, tels que les paramètres de musique et de rappel, dans Skype entreprise Server voix entreprise.
  
Les paramètres au niveau de l’application de l’application Response Group incluent la configuration par défaut de l’attente de musique, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel. Vous pouvez définir un seul ensemble de paramètres de niveau application par pool. Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration**. Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration**.
  
L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.
  
### <a name="to-modify-response-group-application-level-settings"></a>Pour modifier les paramètres au niveau de l’application de Response Group

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Dans la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Exemple :
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Pour spécifier un fichier audio à utiliser comme attente musicale par défaut, vous devez d’abord importer le fichier audio. Par exemple :
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Voir aussi

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Importation-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
