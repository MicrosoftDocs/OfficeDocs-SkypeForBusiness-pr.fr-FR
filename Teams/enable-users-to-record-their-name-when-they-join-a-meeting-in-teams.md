---
title: Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Découvrez comment autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams.
ms.openlocfilehash: 8583ca92de2544946eb898d128e423b6df62cb24
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012936"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams

Lorsque vous configurez les services d’audioconférence dans Office 365, vous recevrez des numéros de téléphone et ce que l'on appelle un pont de conférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.
  
Le pont de conférence répond à l’appel d’un utilisateur qui compose un numéro pour accéder à la réunion en utilisant un téléphone. Le pont de conférence répond à l’appelant à invites vocales à partir d’un standard automatique et, en fonction de leurs paramètres, peut diffuser les notifications, poser aux appelants à enregistrer leur nom et configurer la sécurité du code confidentiel pour les organisateurs de réunions. Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion. Toutefois, vous pouvez configurer il afin d’un code confidentiel n’est pas nécessaire pour démarrer une réunion.

  
## <a name="set-whether-callers-should-record-their-name"></a>Définir si les appelants doivent enregistrer leur nom

1. Accédez à des **réunions**dans le Microsoft Teams & Skype pour la navigation de gauche, du centre d’administration Business > **Ponts de conférence**. 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).

4. Si vous activez les notifications, sélectionnez **Names or phone numbers** (Noms ou numéros de téléphone) sous **Type d’annonces entrée-sortie**, et activez l’option **Ask callers to record their name before joining a meeting** (Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion).

6. Cliquez sur **Enregistrer**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
