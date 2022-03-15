---
title: Configurer des réunions coordonnées avec des Salles Microsoft Teams réunion Surface Hub
ms.author: czawideh
author: cazawideh
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Configurez salles Teams appareils et des Surface Hub pour participer à des réunions quand un appareil ou l’autre participe à une réunion.
ms.openlocfilehash: 5c52b1f6465db57613f45401c425a05286503454
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503701"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurer des réunions coordonnées avec des Salles Microsoft Teams et des Surface Hub

Si vous avez un ou plusieurs Salles Microsoft Teams surface Hub dans une salle de réunion, vous pouvez configurer des réunions coordonnées. Les réunions coordonnées vous permet de configurer vos appareils salles Teams et Surface Hub de façon à ce que, lorsque vous rejoignez une réunion sur un appareil, les autres appareils de la salle soient également joints à la même réunion. Vous pouvez configurer vos caméras, haut-parleurs et microphones de façon à ce que ceux qui offrent le meilleur expérience aux participants soient activés tandis que d’autres sont désactivés. Cela permet d’éviter l’écho dreaded et le bruit des commentaires que les participants peuvent rencontrer lors de l’ajout de plusieurs appareils à une réunion.

Pour configurer des réunions coordonnées, vous devez vous assurer que vos appareils salles Teams et Surface Hub sont déjà correctement configurés pour participer aux réunions. Mais surtout, chaque appareil doit avoir sa propre boîte aux lettres Exchange salle. Pour plus d’informations sur leur mise en place, consultez les articles suivants :

- [Déployer les Salles Microsoft Teams](../rooms/rooms-deploy.md)
- [Créer Surface Hub compte d’appareil 2S](/surface-hub/surface-hub-2s-account)

Après avoir confirmé que vos appareils salles Teams et Surface Hub peuvent accepter automatiquement les réunions et les rejoindre avec succès, vous pouvez configurer des réunions coordonnées.

Les étapes suivantes doivent être effectuées pour chaque salle de réunion séparément.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Étape 1 : planifier votre expérience de réunion coordonnée

Avant d’apporter des modifications de configuration, vous devez décider des périphériques qui feront quoi dans chaque salle de réunion. Autrement dit, pour une salle de réunion donnée, vous devez choisir quel périphérique aura le microphone, la caméra et le tableau blanc actifs. La configuration de vos appareils dépend de votre environnement spécifique, mais voici quelques recommandations générales à prendre en compte :

- **Microphone** salles Teams device
- **Appareil** photo salles Teams (option par défaut) et Surface Hub (désactivée par défaut, mais autorisée à être allumée par les participants)
- **Tableau blanc** Surface Hub

> [!IMPORTANT]
> Veillez à n’activer le microphone que sur un appareil. Si vous l’activez sur plusieurs appareils, vous aurez un retour audio et des commentaires.

## <a name="step-2-get-your-devices-upns"></a>Étape 2 : obtenir les upns de vos appareils

Lorsque vous définissez une expérience de réunion coordonnée dans une salle de réunion, vous devez indiquer aux appareils salles Teams et surface Hubs de cette salle avec lesquels les appareils doivent être coordonnés. Pour ce faire, ajoutez le nom d’utilisateur principal (UPN) des appareils avec qui il doit s’coordonner à sa configuration. Si vous ne connaissez pas les upns de chacun des appareils que vous souhaitez configurer pour les réunions coordonnées, vous pouvez les trouver à l’aide de la Centre d'administration Microsoft 365. 

Un rôle d’administrateur doit vous être attribué pour pouvoir accéder à la Centre d'administration Microsoft 365. Pour plus d’informations, voir [À propos des rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles).

Pour obtenir les upns de vos appareils salles Teams surface Hub, vous pouvez :

