---
title: Gérer la configuration de Microsoft teams sur surface Hub
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
description: Gérer les paramètres de Microsoft teams sur surface Hub à l’aide du concepteur de configuration Microsoft Intune et Windows
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761436"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Gérer les paramètres de Microsoft teams sur surface Hub

Vous pouvez gérer les paramètres de Microsoft teams sur un surface Hub à l’aide du concepteur de configuration Windows ou de Microsoft Intune dans le gestionnaire de points de terminaison Microsoft. Les connaissances du concepteur de configuration Windows ou de Microsoft Intune sont nécessaires pour apporter des modifications aux paramètres d’équipe. Pour plus d’informations sur ces options, reportez-vous aux articles suivants :

- [Créer un package de déploiement pour Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Qu’est-ce que la gestion des périphériques Microsoft Intune ?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Le concepteur de configuration Windows est une bonne option si vous disposez uniquement de quelques appareils surface Hub et que vous pouvez y accéder facilement. Si vous avez de nombreux contrôleurs de surface, ou s’ils sont situés à des emplacements distants, utilisez Microsoft Intune dans le gestionnaire de points de terminaison Microsoft s’il est déployé au sein de votre organisation. Quelle que soit la méthode choisie, vous devez créer un fichier de configuration XML pour apporter des modifications aux paramètres d’équipe sur surface Hub.

## <a name="teams-configuration-file-syntax"></a>Syntaxe du fichier de configuration teams

La configuration des équipes sur un surface Hub est définie à l’aide d’un fichier XML. Le fichier XML contient tous les paramètres qui peuvent être utilisés pour contrôler le fonctionnement d’Teams. Le concepteur de configuration Windows et Microsoft Intune utilisent la même syntaxe XML. Voici un exemple du fichier XML de configuration d’équipes :

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

Le tableau suivant décrit tous les paramètres de configuration disponibles dans le fichier de configuration :

| Dernier                  | Élément                                   | Attribut | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aucun                    | `<SurfaceHubSettings>`                    |           | Contient tous les éléments de configuration pour la configuration des équipes sur un surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Détermine si surface Hub annonce qu’il est disponible pour les connexions Bluetooth.<br>Valeurs acceptées : `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Détermine si teams acceptera automatiquement les réunions basées sur la proximité.<br>Valeurs acceptées : `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | Contient tous les éléments de configuration pour les réunions coordonnées.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Détermine si teams est configuré pour participer à des réunions coordonnées avec d’autres appareils.<br>Valeurs acceptées : `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | Il s’agit d’une liste séparée par des virgules d’UPN pour chaque appareil de salle de réunion ou surface Hub sur lequel l’appareil doit accepter les demandes de participation à une réunion, ou pour lesquelles des demandes de participation à une réunion doivent être envoyées.<br>Valeurs acceptées : chaîne                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | Contient des éléments de configuration audio et vidéo pour les réunions coordonnées                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Contrôle la configuration audio de teams sur un surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Détermine sur quel appareil le micro est actif lors du démarrage d’une réunion. Ce champ doit être défini sur un seul appareil (en général, sur un appareil d’équipe) pour `true` que le reste des appareils doit être paramétré pour `false` éviter l’écho et le retour audio.<br>Valeurs acceptées : `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | Détermine si les participants à une réunion peuvent activer ou désactiver le micro. Les appareils sur lesquels la **valeur par défaut** de l’audio est définie sur `false` doivent avoir ce paramètre configuré pour `false` que les participants puissent accidentellement allumer un micro et provoquer un écho ou un retour audio.<p>Si la **valeur par défaut** de l’audio est définie sur `true` , ce paramètre est ignoré et les participants peuvent activer ou désactiver le micro.<br>Valeurs acceptées : `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Contrôle la configuration vidéo des équipes sur un surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | Détermine sur quel appareil l’appareil photo sera actif lors du démarrage de la réunion. Pour une utilisation optimale, nous vous conseillons de définir uniquement le périphérique de salle teams `true` lorsque tous les autres appareils sont définis sur `false` .<br>Valeurs acceptées : `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | Détermine si les participants à une réunion peuvent activer ou désactiver la caméra. Vous pouvez définir ce `true` type sur sur n’importe quel autre appareil dans lequel vous voulez partager différentes perspectives vidéo (par exemple, si un participant utilise le tableau blanc surface Hub). Si vous ne voulez pas que les participants activent ou désactivent la caméra sur un appareil, définissez cette valeur sur `false` .<p> Si la **valeur par défaut** de la vidéo est définie sur `true` , ce paramètre est ignoré et les participants peuvent activer ou désactiver la caméra.<br>Valeurs acceptées : `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Appliquer les paramètres d’équipe aux surface Hub

Appliquez ou mettez à jour les paramètres de configuration des équipes sur surface Hub à l’aide de Windows configuration Designer ou Microsoft Intune dans le gestionnaire de points de terminaison Microsoft.

### <a name="use-windows-configuration-designer"></a>Utiliser le concepteur de configuration Windows

Vous pouvez utiliser le concepteur de configuration Windows pour créer un package de mise en service que vous pouvez utiliser pour appliquer les paramètres d’équipe à vos hubs de surface. Pour créer le package de mise en service, vous devez coller le fichier XML que vous avez créé précédemment dans le concepteur de configuration Windows.

> [!IMPORTANT]
> Si vous avez déjà appliqué la configuration des équipes à votre surface Hub à l’aide d’un package de mise à service et que vous souhaitez le modifier, vous devez tout d’abord supprimer le package de mise en service existant. Pour plus d’informations, voir [supprimer un package de mise à service créé par le concepteur de configuration Windows](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Pour créer le package de mise en service dans l’éditeur de configuration Windows, procédez comme suit :

1. Installez le concepteur de configuration Windows à partir du Windows Store sur votre ordinateur local, puis ouvrez-le
2. Sélectionner **approvisionner les appareils surface Hub** puis **basculer vers l’éditeur avancé**
3. Dans l’écran suivant, développez **WindowsTeamSettings**  >  **équipes** WindowsTeamSettings et sélectionnez **configurations** .
4. Dans le champ en regard de **configurations** dans le volet central, collez la seule ligne de code XML créée au-dessus.
5. Sélectionner **Exporter**le  >  **package de mise en service**
6. Indiquez un nom pour le package de mise en service de **nom** et **Sélectionnez Next Next (**  >  **Next** suivant).
7. Spécifiez un emplacement pour enregistrer le package de mise à service, puis sélectionnez **suivant** .
8. Sélectionnez **Build** pour créer le package de mise en service, puis cliquez sur **Terminer** .

Enfin, une fois que vous avez créé le package de mise en service, procédez comme suit pour appliquer le package de mise à service à votre surface Hub :

1. Enregistrez le package de mise à service créé ci-dessus sur un lecteur USB.
2. Insérez le lecteur USB dans votre surface Hub.
3. Sur votre surface Hub, ouvrez le menu Démarrer, sélectionnez **toutes les applications**, puis sélectionnez **paramètres** .
4. Entrez votre nom d’utilisateur et votre mot de passe d’administrateur, puis sélectionnez **Oui** .
5. Accédez à **surface Hub**, **gestion des appareils**, **ajoutez ou supprimez un package de mise à service**, puis **Ajoutez un package** .
6. Sous **Sélectionner un package**, sélectionnez **Ajouter** en regard de votre package de mise en service, puis redémarrez votre surface Hub.

### <a name="use-microsoft-intune"></a>Utiliser Microsoft Intune

Si vos hubs de surface sont gérés à l’aide de Microsoft Intune dans Microsoft Endpoint Management, vous pouvez l’utiliser pour appliquer les paramètres d’équipe à vos hubs de surface. Vous devez créer un profil de configuration et coller le fichier XML que vous avez créé précédemment.

> [!IMPORTANT]
> Vos hubs de surface doivent se trouver dans un groupe d’appareils, de sorte que Microsoft Intune puisse identifier les appareils auxquels appliquer le profil de configuration. Pour plus d’informations sur la création d’un groupe d’appareils, voir [Ajouter des groupes pour organiser les utilisateurs et les appareils](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

Procédez comme suit pour créer un profil de configuration pour appliquer les paramètres d’équipe à vos hubs de surface :

1. Connectez-vous au gestionnaire de points de terminaison Microsoft en visitant https://endpoint.microsoft.com/
2. Accédez à **Devices**  >  **profils de configuration** des appareils et sélectionnez **créer un profil** .
3. Sous **plateforme**, sélectionnez **Windows 10 et versions ultérieures** .
4. Sous **Profil**, sélectionnez **personnalisé**, puis cliquez sur **créer** .
5. Sous l’onglet **concepts de base** , dans **nom**, entrez un nom descriptif pour votre profil de configuration, puis sélectionnez **suivant** .
6. Dans l’onglet **paramètres de configuration** , sélectionnez **Ajouter** .
7. Dans le volet **Ajouter une ligne** , procédez comme suit :
    1. Entrez un nom descriptif et, éventuellement, une description du paramètre teams que vous ajoutez
    2. Dans l' **URI OMA**, entrez `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. Dans **type de données**, sélectionnez **chaîne (fichier XML)**
    4. Ouvrez l’Explorateur de fichiers, sélectionnez le fichier XML que vous avez créé précédemment, puis **ouvrez**
8. Cliquez sur **Ajouter** , puis sur **suivant** .
9. Dans l’onglet **affectations** , vérifiez que l’option **affecter à** est définie sur **groupes sélectionnés** .
10. Sous **groupes sélectionnés**, sélectionnez **Sélectionner des groupes à inclure** et choisissez le groupe qui contient vos hubs de surface, puis **Sélectionnez**
11. Sélectionnez **suivant**, **suivant**
12. Dans l' **Aperçu**, cliquez sur créer, puis sélectionnez **créer**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Supprimer les paramètres d’équipe d’un surface Hub

Supprimer les paramètres de configuration d’équipe sur surface Hub à l’aide de Windows configuration Designer ou Microsoft Intune dans le gestionnaire de points de terminaison Microsoft.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Supprimer un package de mise à service créé par le concepteur de configuration Windows

Si vous avez appliqué des paramètres d’équipe à un surface Hub à l’aide d’un package de mise en service créé par le concepteur de configuration Windows, procédez comme suit pour supprimer le package et ses paramètres :

1. Sur votre surface Hub, ouvrez le menu Démarrer, sélectionnez **toutes les applications**, puis sélectionnez **paramètres** .
2. Entrez votre nom d’utilisateur et votre mot de passe d’administrateur, puis sélectionnez **Oui** .
3. Accédez à **surface Hub**, **gestion des appareils** , puis **ajoutez ou supprimez un package de mise à service**
4. En regard du package de mise en service que vous voulez supprimer, sélectionnez **supprimer** .
5. Accédez à **surface Hub** , puis **applications & fonctionnalités**
6. Recherchez **Microsoft teams surface Hub** , puis sélectionnez **Options avancées** .
7. Sélectionner **Réinitialiser**, puis **Réinitialiser** de nouveau
8. Redémarrer votre surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>Supprimer les paramètres appliqués par Microsoft Intune

Si vous avez appliqué des paramètres d’équipe à un surface Hub à l’aide de Microsoft Intune dans le centre de points de terminaison Microsoft, procédez comme suit pour supprimer le profil de configuration et ses paramètres :

1. Connectez-vous au gestionnaire de points de terminaison Microsoft en visitant https://endpoint.microsoft.com/
2. Accéder aux **Devices**  >  **profils de configuration** des appareils
3. Sélectionnez le profil de configuration qui contient les paramètres de réunion coordonnés que vous voulez supprimer.
4. Dans la page Détails du profil de configuration, sélectionnez **supprimer** , puis **OK** .

Après avoir supprimé le profil de configuration qui contenait les paramètres de réunion coordonnés pour votre surface Hub, procédez comme suit pour réinitialiser l’application teams sur surface Hub :

1. Sur votre surface Hub, ouvrez le menu Démarrer, sélectionnez **toutes les applications**, puis sélectionnez **paramètres** .
2. Entrez votre nom d’utilisateur et votre mot de passe d’administrateur, puis sélectionnez **Oui** .
3. Accédez à **surface Hub** , puis **applications & fonctionnalités**
4. Recherchez **Microsoft teams surface Hub** , puis sélectionnez **Options avancées** .
5. Sélectionner **Réinitialiser**, puis **Réinitialiser** de nouveau
6. Redémarrer votre surface Hub