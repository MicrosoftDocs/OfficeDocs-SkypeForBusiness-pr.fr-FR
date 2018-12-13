---
title: Déplacer les utilisateurs locaux vers des équipes
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et de déplacer les utilisateurs à des équipes.'
ms.openlocfilehash: 6bee0562b38ce3119306e23b11ea50ebdb8ac3e9
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244031"
---
# <a name="move-users-from-on-premises-to-teams"></a>Déplacer les utilisateurs locaux vers des équipes

Lorsqu’un utilisateur est déplacé à partir de sur site pour les équipes uniquement, de l’utilisateur Skype pour accueil Business est déplacé sur site vers en ligne et l’utilisateur est affecté TeamsUpgradePolicy avec mode = TeamsOnly.  Après qu’un utilisateur est déplacé sur site vers le mode TeamsOnly :

- Entrant tous les appels et conversations par d’autres utilisateurs (si envoyé à partir de Skype pour les équipes ou de l’entreprise), sera atteindre dans le client de l’utilisateur équipes.
- L’utilisateur sera en mesure d’interagir avec d’autres utilisateurs qui utilisent Skype pour les entreprises (en ligne ou sur site). 
- L’utilisateur sera en mesure de communiquer avec les utilisateurs des organisations fédérées.
- Nouvelles réunions planifiées par l’utilisateur sont des réunions d’équipes.
- Utilisateur peut tout de même rejoindre n’importe quel Skype pour les réunions d’entreprise.
- Réunions existant de l’utilisateur planifiées pour l’avenir seront migrées sur site à Skype pour Business Online.
- Contacts qui existaient dans les locaux sont disponibles dans les équipes peu de temps une fois que l’utilisateur se connecte pour la première fois.
- Les utilisateurs ne peuvent pas lancer des appels ou des conversations de Skype pour les entreprises, ni peuvent qu’ils planifient des réunions dans Skype pour les entreprises. S’ils essaient d’ouvrir le Skype pour client d’entreprise, ils sont redirigés pour utiliser des équipes comme indiqué ci-dessous. Si le client équipes n’est pas installé, ils sont dirigés vers la version web des équipes à l’aide de leur navigateur.<br><br>
    ![Redirection d’un utilisateur aux équipes de message](../media/go-to-teams-page.png)