1. Connectez-vous au Centre d'administration Microsoft 365 par visitehttps://admin.microsoft.com.
2. Allez aux **utilisateurs UsersActive** > **.**
3. Recherchez le nom de votre salles Teams ou Surface Hub dans la colonne Nom complet (vous  pouvez utiliser la zone de recherche si vous  avez de nombreux utilisateurs).
4. Recherchez le nom d’utilisateur utilisateur dans la colonne **Nom** d’utilisateur (il ressemblera à alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Répétez cette opération pour chaque appareil qui participera aux réunions coordonnées.

## <a name="step-3-create-a-deployment-worksheet"></a>Étape 3 : créer une feuille de calcul de déploiement

Après avoir planifié votre expérience de réunion coordonnée et rassemblé une liste des upN de vos appareils, il est important de créer une feuille de calcul de déploiement. Une feuille de calcul de déploiement vous aide à visualiser la configuration que vous voulez définir sur l’ensemble de vos appareils, ce qui vous permet de valider vos choix et de vérifier les erreurs.

Dans une application de feuille de calcul, ajoutez des lignes pour ce qui suit dans la première colonne :

| Paramètres                | Description      |
|------------------------|-----------------|
| **Audio default**      | Détermine le périphérique sur lequel le microphone sera actif lorsqu’une réunion débute. Un seul appareil (généralement un appareil salles Teams) `true` `false` peut définir ce champ tandis que le champ de ce champ doit être utilisé pour éviter l’écho et les commentaires des autres appareils.          |
| **Audio activé**      | Détermine si les participants à une réunion peuvent ou non éteindre le microphone. Les périphériques  `false` `false` sur lesquels l’audio est réglé par défaut doivent avoir ce paramètre réglé de sorte que les participants ne peuvent pas activer accidentellement un microphone et provoquer un écho ou des commentaires audio.<p>Si **la valeur audio** par défaut est définie sur `true`, ce paramètre est ignoré et les participants peuvent activer ou désactiver le micro.          |
| **Vidéo par défaut**      | Détermine le périphérique sur lequel l’appareil photo sera actif lorsqu’une réunion commence. Pour une expérience utilisateur qui soit la meilleure possible, nous vous recommandons de définir le salles Teams uniquement `true` lorsque tous les autres appareils sont réglés sur `false`.          |
| **Vidéo activée**      | Détermine si les participants à une réunion peuvent faire bascule l’appareil photo sur ou hors de l’appareil photo. Vous pouvez définir cette `true` action sur tous les autres appareils dans l’événement que les participants souhaitent partager avec d’autres perspectives vidéo (par exemple, si un participant utilise le tableau Surface Hub blanc). Si vous ne voulez pas que les participants activer ou désactiver une caméra sur un appareil, définissez cette fonction sur `false`.<p> Si **la vidéo est** définie par défaut `true`sur, ce paramètre est ignoré et les participants peuvent activer ou désactiver la caméra.         |
| **Tableau blanc par défaut** | Détermine si l’salles Teams affiche un tableau blanc partagé par l’un des participants à la réunion. Nous vous recommandons de le définir `false` si vous avez une Surface Hub et `true` si vous n’en avez pas. Ce paramètre n’a aucun effet sur les Surface Hubs. Les Surface Hubs afficheront toujours un tableau blanc partagé par les participants à la réunion.         |
| **Tableau blanc activé** | Détermine si les participants à une réunion peuvent ou non utiliser le tableau blanc. Si vous ne voulez pas que les participants activer ou désactiver le tableau blanc sur un appareil, définissez cette fonction sur `false`. <p>Si **l’option Tableau** blanc par défaut est définie sur `true`, ce paramètre est ignoré et les participants peuvent activer ou désactiver le tableau blanc.
| **Comptes de confiance**   | Il s’agit d’une liste séparée par des virgules des upns pour chaque appareil ou Surface Hub de salle Teams à partir duquel l’appareil doit accepter les demandes de réunion ou vers laquelle les demandes de réunion doivent être envoyées. |

Dans les colonnes suivantes, ajoutez chacun de vos appareils salles Teams surface Hub. Dans chaque colonne, remplissez les valeurs correspondant à l’expérience que vous voulez pour la salle de réunion. Voici un exemple avec un salles Teams et un Surface Hub :

- Teams appareil
  - L’audio et la vidéo **sont allumés** au début d’une réunion. Les **participants peuvent** faire des basculements audio et vidéo sur ou non.
  - L’affichage d’un tableau blanc partagé est désactivé.
- Surface Hub
  - L’audio **est désactivé lorsqu’une** réunion commence. Les **participants ne peuvent pas** faire des basculements audio.
  - La vidéo est **désactivée au** début d’une réunion. Les **participants peuvent** utiliser ou non la vidéo.

| Paramètres                | Teams salle      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio default**      | `true`          | `false`          |
| **Audio activé**      | `true`          | `false`          |
| **Vidéo par défaut**      | `true`          | `false`          |
| **Vidéo activée**      | `true`          | `true`           |
| **Tableau blanc par défaut** | `false`         | `false`          |
| **Comptes de confiance**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Étape 4 : configurer salles Teams appareil

Vous pouvez configurer des réunions coordonnées sur un appareil salles Teams à l’aide de l’écran tactile de l’appareil ou, si vous devez configurer plusieurs appareils et que vous souhaitez le faire à partir d’un emplacement central, vous pouvez utiliser un fichier de configuration XML.

Utilisez la feuille de calcul que vous avez créée à l’étape précédente pour configurer vos appareils.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Utiliser l’salles Teams tactile de votre appareil

Pour configurer des réunions coordonnées sur un appareil, vous pouvez :

1. **Sélectionnez ... Plus** >  **Paramètres**.
2. Entrez le mot de passe administrateur, puis sélectionnez **Oui**.
3. **Sélectionnez Réunions coordonnées**.
4. Sous **Options**, définissez **l’option Réunion** _coordonnée sur._
5. Si **l’audio** est utilisé par `true`défaut dans votre feuille de calcul, définissez **l’option** Activer le microphone de cet appareil, sinon laissez-la _hors option_.
6. Si **l’audio est activé** dans votre `true`feuille de calcul, sélectionnez Permettre aux utilisateurs d’activer lorsque vous rejoignez une réunion sous Activer le **microphone de cet appareil**. Cette option ne peut pas être désactivée si le **microphone de cet** appareil est allumé.
7. Si **la fonction vidéo** par défaut est définie `true`sur votre feuille de calcul, définissez **l’option Activer l’appareil** photo de cet appareil, sinon laissez cette _option hors option_.
8. Si **la vidéo est activée** dans votre feuille `true`de calcul,  sélectionnez Permettre aux utilisateurs d’activer lorsque vous participez à une réunion sous Activer la **caméra de cet appareil**. Cette option ne peut pas être désactivée si **l’option Activer l’appareil photo** de cet _appareil est allumée_.
9. Si **l’option Tableau blanc** par défaut est définie `true`sur  votre feuille de calcul, définissez l’option Activer le tableau blanc sur cet _appareil._ _Autrement, laissez-la désactiver_.
10. Sous **Comptes d’appareils de confiance**, tapez chaque nom d’utilisateur utilisateur (UPN) répertorié **dans les comptes de confiance** de votre feuille de calcul. Séparez les différents upns par des virgules.
11. Sélectionnez **Enregistrer et quitter**.

Une fois que **vous avez sélectionné Enregistrer et quitter**, l’appareil redémarre et il est prêt à participer aux réunions coordonnées.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Utiliser le fichier salles Teams de configuration XML complet

Les réunions coordonnées peuvent être définies à l’aide `SkypeSettings.xml` du salles Teams de configuration XML de votre appareil. Le `SkypeSettings.xml` fichier n’est pas statique. Au démarrage salles Teams d’un appareil, celui-ci recherche `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` un fichier nommé`SkypeSettings.xml`. Si le fichier existe, l’appareil lit et applique la configuration spécifiée dans le fichier. Une fois la configuration appliquée, le fichier est supprimé. Pour plus d’informations sur le `SkypeSettings.xml` fichier, voir [Gérer les paramètres de la console avec un fichier de configuration XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Voici la syntaxe des paramètres de réunion coordonnées dans le fichier de configuration :

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

Pour configurer des réunions coordonnées sur un appareil, vous pouvez :

1. Dans un éditeur de fichiers texte, par exemple, Visual Studio Code ou Bloc-notes texte, collez le fichier XML ci-dessus dans un nouveau fichier.

2. Définissez chacun des éléments XML sur la valeur ou la `true` `false` valeur correspondante dans votre feuille de calcul. Par exemple, si la **valeur audio par défaut** est `true`définie.`<Audio default="true">`

3. N’oubliez pas de `TrustedAccounts` modifier votre liste d’upns.

4. Enregistrez le fichier avec le nom `SkypeSettings.xml`.

5. Placez le fichier dans le salles Teams de l’appareil`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Vous pouvez faire cela de plusieurs façons :

    - **Copiez le fichier sur votre salles Teams appareil**. Vous devez activer le partage de fichiers et créer un partage réseau avant de pouvoir copier des fichiers sur votre appareil. Vous pouvez ensuite vous connecter au partage réseau et copier le fichier sur l’appareil. Pour plus d’informations, [voir Salles Microsoft Teams maintenance et les opérations](../rooms/rooms-operations.md).
    - **Utiliser une stratégie de groupe** Créez une stratégie de groupe pour copier le fichier sur l’appareil. Pour plus d’informations, voir [Vue d’ensemble de la stratégie de groupe](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Téléchargez le fichier sur l’appareil salles Teams** Vous pouvez vous connecter à l’appareil à l’aide du mode d’administration, puis copier le fichier sur l’appareil à partir d’un partage réseau ou d’un lecteur USB. Pour plus d’informations, [voir Passer en mode Administrateur](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Redémarrez l’appareil. Vous pouvez faire cela de deux façons :

    - **Remote PowerShell** Vous pouvez exécuter la commande d’arrêt sur l’appareil à l’aide de Remote PowerShell. Pour plus d’informations, voir [Gestion à distance à l’aide de PowerShell](../rooms/rooms-operations.md).
    - **Exécuter l’ordinateur-redémarrage** Vous pouvez exécuter l’cmdlet `Restart-Computer` sur votre ordinateur local et spécifier le nom d’ordinateur de l’appareil que vous voulez redémarrer. Pour plus d’informations, [voir Redémarrer l’ordinateur](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Étape 5 : configurer Surface Hub

Vous pouvez utiliser Windows Configuration Designer pour créer un package d’approvisionnement que vous pouvez utiliser pour appliquer des paramètres de réunions coordonnés à vos Surface Hubs. Vous collez le fichier XML que vous avez créé ci-dessus dans Windows Configuration Designer pour créer le package de mise en service.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Créer un fichier XML de configuration de réunions coordonnées pour Surface Hub

Les Windows Configuration Designer et Microsoft Intune sont utilisés pour appliquer la configuration des réunions coordonnées à vos Surface Hubs. La configuration se définit à l’aide de XML. Avant d’aller plus loin, vous devez créer le XML qui sera appliqué.

La syntaxe suivante est celle du fichier XML de configuration des réunions coordonnées.

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

Pour préparer le XML pour Windows Configuration Designer ou Microsoft Intune, vous pouvez :

1. Dans un éditeur de fichiers texte, par exemple, Visual Studio Code ou Bloc-notes texte, collez le fichier XML ci-dessus dans un nouveau fichier.

2. Définissez chacun des éléments XML sur la valeur ou la `true` `false` valeur correspondante dans votre feuille de calcul. Par exemple, si la **valeur audio par défaut** est `true`définie.`<Audio default="true">`

3. N’oubliez pas de `TrustedAccounts` modifier votre liste d’upns.

4. Windows Configuration Designer nécessite que le XML soit sur une seule ligne. Supprimez tous les coupures de ligne entre chaque ligne de sorte que le XML ressemble à ce qui suit :

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Enregistrez le fichier sur votre ordinateur.

Après avoir créé votre fichier de configuration XML, utilisez les étapes de La gestion des [paramètres](surface-hub-manage-config.md) Microsoft Teams sur Surface Hub pour l’appliquer à vos Surface Hubs.