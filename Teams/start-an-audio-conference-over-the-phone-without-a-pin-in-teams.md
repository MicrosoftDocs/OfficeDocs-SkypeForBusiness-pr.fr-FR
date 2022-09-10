---
title: Démarrer la conférence audio par téléphone sans code confidentiel dans Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
- seo-marvel-mar2020
description: 'Découvrez comment activer ou désactiver la participation des appelants anonymes à une réunion à partir du Centre d’administration Teams. '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641945"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams

Il peut être frustrant pour les utilisateurs qui se rendent à une réunion de se tenir dans la salle d’attente de la réunion en écoutant de la musique, car l’organisateur de la réunion Microsoft Teams n’a pas démarré la réunion.
  
Si un organisateur de réunion appelle la réunion, par défaut, un code confidentiel est nécessaire pour démarrer une réunion. Vous pouvez la configurer pour que n’importe qui puisse se connecter à une réunion et ne pas être invité à entrer un code confidentiel pour démarrer la réunion. Vous pouvez utiliser le Centre d’administration pour activer ou désactiver ce paramètre pour un seul utilisateur.
  
Un code confidentiel n’est pas nécessaire pour l’organisateur de la réunion si quelqu’un a démarré la réunion à partir de l’application Microsoft Teams. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone. Le code confidentiel des réunions est envoyé à l’utilisateur audio lorsqu’il reçoit la licence **d’audioconférence** et qu’il est activé pour l’audioconférence. Consultez [Envoyer un e-mail à un utilisateur avec ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) et ses [e-mails qui sont automatiquement envoyés aux utilisateurs lorsque leurs paramètres d’audioconférence changent](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Autorisation ou refus des appelants anonymes à participer à une réunion

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**.

2. Sélectionnez un utilisateur dans la liste, puis cliquez sur **Modifier** en haut de la page.

3. A côté de **Conférence Audio**, cliquez sur **Modifier**.

4. Dans le volet **Audioconférence** , activer ou désactiver **les appelants rendez-vous peut être la première personne à participer à une réunion**.

5. Cliquez sur **Appliquer**.

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.

Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous souhaitez réinitialiser le code confidentiel, consultez [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).

- Si l’accès anonyme, ou si vous n’avez pas besoin d’un code confidentiel pour démarrer une réunion, est désactivé :

  - Si la réunion n’a pas démarré (il n’y a personne dans la réunion pour l’instant) : un appelant est invité s’il est l’organisateur ; S’il répond oui, il est invité à entrer son code confidentiel et, une fois qu’il a entré le code confidentiel, la réunion démarre et l’utilisateur rejoint la réunion.

  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.

- Si l’accès anonyme, ou si vous n’avez pas besoin d’un code confidentiel pour démarrer une réunion, est activé :

  - Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel. Étant donné que le paramètre de l’organisateur est désactivé, la réunion démarre et les appelants anonymes rejoignent la réunion.

  - Si la réunion a déjà démarré (quelqu’un d’autre est déjà dans la réunion) : l’appelant n’est pas invité s’il s’agit de l’organisateur et qu’il n’est jamais invité à entrer le code confidentiel; la réunion est déjà démarrée et l’appelant y participera.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Essayer ou acheter l’audioconférence dans Microsoft 365 pour Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
