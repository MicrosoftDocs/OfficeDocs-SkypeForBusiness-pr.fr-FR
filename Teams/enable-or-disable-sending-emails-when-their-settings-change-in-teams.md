---
title: Options de messagerie électronique en cas de modification des paramètres d’audioconférence
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
description: 'Découvrez comment activer ou désactiver Skype d’envoyer des courriers électroniques aux utilisateurs lorsque des paramètres tels que les modifications d’épingle ou le numéro de conférence par défaut changent dans Microsoft Teams. '
ms.openlocfilehash: 568a42badd375314ee5b29529a53b52b1f6267eb
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055294"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams

Les utilisateurs sont automatiquement avertis par courrier électronique lorsqu’ils sont activés pour l’audioconférence. Toutefois, il peut être possible que vous vouliez réduire le nombre de courriers électroniques envoyés à Microsoft Teams utilisateurs. Dans ce cas, vous pouvez désactiver l’envoi de courriers électroniques.
  
Si vous désactivez l’envoi de courriers électroniques, les messages audioconférences ne seront pas envoyés à vos utilisateurs, y compris les courriers électroniques concernant les moments où les utilisateurs sont activés ou désactivés pour l’audioconférence, la réinitialisation de leur code confidentiel et la modification de l’ID de conférence et du numéro de téléphone de conférence par défaut.
  
Voici un exemple du courrier électronique envoyé aux utilisateurs lorsqu’ils sont activés pour l’audioconférence :
  
![Exemple de message électronique d’audioconférence.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Après avoir activé l’audioconférence, plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation :

  - **Lorsqu’une licence d’audioconférence** leur est affectée.

  - Lorsque vous réinitialisez manuellement le code confidentiel de l’utilisateur pour l’audioconférence.

  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.

  - Lorsque la **licence d’audioconférence** leur est retirée.

  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun.**

  - Lorsque Microsoft est le fournisseur de services d’audioconférence.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs

Vous pouvez utiliser des Microsoft Teams ou Windows PowerShell pour activer ou désactiver le courrier électronique envoyé aux utilisateurs.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page Ponts **de** conférence, cliquez **sur Paramètres du pont.**

3. Dans le **volet Paramètres du** pont, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leurs paramètres de connexion.**

4. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Utilisation de Windows PowerShell

Vous pouvez également utiliser le module Microsoft Teams PowerShell et exécuter :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Rubriques connexes

[Messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
