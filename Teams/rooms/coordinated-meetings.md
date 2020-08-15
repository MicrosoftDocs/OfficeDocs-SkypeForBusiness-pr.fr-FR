---
title: Configurer des réunions coordonnées avec Microsoft teams salles et surface Hub
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
description: Configurez les appareils de salle d’équipe et surface Hub pour participer à des réunions lorsqu’un appareil ou l’autre rejoint une réunion.
ms.openlocfilehash: c1200b4e949cb866440907f8577f61f4528630e2
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761435"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurer des réunions coordonnées avec Microsoft teams salles et surface Hub

Si vous avez un ou plusieurs appareils Microsoft teams ou surface hubs dans une salle de réunion, vous pouvez configurer des réunions coordonnées. Les réunions coordonnées vous permettent de configurer les appareils de salle de votre équipe et les concentrateurs de surface de telle sorte que lorsque vous participez à une réunion sur un appareil, les autres appareils dans la salle sont également joints à la même réunion. Vous pouvez configurer vos webcams, vos haut-parleurs et vos micros de manière à ce que les personnes qui fournissent des participants la meilleure utilisation soient activées alors que d’autres sont désactivées. Cela permet d’éviter les participants au bruit d’écho et de commentaires qui peuvent être rencontrés lors de l’ajout de plusieurs appareils à une réunion.

Pour configurer des réunions coordonnées, vous devez vous assurer que les appareils de votre équipe et les hubs de surface sont déjà configurés correctement pour participer aux réunions. Plus important encore, chaque appareil doit disposer de sa propre boîte aux lettres Exchange Room. Pour plus d’informations sur la configuration, voir les articles suivants :

