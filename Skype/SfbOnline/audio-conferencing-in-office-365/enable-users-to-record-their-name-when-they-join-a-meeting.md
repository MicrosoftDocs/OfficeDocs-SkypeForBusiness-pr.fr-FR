---
title: Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Skype pour Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Découvrez comment activer ou désactiver si vos utilisateurs peuvent enregistrer leurs noms lorsqu’ils rejoignent une réunion dans Skype pour Business Online.
ms.openlocfilehash: b920f0cfea6aa607f5bc3ea7c8a53b5668ba02da
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490724"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Skype pour Business Online

> [!Note]
> Si vous souhaitez autoriser les utilisateurs à enregistrer leurs noms dans les équipes, voir [permettent aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans les équipes Microsoft](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Lorsque vous configurez les services d’audioconférence dans Office 365, vous recevrez des numéros de téléphone et ce que l'on appelle un pont de conférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.
  
Le pont de conférence répond à un appel d’un utilisateur qui est qui se connectent à une réunion à l’aide d’un téléphone. Le pont de conférence répond à l’appelant à invites vocales à partir d’un standard automatique et, en fonction de leurs paramètres, peut diffuser les notifications, poser aux appelants à enregistrer leur nom et configurer la sécurité du code confidentiel pour les organisateurs de réunions. Codes confidentiels accordées aux organisateurs de réunions pour pouvoir démarrer une réunion. Toutefois, vous pouvez configurer il afin d’un code confidentiel n’est pas nécessaire pour démarrer une réunion.

## <a name="set-whether-callers-should-record-their-name"></a>Définir si les appelants doivent enregistrer leur nom
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
2. Sous **l’expérience de participation aux réunions**, voir la case à cocher **Activer l’accès à la réunion et quitter des notifications à être activée**.
    
  - **Sélectionné** Les appelants seront invités à enregistrer leur nom avant leur accès à la réunion. Cette fonctionnalité est sélectionnée par défaut.
    
  - **Désactivée** Les appelants ne sont pas invités à enregistrer leur nom avant leur accès à la réunion.
    
3. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser le processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).
    
-  Windows PowerShell est axé sur la gestion des utilisateurs et les utilisateurs sont autorisés à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