Avant de déplacer des utilisateurs, veillez à consulter les [conditions requises](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer des utilisateurs vers le nuage. Assurez-vous également vérifier la [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Il existe deux méthodes pour déplacer un utilisateur à partir de sur site aux équipes :

- Si vous utilisez une version antérieure à Skype pour Business Server 2015 CU8, le déplacement nécessite deux étapes (qui peuvent être scriptées à faire dans une seule étape, si vous le souhaitez) :
    - [Déplacer l’utilisateur à partir de Skype pour Business Server (localement) Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
    - Une fois que l’utilisateur est hébergé dans Skype pour l’activité en ligne, affectez l’utilisateur TeamsUpgradePolicy avec mode = TeamsOnly. Pour accorder TeamsOnly mode, exécutez l’applet de commande suivante à partir d’un Skype pour fenêtre Business Online PowerShell :`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Si vous disposez des outils d’administration de Skype pour Business Server 2015 CU8 ou version ultérieure, vous pouvez utiliser la méthode ci-dessus, ou vous pouvez effectuer cette modification en une seule étape, comme indiqué ci-dessous. En outre, vous pouvez éventuellement fournir une notification au sein de la Skype pour client d’entreprise avant de les déplacer vers les équipes uniquement ainsi éventuellement que le client d’équipes en mode silencieux téléchargé par le Skype pour le client Business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Déplacer un utilisateur directement à partir de Skype pour les entreprises dans les locaux pour les équipes uniquement

Les outils d’administration locale dans Skype pour Business Server 2015 avec CU8, ainsi que dans Skype pour Business Server 2019, permettent de déplacer des utilisateurs à partir de localement équipes uniquement en mode en une seule étape à l’aide de l’applet de commande Move-CsUser dans PowerShell ou le Skype pour Se Business rveur avec le panneau de configuration, comme décrit ci-dessous.

### <a name="move-to-teams-using-move-csuser"></a>Déplacer à l’aide de Move-CsUser des équipes

Move-CsUser est disponible à partir d’un Skype locale de fenêtre Business Management Shell PowerShell. Les étapes ci-dessous et les autorisations requises sont les mêmes que déplacement d’un utilisateur à Skype pour Business Online, sauf que vous devez également spécifier le commutateur MoveToTeams et vous devez vous assurer que l’utilisateur a également reçu une licence pour les équipes (en plus de Skype pour les entreprises En ligne).

Vous devez disposer de privilèges suffisants dans l’environnement local et le client Office 365, comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un seul compte disposant de privilèges dans les deux environnements, ou vous pouvez démarrer une Skype locale de fenêtre Business Server Management Shell avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier les informations d’identification pour un Office 365 compte doté du rôle d’administration Office 365 nécessaire.

Pour déplacer un utilisateur équipes uniquement en mode à l’aide de Move-CsUser :

- Spécifiez l’utilisateur à déplacer à l’aide de la `Identity` paramètre.
- Spécifiez-paramètre cible avec la valeur « sipfed.online.lync. <span>com ».
- Spécifier la `MoveToTeams` basculer.
- Si vous ne disposez pas d’un compte disposant des autorisations suffisantes dans les locaux et Office 365, utilisez la `-credential` paramètre pour fournir un compte disposant des autorisations suffisantes dans Office 365.
- Si le compte possédant des autorisations dans Office 365 ne se termine pas par « on.microsoft. <span>com », vous devez spécifier le `-HostedMigrationOverrideUrl` paramètre avec la valeur correcte, comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La séquence d’applet de commande suivante peut être utilisée pour déplacer un utilisateur vers TeamsOnly et suppose que les informations d’identification Office 365 est un compte distinct et fourni comme entrée pour l’invite de Get-Credential.

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Déplacer vers les équipes utilisant Skype pour Business Server Control Panel

1.  Ouvrez le Skype pour le contrôle serveur Business application du Panneau de configuration.
2.  Dans la navigation de gauche, choisissez **utilisateurs**.
3.  Utiliser la **recherche** pour localiser les utilisateurs que vous souhaitez déplacer vers les équipes.
4.  Sélectionnez l’ou les utilisateurs, puis, dans la liste déroulante **Action** au-dessus de la liste, cliquez sur **déplacer les utilisateurs sélectionnés aux équipes**.
5.  Dans l’Assistant, cliquez sur **suivant**.
6.  Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et dispose des autorisations suffisantes.
7.  Cliquez sur **suivant**, puis **suivant** une fois plus de déplacer l’utilisateur.
8. Notez que les messages d’état en ce qui concerne la réussite ou l’échec sont fournis dans la partie supérieure de l’application le panneau de configuration principale, pas dans l’Assistant.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Avertir votre Skype pour les utilisateurs locaux professionnels du déplacement aux équipes à venir

Les outils d’administration locale dans Skype pour Business Server 2015 avec CU8, ainsi que dans Skype pour Business Server 2019, permettent de notifier Skype sur site pour les utilisateurs de leur passage à venir aux équipes. Lorsque vous activez ces notifications, les utilisateurs verront une notification dans leur Skype pour client d’entreprise (Win32, Mac, web et mobile) comme indiqué ci-dessous. Si les utilisateurs cliquent sur le bouton **Réessayer** , le client équipes sera lancé s’il est installé ; dans le cas contraire, accédez à la version web d’équipes dans leur navigateur des utilisateurs. Par défaut, lorsque les notifications sont activées, Skype Win32 pour les clients d’entreprise en mode silencieux télécharger l’équipes client afin que le client riche est disponible avant de déplacer l’utilisateur équipes uniquement en mode ; Toutefois, vous pouvez également désactiver ce comportement.  Les notifications sont configurées à l’aide de la version locale de `TeamsUpgradePolicy`, et télécharger en mode silencieux des clients Win32 est contrôlé par le biais de l’environnement local `TeamsUpgradeConfiguration` applet de commande.

![Notification de déplacement à venir aux équipes](../media/teams-upgrade-notification.png)

Pour avertir les utilisateurs locaux qu’ils seront bientôt être mis à niveau aux équipes, créer une nouvelle instance de TeamsUpgradePolicy avec NotifySfBUsers = true. Puis assigner cette stratégie aux utilisateurs auxquels vous souhaitez signaler, en affectant la stratégie directement à l’utilisateur ou en définissant la stratégie au niveau global, pool ou site. Les applets de commande suivantes créer et accorder une stratégie au niveau de l’utilisateur :

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Le téléchargement automatique des équipes via le Skype pour Win32 Business client est contrôlé par le biais de l’applet de commande TeamsUpgradeConfiguration local avec le paramètre DownloadTeams. Vous créez cette configuration sur global, site et au niveau du pool. Par exemple, la commande suivante crée la configuration pour le site Redmond1 :

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

Par défaut, la valeur de DownloadTeams a la valeur True ; Toutefois, il est *uniquement* respecté si NotifySfbUser = True pour un utilisateur donné.


## <a name="see-also"></a>Voir aussi

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistence avec Skype Entreprise](/microsoftteams/coexistence-chat-calls-presence)
