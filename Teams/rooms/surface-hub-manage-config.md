---
title: Gérer Microsoft Teams configuration de l’ordinateur Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Gérer Microsoft Teams paramètres d’Surface Hub à l Microsoft Intune et Windows Configuration Designer
ms.openlocfilehash: d368bed6db1d86e9c97d849d462edd1ff0a21c6d
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278467"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gérer Microsoft Teams paramètres d’Surface Hub

Vous pouvez gérer Microsoft Teams paramètres de configuration sur un Surface Hub en Windows Configuration Designer ou Microsoft Intune dans Microsoft Endpoint Manager. Une connaissance approfondie Windows Configuration Designer ou Microsoft Intune est requise pour apporter des modifications à Teams paramètres. Pour plus d’informations sur ces options, voir les articles suivants :

- [Créer un package d’approvisionnement pour Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Qu’est-ce Microsoft Intune gestion des appareils ?](/mem/intune/remote-actions/device-management)

Windows Configuration Designer est une bonne option si vous n’avez que Surface Hub appareils mobiles et que vous pouvez y accéder facilement. Si vous avez de nombreux Surface Hubs ou s’ils se trouveront dans des emplacements distants, utilisez Microsoft Intune dans Microsoft Endpoint Manager si le surface est déployé dans votre organisation. Quelle que soit la méthode choisie, vous devez créer un fichier de configuration XML pour apporter des modifications aux paramètres Teams’Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Teams syntaxe du fichier de configuration

Teams configuration d’Surface Hub se définit à l’aide d’un fichier XML. Le fichier XML contient tous les paramètres qui peuvent être utilisés pour contrôler le fonctionnement Teams’utilisation. Les Windows Concepteur de configuration Microsoft Intune utiliser la même syntaxe XML. Voici un exemple de fichier XML Teams de configuration :

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
| Aucun                    | `<SurfaceHubSettings>`                    |           | Contient tous les éléments de configuration pour Teams configuration sur un Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Détermine si Surface Hub annonce qu’elle est disponible pour Bluetooth connexions.<br>Valeurs acceptées `true` : , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Détermine si les Teams accepteront automatiquement les réunions basées sur la proximité.<br>Valeurs acceptées `true` : , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contient tous les éléments de configuration pour les réunions coordonnées.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Détermine si une Teams est configurée pour participer à des réunions coordonnées avec d’autres appareils.<br>Valeurs acceptées `true` : , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Il s’agit d’une liste séparée par des virgules des upns pour chaque appareil ou Surface Hub de salle Teams à partir duquel l’appareil doit accepter les demandes de réunion ou vers laquelle les demandes de réunion doivent être envoyées.<br>Valeurs acceptées : chaîne                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contient des éléments de configuration audio et vidéo pour les réunions coordonnées                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Contrôle la configuration audio pour les Teams sur une Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Détermine le périphérique sur lequel le microphone sera actif lorsqu’une réunion débute. Un seul appareil (généralement un appareil salles Teams) peut définir ce champ tandis que le champ de ce champ doit être utilisé pour éviter l’écho et les commentaires des autres `true` `false` appareils.<br>Valeurs acceptées `true` : , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Détermine si les participants à une réunion peuvent ou non éteindre le microphone. Les périphériques sur lesquels  `false` l’audio est réglé par défaut doivent avoir ce paramètre réglé de sorte que les participants ne peuvent pas activer accidentellement un microphone et provoquer un écho ou des commentaires `false` audio.<p>Si **la valeur par** défaut de l’audio est définie sur, ce paramètre est ignoré et les participants peuvent activer ou désactiver le `true` micro.<br>Valeurs acceptées `true` : , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Contrôle la configuration de la vidéo Teams sur une Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Détermine le périphérique sur lequel l’appareil photo sera actif lorsqu’une réunion commence. Pour une expérience qui soit la meilleure possible, nous vous recommandons de définir l salles Teams de l’appareil lorsque tous les autres appareils `true` sont sur `false` .<br>Valeurs acceptées `true` : , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Détermine si les participants à une réunion peuvent faire bascule l’appareil photo sur ou hors de l’appareil photo. Vous pouvez définir cette action sur tous les autres appareils de l’événement pour que les participants partagent des perspectives vidéo différentes (par exemple, si un participant utilise le `true` Surface Hub tableau blanc). Si vous ne voulez pas que les participants activer ou désactiver une caméra sur un appareil, définissez cette fonction sur `false` .<p> Si **la vidéo est** définie par défaut sur, ce paramètre est ignoré et les participants peuvent activer ou désactiver la `true` caméra.<br>Valeurs acceptées `true` : , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Appliquer Teams paramètres d’accès Surface Hub

