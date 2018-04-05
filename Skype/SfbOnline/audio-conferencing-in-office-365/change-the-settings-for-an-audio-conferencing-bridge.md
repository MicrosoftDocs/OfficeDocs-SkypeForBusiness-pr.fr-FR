---
title: Modifier les paramètres d’un pont de conférence de données Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. "
ms.openlocfilehash: d9b80b06a3c52c6ec386a0e5052f1bb71f914650
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modifier les paramètres d’un pont de conférence de données Audio

Lorsque vous configurez une conférence Audio dans Office 365, vous recevrez des numéros de téléphone pour vos utilisateurs à partir de ce que l'on appelle un pont de téléconférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone. Ces numéros de téléphone sont utilisés lorsque les appelants de se connectent à une réunion. Le numéro de téléphone est inclus au bas de la Skype pour l’invitation à une réunion commerciale ou Teams de Microsoft.
  
Le pont de conférence répond à un appel et vous demande de l’appelant avec des invites vocales à l’aide d’un fichier auto réunion standard, puis, selon vos paramètres, peut lire les notifications, demandez les appelants pour enregistrer leur nom et contrôler les paramètres de code PIN. Broches sont indiquées pour les organisateurs de la réunion pour pouvoir démarrer une réunion lorsqu’ils sont ne sont pas à l’aide un Skype pour application métier ou Teams de Microsoft.

  > [!IMPORTANT]
  > Un code PIN n’est requis pour la réunion lorsqu’un Skype pour l’utilisateur d’application métier ou Teams de Microsoft n’a pas déjà commencée. Si tout le monde appelle à la réunion, le code PIN est nécessaire pour l’organisateur de la réunion démarrer la réunion. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modifier les paramètres d’un pont de conférence audio 

### <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a>À l’aide de Skype les équipes Microsoft pour Business Admin Center

1. Dans la navigation de gauche, accédez à des **réunions** > **Les ponts de conférence**. 

2. En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**. 

3. Dans le volet **paramètres du pont** , sélectionnez : 
  - **Activer l’accès à la réunion et de quitter des notifications pour être activé** Si vous désactivez cette option, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
    Lorsque vous sélectionnez **Activer l’accès à la réunion et de quitter des notifications pour être activé**, vous pouvez sélectionner ces options dans la liste **type d’annonce d’entrée et de sortie** :
    
  - **Les noms ou les numéros de téléphone** Lorsque les utilisateurs se connecter à une réunion, son numéro de téléphone sera lu lorsqu’ils joignent l’il.
    
  - **Tonalités** Lorsque les utilisateurs se connecter à une réunion, un signal audio est lu lorsqu’ils joignent l’il.
      
  - **Appelants de demander d’enregistrer leur nom avant de rejoindre la réunion** Si vous désactivez cette option, les appelants ne vous demandera d’enregistrer leur nom avant de participer à une réunion.

4. Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **longueur du code confidentiel** .

5. Pour spécifier s’il faut envoyer un courrier électronique à vos utilisateurs, activer ou désactiver les **Envoyer automatiquement des e-mails aux utilisateurs si leur configuration d’audioconférence change**.
    Pour plus d’informations, reportez-vous à la section [E-mails envoyés automatiquement aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md) .
 
6. Cliquez sur **Appliquer**. 

### <a name="using-skype-for-business-online"></a>À l’aide de Skype pour les entreprises en ligne

 **Configurer l’expérience de réunion lorsque les appelants de joindre une réunion**
    
1. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation gauche atteindre **audioconférence** > **paramètres de pont de Microsoft**.
    
2. Dans la page **paramètres du pont Microsoft** , sous **rencontrer de jointure de la réunion**, sélectionnez :
    
  - **Activer ou désactiver les annonces d'entrée et de sortie des réunions**: cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
    Lorsque vous sélectionnez **Activer l’accès à la réunion et de quitter des notifications pour être activé**, vous pouvez sélectionner ces options dans la liste **type d’annonce d’entrée et de sortie** :
    
  - **Les noms ou les numéros de téléphone** Lorsque les utilisateurs se connecter à une réunion, son numéro de téléphone sera lu lorsqu’ils joignent l’il.
    
  - **Tonalités** Lorsque les utilisateurs se connecter à une réunion, un signal audio est lu lorsqu’ils joignent l’il.
    
    > [!NOTE]
    > L'utilisation de **sonnerie** comme type d'annonce est actuellement disponible pour tous les clients sous forme de fonctionnalité en préversion.
  
  - **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous désactivez la case à cocher, les appelants ne vous demandera d’enregistrer leur nom avant de participer à une réunion.
    
3. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.
  
1. Définition de la longueur du code confidentiel pour les réunions
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft** , sous **sécurité**, entrez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.
    
    > [!IMPORTANT]
    > Le code confidentiel doit comporter entre 4 et 12 chiffres. 
  
**Indiquez si vous souhaitez envoyer un courrier électronique à vos utilisateurs**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft** , sélectionnez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leur configuration d’audioconférence change**, puis cliquez sur **Enregistrer**.
    
    Pour plus d’informations, reportez-vous à la section [E-mails envoyés automatiquement aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l’applet de commande [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer l'audioconférence](set-up-audio-conferencing.md)
