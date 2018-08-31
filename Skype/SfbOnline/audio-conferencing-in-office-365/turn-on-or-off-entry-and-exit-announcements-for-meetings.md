---
title: Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Skype Entreprise Online
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
description: "Découvrez comment activer et désactiver les annonces d'entrée et de sortie d'une réunion Skype Entreprise Online en utilisant centre d'administration Skype Entreprise. "
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779034"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur les annonces d’entrée et de sortie dans Microsoft Teams, voir [Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Lorsque vous configurez les services d’audioconférence dans Office 365, vous obtenez un pont d'audioconférence. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que les personnes pourront utiliser pour rejoindre une réunion Skype Entreprise. 
  
Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone. Le pont de conférence répond en utilisant une invite vocale à partir d'un standard automatique, puis, selon vos paramètres, propose des notifications, demande aux appelants d'enregistrer leur nom et fixe la sécurité par code confidentiel. Un code confidentiel est attribué à l'organisateur de la réunion Skype Entreprise et permet de démarrer une réunion s'il lui est impossible de démarrer la réunion en utilisant l'application Skype Entreprise. Vous pouvez toute fois le régler pour qu'aucun code confidentiel ne soit nécessaire pour débuter une réunion.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Définir les options de participation à une réunion
    
1. Dans le **Centre d'administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.
    
2. Sous **Expérience de participation aux réunions**, activez ou désactivez **Activer les notifications d'entrée et de sortie de la réunion**. Cette fonctionnalité est sélectionnée par défaut. Si vous la désactivez, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsque quelqu'un rejoindra ou quittera la réunion.
    
3. Sous **Type d'annonce d’entrée/sortie**, sélectionnez **Noms ou numéros de téléphone** ou **Tonalités**.
    
4. Activez ou désactivez **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**.
    
5. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
-  Skype Entreprise Online est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 avec un seul point d'administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages en termes de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 seul, par exemple lorsque vous désirez effectuer des modifications de paramètres pour un grand nombre d'utilisateurs. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
