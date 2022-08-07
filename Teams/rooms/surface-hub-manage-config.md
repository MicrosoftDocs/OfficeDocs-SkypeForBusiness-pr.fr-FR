---
title: Gérer la configuration de Microsoft Teams sur Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Gérer les paramètres Microsoft Teams sur Surface Hub à l’aide de Microsoft Intune et du Concepteur de configuration Windows
ms.openlocfilehash: 6e99922ebb7bb30db1b5e94fd1a4d30b8ec653b8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272209"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gérer les paramètres Microsoft Teams sur le Surface Hub

Vous pouvez gérer les paramètres Microsoft Teams sur un Surface Hub à l’aide du Concepteur de configuration Windows ou de Microsoft Intune dans Microsoft Endpoint Manager. Une connaissance du Concepteur de configuration Windows ou Microsoft Intune est nécessaire pour apporter des modifications aux paramètres Teams. Pour plus d’informations sur ces options, consultez les articles suivants :

- [Créer un package d’approvisionnement pour Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Qu’est-ce que la gestion des appareils Microsoft Intune ?](/mem/intune/remote-actions/device-management)

Le Concepteur de configuration Windows est une bonne option si vous n’avez que quelques appareils Surface Hub et que vous pouvez y accéder facilement. Si vous avez de nombreux Surface Hubs, ou s’ils se trouvent dans des emplacements distants, utilisez Microsoft Intune dans Microsoft Endpoint Manager s’il est déployé dans votre organisation. Quelle que soit la méthode choisie, vous devez créer un fichier de configuration XML pour apporter des modifications aux paramètres Teams sur le Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Syntaxe du fichier de configuration Teams

La configuration Teams sur un Surface Hub est définie à l’aide d’un fichier XML. Le fichier XML contient tous les paramètres qui peuvent être utilisés pour contrôler le fonctionnement de Teams. Le Concepteur de configuration Windows et Microsoft Intune utilisent la même syntaxe XML. Voici un exemple de fichier XML de configuration Teams :

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

Le tableau suivant décrit tous les paramètres de configuration disponibles dans le fichier de configuration :

