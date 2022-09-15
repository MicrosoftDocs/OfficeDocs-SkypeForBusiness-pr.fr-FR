---
title: Déplacer des utilisateurs de Skype Entreprise Server 2019 vers Teams
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
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et déplacer des utilisateurs vers Teams.'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705843"
---
# <a name="move-users-from-on-premises-to-teams"></a>Déplacer des utilisateurs de l’environnement local vers Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Lorsqu’un utilisateur est déplacé d’un emplacement local vers Teams uniquement, le domicile Skype Entreprise de l’utilisateur est déplacé de l’emplacement local vers le site en ligne, et l’utilisateur se voit attribuer TeamsUpgradePolicy avec mode=TeamsOnly.  Une fois qu’un utilisateur est déplacé d’un emplacement local vers le mode TeamsOnly :

- Tous les appels entrants et conversations provenant d’autres utilisateurs (qu’ils soient envoyés à partir de Skype Entreprise ou Teams) arrivent dans le client Teams des utilisateurs.
- L’utilisateur pourra interagir avec d’autres utilisateurs qui utilisent Skype Entreprise.
- L’utilisateur pourra communiquer avec les utilisateurs des organisations fédérées.
- Les nouvelles réunions planifiées par cet utilisateur sont des réunions Teams.
- L’utilisateur peut toujours participer à n’importe quelle réunion Skype Entreprise. Toutefois, à compter d’octobre 2022, les utilisateurs TeamsOnly des organisations hybrides ne pourront participer qu’à Skype Entreprise réunions de manière anonyme. Pour plus d’informations, voir [à quoi s’attendre après la retraite](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement).
- Les réunions pré-existantes des utilisateurs planifiées pour l’avenir seront migrées de l’environnement local vers Teams.
- Les contacts qui existaient localement sont disponibles dans Teams peu de temps après l’ouverture de session de l’utilisateur pour la première fois.
- Les utilisateurs ne peuvent pas lancer d’appels ou de conversations à partir de Skype Entreprise, ni planifier de nouvelles réunions dans Skype Entreprise. S’ils tentent d’ouvrir le client Skype Entreprise, ils sont redirigés pour utiliser Teams comme indiqué ci-dessous. Si le client Teams n’est pas installé, il est dirigé vers la version web de Teams à l’aide de son navigateur.<br><br>
    ![Message redirigeant un utilisateur vers Teams.](../media/go-to-teams-page.png)

