---
title: Activer ou désactiver les annonces d'entrée et de sortie des réunions
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: 0e15116061d35af39e8010c8e079395aaa7c4a8b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Activer ou désactiver les annonces d'entrée et de sortie des réunions

Lorsque vous configurez une conférence Audio dans Office 365, vous obtiendrez un pont de téléconférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui sera véritablement utilisée pour appeler un Skype pour une réunion commerciale ou Teams de Microsoft. 
  
Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone. Le pont de conférence répond à l’appelant avec des invites vocales à partir d’une surveillance automatique de conférence et ensuite, en fonction de vos paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN. Un code confidentiel est attribué un Skype pour l’organisateur de la réunion commerciale ou Teams de Microsoft, et il permet de démarrer une réunion si elles ne peut pas démarrer la réunion à l’aide d’un Skype pour application métier ou Teams de Microsoft. Vous pouvez, toutefois, définir afin qu’un code PIN n’est pas nécessaire pour démarrer une réunion.
  
## <a name="setting-meeting-join-options"></a>Définir les options de participation à une réunion

**À l’aide de Skype les équipes Microsoft pour Business Admin Center**

1. Dans la navigation de gauche, accédez à des **réunions** > **Les ponts de conférence**. 

2. En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**. 

3. Dans le volet **paramètres du pont** , activer ou désactiver **Activer l’accès à la réunion et de quitter des notifications pour être activée**. Cette fonctionnalité est sélectionnée par défaut. Si vous le désactivez, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
4. Sous **type d’annonce d’entrée et de sortie**, sélectionnez **les noms ou les numéros de téléphone** ou des **tonalités**.
    
5. Activer ou désactiver des **appelants de demander d’enregistrer leur nom avant de rejoindre la réunion**.
    
6. Après avoir apporté vos modifications, cliquez sur **Appliquer**.

Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.
    
1. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
2. Sous **l’expérience de jointure de la réunion**, activez ou désactivez **Activer l’accès à la réunion et de quitter des notifications pour être activée**. Cette fonctionnalité est sélectionnée par défaut. Si vous le désactivez, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
3. Sous **type d’annonce d’entrée et de sortie**, sélectionnez **les noms ou les numéros de téléphone** ou des **tonalités**.
    
4. Activez ou désactivez des **appelants de demander d’enregistrer leur nom avant de rejoindre la réunion**.
    
5. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell a de nombreux avantages de vitesse, de simplicité et de productivité qu’à l’aide du centre d’administration Office 365 tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
