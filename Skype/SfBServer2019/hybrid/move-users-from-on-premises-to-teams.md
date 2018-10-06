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
ms.openlocfilehash: 78f0c49fa2179b4a0aa95a993476c21fb679f489
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436564"
---
# <a name="move-users-from-on-premises-to-teams"></a>Déplacer les utilisateurs locaux vers des équipes

Avec Skype pour Business Server 2019, vous pouvez migrer vos utilisateurs locaux aux équipes comme décrit dans cet article.

Gardez à l’esprit qu’après le déplacement de vos utilisateurs à des équipes : 
 
- Leurs réunions sont migrées vers Skype pour Business Online, et leurs contacts sont migrés vers les équipes. 
- Ils peuvent participer à des réunions Skype via le Skype pour le client riche Business (les utilisateurs ne sont pas invités pour la connexion chaque fois) ou par le biais de l’application de réunions Skype (requiert un téléchargement unique et une connexion). Lorsqu’un utilisateur clique sur un Skype pour le lien de la réunion métiers au sein des équipes, la réunion est lancé dans l’application appropriée.

- Sur Mobile, vos utilisateurs pourront participer à Skype existant pour les réunions d’entreprise à l’aide de l’application native uniquement.

> [!NOTE]
> Une fois un utilisateur est déplacé vers le mode TeamsOnly, l’utilisateur est hébergé dans Skype pour Business Online.

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a>Conditions préalables pour le déplacement des utilisateurs locaux aux équipes 

