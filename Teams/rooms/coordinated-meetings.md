---
title: Configurer des réunions coordonnées avec des salles Microsoft Teams et Surface Hub
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
description: Configurez les appareils Salles Teams et Surface Hub pour participer à des réunions quand un appareil ou un autre participe à une réunion.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803936"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurer des réunions coordonnées avec des salles Microsoft Teams et Surface Hub

Si vous disposez d’un ou plusieurs appareils Salles Microsoft Teams ou Surface Hub dans une salle de réunion, vous pouvez configurer des réunions coordonnées. Les réunions coordonnées vous permet de configurer vos appareils Salles d’équipe et Surface Hub de façon à ce que, lorsque vous rejoignez une réunion sur un appareil, les autres appareils de la salle soient également joints à la même réunion. Vous pouvez configurer vos caméras, haut-parleurs et microphones de façon à ce que ceux qui offrent le meilleur expérience aux participants soient activés tandis que d’autres sont désactivés. Cela permet d’éviter l’écho dreaded et le bruit des commentaires que les participants peuvent rencontrer lors de l’ajout de plusieurs appareils à une réunion.

Pour configurer des réunions coordonnées, vous devez vous assurer que vos appareils Salles d’équipe et Surface Hub sont déjà correctement configurés pour participer aux réunions. Mais surtout, chaque appareil doit avoir sa propre boîte aux lettres de salle Exchange. Pour plus d’informations sur leur mise en place, consultez les articles suivants :

