---
title: Déplacer des utilisateurs Skype Entreprise Server 2019 vers Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et déplacer les utilisateurs vers Teams.'
ms.openlocfilehash: 370b9ba170362168a421377ab2af56c96016271d
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887192"
---
# <a name="move-users-from-on-premises-to-teams"></a>Déplacer des utilisateurs de l’environnement local vers Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Lorsqu’un utilisateur est déplacé de l’local vers Teams Uniquement, le domicile Skype Entreprise de l’utilisateur est déplacé de l’local vers le mode en ligne et teamsUpgradePolicy est affecté à l’utilisateur avec mode=TeamsOnly.  Une fois qu’un utilisateur est déplacé de l’local vers le mode TeamsOnly :

- Tous les appels entrants et conversations en provenance d’autres utilisateurs (qu’ils soient Skype Entreprise ou Teams), arrivent dans le client Teams utilisateur.
- L’utilisateur peut interopérer avec d’autres utilisateurs qui utilisent Skype Entreprise (en ligne ou en local).
- L’utilisateur pourra communiquer avec les utilisateurs des organisations fédérées.
- Les nouvelles réunions prévues par cet utilisateur sont Teams réunions.
- L’utilisateur peut toujours participer à Skype Entreprise réunions.
- Les réunions pré-existantes de l’utilisateur prévues à l’avenir seront migrées de l’local vers Teams.
- Les contacts qui existaient en local sont disponibles Teams peu de temps après la première connexion de l’utilisateur.
- Les utilisateurs ne peuvent pas lancer d’appels ou de conversations Skype Entreprise, ni planifier de nouvelles réunions dans Skype Entreprise. S’ils tentent d’ouvrir Skype Entreprise client, ils sont redirigés vers l’Teams comme indiqué ci-dessous. Si le client Teams n’est pas installé, il est dirigé vers la version web de Teams à l’aide de son navigateur.<br><br>
    ![Message redirigeant un utilisateur vers Teams.](../media/go-to-teams-page.png)

