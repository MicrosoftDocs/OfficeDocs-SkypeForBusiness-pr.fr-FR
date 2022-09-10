---
title: Email options lorsque les paramètres d’audioconférence changent
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: 'Découvrez comment activer ou désactiver l’envoi d’e-mails aux utilisateurs par Microsoft Teams lorsque des paramètres tels que les modifications de broche ou le numéro de conférence par défaut sont modifiés dans Teams. '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642105"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams

Les utilisateurs sont automatiquement avertis par e-mail lorsqu’ils sont activés pour l’audioconférence. Toutefois, il peut arriver que vous souhaitiez réduire le nombre d’e-mails envoyés aux utilisateurs de Microsoft Teams. Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.
  
Si vous désactivez l’envoi d’e-mails, les e-mails d’audioconférence ne seront pas envoyés à vos utilisateurs, y compris les e-mails pour le moment où les utilisateurs sont activés ou désactivés pour l’audioconférence, quand leur code confidentiel est réinitialisé et lorsque l’ID de conférence et le numéro de téléphone de conférence par défaut changent.
  
Voici un exemple d’e-mail envoyé aux utilisateurs lorsqu’ils sont activés pour l’audioconférence :
  
![Exemple de message électronique d’audioconférence.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Plusieurs e-mails sont envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour l’audioconférence :

  - Lorsqu’une licence **d’audioconférence** leur est attribuée.

  - Lorsque vous réinitialisez manuellement le code confidentiel de l’audioconférence de l’utilisateur.

  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.

  - Lorsque la licence **d’audioconférence** leur est supprimée.

  - Lorsque le fournisseur d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou **à Aucun**.

  - Lorsque le fournisseur d’audioconférence d’un utilisateur est remplacé par Microsoft.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver l’envoi d’e-mails aux utilisateurs

Vous pouvez utiliser Microsoft Teams ou Windows PowerShell pour activer ou désactiver les e-mails envoyés aux utilisateurs.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Paramètres du pont** , activez ou désactivez **l’envoi automatique d’e-mails aux utilisateurs si leurs paramètres de connexion changent**.

4. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Utilisation de Windows PowerShell

Vous pouvez également utiliser le module Microsoft Teams PowerShell et exécuter :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Rubriques connexes

[E-mails envoyés aux utilisateurs lorsque leurs paramètres d’audioconférence changent](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
