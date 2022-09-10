---
title: Modifier les paramètres d’un pont d’audioconférence.
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modifiez les paramètres du pont d’audioconférence, notamment les notifications d’entrée et de sortie, les noms de lecture ou les numéros de téléphone, les tonalités et les appelants d’invite pour enregistrer leur nom.
ms.openlocfilehash: d9853826d9a93c5794017185f561b9d6a6cd1ffb
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641785"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modifier les paramètres d’un pont d’audioconférence.

Lorsque vous configurez l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone pour vos utilisateurs à partir d’un pont d’audioconférence. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Ces numéros de téléphone sont utilisés lorsque les appelants se connecter à une réunion. Le numéro de téléphone est inclus au bas de l’invitation à la réunion Teams.
  
Le pont de conférence répond à un appel et invite l’appelant avec des invites vocales à l’aide d’un standard automatique de réunion, puis, selon vos paramètres, il peut lire des notifications, demander aux appelants d’enregistrer leur nom et contrôler les paramètres du code confidentiel. Les codes confidentiels sont donnés aux organisateurs de réunion pour leur permettre de démarrer une réunion lorsqu’ils n’utilisent pas d’application Microsoft Teams.

  > [!IMPORTANT]
  > Un code confidentiel est requis uniquement pour l’organisateur de la réunion lorsqu’un utilisateur d’application Teams n’a pas encore démarré la réunion. Si tout le monde se présente à la réunion, le code confidentiel est requis pour que l’organisateur de la réunion démarre la réunion.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, accédez aux **ponts de conférence** **Meetings** > .

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Paramètres du pont** , sélectionnez :
   - **Notifications d’entrée et de sortie de réunion** Si vous désactivez cette option, les utilisateurs qui ont déjà rejoint la réunion ne seront pas avertis lorsqu’une personne entre ou quitte la réunion.

     Lorsque vous activez les **notifications d’entrée et de sortie** de réunion, vous pouvez sélectionner les options suivantes :

   - **Noms ou numéros de téléphone** Lorsque les utilisateurs se rendent à une réunion, leur numéro de téléphone est lu lorsqu’ils la rejoignent.

   - **Tons** Lorsque les utilisateurs se rendent à une réunion, un son audio est lu lorsqu’ils la rejoignent.

   - **Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion** Si vous désactivez cette option, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre une réunion.

4. Pour définir la longueur du code confidentiel pour les réunions, sélectionnez le nombre de chiffres souhaité pour le code confidentiel dans la liste de **longueurs de code confidentiel** .

5. Pour spécifier s’il faut envoyer des e-mails à vos utilisateurs, activez ou désactivez **l’envoi automatique de courriers électroniques aux utilisateurs si leur configuration de l’audioconférence change**.
    Pour plus d’informations, consultez [les e-mails envoyés automatiquement aux utilisateurs lorsque leurs paramètres d’audioconférence changent dans Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) .

6. Cliquez sur **Enregistrer**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l’applet de commande [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) .

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell présente de nombreux avantages en termes de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d'administration Microsoft 365, par exemple lorsque vous apportez des modifications de paramètres à de nombreux utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :

  - [Vue d’ensemble de Microsoft Teams PowerShell](teams-powershell-overview.md)

  - [Installer le module Microsoft Teams PowerShell](teams-powershell-install.md)
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)