- [Déployer les Salles Microsoft Teams](../rooms/rooms-deploy.md)
- [Créer un compte d’appareil Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Après avoir confirmé que vos appareils Salles d’équipe et Surface Hub peuvent accepter automatiquement les réunions et les rejoindre avec succès, vous pouvez configurer des réunions coordonnées.

Les étapes suivantes doivent être effectuées pour chaque salle de réunion séparément. Les appareils dans une salle de réunion ne doivent pas être configurer pour des réunions coordonnées avec des appareils dans d’autres salles de réunion.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Étape 1 : planifier votre expérience de réunion coordonnée

Avant d’apporter des modifications de configuration, vous devez décider des périphériques qui feront quoi dans chaque salle de réunion. Autrement dit, pour une salle de réunion donnée, vous devez choisir quel périphérique aura le microphone, la caméra et le tableau blanc actifs. La configuration de vos appareils dépend de votre environnement spécifique, mais voici quelques recommandations générales à prendre en compte :

- **Microphone** Appareil Salles Teams
- **Appareil photo** Périphérique Salles d’équipes (par défaut) et Surface Hub (désactivé par défaut, mais autorisé à être allumé par les participants)
- **Tableau blanc** Surface Hub

> [!IMPORTANT]
> Veillez à n’activer le microphone que sur un appareil. Si vous l’activez sur plusieurs appareils, vous aurez un retour audio et des commentaires.

## <a name="step-2-get-your-devices-upns"></a>Étape 2 : obtenir les upns de vos appareils

Lorsque vous définissez une expérience de réunion coordonnée dans une salle de réunion, vous devez indiquer aux appareils Salles d’équipe et Surface Hub de cette salle avec lesquels les appareils doivent être coordonnés. Pour ce faire, ajoutez le nom d’utilisateur principal (UPN) des appareils avec qui il doit s’coordonner à sa configuration. Si vous ne connaissez pas les upns de chacun des appareils que vous souhaitez configurer pour les réunions coordonnées, vous pouvez les trouver via le Centre d’administration Microsoft 365. 

Un rôle d’administrateur doit vous être attribué pour pouvoir accéder au Centre d’administration Microsoft 365. Pour plus d’informations, voir [À propos des rôles d’administrateur.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

Pour obtenir les upns de vos appareils Salles d’équipe et Surface Hub, vous pouvez :

1. Connectez-vous au Centre d’administration Microsoft 365 en visitant https://admin.microsoft.com .
2. Allez à **Utilisateurs**  >  **actifs.**
3. Recherchez le nom de votre appareil Salles Teams ou Surface  Hub dans la colonne **Nom** complet (vous pouvez utiliser la zone de recherche si vous avez de nombreux utilisateurs).
4. Recherchez le nom d’utilisateur utilisateur dans la colonne **Nom** d’utilisateur (il ressemblera alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Répétez cette opération pour chaque appareil qui participera aux réunions coordonnées.

## <a name="step-3-create-a-deployment-worksheet"></a>Étape 3 : créer une feuille de calcul de déploiement

Après avoir planifié votre expérience de réunion coordonnée et rassemblé une liste des upN de vos appareils, il est important de créer une feuille de calcul de déploiement. Une feuille de calcul de déploiement vous aide à visualiser la configuration que vous voulez définir sur l’ensemble de vos appareils, ce qui vous permet de valider vos choix et de vérifier les erreurs.

Dans une application de feuille de calcul, ajoutez des lignes pour ce qui suit dans la première colonne :

| Paramètres                | Description      |
|------------------------|-----------------|
| **Audio default**      | Détermine le périphérique sur lequel le microphone sera actif au début d’une réunion. Un seul appareil (généralement un appareil Salles d’équipe) peut définir ce champ tandis que le reste des périphériques doit avoir ce champ pour éviter l’écho et les commentaires `true` `false` audio.          |
| **Audio activé**      | Détermine si les participants à une réunion peuvent faire bascule le microphone. Les périphériques sur lesquels  `false` l’audio est réglé par défaut doivent avoir ce paramètre réglé de sorte que les participants ne peuvent pas activer accidentellement un microphone et provoquer un écho ou des commentaires `false` audio.<p>Si **la valeur audio** par défaut est définie sur, ce paramètre est ignoré et les participants peuvent activer ou désactiver le `true` micro.          |
| **Vidéo par défaut**      | Détermine le périphérique sur lequel l’appareil photo sera actif lorsqu’une réunion commence. Pour une expérience qui soit la meilleure possible, nous vous recommandons de définir uniquement l’appareil Salles d’équipe lorsque tous les autres `true` appareils sont réglés sur `false` .          |
| **Vidéo activée**      | Détermine si les participants à une réunion peuvent faire bascule la caméra sur ou non. Vous pouvez définir ce point sur tous les autres appareils au cours de l’événement pour que les participants partagent différentes perspectives vidéo (par exemple, si un participant utilise le tableau blanc `true` de Surface Hub). Si vous ne voulez pas que les participants activer ou désactiver une caméra sur un appareil, définissez cette fonction sur `false` .<p> Si **la vidéo est** définie par défaut sur, ce paramètre est ignoré et les participants peuvent activer ou désactiver la `true` caméra.         |
| **Tableau blanc par défaut** | Détermine si l’appareil Salles Teams affichera un tableau blanc partagé par l’un des participants à la réunion. Nous vous recommandons de le définir si vous n’avez pas de Surface Hub et si vous `false` `true` n’en avez pas. Ce paramètre n’a aucun effet sur les Surface Hubs. Les Surface Hubs afficheront toujours un tableau blanc partagé par les participants à la réunion.         |
| **Tableau blanc activé** | Détermine si les participants à une réunion peuvent ou non utiliser le tableau blanc. Si vous ne voulez pas que les participants activer ou désactiver le tableau blanc sur un appareil, définissez cette fonction sur `false` . <p>Si **l’option Tableau** blanc par défaut est définie sur, ce paramètre est ignoré et les participants peuvent activer ou désactiver le tableau `true` blanc.
| **Comptes de confiance**   | Il s’agit d’une liste séparée par des virgules d’UPN pour chaque appareil Teams Room ou Surface Hub à partir duquel l’appareil doit accepter les demandes de réunion ou vers laquelle les demandes de réunion doivent être envoyées. |

Dans les colonnes suivantes, ajoutez chacun de vos appareils Salles d’équipe et Surface Hub. Dans chaque colonne, remplissez les valeurs correspondant à l’expérience que vous voulez pour la salle de réunion. Voici un exemple avec un appareil Salles Teams et un Surface Hub :

- Appareil Teams
  - L’audio et la vidéo **sont allumés** au début d’une réunion. Les **participants peuvent** faire des basculements audio et vidéo sur ou non.
  - L’affichage d’un tableau blanc partagé est désactivé.
- Surface Hub
  - L’audio **est désactivé lorsqu’une** réunion commence. Les **participants ne peuvent pas** faire des basculements audio.
  - La vidéo est **désactivée lorsqu’une** réunion commence. Les **participants peuvent** utiliser ou non la vidéo.

| Paramètres                | Salle Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio default**      | `true`          | `false`          |
| **Audio activé**      | `true`          | `false`          |
| **Vidéo par défaut**      | `true`          | `false`          |
| **Vidéo activée**      | `true`          | `true`           |
| **Tableau blanc par défaut** | `false`         | `false`          |
| **Comptes de confiance**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Étape 4 : configurer l’appareil Salles Teams

Vous pouvez configurer des réunions coordonnées sur un appareil Salles Teams à l’aide de l’écran tactile de l’appareil ou, si vous devez configurer plusieurs appareils et que vous souhaitez le faire à partir d’un emplacement central, vous pouvez utiliser un fichier de configuration XML.

Utilisez la feuille de calcul que vous avez créée à l’étape précédente pour configurer vos appareils.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Utiliser l’écran tactile de l’appareil Salles Teams

Pour configurer des réunions coordonnées sur un appareil, vous pouvez :

1. Sélectionnez **... Paramètres**  >  **plus.**
2. Entrez le mot de passe administrateur, puis sélectionnez **Oui.**
3. Sélectionnez **Réunions coordonnées.**
4. Sous **Options,** définissez **l’option Réunion** coordonnée _sur ._
5. Si **l’audio** est utilisé par défaut dans votre feuille de calcul, définissez l’option Activer le microphone de cet appareil, sinon `true`  laissez-la hors _option._
6. Si **l’audio est activé** dans votre feuille de calcul, sélectionnez Permettre aux utilisateurs `true` d’activer lorsque vous rejoignez une réunion sous Activer le **microphone de cet appareil.**  Cette option ne peut pas être désactivée si le **microphone de cet** appareil est allumé.
7. Si **la fonction vidéo** par défaut est définie sur votre feuille de calcul, définissez l’option Activer `true` **l’appareil** photo de cet appareil, sinon laissez cette _option hors option._
8. Si **la vidéo est activée** dans votre feuille de calcul, sélectionnez Permettre aux utilisateurs `true` **d’activer** lorsque vous participez à une réunion sous Activer la caméra de cet appareil.  Cette option ne peut pas être désactivée si **l’option Activer l’appareil photo** de cet appareil est définie sur _._
9. Si **l’option Tableau blanc** par défaut est définie sur votre feuille de calcul, définissez l’option Activer le tableau blanc sur cet appareil, sinon `true` laissez-la hors _option._ 
10. Sous **Comptes d’appareils de confiance,** tapez chaque nom d’utilisateur utilisateur (UPN) répertorié **dans les comptes de confiance** de votre feuille de calcul. Séparez les différents upns par des virgules.
11. Sélectionnez **Enregistrer et quitter.**

Une fois que vous **avez sélectionné Enregistrer et quitter,** l’appareil redémarre et il est prêt à participer aux réunions coordonnées.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Utiliser le fichier de configuration XML de salles Teams

Les réunions coordonnées peuvent être définies à l’aide du fichier de configuration XML de l’appareil Salles `SkypeSettings.xml` d’équipe. Le `SkypeSettings.xml` fichier n’est pas statique. Lorsque l’appareil Salles Teams démarre, il recherche un `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` fichier `SkypeSettings.xml` nommé. Si le fichier existe, l’appareil lit et applique la configuration spécifiée dans le fichier. Une fois la configuration appliquée, le fichier est supprimé. Pour plus d’informations sur `SkypeSettings.xml` le fichier, voir [Gérer les paramètres de la console avec un fichier de configuration XML.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

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

1. Dans un éditeur de fichiers texte, tel que Visual Studio ou bloc-notes, collez le fichier XML ci-dessus dans un nouveau fichier.

2. Définissez chacun des éléments XML sur la valeur ou la valeur `true` correspondante dans votre feuille de `false` calcul. Par exemple, si la **valeur audio par défaut** est `true` `<Audio default="true">` définie.

3. N’oubliez pas `TrustedAccounts` de modifier votre liste d’upns.

4. Enregistrez le fichier avec le `SkypeSettings.xml` nom.

5. Placez le fichier dans le dossier de l’appareil Salles `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Teams. Vous pouvez faire cela de plusieurs façons :

    - **Copier le fichier sur votre appareil Salles Teams** Vous devez activer le partage de fichiers et créer un partage réseau avant de pouvoir copier des fichiers sur votre appareil. Vous pouvez ensuite vous connecter au partage réseau et copier le fichier sur l’appareil. Pour plus d’informations, consultez les opérations et [maintenance des salles Microsoft Teams.](../rooms/rooms-operations.md)
    - **Utiliser une stratégie de groupe** Créez une stratégie de groupe pour copier le fichier sur l’appareil. Pour plus d’informations, voir [Vue d’ensemble de la stratégie de groupe.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Télécharger le fichier sur l’appareil Salles Teams** Vous pouvez vous connecter à l’appareil en mode d’administration, puis copier le fichier sur l’appareil à partir d’un lecteur USB ou d’un partage réseau. Pour plus d’informations, [voir Passer en mode Administrateur.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Redémarrez l’appareil. Vous pouvez faire cela de deux façons :

    - **Remote PowerShell** Vous pouvez exécuter la commande d’arrêt sur l’appareil à l’aide de Remote PowerShell. Pour plus d’informations, voir [Gestion à distance à l’aide de PowerShell.](../rooms/rooms-operations.md)
    - **Exécuter Restart-Computer** Vous pouvez exécuter l’cmdlet sur votre ordinateur local et spécifier le nom d’ordinateur de `Restart-Computer` l’appareil que vous voulez redémarrer. Pour plus d’informations, [voir Redémarrer l’ordinateur.](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>Étape 5 : configurer Surface Hub

Vous pouvez utiliser Windows Configuration Designer pour créer un package d’approvisionnement que vous pouvez utiliser pour appliquer des paramètres de réunions coordonnés à vos Surface Hubs. Vous collez le fichier XML que vous avez créé ci-dessus dans Windows Configuration Designer pour créer le package de mise en service.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Créer un fichier XML de configuration de réunions coordonnées pour Surface Hub

Windows Configuration Designer et Microsoft Intune sont utilisés pour appliquer la configuration des réunions coordonnées à vos Surface Hubs. La configuration se définit à l’aide de XML. Avant d’aller plus loin, vous devez créer le XML qui sera appliqué.

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

1. Dans un éditeur de fichiers texte, tel que Visual Studio ou bloc-notes, collez le fichier XML ci-dessus dans un nouveau fichier.

2. Définissez chacun des éléments XML sur la valeur ou la valeur `true` correspondante dans votre feuille de `false` calcul. Par exemple, si la **valeur audio par défaut** est `true` `<Audio default="true">` définie.

3. N’oubliez pas `TrustedAccounts` de modifier votre liste d’upns.

4. Windows Configuration Designer requiert que le XML soit sur une seule ligne. Supprimez tous les coupures de ligne entre chaque ligne de sorte que le XML ressemble à ce qui suit :

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Enregistrez le fichier sur votre ordinateur.

Après avoir créé votre fichier de configuration XML, utilisez les étapes de la gestion des [paramètres de Microsoft Teams](surface-hub-manage-config.md) sur Surface Hub pour l’appliquer à vos Surface Hubs.
