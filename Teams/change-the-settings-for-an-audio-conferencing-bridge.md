---
title: Modifier les paramètres d’un pont d’audioconférence.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modifiez les paramètres du pont de conférence audio, y compris les notifications d’entrée et de sortie, appelez les appelants et appelez-les pour enregistrer leur nom.
ms.openlocfilehash: 0c64fa8c8717ae7fd401c4476896e6e52e833769
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537045"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modifier les paramètres d’un pont d’audioconférence.

Lors de la configuration de l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone pour vos utilisateurs, ainsi qu’un « pont de conférence audio ». Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Ces numéros de téléphone sont utilisés lorsque les appelants appellent une réunion. Le numéro de téléphone est inclus dans la partie inférieure de l Skype Entreprise ou Microsoft Teams’invitation à la réunion.
  
Le pont de conférence répond à un appel et invite l’appelant à lire les invites vocales à l’aide d’un employé de la réunion automatique de la réunion, puis, selon vos paramètres, il peut lire les notifications, demander aux appelants d’enregistrer leur nom et de contrôler les paramètres du code confidentiel. Les piN sont attribués aux organisateurs de la réunion pour leur permettre de démarrer une réunion lorsqu’ils n’utilisent pas une application Skype Entreprise ou Microsoft Teams réunion.

  > [!IMPORTANT]
  > Un code confidentiel n’est nécessaire pour l’organisateur de la réunion que si Skype Entreprise ou un Microsoft Teams d’application n’a pas encore commencé la réunion. Si tout le monde compose un numéro pour se rendre à la réunion, le code confidentiel est nécessaire pour que l’organisateur puisse commencer la réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

##  <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigateur de gauche, allez sur **des ponts de conférence**  >  **Réunions.** 

2. En haut de la page **Ponts de conférence,** cliquez **sur Paramètres du pont.** 

3. Dans le **volet Paramètres du** pont, sélectionnez : 
   - **Notifications d’entrée et de sortie des réunions** Si vous la désactiver, les utilisateurs qui ont déjà rejoint la réunion ne seront pas informés de l’arrivée ou du départ d’une personne.
    
     Lorsque vous activerez les **notifications d’entrée et de sortie** des réunions, vous pouvez sélectionner ces options :
    
   - **Noms ou numéros de téléphone** Lorsque les utilisateurs appellent pour rejoindre une réunion, leur numéro de téléphone est joué lorsqu’ils la rejoignent.
    
   - **Sonnerie** Lorsque les utilisateurs composent un numéro pour rejoindre une réunion, une sonnerie est sonore lorsqu’ils la rejoignent.
      
   - **Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion** Si vous la désactiver, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre une réunion.

4. Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste des longueurs **du** code confidentiel.

5. Pour indiquer si vous envoyez des courriers électroniques à vos utilisateurs, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leur configuration d’audioconférence.**
    Consultez les messages électroniques envoyés automatiquement aux utilisateurs en cas de modification de leurs [paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change-in-teams.md) dans Microsoft Teams ou les messages électroniques envoyés aux utilisateurs lorsque leurs [paramètres](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) changent dans Skype Entreprise Online pour plus d’informations.
 
6. Cliquez sur **Enregistrer**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l’cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d'administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Sujets associés

[Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurer l’audioconférence pour Skype Entreprise Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)