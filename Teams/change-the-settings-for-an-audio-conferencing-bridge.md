---
title: Modifier les paramètres pour un pont d'audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir les étapes que vous devez modifier les paramètres d’un pont de conférence qui permet de demander des appelants et recueillir les noms et les codes confidentiels pour les organisateurs de réunion lorsqu’ils utilisent pas Skype pour les applications Microsoft Teams ou de l’entreprise. '
ms.openlocfilehash: 21db05e2b4e5ae4688db86af29fbf7c919293e57
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23785701"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modifier les paramètres pour un pont d'audioconférence

Lorsque vous configurez les services d’audioconférence dans Office 365, vous recevrez des numéros de téléphone pour vos utilisateurs à partir de ce que l'on appelle un pont de conférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone. Ces numéros de téléphone sont utilisés lorsque les appelants se connectent à une réunion. Le numéro de téléphone est inclus en bas de la Skype pour l’invitation à la réunion Microsoft Teams ou de l’entreprise.
  
Le pont de conférence répond à un appel et demande à l’appelant avec les invites vocales à l’aide d’un standard automatique de réunion standard, puis, en fonction de vos paramètres, il peut lire des notifications, poser aux appelants à enregistrer leur nom et contrôler les paramètres de code confidentiel. Codes confidentiels accordées aux organisateurs de réunions pour leur permettre de pour démarrer une réunion lorsqu’ils sont ne sont pas à l’aide un Skype pour l’application Microsoft Teams ou de l’entreprise.

  > [!IMPORTANT]
  > Un code confidentiel est uniquement requis pour l’organisateur lorsqu’une Skype pour l’utilisateur d’application Microsoft Teams ou de l’entreprise n’a pas déjà démarré la réunion. Si tout le monde est qui se connectent à la réunion, le code confidentiel est requis pour l’organisateur de la réunion démarrer la réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![les équipes-logo-30x30.png](media/teams-logo-30x30.png) À l’aide de Skype les équipes Microsoft Business centre d’administration

1. Dans la navigation de gauche, accédez à des **réunions** > **ponts de conférence**. 

2. En haut de la page de **ponts de conférence** , cliquez sur **paramètres du pont**. 

3. Dans le volet **paramètres du pont** , sélectionnez : 
  - **Entrée de réunion et quitter les notifications** Si vous désactivez cette option, les utilisateurs qui ont déjà joint la réunion ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.
    
    Lorsque vous activez **les notifications d’entrée et de sortie de la réunion**, vous pouvez sélectionner ces options :
    
  - **Les noms ou les numéros de téléphone** Lorsque les utilisateurs se connecter à une réunion, son numéro de téléphone sera diffusé lorsqu’ils se joignent à.
    
  - **Tonalités** Lorsque les utilisateurs se connecter à une réunion, une tonalité audio sera diffusée lorsqu’ils se joignent à.
      
  - **Appelants ASK à enregistrer leur nom avant de participer à la réunion** Si vous désactivez cette option, les appelants ne sont pas invités à enregistrer leur nom avant de participer à une réunion.

4. Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** .

5. Pour spécifier s’il faut envoyer un message électronique à vos utilisateurs, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si la configuration de leurs services d’audioconférence**.
    Pour plus d’informations, voir [les messages électroniques envoyés automatiquement aux utilisateurs lorsque les paramètres de conférence Audio changent dans les équipes Microsoft](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [les messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans Skype pour Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
 
6. Cliquez sur **Enregistrer**. 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  Utilisation du centre d'administration Skype Entreprise

 **Configurer l’expérience lorsque les appelants participer à une réunion**
    
1. Dans la **Skype entreprise centre d’administration**, dans le volet de navigation gauche accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
2. Dans la page **paramètres du pont Microsoft** , sous **l’expérience de participation aux réunions**, sélectionnez :
    
  - **Activer ou désactiver les annonces d'entrée et de sortie des réunions**: cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les utilisateurs qui ont déjà joint la réunion ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.
    
  - Lorsque vous sélectionnez **Activer l’accès à la réunion et quitter notifications est activé**, vous pouvez sélectionner ces options dans la liste **type d’entrée/sortie annonce** :
    
   - **Les noms ou les numéros de téléphone** Lorsque les utilisateurs se connecter à une réunion, son numéro de téléphone sera diffusé lorsqu’ils se joignent à.
    
   - **Tonalités** Lorsque les utilisateurs se connecter à une réunion, une tonalité audio sera diffusée lorsqu’ils se joignent à.
  
   - **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les appelants ne sont pas invités à enregistrer leur nom avant de participer à une réunion.
    
3. Après avoir fait vos modifications, cliquez sur **Enregistrer**.
    
**Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft** , sous **sécurité**, entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.
    
    > [!IMPORTANT]
    > Le code confidentiel doit comporter entre 4 et 12 chiffres. 
  
**Sélectionnez s’il faut envoyer un message électronique à vos utilisateurs**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs informations de numérotation changent**, puis cliquez sur **Enregistrer**.
    
    Pour plus d’informations, voir [les messages électroniques envoyés automatiquement aux utilisateurs lorsque les paramètres de conférence Audio changent dans les équipes Microsoft](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [les messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans Skype pour Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l’applet de commande [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer l'audioconférence](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
