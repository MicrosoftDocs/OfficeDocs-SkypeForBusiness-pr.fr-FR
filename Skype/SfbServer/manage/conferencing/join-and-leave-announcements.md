---
title: Gérer la participation à une conférence et de laisser des annonces dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Résumé : Découvrez comment gérer la participation à une conférence et de laisser des annonces dans Skype pour Business Server.'
ms.openlocfilehash: 33c20319142608f38451a547687bc1bc9eae47d1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371587"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gérer la participation à une conférence et de laisser des annonces dans Skype pour Business Server
 
**Résumé :** Découvrez comment gérer la participation à une conférence et de laisser des annonces dans Skype pour Business Server.
  
Lorsque les utilisateurs rejoignent ou quittent une conférence, l’application d’annonce de conférence peut annoncer leur ouverture ou quitter en lecture d’une tonalité ou indiquant leur nom. Vous pouvez modifier le fonctionnement des annonces à l’aide de Skype pour Business Server Management Shell et l’applet de commande **Set-CsDialinConferencing** avec les paramètres suivants :
  
- EnableNameRecording : détermine si des participants anonymes doivent être invités à enregistrer leur nom ou pas avant de participer à la conférence. La valeur par défaut est « $true », ce qui signifie que les participants anonymes sont invités à donner leur nom avant de participer à une conférence. (Les participants authentifiés ne sont pas tenus d’indiquer leur nom, car leur nom complet est utilisé.)
    
- EntryExitAnnouncementsEnabledByDefault : indique si les annonces sont activées ou désactivées par défaut. La valeur par défaut est « $false », ce qui signifie qu’aucune annonce n’est effectuée lorsque les participants rejoignent ou quittent une conférence. Lorsqu’il planifie une réunion, l’organisateur peut ignorer ce paramètre.
    
- EntryExitAnnouncementsType : indique l’action entreprise à chaque fois qu’un participant rejoint ou quitte une conférence pour laquelle les annonces ont été activées. La valeur par défaut est « UseNames », ce qui signifie qu’une annonce similaire à la suivante est effectuée : « Ken Myer a rejoint la conférence » lorsque les annonces sont activées.
    
Vous pouvez configurer ces paramètres globalement ou au niveau d’un site. (Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Pour modifier le comportement des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

Cette applet de commande extrait des informations sur les participants doivent à enregistrer leur nom en rejoignant une conférence et comment Skype pour Business Server répond lorsque des participants rejoignent ou quittent une conférence rendez-vous.
    
4. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Dans l’exemple ci-dessous, les paramètres sont configurés au niveau du site de Redmond. Les annonces sont activées, mais les participants ne sont pas invités à donner leur nom lorsqu’ils rejoignent une conférence. Une tonalité est émise lorsque les participants rejoignent ou quittent une conférence :
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Pour plus d’informations, notamment la syntaxe et une liste complète des paramètres, voir [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