Avant de déplacer des utilisateurs, veillez à passer en revue les [prérequis](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer les utilisateurs vers le cloud. Veillez également à consulter les [conseils relatifs à la migration et à l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> Le magasin de contacts unifié doit être désactivé sur le compte SfB local pour que le contact soit déplacé vers Teams.

> [!IMPORTANT]
>
> - Lors du déplacement d’un utilisateur local vers le cloud avec Move-CsUser, le mode TeamsOnly est automatiquement attribué aux utilisateurs et leurs réunions locales sont automatiquement converties en réunions Teams, que le `-MoveToTeams` commutateur soit réellement spécifié ou non. (Cela inclut les migrations à partir de Lync Server 2013, qui n’a jamais eu le `-MoveToTeams` commutateur.)  Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs sont passés de Skype Entreprise Server local à Skype Entreprise Online, et leur mode est resté inchangé. Cela a été modifié en vue de la retraite de Skype Entreprise Online.
> - Le déplacement d’utilisateurs entre votre déploiement local et Teams *nécessite* désormais des versions minimales mises à jour des composants locaux Skype Entreprise Server ou Lync Server qui ne s’appuie plus sur l’infrastructure héritée Skype Entreprise Online. Pour plus d’informations, consultez [Prérequis](move-users-between-on-premises-and-cloud.md#prerequisites).

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Déplacer un utilisateur directement de Skype Entreprise localement vers Teams uniquement

Les outils d’administration locaux dans Skype Entreprise Server et Lync Server 2013 vous permettent de déplacer des utilisateurs d’un emplacement local vers le mode TeamsOnly en une seule étape à l’aide de l’applet de commande Move-CsUser dans PowerShell ou du Skype Entreprise Server Panneau de configuration, comme décrit ci-dessous. Il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur et le comportement de passer directement d’un emplacement local à Teams Uniquement est désormais automatique, quelle que soit la version de Skype Entreprise Server ou Lync Server utilisée. 

Vous devez disposer de privilèges suffisants à la fois dans l’environnement local et dans le service cloud (Microsoft 365 ou Office 365), comme décrit dans [Les informations d’identification administratives requises](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un seul compte disposant de privilèges dans les deux environnements, ou démarrer une fenêtre locale Skype Entreprise Server Management Shell avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier les informations d’identification d’un Microsoft 365 avec le rôle d’administration nécessaire.

En outre, vous devez vous assurer que l’utilisateur a reçu une licence pour Teams (en plus de Skype Entreprise Online). Ne désactivez pas la licence Skype Entreprise Online.

### <a name="move-to-teams-using-move-csuser"></a>Passer à Teams à l’aide de Move-CsUser

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype Entreprise Server Management Shell locale ou d’une fenêtre PowerShell Lync Server Management Shell. Pour déplacer un utilisateur en mode TeamsOnly à l’aide de Move-CsUser :
- Spécifiez l’utilisateur à déplacer à l’aide du `Identity` paramètre.
- Spécifiez le `-Target` paramètre avec la valeur « sipfed.online.lync.<span> com » (ou valeur similaire si votre locataire est un cloud gouvernemental).
- Si vous n’avez pas un seul compte disposant d’autorisations suffisantes à la fois en local et dans le service cloud (Microsoft 365), utilisez le `-credential` paramètre pour fournir un compte disposant d’autorisations suffisantes dans Microsoft 365.
- Si le compte disposant d’autorisations dans Microsoft 365 ne se termine pas par « onmicrosoft ».<span> com », vous devez spécifier le `-HostedMigrationOverrideUrl` paramètre, avec la valeur correcte comme décrit dans [Les informations d’identification administratives requises](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).
- Assurez-vous que l’ordinateur exécutant les outils d’administration locaux utilise la dernière CU pour votre version de Skype Entreprise Server ou Lync Server 2013, afin de vous assurer qu’OAuth est utilisé pour l’authentification. 

La séquence d’applets de commande suivante peut être utilisée pour déplacer un utilisateur vers TeamsOnly et suppose que les informations d’identification Microsoft 365 sont un compte distinct et fournies en tant qu’entrée pour l’invite de Get-Credential. Le comportement est le même que `-MoveToTeams` le commutateur soit spécifié ou non.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Étant donné qu’il existe différentes circonstances nécessitant différents paramètres, la commande par défaut pour la plupart des cas est la suivante :

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passer à Teams à l’aide de Skype Entreprise Server Panneau de configuration

1. Ouvrez l’application Skype Entreprise Server Panneau de configuration.
2. Dans le volet de navigation de gauche, choisissez **Utilisateurs**.
3. Utilisez **Find** pour localiser les utilisateurs que vous souhaitez déplacer vers Teams.
4. Sélectionnez les utilisateurs, puis, dans la liste déroulante **Action** au-dessus de la liste, **choisissez Déplacer les utilisateurs sélectionnés vers Teams** ou **Déplacer les utilisateurs sélectionnés vers Skype Entreprise Online**.   Les deux options déplacent désormais les utilisateurs directement vers TeamsOnly.
5. Dans l'Assistant, cliquez sur **Suivant**.
6. Si vous y êtes invité, connectez-vous à Microsoft 365 avec un compte qui se termine par .onmicrosoft.com et dispose des autorisations suffisantes.
7. Cliquez sur **Suivant**, puis **sur Suivant** une autre fois pour déplacer l’utilisateur.
8. Les messages d’état concernant la réussite ou l’échec sont fournis en haut de l’application principale Panneau de configuration, et non dans l’Assistant.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notifier vos Skype Entreprise utilisateurs locaux du déplacement à venir vers Teams

Les outils d’administration locaux de Skype Entreprise Server 2015 avec CU8 et en Skype Entreprise Server 2019 vous permettent d’informer les utilisateurs locaux Skype Entreprise de leur prochain passage à Teams. Lorsque vous activez ces notifications, les utilisateurs voient une notification dans leur client Skype Entreprise (Win32, Mac, web et mobile) comme indiqué ci-dessous. Si les utilisateurs cliquent sur le bouton **Essayer** , le client Teams est lancé s’il est installé ; Sinon, les utilisateurs seront accédés à la version web de Teams dans leur navigateur. Par défaut, lorsque les notifications sont activées, Win32 Skype Entreprise clients téléchargent silencieusement le client Teams afin que le client enrichi soit disponible avant de déplacer l’utilisateur en mode TeamsOnly. Toutefois, vous pouvez également désactiver ce comportement.  Les notifications sont configurées à l’aide de la version locale de `TeamsUpgradePolicy`, et le téléchargement en mode silencieux pour les clients Win32 est contrôlé via l’applet de commande locale `TeamsUpgradeConfiguration` .


![Notification du déplacement à venir vers Teams.](../media/teams-upgrade-notification.png)

Pour informer les utilisateurs locaux qu’ils seront bientôt mis à niveau vers Teams, créez une nouvelle instance de TeamsUpgradePolicy avec NotifySfBUsers=true. Ensuite, affectez cette stratégie aux utilisateurs que vous souhaitez notifier, soit en affectant la stratégie directement à l’utilisateur, soit en définissant la stratégie au niveau du site, du pool ou du niveau global. Les applets de commande suivantes créent et accordent une stratégie au niveau de l’utilisateur :

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Le téléchargement automatique de Teams via le Skype Entreprise client Win32 est contrôlé via l’applet de commande TeamsUpgradeConfiguration locale avec le paramètre DownloadTeams. Vous créez cette configuration au niveau global, du site et du pool. Par exemple, la commande suivante crée la configuration pour le site Redmond1 :

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Par défaut, la valeur de DownloadTeams est True ; toutefois, elle n’est honorée *que* si NotifySfbUser = True pour un utilisateur donné.

## <a name="see-also"></a>Voir aussi

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coexistence avec Skype Entreprise](/microsoftteams/coexistence-chat-calls-presence)
