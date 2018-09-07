---
title: Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: Learn how to enable or disable whether your users can record their names when they join a meeting in Skype Entreprise Online.
ms.openlocfilehash: 6022d7ebf0e653bc43373cb00faabc207f91562a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850040"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Skype Entreprise Online

> [!Note]
> Si vous souhaitez autoriser les utilisateurs à enregistrer leurs noms dans Teams, Consultez [Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Lorsque vous configurez les services d’audioconférence dans Office 365, vous recevrez des numéros de téléphone et ce que l’on appelle un pont d’audioconférence. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.
  
Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone. Le pont de conférence répond en utilisant une invite vocale à partir d’un standard automatique, puis, selon leurs paramètres, propose des notifications, demande aux appelants d’enregistrer leur nom et, pour les organisateurs de réunions, définit leur sécurité par code confidentiel. Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion. Vous pouvez toutefois le régler de manière à ce qu’aucun code confidentiel ne soit nécessaire pour démarrer une réunion.

## <a name="set-whether-callers-should-record-their-name"></a>Définir si les appelants doivent enregistrer leur nom
    
1. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.
    
2. Sous **Expérience de participation aux réunions**, voir la case nommée **Activer les notifications d’entrée et de sortie de la réunion**.
    
  - **Activé** : les appelants seront invités à enregistrer leur nom avant d’assister à la réunion. Cette fonctionnalité est sélectionnée par défaut.
    
  - **Désactivé** : les appelants ne seront pas invités à enregistrer leur nom avant d’assister à la réunion.
    
3. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser le processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).
    
-  Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu’ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
