---
title: "Activer ou désactiver les annonces d’entrée et de sortie pour les réunions"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Apprenez à transformer les entrées et quitter ou désactiver les annonces dans un Skype pour une réunion commerciale en ligne à l’aide de la Skype pour le centre d’administration de Business. "
ms.openlocfilehash: 2298450d28ebb09acb87820b1f8a01cb9196708e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Activer ou désactiver les annonces d’entrée et de sortie pour les réunions

Lorsque vous configurez une conférence Audio dans Office 365, vous obtiendrez un pont de téléconférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui sera véritablement utilisée pour appeler un Skype pour une réunion commerciale ou Teams de Microsoft. 
  
Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone. Le pont de conférence répond à l’appelant avec des invites vocales à partir d’une surveillance automatique de conférence et ensuite, en fonction de vos paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN. Un code confidentiel est attribué un Skype pour l’organisateur de la réunion commerciale ou Teams de Microsoft, et il permet de démarrer une réunion si elles ne peut pas démarrer la réunion à l’aide d’un Skype pour application métier ou Teams de Microsoft. Vous pouvez, toutefois, définir afin qu’un code PIN n’est pas nécessaire pour démarrer une réunion.
  
## <a name="setting-meeting-join-options"></a>Définition des options de jointure de la réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Sous **l’expérience de jointure de la réunion**, activez ou désactivez **Activer l’accès à la réunion et de quitter des notifications pour être activée**. Cette option est sélectionnée par défaut. Si vous le désactivez, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
5. Sous **type d’annonce d’entrée et de sortie**, sélectionnez **les noms ou les numéros de téléphone** ou des **tonalités**.
    
6. Activez ou désactivez des **appelants de demander d’enregistrer leur nom avant de rejoindre la réunion**.
    
7. **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell a de nombreux avantages de vitesse, de simplicité et de productivité qu’à l’aide du centre d’administration Office 365 tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Questions courantes des conférences audio](audio-conferencing-common-questions.md)

