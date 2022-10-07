---
title: Gérer les paramètres de Messagerie vocale infonuagique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gérer les paramètres de messagerie vocale pour vos utilisateurs.
ms.openlocfilehash: 96ac5e13360463150a5ff21bc8042b701a4f9717
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999489"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>Gérer les paramètres Messagerie vocale infonuagique pour les utilisateurs

Les paramètres de messagerie vocale vous permettent de configurer les paramètres de messagerie vocale pour les utilisateurs individuels.

Avant de configurer les paramètres de messagerie vocale pour vos utilisateurs, vous devez lire [Configurer Messagerie vocale infonuagique](set-up-phone-system-voicemail.md). Pour plus d’informations sur la définition de stratégies pour des groupes d’utilisateurs, consultez [Gérer les stratégies de messagerie vocale](manage-voicemail-policies.md).

Les paramètres par défaut pour Messagerie vocale infonuagique sont les suivants :

- La messagerie vocale est activée.
- La langue d’invite est définie sur la langue préférée de l’utilisateur.
- Le message d’accueil d’absence du bureau est désactivé.
- Le message d’accueil d’absence du bureau, lorsque les réponses automatiques sont définies dans Outlook, est désactivé.
- Le message d’accueil d’absence du bureau, lorsque le calendrier dans Outlook s’affiche en dehors du bureau, est désactivé.
- Le partage des données de messagerie vocale et de transcription avec le service à des fins d’entraînement et d’amélioration de la précision est désactivé.
- La règle de réponse aux appels est définie sur Messagerie vocale régulière.
- Le remplacement de l’invite de message d’accueil par défaut n’est pas défini.
- Le remplacement par défaut de l’invite de message d’accueil d’absence du bureau n’est pas défini.
- La cible de transfert n’est pas définie.


Pour gérer Messagerie vocale infonuagique fonctionnalités pour vos utilisateurs, vous pouvez utiliser le Centre d’administration Teams ou PowerShell. Vos utilisateurs finaux peuvent également configurer ces paramètres dans le client Teams en allant à **Paramètres -> Appels -> Configurer la messagerie vocale.**

## <a name="use-teams-admin-center"></a>Utiliser le Centre d’administration Teams

Dans le Centre d’administration Teams :

1.  Dans le volet de navigation de gauche, accédez à **Utilisateurs > Gérer les utilisateurs** et sélectionnez l’utilisateur.

2.  Dans la page des détails de l’utilisateur, accédez à l’onglet **Messagerie vocale** .

3.  Modifiez les paramètres.

4.  Sélectionnez **Enregistrer**.


## <a name="use-powershell"></a>Utiliser PowerShell

Vous pouvez également utiliser PowerShell pour gérer les paramètres de messagerie vocale comme suit :

- Pour gérer Messagerie vocale infonuagique paramètres pour les utilisateurs individuels, utilisez l’applet de commande [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). 

- Pour afficher les paramètres, utilisez l’applet de commande [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) .

- Vous pouvez désactiver Messagerie vocale infonuagique pour un utilisateur à l’aide de l’applet de commande [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) et en définissant le paramètre VoicemailEnabled sur $false. 

## <a name="voicemail-settings"></a>Paramètres de messagerie vocale

- **Messagerie vocale activée** : ce paramètre détermine si Messagerie vocale infonuagique est activé pour l’utilisateur. Si le paramètre est false, Messagerie vocale infonuagique service n’est pas disponible pour l’utilisateur et n’enregistre pas de messagerie vocale pour l’utilisateur.

- **Langue** de l’invite : ce paramètre spécifie la langue utilisée pour les invites dans le Messagerie vocale infonuagique. Pour plus d’informations, consultez [Modifier la langue par défaut pour les messages d’accueil et les e-mails](change-the-default-language-for-greetings-and-emails.md).

- **Paramètres d’accueil** : Messagerie vocale infonuagique est en mesure de lire un message d’accueil spécifique pour le moment où l’utilisateur se trouve au bureau et pour le moment où l’utilisateur est en dehors du bureau. Les deux messages d’accueil peuvent être enregistrés par l’utilisateur ou un message d’accueil de synthèse vocale peut être utilisé.

  - **Remplacement de l’invite de message d’accueil par défaut** : spécifie le message d’accueil de synthèse vocale qui sera lu au cas où l’utilisateur n’aurait pas enregistré de message d’accueil.

  - **Oof Greeting Enabled** : spécifie si le message d’accueil d’absence du bureau est lu dans le scénario de dépôt de messagerie vocale, quels que soient les paramètres d’Outlook.

  - **Oof Greeting Follow Automatic Replies Enabled** - spécifie s’il faut lire le message d’accueil hors bureau dans le scénario de dépôt de messagerie vocale lorsque l’utilisateur définit des réponses automatiques dans Outlook.

  - **Oof Greeting Follow Calendar Enabled** : spécifie s’il faut lire le message d’accueil hors bureau dans le scénario de dépôt de messagerie vocale lorsque l’utilisateur définit l’absence du bureau dans le calendrier.

  - **Remplacement par défaut de l’invite de message** d’accueil Oof : spécifie le message d’accueil de synthèse vocale qui sera lu si l’utilisateur n’est pas au bureau et n’a pas enregistré de message d’accueil en dehors du bureau.

- **Règle de réponse aux appels** : ce paramètre spécifie la règle de réponse aux appels. La règle peut être :
  - Le service refuse l’appel sans message.
  - Seul le message d’accueil approprié (normal ou hors bureau) est lu.
  - Le message d’accueil approprié (normal ou hors bureau) est lu et l’appelant est transféré vers l’utilisateur ou le numéro de téléphone spécifié.
  -  Le message d’accueil approprié (normal ou hors bureau) est lu et l’appelant peut quitter une messagerie vocale.
  - Le message d’accueil approprié (normal ou hors bureau) est lu, l’appelant peut quitter une messagerie vocale et est autorisé à appuyer sur 0 pour être transféré vers l’utilisateur ou le numéro de téléphone spécifié.

- **Partager des données pour améliorer le service** : spécifie si les données de messagerie vocale et de transcription sont partagées avec le service pour l’entraînement et l’amélioration de la précision. Si la valeur est false, les données de messagerie vocale ne sont pas partagées, quel que soit le choix de l’utilisateur.

- **Transfert d’appel** : spécifie l’utilisateur ou le numéro de téléphone vers lequel l’appelant est transféré.


