---
title: Gérer les annonces de rejoindre et de quitter une conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Résumé : Découvrez comment gérer les annonces de participer à une conférence et de laisser des annonces dans Skype Entreprise Server.'
ms.openlocfilehash: 375cd1da4e60ccd9c6d7e4eb2864d49279e3c62a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765482"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gérer les annonces de rejoindre et de quitter une conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les annonces de participer à une conférence et de laisser des annonces dans Skype Entreprise Server.
  
Lorsque des utilisateurs d’appels sortants rejoignent ou quittent une conférence, les application Annonce de conférence peuvent annoncer leur entrée ou leur sortie en nonant une tonalité ou en nonant leurs noms. Vous pouvez modifier le fonctionnement des annonces à l’aide de Skype Entreprise Server Management Shell et de l’cmdlet **Set-CsDialinConferencing** avec les paramètres suivants :
  
- EnableNameRecording : détermine si les participants anonymes sont invités à enregistrer leur nom avant d’accéder à la conférence. La valeur par défaut est « $true », ce qui signifie que les participants anonymes sont invités à donner leur nom avant de participer à une conférence. (Les participants authentifiés ne sont pas tenus d’indiquer leur nom, car leur nom complet est utilisé.)
    
- EntryExitAnnouncementsEnabledByDefault : indique si les annonces sont allumées ou désactivées par défaut. La valeur par défaut est « $false », ce qui signifie qu’aucune annonce n’est effectuée lorsque les participants rejoignent ou quittent une conférence. Lorsqu’il planifie une réunion, l’organisateur peut ignorer ce paramètre.
    
- EntryExitAnnouncementsType : indique l’action prise chaque fois qu’un participant rejoint ou quitte une conférence pour laquelle les annonces sont activées. La valeur par défaut est « UseNames », ce qui signifie qu’une annonce similaire à la suivante est effectuée : « Ken Myer a rejoint la conférence » lorsque les annonces sont activées.
    
Vous pouvez configurer ces paramètres globalement ou au niveau d’un site. (Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Pour modifier le comportement des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Cette cmdlet récupère des informations sur la nécessité pour les participants d’enregistrer leur nom lors de leur participation à une conférence et la façon dont Skype Entreprise Server répond lorsque les participants rejoignent ou quittent une conférence d’accès.
    
4. Exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Dans l’exemple suivant, les paramètres sont configurés au niveau de l’étendue Site pour Redmond. Les annonces sont activées, mais les participants ne sont pas invités à donner leur nom lorsqu’ils rejoignent une conférence. Une tonalité est lus lorsque les participants entrent ou quittent une conférence :
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Pour plus d’informations, y compris la syntaxe et une liste complète des paramètres, voir [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
