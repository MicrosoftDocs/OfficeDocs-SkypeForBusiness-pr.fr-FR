---
title: Démarrer une audioconférence par téléphone sans code confidentiel dans Teams
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
description: 'Découvrez comment activer ou désactiver l’accès des appelants anonymes à une réunion à partir du Teams d’administration. '
ms.openlocfilehash: 2937ebc2c8ddec830c6eb130fc5824ed8273a9d3
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055704"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Démarrer une audioconférence par téléphone sans code confidentiel dans Microsoft Teams

Il peut être frustrant pour des utilisateurs qui se sont appelés à une réunion d’être placés dans la salle d’accueil de la réunion à l’écoute de la musique, car l’organisateur de la réunion Microsoft Teams n’a pas commencé la réunion.
  
Si l’organisateur de la réunion appelle la réunion, un code confidentiel est requis par défaut pour commencer une réunion. Vous pouvez configurer de sorte que tout le monde puisse composer le numéro d’accès à une réunion sans être invité à composer un code confidentiel pour commencer la réunion. Vous pouvez utiliser le Centre d’administration pour activer ou désactiver ce paramètre pour un seul utilisateur.
  
Un code confidentiel n’est pas nécessaire pour l’organisateur de la réunion si quelqu’un a commencé la réunion à partir de l Microsoft Teams appeille de messagerie. Un code confidentiel n'est nécessaire que lorsque l'organisateur d'une réunion participe à sa réunion sur un téléphone. Le code confidentiel des réunions est envoyé à l’utilisateur audio lorsqu’il est affecté à la licence **Audioconférence** et activé pour l’audioconférence. Consultez [envoyer un courrier](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) électronique à un utilisateur avec ses informations d’audioconférence et des messages électroniques envoyés automatiquement aux utilisateurs en cas de modification de [leurs paramètres.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Autorisation ou refus des appelants anonymes à participer à une réunion

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le groupe de navigation de gauche, cliquez sur **Utilisateurs.**

2. Sélectionnez un utilisateur dans la liste, puis cliquez sur **Modifier** en haut de la page.

3. A côté de **Conférence Audio**, cliquez sur **Modifier**.

4. Dans le **volet Audioconférence,** les appelants peuvent être la première personne à avoir accès **à une réunion.**

5. Cliquez sur **Appliquer**.

### <a name="using-windows-powershell"></a>Reportez-vous à la rubrique Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio.

Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Si vous voulez réinitialiser le code confidentiel, consultez Réinitialiser le code confidentiel [de l’audioconférence.](reset-the-audio-conferencing-pin-in-teams.md)

- Si l’accès est anonyme ou si vous n’avez pas besoin d’un code confidentiel pour commencer une réunion, est désactivé :

  - Si la réunion n’a pas commencé (il n’y a pas encore de personne dans la réunion) : un appelant sera invité à s’en faire l’organisateur. S’il répond Oui, il est invité à saisir son code confidentiel. Une fois qu’il entre le code confidentiel, la réunion commence et l’utilisateur rejoint la réunion.

  - Si la réunion a déjà démarré (une autre personne a déjà rejoint la réunion) : l’appelant ne recevra pas d'invite, même s'il est l’organisateur, et il ne lui sera pas demandé de code confidentiel ; la réunion a déjà démarré, et il pourra la rejoindre.

- Si l’accès est anonyme ou si vous n’avez pas besoin d’un code confidentiel pour commencer une réunion, est activé :

  - Si la réunion n’a pas démarré (personne n'a encore joint la réunion) : l'organisateur ne sera pas invité et il ne lui sera jamais demandé de saisir son code confidentiel. Étant donné que le paramètre de l’organisateur est définie sur Off, la réunion démarre et les appelants anonymes la rejoignent.

  - Si la réunion a déjà commencé (une autre personne y est déjà), l’appelant ne sera pas invité à en être l’organisateur, et elle ne sera jamais invité à lui demander le code confidentiel. la réunion a déjà commencé et l’appelant la rejointe.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures méthodes pour gérer vos Microsoft 365 vos Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