Appliquez ou mettez à jour Teams paramètres de configuration sur Surface Hub à l’aide de Windows Configuration Designer ou Microsoft Intune dans Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>Utiliser Windows Configuration Designer

Vous pouvez utiliser Windows Configuration Designer pour créer un package d’approvisionnement que vous pouvez utiliser pour appliquer Teams paramètres de configuration à vos Surface Hubs. Vous collez le fichier XML que vous avez créé ci-dessus dans Windows Configuration Designer pour créer le package de mise en service.

> [!IMPORTANT]
> Si vous avez déjà appliqué une configuration Teams à votre Surface Hub à l’aide d’un package d’approvisionnement et que vous souhaitez le modifier, vous devez d’abord supprimer le package de mise en service existant. Pour plus d’informations, [voir Supprimer un package d’approvisionnement créé Windows Configuration Designer.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

Pour créer le package d’approvisionnement dans Windows Configuration Designer, vous pouvez :

1. Installer Windows Configuration Designer à partir du Windows Store sur votre ordinateur local et l’ouvrir
2. Sélectionnez **Provision Surface Hub appareils,** puis **Basculez vers l’éditeur avancé**
3. Sur l’écran suivant, développez **WindowsTeamSettings**  >  **Teams** et sélectionnez **Configurations.**
4. Dans le champ à côté **de Configurations** dans le volet du milieu, collez la seule ligne de XML que vous avez créée ci-dessus.
5. Sélectionnez **Exporter**  >  **le package d’approvisionnement**
6. Nommez le package d’approvisionnement sous **Nom,** puis sélectionnez  >  **Suivant**
7. Spécifiez un emplacement pour enregistrer le package d’approvisionnement, puis sélectionnez **Suivant**
8. Sélectionnez **Générer** pour créer le package d’approvisionnement, puis **Terminer**

Enfin, après avoir créé le package d’approvisionnement, appliquez le package d’approvisionnement à votre Surface Hub :

1. Enregistrer le package d’approvisionnement que vous avez créé ci-dessus sur un lecteur USB
2. Insérez le lecteur USB dans votre Surface Hub
3. Sur votre Surface Hub, ouvrez le menu Démarrer, sélectionnez **Toutes**  les applications, puis Paramètres
4. Fournissez votre nom d’utilisateur et votre mot de passe d’administrateur, puis sélectionnez **Oui**
5. Go to **Surface Hub,** **Device management,** **Add or remove a provisioning package,** and then Add a **package**
6. Sous **Sélectionner un package,** **sélectionnez Ajouter** en côté de votre package de mise en service, puis redémarrez votre Surface Hub

### <a name="use-microsoft-intune"></a>Utiliser la Microsoft Intune

Si vos Surface Hubs sont gérés à l’aide de Microsoft Intune microsoft Endpoint Management, vous pouvez l’utiliser pour appliquer Teams paramètres à vos Surface Hubs. Vous allez créer un profil de configuration, puis y coller le fichier XML que vous avez créé ci-dessus.

> [!IMPORTANT]
> Vos Surface Hubs doivent se trouver dans un groupe d’appareils afin que le Microsoft Intune puisse identifier les appareils à lesquels appliquer le profil de configuration. Pour plus d’informations sur la création d’un groupe d’appareils, voir [Ajouter des groupes pour organiser les utilisateurs et les appareils.](/mem/intune/fundamentals/groups-add)

Pour créer un profil de configuration à appliquer à vos Surface Hubs, Teams comme suit :

1. Connectez-vous Microsoft Endpoint Manager en visitanthttps://endpoint.microsoft.com/
2. Accédez aux  >  **profils configuration des appareils** et **sélectionnez Créer un profil**
3. Sous **Plateforme,** sélectionnez Windows 10 **et ultérieure**
4. Sous **Profil,** **sélectionnez Personnalisé,** puis cliquez sur **Créer**
5. Sous **l’onglet Informations de** base, dans **Nom,** fournissez un nom descriptif pour votre profil de configuration, puis sélectionnez **Suivant**
6. Sous **l’onglet Paramètres de configuration,** sélectionnez **Ajouter**
7. Dans le **volet Ajouter une** ligne, faites les choses suivantes :
    1. Fournir un nom descriptif et éventuellement une description du Teams que vous ajoutez
    2. En **OMA-URI,** entrez `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Dans **Type de données,** **sélectionnez Chaîne (fichier XML)**
    4. Ouvrez le navigateur de fichiers, sélectionnez le fichier XML que vous avez créé ci-dessus, puis **ouvrez**
8. Sélectionnez **Ajouter,** puis **Suivant**
9. Sous **l’onglet Devoirs,** assurez-vous que **l’attribution** est définie sur **Groupes sélectionnés.**
10. Sous **Groupes sélectionnés,** **sélectionnez Sélectionner les groupes à inclure et** choisissez le groupe qui contient vos Surface Hubs, puis **sélectionnez Sélectionner**
11. Sélectionner **Suivant,** **Suivant**
12. Dans révision **+ création,** sélectionnez **Créer**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Supprimer Teams paramètres d’un Surface Hub

Supprimez Teams paramètres de configuration Surface Hub à l’aide Windows Configuration Designer ou Microsoft Intune dans Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Supprimer un package d’approvisionnement créé par Windows Configuration Designer

Si vous avez appliqué des paramètres Teams à un Surface Hub à l’aide d’un package d’approvisionnement créé par Windows Configuration Designer, pour supprimer le package et ses paramètres, utilisez les étapes suivantes :

1. Sur votre Surface Hub, ouvrez le menu Démarrer, sélectionnez **Toutes**  les applications, puis Paramètres
2. Fournissez votre nom d’utilisateur et votre mot de passe d’administrateur, puis sélectionnez **Oui**
3. Go to **Surface Hub,** **Device management** and then **Add or remove a provisioning package**
4. En côté du package d’approvisionnement à supprimer, sélectionnez **Supprimer**
5. Allez à **l Surface Hub** puis **aux fonctionnalités de & applications**
6. Recherchez **Microsoft Teams’Surface Hub,** puis sélectionnez **Options avancées**
7. Sélectionnez **Réinitialiser,** puis **Réinitialiser à** nouveau
8. Redémarrez votre Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Supprimer les paramètres appliqués par Microsoft Intune

Si vous avez appliqué des paramètres Teams à une Surface Hub à l’aide d’Microsoft Intune dans Microsoft Endpoint Management, pour supprimer le profil de configuration et ses paramètres, utilisez les étapes suivantes :

1. Connectez-vous Microsoft Endpoint Manager en visitanthttps://endpoint.microsoft.com/
2. Accéder aux **profils**  >  **de configuration des appareils**
3. Sélectionnez le profil de configuration qui contient les paramètres de réunion coordonnée que vous souhaitez supprimer
4. Dans la page des détails du profil de configuration, **sélectionnez Supprimer,** puis **OK**

Après avoir supprimé le profil de configuration qui contenait les paramètres de réunion coordonnée pour votre Surface Hub, utilisez les étapes suivantes pour réinitialiser l’application Teams sur la Surface Hub :

1. Sur votre Surface Hub, ouvrez le menu Démarrer, sélectionnez **Toutes**  les applications, puis Paramètres
2. Fournissez votre nom d’utilisateur et votre mot de passe d’administrateur, puis sélectionnez **Oui**
3. Allez à **l Surface Hub** puis **aux fonctionnalités de & applications**
4. Recherchez **Microsoft Teams’Surface Hub,** puis sélectionnez **Options avancées**
5. Sélectionnez **Réinitialiser,** puis **Réinitialiser à** nouveau
6. Redémarrez votre Surface Hub