Avant de déplacer des utilisateurs, veillez à passer en revue les conditions préalables pour déplacer les [utilisateurs](move-users-between-on-premises-and-cloud.md#prerequisites) vers le cloud. Assurez-vous également de passer en revue les instructions de migration et d’interopérabilité pour les organisations qui utilisent Teams avec [Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> Le magasin de contacts unifié doit être désactivé sur le compte SfB local pour que le contact soit déplacé vers Teams.

> [!IMPORTANT]
>Lors du déplacement d’un utilisateur de l’local vers le cloud avec Move-CsUser, le mode TeamsOnly est désormais automatiquement affecté aux utilisateurs et leurs réunions sont automatiquement converties en réunions Teams, que le commutateur soit réellement spécifié `-MoveToTeams` ou non. (Cela inclut les migrations de Lync Server 2013, qui n’ont jamais eu le `-MoveToTeams` commutateur.)  Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs passaient du mode d’accueil Skype Entreprise Server local à Skype Entreprise Online, et leur mode était inchangé. Cette situation a récemment été modifiée en vue du retrait de Skype Entreprise Online.


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Déplacer un utilisateur directement de Skype Entreprise local vers Teams uniquement

Les outils d’administration locaux dans Skype Entreprise Server et Lync Server 2013 vous permettent de déplacer les utilisateurs de l’local vers le mode TeamsOnly en une seule étape à l’aide de l’cmdlet Move-CsUser dans PowerShell ou du Panneau de contrôle Skype Entreprise Server, comme décrit ci-dessous. Il n’est plus nécessaire de spécifier le commutateur et le comportement à déplacer directement de l’local vers Teams Seul est désormais automatique, quelle que soit la version de Skype Entreprise Server ou `-MoveToTeams` de Lync Server utilisée. 

Vous devez avoir des privilèges suffisants dans l’environnement local et le service cloud (Microsoft 365 ou Office 365), comme décrit dans Informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Vous pouvez utiliser un seul compte spécifiant des privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype Entreprise Server Management Shell sur site avec des informations d’identification sur site et utiliser le paramètre pour spécifier les informations d’identification d’un Microsoft 365 avec le rôle d’administration `-Credential` nécessaire.

En outre, vous devez vous assurer que l’utilisateur a reçu une licence pour Teams (en plus de Skype Entreprise Online). Ne désactivez pas la licence Skype Entreprise Online.

### <a name="move-to-teams-using-move-csuser"></a>Passer à la Teams à l’aide Move-CsUser

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype Entreprise Server Management Shell ou d’une fenêtre PowerShell Lync Server Management Shell. Pour déplacer un utilisateur en mode TeamsOnly à l’aide de Move-CsUser :
- Spécifiez l’utilisateur à déplacer à l’aide du `Identity` paramètre.
- Spécifiez `-Target` le paramètre avec la valeur « sipfed.online.lync. <span> com ».
- Si vous n’avez pas un compte avec des autorisations suffisantes à la fois sur site et dans le service cloud (Microsoft 365), utilisez le paramètre pour fournir à un compte des `-credential` autorisations suffisantes dans Microsoft 365.
- Si le compte avec des autorisations dans Microsoft 365 ne se termine pas par « onmicrosoft. <span> com « , vous devez spécifier le paramètre, avec la valeur correcte comme `-HostedMigrationOverrideUrl` décrit dans informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La séquence de cmdlet suivante peut être utilisée pour déplacer un utilisateur vers TeamsOnly et suppose que les informations d’identification Microsoft 365 sont un compte distinct et fournies en tant qu’entrée pour l’invite Get-Credential. Le comportement est le même, `-MoveToTeams` que le commutateur soit spécifié ou non.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Comme il existe différentes circonstances nécessitant différents paramètres, la commande par défaut dans la plupart des cas est :

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passer à la Teams à l’aide Skype Entreprise Server panneau de commande

1. Ouvrez l Skype Entreprise Server du Panneau de Skype Entreprise Server.
2. Dans le navigation de gauche, sélectionnez **Utilisateurs.**
3. Utilisez **Find** pour localiser le ou les utilisateurs que vous souhaitez déplacer vers Teams.
4. Sélectionnez le(s) utilisateur(s), puis, dans la liste dropdown **Action** au-dessus de la liste, choisissez Déplacer les utilisateurs sélectionnés vers **Teams** ou Déplacer les utilisateurs sélectionnés vers **Skype Entreprise Online**.   Les deux options déplacent désormais les utilisateurs directement vers TeamsOnly.
5. Dans l'Assistant, cliquez sur **Suivant**.
6. Si vous y êtes invité, connectez-vous Microsoft 365 un compte qui se termine par .onmicrosoft.com et dispose d’autorisations suffisantes.
7. Cliquez **sur** Suivant, puis **sur Suivant** une fois de plus pour déplacer l’utilisateur.
8. Notez que les messages d’état concernant la réussite ou l’échec sont fournis en haut de l’application principale du Panneau de contrôle, et non dans l’Assistant.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Informez Skype Entreprise utilisateurs locaux du déplacement à venir vers Teams

Les outils d’administration locaux dans Skype Entreprise Server 2015 avec CU8, ainsi que dans Skype Entreprise Server 2019, vous permettent d’informer les utilisateurs Skype Entreprise locaux de leur déplacement à venir vers Teams. Lorsque vous activez ces notifications, les utilisateurs voient une notification dans leur client Skype Entreprise (Win32, Mac, web et mobile), comme illustré ci-dessous. Si les utilisateurs **cliquent sur** le bouton Essayer, le client Teams est lancé s’il est installé ; Dans le cas contraire, les utilisateurs seront accédés à la version web de Teams dans leur navigateur. Par défaut, lorsque les notifications sont activées, les clients Win32 Skype Entreprise téléchargent silencieusement le client Teams afin que le client riche soit disponible avant de déplacer l’utilisateur en mode TeamsOnly . Toutefois, vous pouvez également désactiver ce comportement.  Les notifications sont configurées à l’aide de la version sur site de , et le téléchargement en mode silencieux pour les clients Win32 est contrôlé `TeamsUpgradePolicy` via l’cmdlet `TeamsUpgradeConfiguration` sur site.

> [!TIP]
> Certains serveurs devront peut-être redémarrer pour que cela fonctionne Skype Entreprise 2015 avec CU8.

![Notification du déplacement à venir vers Teams.](../media/teams-upgrade-notification.png)

Pour informer les utilisateurs locaux qu’ils seront bientôt mis à niveau vers Teams, créez une instance de TeamsUpgradePolicy avec NotifySfBUsers=true. Affectez ensuite cette stratégie aux utilisateurs que vous souhaitez notifier, soit en attribuant la stratégie directement à l’utilisateur, soit en la fixant au niveau du site, du pool ou au niveau global. Les cmdlets suivantes créent et accordent une stratégie de niveau utilisateur :

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Le téléchargement automatique des Teams via le client Win32 Skype Entreprise est contrôlé via l’cmdlet TeamsUpgradeConfiguration sur site avec le paramètre DownloadTeams. Vous créez cette configuration au niveau global, du site et du pool. Par exemple, la commande suivante crée la configuration pour le site Redmond1 :

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Par défaut, la valeur de DownloadTeams est True ; toutefois, *elle* est honorée uniquement si NotifySfbUser = True pour un utilisateur donné.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistence avec Skype Entreprise](/microsoftteams/coexistence-chat-calls-presence)
