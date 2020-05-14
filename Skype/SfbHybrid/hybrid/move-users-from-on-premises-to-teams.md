---
title: Déplacer des utilisateurs de Skype entreprise Server 2019 vers teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et déplacer des utilisateurs vers Teams.'
ms.openlocfilehash: 7b6925917cff3265280b88979660ad1289a63d12
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221374"
---
# <a name="move-users-from-on-premises-to-teams"></a>Déplacer des utilisateurs de l’environnement local vers Teams

Quand un utilisateur est déplacé de local vers teams uniquement, le domicile Skype entreprise de l’utilisateur est déplacé de local vers en ligne et l’utilisateur est affecté TeamsUpgradePolicy avec le mode = TeamsOnly.  Une fois qu’un utilisateur est déplacé du mode local au mode TeamsOnly :

- Tous les appels entrants et les conversations provenant d’autres utilisateurs (envoyés par Skype entreprise ou Teams) sont acheminés vers le client teams de l’utilisateur.
- L’utilisateur pourra interagir avec d’autres utilisateurs qui utilisent Skype entreprise (en ligne ou en local).
- L’utilisateur pourra communiquer avec des utilisateurs dans des organisations fédérées.
- Les nouvelles réunions planifiées par cet utilisateur sont des réunions de teams.
- L’utilisateur peut toujours participer à des réunions Skype entreprise.
- Les réunions préexistantes de l’utilisateur planifiées pour le futur seront migrées de l’organisation locale à la version Teams.
- Les contacts qui se trouvaient sur site sont disponibles dans teams peu de temps après que l’utilisateur se connecte pour la première fois.
- Les utilisateurs ne peuvent pas initier des appels ou des conversations à partir de Skype entreprise, ni planifier de nouvelles réunions dans Skype entreprise. S’ils essaient d’ouvrir le client Skype entreprise, ils seront redirigés pour utiliser teams comme indiqué ci-dessous. Si le client teams n’est pas installé, il sera dirigé vers la version Web de teams à l’aide de son navigateur.<br><br>
    ![Message redirection d’un utilisateur vers teams](../media/go-to-teams-page.png)

