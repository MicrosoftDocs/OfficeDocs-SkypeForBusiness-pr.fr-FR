---
title: Configurer des réunions coordonnées avec Salles Microsoft Teams et Surface Hub
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
description: Configurez salles Teams appareils et Surface Hub pour participer à des réunions lorsqu’un appareil ou l’autre participe à une réunion.
ms.openlocfilehash: 759574015f2138476e0b03ef6fa85b8b105d81ef
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706981"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurer des réunions coordonnées avec Salles Microsoft Teams et Surface Hub

Si vous avez un ou plusieurs appareils Salles Microsoft Teams ou Surface Hubs dans une salle de réunion, vous pouvez configurer des réunions coordonnées. Les réunions coordonnées vous permettent de configurer vos appareils salles Teams et Surface Hubs afin que, lorsque vous participez à une réunion sur un appareil, les autres appareils de la salle soient également joints à la même réunion. Vous pouvez configurer vos caméras, haut-parleurs et microphones afin que ceux qui offrent aux participants la meilleure expérience soient activés tandis que d’autres sont désactivés. Cela permet d’éviter l’écho redouté et les commentaires que les participants peuvent rencontrer lors de l’ajout de plusieurs appareils à une réunion.

Pour configurer des réunions coordonnées, vous devez vous assurer que vos appareils salles Teams et surface Hubs sont déjà correctement configurés pour participer aux réunions. Plus important encore, chaque appareil doit avoir sa propre boîte aux lettres de salle Exchange. Pour plus d’informations sur la façon de les configurer, consultez les articles suivants :

- [Déployer les Salles Microsoft Teams](../rooms/rooms-deploy.md)
- [Créer un compte d’appareil Surface Hub 2S](/surface-hub/surface-hub-2s-account)

Une fois que vous avez confirmé que vos appareils salles Teams et Surface Hubs peuvent accepter automatiquement les réunions et les rejoindre avec succès, vous pouvez configurer des réunions coordonnées.

Les étapes suivantes doivent être effectuées séparément pour chaque salle de réunion.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Étape 1 : Planifier votre expérience de réunion coordonnée

Avant d’apporter des modifications à la configuration, vous devez décider quels appareils feront quoi dans chaque salle de réunion. Autrement dit, pour une salle de réunion donnée, vous devez décider quel appareil aura le microphone, la caméra et le tableau blanc actifs. La façon dont vous configurez vos appareils dépend de votre environnement spécifique, mais voici quelques recommandations générales pour commencer :

- **Microphone** salles Teams appareil
- **Appareil photo** salles Teams (activé par défaut) et Surface Hub (désactivé par défaut, mais autorisé à être activé par les participants)
- **Tableau** Surface Hub

> [!IMPORTANT]
> Veillez à activer le microphone sur un seul appareil. Si vous l’activez sur plusieurs appareils, vous obtiendrez un écho audio et des commentaires.

## <a name="step-2-get-your-devices-upns"></a>Étape 2 : Obtenir les UPN de vos appareils

Lorsque vous configurez une expérience de réunion coordonnée dans une salle de réunion, vous devez indiquer aux appareils salles Teams et aux Surface Hubs de cette salle les appareils avec lesquels se coordonner. Pour ce faire, ajoutez le nom d’utilisateur principal (UPN) des appareils avec lesquels il doit se coordonner à sa configuration. Si vous ne connaissez pas les upN pour chacun des appareils que vous souhaitez configurer pour les réunions coordonnées, vous pouvez les trouver à l’aide de la Centre d'administration Microsoft 365. 

Vous devez disposer d’un rôle d’administrateur pour accéder au Centre d'administration Microsoft 365. Pour plus d’informations, consultez [À propos des rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles).

Pour obtenir les upN de vos appareils salles Teams et surface Hubs, procédez comme suit :