Cette section décrit les conditions préalables pour le déplacement de vos utilisateurs sur site aux équipes. Il le faut :
- [Configurer la connectivité hybride](#set-up-hybrid-connectivity) (si vous n’avez pas déjà fait)
- [Informez les utilisateurs du déplacement aux équipes](#notify-your-users-of-the-move-to-teams) (facultatif)
- [Assurez-vous que vos utilisateurs disposent d’une licence valide](#make-sure-your-users-have-a-valid-license)
- [Prenez note des exigences de configuration vocale](#voice-configuration-requirements)
- [Attribuer une stratégie de mise à niveau des équipes](#assign-a-teams-upgrade-policy) (facultatif)

## <a name="set-up-hybrid-connectivity"></a>Configurer la connectivité hybride
Avant de migrer vos utilisateurs, si vous n’avez pas déjà fait, vous devez vous assurer que vous avez configuré la connectivité hybride entre votre Skype pour l’environnement local de Business Server et le Skype pour Business Online. Connectivité hybride nécessite la synchronisation Active Directory, configuration de la fédération et ainsi de suite. Pour plus d’informations, voir [planification de la connectivité hybride](plan-hybrid-connectivity.md) et de [connectivité de configuration hybride](configure-hybrid-connectivity.md).

## <a name="notify-your-users-of-the-move-to-teams"></a>Informez les utilisateurs du déplacement aux équipes 
Il s’agit d’une étape facultative, mais celle dont vous devez prendre en compte. Pour avertir les utilisateurs de la mise à niveau d’équipes en attente, vous pouvez utiliser les applets de commande TeamsUpgradePolicy et TeamsUpgradeConfiguration du local. Vous pouvez également configurer le téléchargement automatique en mode silencieux d’équipes en arrière-plan avant la mise à niveau (clients Win32 uniquement). 

Par exemple, pour avertir les utilisateurs qu’ils sont mis à des équipes, utilisez l’applet de commande TeamsUpgradePolicy local avec le paramètre - NotifySbUser. Vous pouvez définir la stratégie à un niveau global, site, de pool ou utilisateur. La commande suivante crée et accorde une stratégie au niveau de l’utilisateur :
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

Vous pouvez vérifier cette stratégie à l’aide de l’applet de commande Get-csTeamsUpgradePolicy.

Les utilisateurs verront une notification du déplacement imminente aux équipes. La notification se produit Win32, Mac, Mobile et les Clients Web (avec la version de droite).

Vous pouvez spécifier le téléchargement automatique des équipes (pour les clients Win32) pour les utilisateurs à mettre à niveau à l’aide de l’applet de commande TeamsUpgradeConfiguration local avec le paramètre DownloadTeams. Vous définissez cette stratégie au niveau du client, et il peut être appliqué à un site global et au niveau du pool. Par exemple, la commande suivante définit la stratégie au niveau du site :

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

Par défaut, la valeur de DownloadTeams a la valeur True, mais vous devez également définir NotifySfbUser sur True pour activer les équipes pour un utilisateur donné. 

## <a name="make-sure-your-users-have-a-valid-license"></a>Assurez-vous que vos utilisateurs possèdent une licence valide  
Avant la migration, locale doit être proposée à l’utilisateur une licence valide, comme suit :

-   Utilisateur doit avoir une licence d’équipes.
-   Si l’utilisateur est configuré pour utiliser locale Enterprise Voice, il doivent avoir une licence vocale en ligne lors du déplacement. 
-   Si l’utilisateur est configuré pour la conférence rendez-vous sur site, ils doivent possèdent une licence pour le système téléphonique (Cloud PBX).

## <a name="voice-configuration-requirements"></a>Configuration requise de voix

Si vos utilisateurs locaux ont vocal sur site, vous avez deux options :

-  **Migrer des utilisateurs grâce à des fonctionnalités de téléphonie.** Les utilisateurs peuvent émettre et recevoir des appels à l’aide du client équipes.  Vous pouvez choisir Microsoft appelant planifier ou routage Direct pour connecter les services de téléphonie aux équipes.  

    -  Appel de Plan de Microsoft fournit une solution vocale tout-en nuage. Pour plus d’informations sur l’appel de Plan de Microsoft, voir (lien bientôt disponible). 
    -  Routage direct vous permet d’utiliser pratiquement n’importe quel jonction PSTN, et vous pouvez configurer l’interopérabilité entre équipement téléphonique appartenant à un client et le système téléphonique de Microsoft.  Pour plus d’informations, voir [Planifier le routage Direct](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) et [Configurer le routage Direct](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).

-  **Migrer les utilisateurs sans fonctionnalités de téléphonie.** Si vous migrez des utilisateurs sans conserver les fonctionnalités de téléphonie, assurez-vous que les utilisateurs ont des licences appropriés dans le nuage. 

## <a name="assign-a-teams-upgrade-policy"></a>Attribuer une stratégie de mise à niveau des équipes  
Vous pouvez utiliser les outils en ligne pour gérer les stratégies d’utilisateur, telles que pour contrôler le routage des messages et les appels entrants. Pour plus d’informations, consultez la rubrique (lien bientôt disponible).

## <a name="move-on-premises-users-to-teams"></a>Déplacer des utilisateurs locaux aux équipes

Vous pouvez déplacer vos utilisateurs locaux aux équipes à l’aide des applets de commande PowerShell ou à l’aide de la Skype pour Business Server 2019 le panneau de configuration.

### <a name="move-users-by-using-powershell"></a>Déplacer les utilisateurs à l’aide de PowerShell
Pour déplacer les utilisateurs vers les équipes à l’aide de PowerShell, vous allez utiliser l’applet de commande Move-CsUser avec le paramètre moveToTeams comme suit :

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

($cred = get-informations d’identification. Vous devez fournir les informations d’identification d’administration Office 365.)

> [!NOTE]
> Cette commande définit la TeamsInteropPolicy aux équipes et définit le TeamsUpgradePolicy en mode TeamsOnly. 
 
Après que le déplacement aux équipes se déroule correctement, Skype l’utilisateur pour client Business affichera le message suivant : 

![Migration réussie au message d’équipes](../media/teams-upgrade-complete-message.png)

Notez que Skype pour les entreprises ne sera plus disponible pour les utilisateurs, sauf pour joindre une réunion. 

Dans les cas rares, lors du déplacement de vos utilisateurs à des équipes, vous souhaiterez remplacer dans les conférences rendez-vous et à la fonctionnalité vocale en nuage. Pour cela, à l’aide des paramètres suivants avec la commande Move-CsUser :
- **BypassAudioConferencingCheck :** Si l’utilisateur a dans les conférences rendez-vous activé pour locale, l’utilisateur doit avoir également une licence AudioConf dans Office 365 avant de migrer. Une fois la migration vers le nuage, l’utilisateur sera mis en service pour l’audioconférence dans le nuage. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le nuage, mais n’utilisez pas la fonctionnalité de conférence audio, vous pouvez le substituer en spécifiant ce paramètre.
- **ByPassEnterpriseVoice :** Si l’utilisateur a Enterprise Voice est activé pour local, l’utilisateur doit disposer d’une licence Enterprise Voice dans Office 365 avant de migrer. Après la migration vers le nuage, l’utilisateur sera mis en service pour la voix dans le nuage. Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le nuage, mais n’utilisez pas la fonctionnalité vocale dans le nuage, vous pouvez substituer voix dans le nuage en spécifiant ce paramètre.
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a>Déplacer les utilisateurs à l’aide de la Skype pour Business Server Control Panel 

Pour déplacer des utilisateurs aux équipes à l’aide de la Skype pour Business le panneau de configuration :

1. Ouvrez le Skype pour Business le panneau de configuration et se connecter à votre compte Office 365.

2. Sélectionnez des **utilisateurs** dans le volet de navigation gauche, puis sélectionnez les utilisateurs à migrer. 
     
3. Dans le menu **Action** , cliquez sur **déplacer les utilisateurs sélectionnés aux équipes**. 

    ![Cliquez sur Suivant pour vérifier la migration](../media/migration-confirmation.png)
    
4. Cliquez sur **suivant** pour confirmer votre migration. 

Une fois que l’utilisateur est déplacé vers les équipes, vous verrez les confirmations comme suit :

![Déplacer les utilisateurs confirmation](../media/move-user-confirmation.png)
<br/><br/>
![Message que les utilisateurs ont été déplacés.](../media/users-moved-successfully.png)

Si le déplacement n’a pas réussi, vous verrez un message comme suit :

![Message d’utilisateur n’a pas pu être déplacé.](../media/users-not-moved.png)