| Parent                  | Élément                                   | Attribut | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aucun                    | `<SurfaceHubSettings>`                    |           | Contient tous les éléments de configuration pour la configuration Teams sur un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Détermine si Surface Hub annonce qu’il est disponible pour les connexions Bluetooth.<br>Valeurs acceptées : `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Détermine si Teams accepte automatiquement les réunions basées sur la proximité.<br>Valeurs acceptées : `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contient tous les éléments de configuration pour les réunions coordonnées.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Détermine si Teams est configuré pour participer à des réunions coordonnées avec d’autres appareils.<br>Valeurs acceptées : `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Il s’agit d’une liste d’UPN séparés par des virgules pour chaque appareil Salle Teams ou Surface Hub à partir duquel l’appareil doit accepter les demandes de participation à une réunion, ou à laquelle les demandes de participation à une réunion doivent être envoyées.<br>Valeurs acceptées : chaîne                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contient des éléments de configuration audio et vidéo de configuration pour les réunions coordonnées                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Contrôle la configuration audio pour Teams sur un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Détermine sur quel appareil le microphone sera actif au démarrage d’une réunion. Un seul appareil (généralement un appareil salles Teams) peut avoir ce champ défini `true` sur tandis que le reste des appareils doit avoir ce champ défini pour `false` éviter l’écho audio et les commentaires.<br>Valeurs acceptées : `true`, `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Détermine si les participants à une réunion peuvent activer ou désactiver le microphone. Les appareils sur lesquels la **valeur par défaut audio** est définie `false` doivent avoir ce paramètre défini pour `false` que les participants ne puissent pas activer accidentellement un microphone et provoquer un écho audio ou des commentaires.<p>Si **la valeur par défaut de** l’audio est définie `true`sur , ce paramètre est ignoré et les participants peuvent désactiver ou désactiver le son du microphone.<br>Valeurs acceptées : `true`, `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Contrôle la configuration vidéo pour Teams sur un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Détermine sur quel appareil la caméra sera active au démarrage d’une réunion. Pour une expérience optimale, nous vous recommandons de définir `true` uniquement le salles Teams appareil, tandis que tous les autres appareils sont définis `false`sur .<br>Valeurs acceptées : `true`, `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Détermine si les participants à une réunion peuvent activer ou désactiver la caméra. Vous pouvez définir cette `true` option sur tous les autres appareils de l’événement que les participants souhaitent partager différentes perspectives vidéo (par exemple, si un participant utilise le tableau blanc Surface Hub). Si vous ne souhaitez pas que les participants activent ou désactivent une caméra sur un appareil, définissez cette `false`option sur .<p> Si **la valeur par défaut** de la vidéo est définie `true`sur , ce paramètre est ignoré et les participants peuvent activer ou désactiver l’appareil photo.<br>Valeurs acceptées : `true`, `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Appliquer les paramètres Teams au Surface Hub

Appliquez ou mettez à jour les paramètres de configuration Teams sur Surface Hub à l’aide du Concepteur de configuration Windows ou de Microsoft Intune dans Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Utiliser le Concepteur de configuration Windows

Vous pouvez utiliser le Concepteur de configuration Windows pour créer un package d’approvisionnement que vous pouvez utiliser pour appliquer les paramètres Teams à vos Surface Hubs. Vous allez coller le fichier XML que vous avez créé ci-dessus dans le Concepteur de configuration Windows pour créer le package d’approvisionnement.

> [!IMPORTANT]
> Si vous avez déjà appliqué la configuration Teams à votre Surface Hub à l’aide d’un package d’approvisionnement et que vous souhaitez le modifier, vous devez d’abord supprimer le package d’approvisionnement existant. Pour plus d’informations, consultez [Supprimer un package d’approvisionnement créé par le Concepteur de configuration Windows](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Procédez comme suit pour créer le package d’approvisionnement dans le Concepteur de configuration Windows :

1. Installer le Concepteur de configuration Windows à partir du Windows Store sur votre ordinateur local et l’ouvrir
2. Sélectionnez **Provisionner des appareils Surface Hub** , puis **basculer vers l’éditeur avancé**
3. Dans l’écran suivant, développez **WindowsTeamSettings** > **Teams** et sélectionnez **Configurations**
4. Dans le champ en regard **de Configurations** dans le volet central, collez la ligne unique de code XML que vous avez créée ci-dessus.
5. Sélectionner **Exporter** > **le package d’approvisionnement**
6. Indiquez un nom pour le package d’approvisionnement dans **Nom**, puis sélectionnez **Suivant** > 
7. Spécifiez un emplacement pour enregistrer le package d’approvisionnement, puis sélectionnez **Suivant**
8. Sélectionnez **Générer** pour créer le package d’approvisionnement, puis **Terminer**

Enfin, une fois que vous avez créé le package d’approvisionnement, procédez comme suit pour appliquer le package d’approvisionnement à votre Surface Hub :

1. Enregistrer le package d’approvisionnement que vous avez créé ci-dessus sur un lecteur USB
2. Insérer le lecteur USB dans votre Surface Hub
3. Sur votre Surface Hub, ouvrez le menu Démarrer, sélectionnez **Toutes les applications**, puis sélectionnez **Paramètres**
4. Indiquez le nom d’utilisateur et le mot de passe de votre administrateur, puis sélectionnez **Oui.**
5. Accédez à **Surface Hub**, **Gestion des appareils**, **Ajouter ou supprimer un package d’approvisionnement**, puis **Ajoutez un package**
6. Sous **Sélectionner un package**, **sélectionnez Ajouter** en regard de votre package d’approvisionnement, puis redémarrez votre Surface Hub

### <a name="use-microsoft-intune"></a>Utiliser Microsoft Intune

Si vos Surface Hubs sont gérés à l’aide de Microsoft Intune dans Microsoft Endpoint Management, vous pouvez l’utiliser pour appliquer des paramètres Teams à vos Surface Hubs. Vous allez créer un profil de configuration, puis y coller le fichier XML que vous avez créé ci-dessus.

> [!IMPORTANT]
> Vos Surface Hubs doivent se trouver dans un groupe d’appareils afin que le Microsoft Intune puisse identifier les appareils auxquels appliquer le profil de configuration. Pour plus d’informations sur la création d’un groupe d’appareils, consultez [Ajouter des groupes pour organiser les utilisateurs et les appareils](/mem/intune/fundamentals/groups-add).

Procédez comme suit pour créer un profil de configuration pour appliquer les paramètres Teams à vos Surface Hubs :

1. Connectez-vous à Microsoft Endpoint Manager en visitanthttps://endpoint.microsoft.com/
2. Accédez aux **profils de configuration** **des appareils** >  et sélectionnez **Créer un profil**
3. Sous **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**
4. Sous **Profil**, sélectionnez **Personnalisé**, puis cliquez sur **Créer**
5. Sous l’onglet **De base** , dans **Nom**, indiquez un nom descriptif pour votre profil de configuration, puis sélectionnez **Suivant**
6. Sous l’onglet **Paramètres de configuration** , sélectionnez **Ajouter**
7. Dans le volet **Ajouter une ligne** , procédez comme suit :
    1. Fournissez un nom descriptif et, éventuellement, une description du paramètre Teams que vous ajoutez
    2. Dans **OMA-URI**, entrez `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Dans **Type de données**, sélectionnez **Chaîne (fichier XML)**
    4. Ouvrez le navigateur de fichiers, sélectionnez le fichier XML que vous avez créé ci-dessus, puis **ouvrez**
