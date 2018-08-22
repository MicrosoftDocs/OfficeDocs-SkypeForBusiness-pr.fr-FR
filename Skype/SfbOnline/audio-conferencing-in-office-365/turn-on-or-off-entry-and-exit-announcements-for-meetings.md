---
title: Activer ou désactiver l’entrée et quitter des annonces pour les réunions dans Skype pour Business en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490484"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Activer ou désactiver l’entrée et quitter des annonces pour les réunions dans Skype pour Business en ligne

> [!Note]
> Pour plus d’informations sur les annonces d’entrée et de sortie dans Microsoft Teams, voir [Activer ou désactiver les annonces d’entrée et de sortie pour les réunions dans les équipes Microsoft](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Lorsque vous configurez les services d’audioconférence dans Office 365, vous obtenez un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que personnes utilisera pour appeler un Skype pour une réunion d’affaires. 
  
Le pont de conférence répond à un appel d’un utilisateur qui est qui se connectent à une réunion à l’aide d’un téléphone. Le pont de conférence répond à l’appelant à invites vocales à partir d’un standard automatique de conférence et, en fonction de vos paramètres, peut diffuser les notifications, poser aux appelants à enregistrer leur nom et configurer la sécurité du code confidentiel. Un code confidentiel est attribué à un Skype pour l’organisateur de la réunion, et vous permet de démarrer une réunion si elles ne peut pas démarrer la réunion à l’aide de la Skype pour l’application de gestion. Vous pouvez, toutefois, l’afin qu’un code confidentiel n’est pas nécessaire de démarrer une réunion.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Définir les options de participation à une réunion
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
2. Sous **l’expérience de participation aux réunions**, activez ou désactivez **Activer l’accès à la réunion et quitter des notifications à être activée**. Cette fonctionnalité est sélectionnée par défaut. Si vous la désactivez, les utilisateurs qui ont déjà joint la réunion ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.
    
3. Sous **type d’entrée/sortie annonce**, sélectionnez les **noms ou les numéros de téléphone** ou des **tonalités**.
    
4. Activez ou désactivez **les appelants Ask à enregistrer leur nom avant de participer à la réunion**.
    
5. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365 tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
