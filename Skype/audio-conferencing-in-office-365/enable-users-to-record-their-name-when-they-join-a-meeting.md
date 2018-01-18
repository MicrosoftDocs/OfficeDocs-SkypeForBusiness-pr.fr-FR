---
title: "Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils joignent une réunion"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: "Apprenez à activer ou à désactiver si les utilisateurs peuvent enregistrer leurs noms lorsqu’ils joignent une réunion "
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils joignent une réunion

Lorsque vous configurez une conférence Audio dans Office 365, vous recevrez les numéros de téléphone et ce que l'on appelle un pont de téléconférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui peuvent être un numéro de téléphone dédiés ou partagés.
  
Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone. Le pont de conférence répond à l’appelant avec des invites vocales de surveillance automatique et ensuite, en fonction de leurs paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN pour les organisateurs de la réunion. Les broches sont donnés aux organisateurs des réunions pour pouvoir démarrer une réunion. Toutefois, vous pouvez configurer un code confidentiel n’est pas requis pour démarrer une réunion.
  
## <a name="set-whether-callers-should-record-their-name"></a>Définir si les appelants doivent enregistrer leur nom

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Sous **l’expérience de jointure de la réunion**, consultez la case à cocher intitulée **Activer l’accès à la réunion et de quitter des notifications pour être activée**.
    
  - **Sélectionné** Vous demandera d’appelants pour enregistrer leur nom avant leur entrée à la réunion. Cette option est sélectionnée par défaut.
    
  - **Désactivée** Les appelants ne seront pas invités à enregistrer leur nom avant leur entrée à la réunion.
    
5. **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
-  Windows PowerShell est la gestion des utilisateurs et les utilisateurs sont autorisés à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l’aide d’un unique point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams](set-up-audio-conferencing.md)