1. Connectez-vous au Centre d'administration Microsoft 365 en visitant https://admin.microsoft.com.
2. Accédez à **Utilisateurs** > **actifs**.
3. Recherchez le nom de votre appareil salles Teams ou surface Hub dans la colonne **Nom d’affichage** (vous pouvez utiliser la zone **de recherche** si vous avez de nombreux utilisateurs).
4. Recherchez l’UPN dans la colonne **Username** (il ressemblera à alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Répétez cette opération pour chaque appareil qui participera aux réunions coordonnées.

## <a name="step-3-create-a-deployment-worksheet"></a>Étape 3 : Créer une feuille de calcul de déploiement

Une fois que vous avez planifié votre expérience de réunion coordonnée et collecté une liste des UPN de vos appareils, il est judicieux de créer une feuille de calcul de déploiement. Une feuille de calcul de déploiement vous permet de visualiser la configuration que vous souhaitez définir sur tous vos appareils, ce qui vous permet de valider vos choix et de rechercher des erreurs.

Dans une application de feuille de calcul, ajoutez des lignes pour les éléments suivants dans la première colonne :

| Paramètres                | Description      |
|------------------------|-----------------|
| **Valeur audio par défaut**      | Détermine sur quel appareil le microphone sera actif au démarrage d’une réunion. Un seul appareil (généralement un appareil salles Teams) peut avoir ce champ défini `true` sur tandis que le reste des appareils doit avoir ce champ défini pour `false` éviter l’écho audio et les commentaires.          |
| **Audio activé**      | Détermine si les participants à une réunion peuvent activer ou désactiver le microphone. Les appareils sur lesquels la **valeur par défaut audio** est définie `false` doivent avoir ce paramètre défini pour `false` que les participants ne puissent pas activer accidentellement un microphone et provoquer un écho audio ou des commentaires.<p>Si **la valeur par défaut de** l’audio est définie `true`sur , ce paramètre est ignoré et les participants peuvent désactiver ou désactiver le son du microphone.          |
| **Valeur par défaut de la vidéo**      | Détermine sur quel appareil la caméra sera active au démarrage d’une réunion. Pour une expérience optimale, nous vous recommandons de définir `true` uniquement le salles Teams appareil, tandis que tous les autres appareils sont définis `false`sur .          |
| **Vidéo activée**      | Détermine si les participants à une réunion peuvent activer ou désactiver la caméra. Vous pouvez définir cette `true` option sur tous les autres appareils de l’événement que les participants souhaitent partager différentes perspectives vidéo (par exemple, si un participant utilise le tableau blanc Surface Hub). Si vous ne souhaitez pas que les participants activent ou désactivent une caméra sur un appareil, définissez cette `false`option sur .<p> Si **la valeur par défaut** de la vidéo est définie `true`sur , ce paramètre est ignoré et les participants peuvent activer ou désactiver l’appareil photo.         |
| **Tableau blanc par défaut** | Détermine si l’appareil salles Teams affichera un tableau blanc partagé par l’un des participants à la réunion. Nous vous recommandons de définir cette `false` valeur sur si vous avez un Surface Hub et `true` si vous n’en avez pas. Ce paramètre n’a aucun effet sur les Surface Hubs. Surface Hubs affiche toujours un tableau blanc partagé par les participants à la réunion.         |
| **Tableau blanc activé** | Détermine si les participants à une réunion peuvent activer ou désactiver le tableau blanc. Si vous ne souhaitez pas que les participants activent ou désactivent le tableau blanc sur un appareil, définissez cette `false`option sur . <p>Si **la valeur par défaut du tableau blanc** est définie `true`sur , ce paramètre est ignoré et les participants peuvent activer ou désactiver le tableau blanc.
| **Comptes approuvés**   | Il s’agit d’une liste d’UPN séparés par des virgules pour chaque appareil salles Teams ou Surface Hub à partir duquel l’appareil doit accepter les demandes de participation à une réunion ou à partir desquels les demandes de participation à une réunion doivent être envoyées. |

Dans les colonnes suivantes, ajoutez chacun de vos appareils salles Teams et Surface Hubs. Dans chaque colonne, renseignez les valeurs qui correspondent à l’expérience souhaitée pour la salle de réunion. Voici un exemple avec un appareil salles Teams et un Surface Hub :

- Appareil Teams
  - L’audio et la vidéo sont **activés** lors du démarrage d’une réunion. Les participants **peuvent** activer ou désactiver l’audio et la vidéo.
  - L’affichage d’un tableau blanc partagé est désactivé.
- Surface Hub
  - L’audio est **désactivé** au démarrage d’une réunion. Les participants **ne peuvent pas** activer ou désactiver l’audio.
  - La vidéo est **désactivée** au démarrage d’une réunion. Les participants **peuvent** activer ou désactiver la vidéo.

| Paramètres                | Salle Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Valeur audio par défaut**      | `true`          | `false`          |
| **Audio activé**      | `true`          | `false`          |
| **Valeur par défaut de la vidéo**      | `true`          | `false`          |
| **Vidéo activée**      | `true`          | `true`           |
| **Tableau blanc par défaut** | `false`         | `false`          |
| **Comptes approuvés**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Étape 4 : Configurer salles Teams appareil

Vous pouvez configurer des réunions coordonnées sur un appareil salles Teams à l’aide de l’écran tactile de l’appareil ou, si vous devez configurer de nombreux appareils et que vous souhaitez le faire à partir d’un emplacement central, vous pouvez utiliser un fichier de configuration XML.

Utilisez la feuille de calcul que vous avez créée à l’étape précédente pour vous aider à configurer vos appareils.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Utiliser l’écran tactile de l’appareil salles Teams

Pour configurer des réunions coordonnées sur un appareil, procédez comme suit :

1. Sélectionnez **... Autres** > **paramètres**.
2. Entrez le mot de passe Administrateur et sélectionnez **Oui**.
3. Sélectionnez **Réunions coordonnées**.
4. Sous **Options**, définissez la **réunion coordonnée** _sur activé_.
5. Si la **valeur par défaut de** l’audio dans votre feuille de calcul est `true`, **activez le microphone de cet appareil** , sinon laissez-le _désactivé_.
6. Si **l’option Audio est activée** dans votre feuille de calcul `true`, **sélectionnez Autoriser les personnes à participer à une réunion** sous **Activer le microphone de cet appareil**. Cette option ne peut pas être désactivée si le **microphone de cet appareil** est activé.
7. Si **la valeur par défaut** de la vidéo dans votre feuille de calcul est `true`, **activez la caméra de cet appareil** , sinon laissez-la _désactivée_.
8. Si **la vidéo activée** dans votre feuille de calcul est `true`activée, sélectionnez **Autoriser les personnes à participer à une réunion** sous **Activer l’appareil photo de cet appareil**. Cette option ne peut pas être désactivée si **l’option Activer l’appareil photo de cet appareil** est _activée._
9. Si **la valeur par défaut du tableau blanc** dans votre feuille de calcul est `true`, **définissez activer le tableau blanc sur cet appareil**_, sinon_ laissez-le _désactivé_.
10. Sous **Comptes d’appareil approuvés**, tapez chaque UPN répertorié dans **les comptes approuvés** de votre feuille de calcul. Séparez plusieurs UPN par des virgules.
11. Sur l’appareil approuvé, désactivez la proximité et la pièce distante. 
12. Sélectionnez **Enregistrer et quitter**.

Une fois que vous avez sélectionné **Enregistrer et quitter**, l’appareil redémarre et il est prêt à participer aux réunions coordonnées.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Utiliser le fichier de configuration XML salles Teams

Les réunions coordonnées peuvent être configurées à l’aide du fichier de configuration XML de `SkypeSettings.xml` l’appareil salles Teams. Le `SkypeSettings.xml` fichier n’est pas un fichier statique. Lorsque l’appareil salles Teams démarre, il recherche `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` un fichier nommé `SkypeSettings.xml`. Si le fichier existe, l’appareil lit et applique la configuration spécifiée dans le fichier. Une fois la configuration appliquée, le fichier est supprimé. Pour plus d’informations sur le `SkypeSettings.xml` fichier, consultez [Gérer les paramètres de la console avec un fichier de configuration XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Voici la syntaxe des paramètres réunions coordonnées dans le fichier de configuration :

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Pour configurer des réunions coordonnées sur un appareil, procédez comme suit :

1. Dans un éditeur de fichier texte, tel que Visual Studio Code ou le Bloc-notes, collez le code XML ci-dessus dans un nouveau fichier.

2. Définissez chacun des éléments XML sur la valeur ou `false` la valeur correspondante `true` dans votre feuille de calcul. Par exemple, si **la valeur par défaut de l’audio** est `true`, définissez `<Audio default="true">`.

3. Veillez à modifier `TrustedAccounts` votre liste d’UPN.

4. Enregistrez le fichier portant le nom `SkypeSettings.xml`.

5. Placez le fichier dans le dossier de `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` l’appareil salles Teams. Vous pouvez effectuer cette opération de plusieurs façons :

    - **Copiez le fichier sur votre appareil salles Teams** Vous devez activer le partage de fichiers et créer un partage réseau avant de pouvoir copier des fichiers sur votre appareil. Après cela, vous pouvez vous connecter au partage réseau et copier le fichier sur l’appareil. Pour plus d’informations, consultez [Salles Microsoft Teams maintenance et opérations](../rooms/rooms-operations.md).
    - **Utilisez une stratégie de groupe** Créer une stratégie de groupe pour copier le fichier sur l’appareil. Pour plus d’informations, consultez [stratégie de groupe Vue d’ensemble](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Téléchargez le fichier sur l’appareil salles Teams** Vous pouvez vous connecter à l’appareil à l’aide du mode Administration, puis copier le fichier sur l’appareil à partir d’un partage réseau ou d’un lecteur USB. Pour plus d’informations, consultez [Basculement vers le mode Administration](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Redémarrez l’appareil. Vous pouvez effectuer cette opération de deux façons :

    - **PowerShell distant** Vous pouvez exécuter la commande Shutdown sur l’appareil à l’aide de Remote PowerShell. Pour plus d’informations, consultez [Gestion à distance à l’aide de PowerShell](../rooms/rooms-operations.md).
    - **Exécuter Restart-Computer** Vous pouvez exécuter l’applet `Restart-Computer` de commande sur votre ordinateur local et spécifier le nom de l’ordinateur de l’appareil à redémarrer. Pour plus d’informations, consultez [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Étape 5 : Configurer le Surface Hub

Vous pouvez utiliser le Concepteur de configuration Windows pour créer un package d’approvisionnement que vous pouvez utiliser pour appliquer les paramètres de coordination des réunions à vos Surface Hubs. Vous allez coller le fichier XML que vous avez créé ci-dessus dans le Concepteur de configuration Windows pour créer le package d’approvisionnement.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Créer un fichier de configuration XML de réunions coordonnées pour le Surface Hub

Le Concepteur de configuration Windows et Microsoft Intune sont utilisés pour appliquer la configuration des réunions coordonnées à vos Surface Hubs. La configuration est définie à l’aide de XML. Avant d’aller plus loin, vous devez créer le code XML qui sera appliqué.

Voici la syntaxe du fichier de configuration XML réunions coordonnées.

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

Procédez comme suit pour préparer le code XML pour le Concepteur de configuration Windows ou Microsoft Intune :

1. Dans un éditeur de fichier texte, tel que Visual Studio Code ou le Bloc-notes, collez le code XML ci-dessus dans un nouveau fichier.

2. Définissez chacun des éléments XML sur la valeur ou `false` la valeur correspondante `true` dans votre feuille de calcul. Par exemple, si **la valeur par défaut de l’audio** est `true`, définissez `<Audio default="true">`.

3. Veillez à modifier `TrustedAccounts` votre liste d’UPN.

4. Le Concepteur de configuration Windows requiert que le code XML soit sur une seule ligne. Supprimez tous les sauts de ligne entre chaque ligne afin que le code XML ressemble à ce qui suit :

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Enregistrez le fichier sur votre ordinateur.

Une fois que vous avez créé votre fichier de configuration XML, suivez les [étapes décrites dans Gérer les paramètres Microsoft Teams sur Surface Hub](surface-hub-manage-config.md) pour l’appliquer à vos Surface Hubs.
