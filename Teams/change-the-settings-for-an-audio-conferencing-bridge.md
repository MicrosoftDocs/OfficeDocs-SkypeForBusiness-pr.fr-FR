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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modifiez les paramètres du pont de conférence audio, y compris les notifications d’entrée et de sortie, les noms de téléphone ou les numéros de téléphone, les tonalités et les appels d’invites pour enregistrer leur nom.
ms.openlocfilehash: acebe42e8dbc5707238975c34ce97961c1493d91
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690910"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modifier les paramètres d’un pont d’audioconférence.

Lorsque vous configurez l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone pour vos utilisateurs à partir d’un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Ces numéros de téléphone permettent aux appelants de se connecter à une réunion. Le numéro de téléphone est inclus en bas de l’invitation à la réunion Skype entreprise ou Microsoft Teams.
  
Le pont de conférence répond à un appel et invite l’appelant à utiliser les invites vocales à l’aide d’un standard automatique de réunion, puis, en fonction de vos paramètres, il peut lire les notifications, demander aux appelants d’enregistrer leur nom et de contrôler les paramètres de code confidentiel. Des broches sont fournies aux organisateurs de la réunion pour leur permettre de démarrer une réunion lorsqu’elles ne sont pas à l’aide d’une application Skype entreprise ou Microsoft Teams.

  > [!IMPORTANT]
  > Un code confidentiel est requis uniquement pour l’organisateur de la réunion lorsqu’un utilisateur de l’application Skype entreprise ou Microsoft teams n’a pas encore commencé la réunion. Si tout le monde se connecte à la réunion, le code confidentiel est requis pour l’organisateur de la réunion pour démarrer la réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez à **conférences**  >  **conférences**. 

2. Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**. 

3. Dans le volet **paramètres du pont** , sélectionnez : 
   - **Notifications d’entrée et de sortie de réunion** Si vous désactivez cette fonctionnalité, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsqu’une personne entre ou quitte la réunion.
    
     Lorsque vous activez les **notifications d’entrée et de sortie**de la réunion, vous pouvez sélectionner les options suivantes :
    
   - **Nom ou numéro de téléphone** Lorsqu’un utilisateur appelle pour rejoindre une réunion, son numéro de téléphone est diffusé lorsqu’il rejoint la réunion.
    
   - **Tonalités** Lorsque des utilisateurs se connectent à une réunion, une sonnerie est diffusée quand ils la rejoignent.
      
   - **Demander aux appelants d’enregistrer leur nom avant de participer à la réunion** Si vous désactivez cette fonctionnalité, les appelants ne seront pas invités à enregistrer leur nom avant de participer à une réunion.

4. Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres souhaité pour le code confidentiel dans la liste **longueur du code confidentiel** .

5. Pour indiquer si vous souhaitez envoyer des courriers électroniques à vos utilisateurs, activez ou désactivez l' **envoi automatique de messages électroniques aux utilisateurs en cas de modification de la configuration**de votre audioconférence.
    Pour plus d’informations, voir [messages électroniques envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence audio sont modifiés dans Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
 
6. Cliquez sur **Enregistrer**. 


## <a name="an-icon-showing-the-skype-for-business-logo--using-the-skype-for-business-admin-center"></a>![Icône illustrant le logo Skype entreprise](media/sfb-logo-30x30.png)  Utilisation du centre d'administration Skype Entreprise

 **Configurer l’interface de réunion lorsque les appelants rejoignent une réunion**
    
1. Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation **Audio conferencing**de gauche, accédez à  >  **paramètres du pont Microsoft**Conferencing.
    
2. Dans la page **paramètres du pont Microsoft** , sous **qualité de participation**à une réunion, sélectionnez :
    
   - **Activer ou désactiver les annonces d'entrée et de sortie des réunions**: cette option est sélectionnée par défaut. Si vous désactivez cette case à cocher, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsqu’une personne entre ou quitte la réunion.
    
   - Lorsque vous sélectionnez **activer ou désactiver les notifications d’entrée et de sortie de la réunion**, vous pouvez sélectionner ces options dans la liste **type d’annonce d’entrée/sortie** :
    
   - **Nom ou numéro de téléphone** Lorsqu’un utilisateur appelle pour rejoindre une réunion, son numéro de téléphone est diffusé lorsqu’il rejoint la réunion.
    
   - **Tonalités** Lorsque des utilisateurs se connectent à une réunion, une sonnerie est diffusée quand ils la rejoignent.
  
   - **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les appelants ne seront pas invités à enregistrer leur nom avant de participer à une réunion.
    
3. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**
  
1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d’administration Microsoft 365**  >  **Skype entreprise**.
    
3. Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche **Audio conferencing**, accédez à  >  **paramètres du pont Microsoft**Conferencing.
    
4. Dans la page **paramètres du pont Microsoft** , sous **sécurité**, entrez le nombre de chiffres souhaités pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.
    
    > [!IMPORTANT]
    > Le code confidentiel doit comporter entre 4 et 12 chiffres. 
  
**Indiquez si vous souhaitez envoyer un courrier électronique à vos utilisateurs.**
  
1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d’administration Microsoft 365**  >  **Skype entreprise**.
    
3. Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche **Audio conferencing**, accédez à  >  **paramètres du pont Microsoft**Conferencing.
    
4. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement les messages électroniques aux utilisateurs en cas de modification de leurs informations de connexion**, puis cliquez sur **Enregistrer**.
    
    Pour plus d’informations, voir [messages électroniques envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence audio sont modifiés dans Microsoft teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser le processus, vous pouvez utiliser l’applet de connexion [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurer l’audioconférence pour Skype entreprise Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