8. Sélectionnez **Ajouter** , puis **Suivant**
9. Sous l’onglet **Affectations** , assurez-vous que **l’option Affecter** est définie sur **Les groupes sélectionnés**
10. Sous **Groupes sélectionnés**, **sélectionnez Sélectionner des groupes à inclure** et choisissez le groupe qui contient vos Surface Hubs, puis **sélectionnez Sélectionner**
11. Sélectionnez **Suivant**, **Suivant**
12. Dans **l’option Vérifier + créer**, sélectionnez **Créer**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Supprimer les paramètres Teams d’un Surface Hub

Supprimez les paramètres de configuration Teams sur Surface Hub à l’aide du Concepteur de configuration Windows ou de Microsoft Intune dans Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Supprimer un package d’approvisionnement créé par le Concepteur de configuration Windows

Si vous avez appliqué des paramètres Teams à un Surface Hub à l’aide d’un package d’approvisionnement créé par le Concepteur de configuration Windows, procédez comme suit pour supprimer le package et ses paramètres :

1. Sur votre Surface Hub, ouvrez le menu Démarrer, sélectionnez **Toutes les applications**, puis sélectionnez **Paramètres**
2. Indiquez le nom d’utilisateur et le mot de passe de votre administrateur, puis sélectionnez **Oui.**
3. Accédez au **Surface Hub**, **gestion des appareils** , puis **ajoutez ou supprimez un package d’approvisionnement**
4. En regard du package d’approvisionnement à supprimer, **sélectionnez Supprimer**
5. Accédez au **Surface Hub** , puis **aux fonctionnalités & applications**
6. Recherchez **Microsoft Teams pour Surface Hub** , puis sélectionnez **Options avancées**
7. Sélectionnez **Réinitialiser**, puis **réinitialiser**
8. Redémarrer votre Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Supprimer les paramètres appliqués par Microsoft Intune

Si vous avez appliqué des paramètres Teams à un Surface Hub à l’aide de Microsoft Intune dans Microsoft Endpoint Management, procédez comme suit pour supprimer le profil de configuration et ses paramètres :

1. Connectez-vous à Microsoft Endpoint Manager en visitanthttps://endpoint.microsoft.com/
2. Accéder aux **profils de configuration** **des appareils** > 
3. Sélectionnez le profil de configuration qui contient les paramètres de réunion coordonnée que vous souhaitez supprimer
4. Dans la page des détails du profil de configuration, **sélectionnez Supprimer** , puis **OK**

Une fois que vous avez supprimé le profil de configuration qui contenait les paramètres de réunion coordonnée pour votre Surface Hub, procédez comme suit pour réinitialiser l’application Teams sur le Surface Hub :

1. Sur votre Surface Hub, ouvrez le menu Démarrer, sélectionnez **Toutes les applications**, puis sélectionnez **Paramètres**
2. Indiquez le nom d’utilisateur et le mot de passe de votre administrateur, puis sélectionnez **Oui.**
3. Accédez au **Surface Hub** , puis **aux fonctionnalités & applications**
4. Recherchez **Microsoft Teams pour Surface Hub** , puis sélectionnez **Options avancées**
5. Sélectionnez **Réinitialiser**, puis **réinitialiser**
6. Redémarrer votre Surface Hub