- [Déployer les Salles Microsoft Teams](../rooms/rooms-deploy.md)
- [Créer un compte d’appareil 2 surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Une fois que vous avez confirmé que les appareils et les concentrateurs de surface de votre équipe peuvent automatiquement accepter des réunions et les regrouper avec succès, vous pouvez configurer des réunions coordonnées.

Les étapes suivantes doivent être effectuées pour chaque salle de réunion séparément. Les appareils dans une salle de réunion ne doivent pas être configurés pour les réunions coordonnées avec des appareils dans d’autres salles de réunion.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Étape 1 : planifier votre interface de réunion coordonnée

Avant d’apporter des modifications à la configuration, vous devez décider des appareils qui feront quoi dans chaque salle de réunion. Pour une salle de réunion donnée, vous devez choisir le périphérique qui dispose du micro actif, de la caméra et du tableau blanc. La configuration de vos appareils dépend de votre environnement spécifique, mais voici quelques recommandations générales pour commencer :

- **Micro** Appareil de salle teams
- **Appareil photo** Appareil d’équipe (option activée par défaut) et surface Hub (désactivée par défaut)
- **Tableau blanc collaboratif** Surface Hub

> [!IMPORTANT]
> Assurez-vous d’activer le micro uniquement sur un seul appareil. Si vous l’activez sur plusieurs appareils, vous obtiendrez un écho et un retour audio.

## <a name="step-2-get-your-devices-upns"></a>Étape 2 : obtenir les UPN de vos appareils

Lorsque vous configurez une connaissance coordonnée d’une réunion dans une salle de réunion, vous devez faire en sorte que les périphériques de la réunion équipes et les hubs de surface soient dans la même salle qui identifient les appareils. Pour cela, il convient d’ajouter le nom d’utilisateur principal (UPN, User Principal Name) des appareils dont il doit être coordonné à sa configuration. Si vous ne connaissez pas les UPN de chaque appareil que vous voulez configurer pour les réunions coordonnées, vous pouvez les retrouver à l’aide du centre d’administration 365 Microsoft. 

Vous devez être doté d’un rôle d’administrateur pour accéder au centre d’administration Microsoft 365. Pour plus d’informations, voir [à propos des rôles d’administrateur](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

Pour obtenir les UPN des appareils de salle de votre équipe et de surface hubs, procédez comme suit :

1. Connectez-vous au centre d’administration 365 Microsoft en visitant https://admin.microsoft.com
2. Accédez à **utilisateurs**  >  **actifs**
3. Recherchez le nom de votre périphérique d’équipe ou surface Hub dans la colonne **nom complet** (vous pouvez utiliser la zone de **recherche** si vous avez de nombreux utilisateurs).
4. Recherchez le nom d’utilisateur principal dans la colonne **nom d’utilisateur** (il ressemble à alias@contoso.com ou alias@contoso.onmicrosoft.com).
5. Répétez cette procédure pour chaque appareil participant aux réunions coordonnées.

## <a name="step-3-create-a-deployment-worksheet"></a>Étape 3 : créer une feuille de calcul de déploiement

Une fois que vous avez planifié votre interface de réunion coordonnée et recueilli une liste des UPN de vos appareils, il est recommandé de créer une feuille de calcul de déploiement. Une feuille de calcul de déploiement vous aidera à visualiser la configuration que vous voulez définir sur l’ensemble de vos appareils, en vous permettant de valider vos choix et de vérifier les erreurs.

Dans une application de feuille de calcul, ajoutez des lignes pour les éléments suivants dans la première colonne :

| Paramètres                | Description      |
|------------------------|-----------------|
| **Valeur audio par défaut**      | Détermine sur quel appareil le micro est actif lors du démarrage d’une réunion. Ce champ doit être défini sur un seul appareil (en général, sur un appareil d’équipe) pour `true` que le reste des appareils doit être paramétré pour `false` éviter l’écho et le retour audio.          |
| **Audio activé**      | Détermine si les participants à une réunion peuvent activer ou désactiver le micro. Les appareils sur lesquels la **valeur par défaut** de l’audio est définie sur `false` doivent avoir ce paramètre configuré pour `false` que les participants puissent accidentellement allumer un micro et provoquer un écho ou un retour audio.<p>Si la **valeur par défaut** de l’audio est définie sur `true` , ce paramètre est ignoré et les participants peuvent activer ou désactiver le micro.          |
| **Vidéo par défaut**      | Détermine sur quel appareil l’appareil photo sera actif lors du démarrage de la réunion. Pour une utilisation optimale, nous vous conseillons de définir uniquement le périphérique de salle teams `true` lorsque tous les autres appareils sont définis sur `false` .          |
| **Vidéo activée**      | Détermine si les participants à une réunion peuvent activer ou désactiver la caméra. Vous pouvez définir ce `true` type sur sur n’importe quel autre appareil dans lequel vous voulez partager différentes perspectives vidéo (par exemple, si un participant utilise le tableau blanc surface Hub). Si vous ne voulez pas que les participants activent ou désactivent la caméra sur un appareil, définissez cette valeur sur `false` .<p> Si la **valeur par défaut** de la vidéo est définie sur `true` , ce paramètre est ignoré et les participants peuvent activer ou désactiver la caméra.         |
| **Tableau blanc par défaut** | Détermine si le dispositif de salle teams affiche un tableau blanc partagé par l’un des participants à la réunion. Nous vous recommandons de définir cette valeur sur `false` si vous disposez d’un surface Hub et `true` si vous n’en avez pas. Ce paramètre n’a aucun effet sur surface Hub. Surface hubs affiche toujours un tableau blanc partagé par des participants à la réunion.         |
| **Comptes approuvés**   | Il s’agit d’une liste séparée par des virgules d’UPN pour chaque appareil de salle de réunion ou surface Hub sur lequel l’appareil doit accepter les demandes de participation à une réunion, ou pour lesquelles des demandes de participation à une réunion doivent être envoyées. |

Dans les colonnes suivantes, ajoutez chacun de vos appareils de salle d’équipe et de surface hubs. Dans chaque colonne, remplissez les valeurs qui correspondent à l’interface que vous souhaitez utiliser pour la salle de réunion. Voici un exemple avec un appareil de salle de l’équipe et un surface Hub :

- Appareil teams
  - Les éléments audio et vidéo sont activés lors **du** démarrage d’une réunion. Les participants **peuvent** activer ou désactiver l’audio et la vidéo.
  - L’affichage d’un tableau blanc partagé est désactivé.
- Surface Hub
  - Le son est **désactivé lors du** démarrage d’une réunion. Les participants **ne peuvent pas** activer ou désactiver le son.
  - La vidéo est **désactivée lors du** démarrage d’une réunion. Les participants **peuvent** activer ou désactiver la vidéo.

| Paramètres                | Salle de équipe      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Valeur audio par défaut**      | `true`          | `false`          |
| **Audio activé**      | `true`          | `false`          |
| **Vidéo par défaut**      | `true`          | `false`          |
| **Vidéo activée**      | `true`          | `true`           |
| **Tableau blanc par défaut** | `false`         | Non applicable   |
| **Comptes approuvés**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Étape 4 : configurer l’appareil de salles d’équipe

Vous pouvez configurer des réunions coordonnées sur un appareil de salle d’équipe à l’aide de l’écran d’accueil de l’appareil ou, si vous avez besoin de configurer un grand nombre d’appareils et que vous souhaitez le faire à partir d’un emplacement central, vous pouvez utiliser un fichier de configuration XML.

Utilisez la feuille de calcul que vous avez créée à l’étape précédente pour vous aider à configurer vos appareils.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Utiliser l’écran d’accueil de l’appareil de salle d’équipe

Pour configurer des réunions coordonnées sur un appareil, procédez comme suit :

1. Sélectionner **... **  >  **Paramètres** supplémentaires
2. Entrez le mot de passe d’administrateur et sélectionnez **Oui** .
3. Sélectionner des **réunions coordonnées**
4. Sous **options**, définissez **réunion coordonnée** sur activé.
5. Si le son est défini **par défaut** dans votre feuille de calcul `true` , **activez la** case à cotacher le micro de votre appareil, sinon quittez-le.
6. Si le **son est activé** dans votre feuille de calcul `true` , sélectionnez permettre aux utilisateurs de s’activer lors de la **participation à une réunion** sous **activer le micro de cet appareil**. Cette option ne peut pas être désactivée si le **micro de l’appareil** est activé.
7. Si la vidéo est définie **par défaut** dans votre feuille de calcul `true` , activez la case à cotacher **l’appareil photo** de votre appareil, sinon quittez-le.
8. Si la **vidéo est activée** dans votre feuille de calcul `true` , sélectionnez permettre aux utilisateurs de s’activer lors de la participation à **une réunion** sous **activer l’appareil photo de l’appareil**. Cette option ne peut pas être désactivée si **l’appareil photo de l’appareil** est activé.
9. S’il s’agit de **tableau blanc par défaut** dans votre feuille de calcul, activez la case à `true` cotacher le **tableau blanc**
10. Sous **comptes d’appareils approuvés**, tapez chaque nom d’utilisateur principal répertorié dans **comptes approuvés** dans votre feuille de calcul. Séparez plusieurs UPN par des virgules.
11. Sélectionnez **enregistrer et quitter**

Après avoir sélectionné **enregistrer et quitter**, l’appareil redémarre et il est prêt à participer à des réunions coordonnées.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Utiliser le fichier de configuration XML des salles teams

Les réunions coordonnées peuvent être configurées à l’aide du fichier de configuration XML de l’appareil salle de réunion `SkypeSettings.xml` . Le `SkypeSettings.xml` fichier n’est pas un fichier statique. Lors du démarrage de l’appareil de salle d’équipe, le fichier s’Archive `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` `SkypeSettings.xml` . Si le fichier existe, l’appareil lit et applique la configuration spécifiée dans le fichier. Lorsque la configuration est terminée, le fichier est supprimé. Pour plus d’informations sur le `SkypeSettings.xml` fichier, voir [gérer les paramètres de console à l’aide d’un fichier de configuration XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Voici la syntaxe des paramètres de réunion coordonnés du fichier de configuration :

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Pour configurer des réunions coordonnées sur un appareil, procédez comme suit :

1. Dans un éditeur de fichier texte, tel que code Visual Studio ou bloc-notes, collez le code XML ci-dessus dans un nouveau fichier
2. Définissez chacun des éléments XML sur la `true` valeur ou correspondante `false` de votre feuille de calcul. Par exemple, si l' **option audio par défaut** est `true` , définissez `<Audio default="true">` .
3. N’hésitez pas à passer `TrustedAccounts` à votre liste d’UPN.
4. Enregistrez le fichier avec le nom `SkypeSettings.xml`
5. Placez le fichier dans le dossier de l’appareil de salle de l’équipe `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Vous pouvez procéder de plusieurs manières :
    - **Copiez le fichier sur votre appareil de salle teams** Vous devez activer le partage de fichiers et créer un partage réseau avant de pouvoir copier des fichiers sur votre appareil. Après cela, vous pouvez vous connecter au partage réseau et copier le fichier sur l’appareil. Pour plus d’informations, reportez-vous à la section [maintenance et opérations de Microsoft teams](../rooms/rooms-operations.md).
    - **Utiliser une stratégie de groupe** Créez une stratégie de groupe pour copier le fichier sur l’appareil. Pour plus d’informations, voir [vue d’ensemble](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))de la stratégie de groupe.
    - **Télécharger le fichier sur l’appareil de salle d’équipe** Vous pouvez vous connecter à l’appareil à l’aide du mode admin, puis copier le fichier sur l’appareil à partir d’un partage réseau ou d’un lecteur USB. Pour plus d’informations, consultez [basculer vers le mode administrateur](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
6. Redémarrez l’appareil. Vous pouvez procéder de deux façons :
    - **PowerShell distant** Vous pouvez exécuter la commande shutdown sur l’appareil à l’aide de Remote PowerShell. Pour plus d’informations, reportez-vous à la rubrique [gestion à distance via PowerShell](../rooms/rooms-operations.md).
    - **Exécuter le redémarrage-ordinateur** Vous pouvez exécuter l' `Restart-Computer` applet de cmdlet sur votre ordinateur local et spécifier le nom d’ordinateur de l’appareil que vous voulez redémarrer. Pour plus d’informations, reportez-vous à la rubrique [redémarrer-ordinateur](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Étape 5 : configurer surface Hub

Vous pouvez utiliser le concepteur de configuration Windows pour créer un package de mise à disponibilité que vous pouvez utiliser pour appliquer les paramètres de réunion coordonnés à vos hubs de surface. Pour créer le package de mise en service, vous devez coller le fichier XML que vous avez créé précédemment dans le concepteur de configuration Windows.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Créer un fichier de configuration XML pour les réunions coordonnées pour surface Hub

Le concepteur de configuration Windows et Microsoft Intune permettent d’appliquer la configuration de réunions coordonnées à vos hubs de surface. La configuration est définie à l’aide de XML. Avant de continuer, vous devez créer le code XML qui sera appliqué.

Voici la syntaxe du fichier de configuration XML pour les réunions coordonnées.

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

Pour préparer le XML pour le concepteur de configuration Windows ou Microsoft Intune, procédez comme suit :

1. Dans un éditeur de fichier texte, tel que code Visual Studio ou bloc-notes, collez le code XML ci-dessus dans un nouveau fichier
2. Définissez chacun des éléments XML sur la `true` valeur ou correspondante `false` de votre feuille de calcul. Par exemple, si l' **option audio par défaut** est `true` , définissez `<Audio default="true">` .
3. N’hésitez pas à passer `TrustedAccounts` à votre liste d’UPN.
4. Le concepteur de configuration Windows exige que le code XML soit sur une seule ligne. Supprimez tous les sauts de ligne entre chaque ligne afin que le code XML ressemble à ce qui suit :

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Enregistrez le fichier sur votre ordinateur.

Une fois que vous avez créé votre fichier de configuration XML, suivez les étapes décrites dans [gérer les paramètres de Microsoft teams sur surface Hub](surface-hub-manage-config.md) pour l’appliquer à vos hubs de surface.