Avant de déplacer des utilisateurs, veillez à passer en revue les [éléments prérequis](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer les utilisateurs vers le Cloud. Veillez également à consulter les [conseils de migration et d’interopérabilité pour les organisations qui utilisent teams avec Skype entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> Le magasin de contacts unifié doit être désactivé sur le compte SfB local du contact à déplacer vers Teams.


Il existe deux méthodes pour déplacer un utilisateur de l’organisation locale vers teams :

- Si vous utilisez une version antérieure à Skype entreprise Server 2015 CU8, le déplacement nécessite deux étapes (qui peuvent être regroupées en une seule étape, si vous le souhaitez) :
  - [Déplacez l’utilisateur de Skype entreprise Server (en local) vers Skype entreprise Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Une fois que l’utilisateur est hébergé dans Skype entreprise Online, affectez à l’utilisateur TeamsUpgradePolicy le mode = TeamsOnly. Pour accorder le mode TeamsOnly, exécutez l’applet de commande suivante à partir d’une fenêtre PowerShell de Skype entreprise Online :`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Si vous avez des outils d’administration de Skype entreprise Server 2015 CU8 ou version ultérieure, vous pouvez utiliser la méthode ci-dessus ou effectuer ce déplacement en une seule étape, comme décrit ci-dessous. En outre, vous pouvez également fournir une notification au sein du client Skype entreprise avant de les transférer vers teams uniquement et, éventuellement, le client teams téléchargé en silence par le client Skype entreprise.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Déplacer un utilisateur directement de Skype entreprise local vers teams uniquement

Les outils d’administration sur site de Skype entreprise Server 2015 avec CU8, ainsi que dans Skype entreprise Server 2019, vous permettent de déplacer des utilisateurs de l’organisation locale vers le mode teams uniquement en une seule étape à l’aide de l’applet de commande Move-CsUser dans PowerShell ou du panneau de configuration de Skype entreprise Server, comme décrit ci-dessous.

### <a name="move-to-teams-using-move-csuser"></a>Passer à teams à l’aide de Move-CsUser

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype entreprise Management Shell locale. Les étapes ci-dessous et les autorisations requises sont les mêmes que pour le transfert d’un utilisateur vers Skype entreprise Online, à la différence que vous devez également spécifier le commutateur MoveToTeams et que vous devez vous assurer que l’utilisateur bénéficie également d’une licence pour Teams (en plus de Skype entreprise Online).

Vous devez disposer de privilèges suffisants dans l’environnement local et le service Cloud (Microsoft 365 ou Office 365), comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un compte unique doté de privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype entreprise Server Management Shell locale avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier les informations d’identification d’un compte Microsoft 365 ou Office 365 avec le rôle d’administration nécessaire.

Pour déplacer un utilisateur vers le mode teams uniquement à l’aide de Move-CsUser :

- Spécifier l’utilisateur à déplacer à l’aide du `Identity` paramètre.
- Spécifiez le paramètre-Target avec la valeur «sipfed. online. Lync. <span> com».
- Spécifiez le `MoveToTeams` commutateur.
- Si vous ne disposez pas d’un compte disposant d’autorisations suffisantes sur site et sur le service Cloud (Microsoft 365 ou Office 365), utilisez le `-credential` paramètre pour fournir un compte disposant d’autorisations suffisantes dans Office 365.
- Si le compte avec des autorisations dans Microsoft 365 ou Office 365 ne se termine pas par «onmicrosoft. <span> com», vous devez spécifier le `-HostedMigrationOverrideUrl` paramètre, avec la valeur correcte comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La séquence d’applets de commande suivante peut être utilisée pour déplacer un utilisateur vers TeamsOnly et suppose que les informations d’identification Microsoft 365 ou Office 365 sont un compte distinct et fourni comme entrée pour l’invite Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passer à teams à l’aide du panneau de configuration de Skype entreprise Server

1. Ouvrez l’application du panneau de configuration de Skype entreprise Server.
2. Dans le volet de navigation de gauche, choisissez **utilisateurs**.
3. Utilisez **Rechercher** pour localiser le ou les utilisateurs que vous souhaitez déplacer vers Teams.
4. Sélectionnez le ou les utilisateurs, puis, dans la liste déroulante **action** située au-dessus de la liste, sélectionnez **déplacer les utilisateurs sélectionnés vers teams**.
5. Dans l'Assistant, cliquez sur **Suivant**.
6. Si vous y êtes invité, connectez-vous à Microsoft 365 ou Office 365 avec un compte qui se termine par. onmicrosoft.com et qui dispose des autorisations suffisantes.
7. Cliquez sur **suivant**, puis une **nouvelle** fois pour déplacer l’utilisateur.
8. Notez que les messages d’État concernant la réussite ou l’échec sont fournis en haut de l’application principale du panneau de configuration, et non dans l’Assistant.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Informer vos utilisateurs locaux de Skype entreprise du déplacement à venir vers teams

Les outils d’administration sur site de Skype entreprise Server 2015 avec CU8, ainsi que dans Skype entreprise Server 2019, vous permettent d’avertir les utilisateurs Skype entreprise locaux de leur déplacement à venir vers Teams. Lorsque vous activez ces notifications, les utilisateurs voient une notification dans leur client Skype entreprise (Win32, Mac, Web et mobile), comme indiqué ci-dessous. Si les utilisateurs cliquent sur le bouton **essayer** , le client teams est lancé s’il est installé ; dans le cas contraire, les utilisateurs accéderont à la version Web de teams dans leur navigateur. Par défaut, lorsque les notifications sont activées, les clients Win32 Skype entreprise téléchargent le client teams de manière silencieuse afin que le client riche soit disponible avant de passer à l’utilisateur en mode teams uniquement ; Toutefois, vous pouvez également désactiver ce comportement.  Les notifications sont configurées à l’aide de la version locale de `TeamsUpgradePolicy` et le téléchargement en mode silencieux pour les clients Win32 est contrôlé via l’applet de commande locale `TeamsUpgradeConfiguration` .

> [!TIP]
> Il se peut que certains serveurs doivent redémarrer pour que cela fonctionne dans Skype entreprise 2015 avec CU8.

![Notification de déplacement imminent vers teams](../media/teams-upgrade-notification.png)

Pour informer les utilisateurs locaux qu’ils seront bientôt mis à niveau vers Teams, créez une nouvelle instance de TeamsUpgradePolicy avec NotifySfBUsers = true. Affectez ensuite cette stratégie aux utilisateurs que vous souhaitez notifier, soit en affectant directement la stratégie à l’utilisateur, soit en définissant la stratégie au niveau du site, du pool ou du niveau global. Les applets de commande suivantes créent et accordent une stratégie au niveau de l’utilisateur :

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Le téléchargement automatique de teams via le client Win32 Skype entreprise est contrôlé via l’applet de commande locale TeamsUpgradeConfiguration avec le paramètre DownloadTeams. Vous créez cette configuration sur un niveau global, de site et de pool. Par exemple, la commande suivante crée la configuration pour le site Redmond1 :

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Par défaut, la valeur de DownloadTeams est true ; Toutefois, elle n’est honorée *que* si NotifySfbUser = true pour un utilisateur donné.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistence avec Skype Entreprise](/microsoftteams/coexistence-chat-calls-presence)
