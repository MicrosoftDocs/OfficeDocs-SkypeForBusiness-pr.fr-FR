---
title: Gérer les Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Découvrez comment développer et exécuter des opérations de maintenance et d’opérations en cours pour vous assurer que vos systèmes Salles Microsoft Teams sont disponibles pour vos utilisateurs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36145202e12cd9b987b50efd6de3efe636c86ac2
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2023
ms.locfileid: "69806369"
---
# <a name="manage-microsoft-teams-rooms-and-surface-hubs"></a>Gérer les Salles Microsoft Teams et les Surface Hubs

Si vous avez Salles Microsoft Teams appareil ou un Surface Hub dans votre organisation, vous disposez d’options de gestion flexibles.  Vous pouvez gérer les appareils vous-même dans le même emplacement central où vous gérez toutes vos solutions Teams, centre d’administration Microsoft Teams.

Avec le Centre d’administration Microsoft Teams, vous pouvez :

- Effectuer la gestion des appareils, comme le redémarrage des appareils et le téléchargement des journaux d’activité des appareils
- Appliquer des paramètres spécifiques à Teams
- Vérifier l’état d’intégrité des Salles Microsoft Teams et de leurs périphériques, y compris les caméras, les écrans, les microphones, et ainsi de suite
- Passer en revue l’activité de réunion actuelle et passée (par exemple, les détails sur la qualité des appels, l’intégrité et la connectivité du réseau et le nombre de participants)
- Voir les périphériques (tels que les caméras et les projecteurs) connectés à Salles Microsoft Teams (uniquement pour salles Teams sur Windows)

Pour gérer salles Teams appareils, ouvrez le [Centre d’administration Microsoft Teams](https://admin.teams.microsoft.com) et accédez à **Appareils** >  Teams **salles Teams sur Windows** ou **Surface Hubs**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="salles Teams page de résumé dans le Centre d’administration Teams.":::


> [!IMPORTANT]
> Pour gérer des appareils à l’aide du Centre d’administration Teams, vous devez disposer des rôles Administrateur général, Administrateur Teams ou Administrateur d’appareils Teams.

## <a name="make-changes-to-teams-rooms-devices-or-surface-hubs"></a>Apporter des modifications aux appareils salles Teams ou aux Surface Hubs

Si vous avez plusieurs appareils salles Teams ou Surface Hub, vous pouvez effectuer la plupart des actions sur plusieurs appareils en même temps. Par exemple, vous pouvez définir les paramètres d’application Teams sur tous vos salles Teams en même temps.

### <a name="device-settings"></a>Paramètres de l’appareil

Vous pouvez modifier les paramètres d’un ou plusieurs salles Teams ou Surface Hubs dans votre organisation. Pour modifier les paramètres, sélectionnez le ou les appareils que vous souhaitez gérer, puis sélectionnez **Modifier les paramètres**. Un nouveau volet s’ouvre avec tous les paramètres que vous pouvez modifier. Le tableau suivant répertorie les paramètres que vous pouvez modifier à l’aide du Centre d’administration Teams. Certains paramètres ne sont disponibles que lorsque vous sélectionnez une seule salles Teams.

Si vous en sélectionnez plusieurs, les paramètres qui prennent en charge la modification en bloc affichent les deux options suivantes.

- **Conserver la valeur existante** Si vous choisissez cette option, aucune modification n’est apportée au paramètre sur le salles Teams que vous avez sélectionné.
- **Remplacer la valeur existante par** Si vous choisissez cette option, vous pouvez mettre à jour le paramètre sur le salles Teams que vous avez sélectionné avec la valeur que vous fournissez.
    > [!CAUTION]
    > Les valeurs existantes sur les paramètres que vous choisissez de mettre à jour sont remplacées par la valeur que vous fournissez. Si vous souhaitez ajouter à une liste de valeurs existantes, vous devez inclure les valeurs existantes avec la valeur que vous souhaitez ajouter. Par exemple, si un paramètre a une liste de domaines existante de `contoso.com, fabrikam.com`et que vous souhaitez ajouter `northwindtraders.com`, la valeur que vous devez fournir est `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Si vous sélectionnez plusieurs salles Teams, le paramètre sur tous les appareils que vous sélectionnez est remplacé par la valeur que vous fournissez. Si salles Teams ont des valeurs différentes pour un paramètre, ils sont tous mis à jour vers la même valeur.

| Paramètres                                                      | Valeurs acceptées                                        | Prend en charge la modification en bloc | Types d’appareils pris en charge |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|------------------------|
| *Compte*                                                    |                                                        |                    | salles Teams sur Windows |
| **Email**                                                    | adresse Email                                          | Non                 | salles Teams sur Windows |
| **Mode de réunion pris en charge**                                   | Microsoft Teams uniquement<br>Skype Entreprise (par défaut) et Microsoft Teams<br>Skype Entreprise et Microsoft Teams (par défaut)<br>Skype Entreprise uniquement|Oui| salles Teams sur Windows |
| **Authentification moderne**                                    | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **Adresse Exchange**                                         | adresse Email                                          | Non                 | salles Teams sur Windows |
| **Domaine\nom d’utilisateur (facultatif)**                               | Domaine et nom d’utilisateur du compte                           | Non                 | salles Teams sur Windows |
| **Configurer un domaine**                                         | Liste séparée par des virgules                                   | Oui                | salles Teams sur Windows |
| *Réunions*                                                   |                                                        |                    | salles Teams sur Windows, Surface Hubs |
| **Partage d’écran automatique**                                 | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **Partage audio d’ingérer HDMI**                                 | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **Afficher les noms des réunions**                                       | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **Quitter automatiquement si tout le monde a quitté la réunion**                 | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **Participer à des réunions tierces**                 | Cisco Webex<br>Zoom                                              | Oui                | salles Teams sur Windows, Surface Hubs |
| **Rejoindre avec les informations de salle**                 | Sélectionné<br>Non sélectionné                                              | Oui                | salles Teams sur Windows, Surface Hubs |
| **Joindre avec des informations personnalisées**                 | Sélectionné<br>Non sélectionné                                              | Oui                | salles Teams sur Windows |
| **Nom (obligatoire)**                 | Nom de la salle ou de l’espace                                              | Oui                | salles Teams sur Windows |
| **Email (obligatoire)**                 | adresse Email                                              | Oui                | salles Teams sur Windows |
| *Device*                                                     |                                                        |                    | salles Teams sur Windows |
| **Mode double moniteur**                                        | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **Autoriser la duplication de contenu** | Sélectionné<br>Non sélectionné                                 | Oui                | salles Teams sur Windows |
| **Balise Bluetooth**                                      | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows, Surface Hubs |
| **Accepter automatiquement les invitations aux réunions basées sur la proximité** | Sélectionné<br>Non sélectionné                                 | Oui                | salles Teams sur Windows, Surface Hubs |
| **Envoyer des journaux avec des commentaires**                                  | Activé<br>Désactivé                                              | Oui                | salles Teams sur Windows |
| **adresse Email pour les journaux et les commentaires**                      | adresse Email                                          | Oui                | salles Teams sur Windows |
| *Coordonner les réunions*                                                     |                                                        |                    | salles Teams sur Windows |
| **Réunions coordonnées** | Activé<br>Désactivé                                 | Non                | salles Teams sur Windows, Surface Hubs |
| **Activer le microphone de cet appareil** | Activé<br>Désactivé                                 | Non                | salles Teams sur Windows, Surface Hubs |
| **Autoriser les utilisateurs à participer à une réunion** | Sélectionné<br>Non sélectionné                                 | Non                | salles Teams sur Windows, Surface Hubs |
| **Activer la caméra de cet appareil** | Activé<br>Désactivé                                 | Non                | salles Teams sur Windows, Surface Hubs |
| **Autoriser les utilisateurs à participer à une réunion** | Sélectionné<br>Non sélectionné                                 | Non                | salles Teams sur Windows, Surface Hubs |
| **Activer le tableau blanc pour cet appareil** | Activé<br>Désactivé                                 | Non                | salles Teams sur Windows, Surface Hubs |
| **Comptes d’appareils approuvés (séparés par des virgules)** | Liste des appareils                              | Non                | salles Teams sur Windows, Surface Hubs |
| *Périphériques*                                                |                                                        |                    | salles Teams sur Windows |
| **Microphone de conférence**                                  | Liste des microphones disponibles                          | Non                 | salles Teams sur Windows |
| **Intervenant de conférence**                                     | Liste des orateurs disponibles                             | Non                 | salles Teams sur Windows |
| **Volume par défaut**                                           | 0-100                                                  | Non                 | salles Teams sur Windows |
| **Haut-parleur par défaut**                                          | Liste des orateurs disponibles                             | Non                 | salles Teams sur Windows |
| **Volume par défaut**                                           | 0-100                                                  | Non                 | salles Teams sur Windows |
| **Caméra de contenu**                                           | Liste des caméras disponibles                              | Non                 | salles Teams sur Windows |
| **Améliorations apportées à la caméra de contenu**                              | Activé<br>Désactivé                                              | Non                 | salles Teams sur Windows |
| **Faire pivoter la caméra de contenu de 180 degrés**                        | Activé<br>Désactivé                                              | Non                 | salles Teams sur Windows |
| *Thématisation*                                                    |                                                        |                    | salles Teams sur Windows |
|                                                              | Par défaut<br>Aucun thème<br>Personnalisé<br>Liste des thèmes intégrés   | Oui                | salles Teams sur Windows |

Consultez [Gérer la configuration de Microsoft Teams sur Surface Hubs](surface-hub-manage-config.md) pour plus d’options de configuration des Surface Hubs.

### <a name="cortana-settings"></a>Paramètres de Cortana

Vous pouvez activer Cortana pour _l’activation vocale_ ou _Push pour parler à_ l’aide de PowerShell pour tous les appareils de votre organisation, ou pour chaque appareil séparément.

Consultez [Salles Microsoft Teams sur Windows](../cortana-in-teams.md) dans l’article « Aide vocale Cortana dans Teams ».

### <a name="front-row-layout-settings"></a>Paramètres de disposition de ligne avant

La première ligne est l’option de disposition du mode réunion pour salles Teams sur Windows.

| Appareil Teams | Version de l’application | Devant l’affichage de la salle |
|--------------|-------------|-----------------------|
|Salles Microsoft Teams sur Windows | 4.11.12.0 ou version ultérieure (la dernière version est recommandée) | Prend en charge les affichages simples et doubles ; Taille minimale : 46 pouces; Proportions 16:9 avec une résolution de 1920x1080 ou 21:9 avec une résolution de 2560x1080; Tous les affichages doivent être définis à une mise à l’échelle de 100 % dans les paramètres Windows |

Consultez [Salles Microsoft Teams maintenance et opérations](rooms-operations.md#scale-and-resolution) pour ajuster vos paramètres d’affichage afin de répondre aux exigences de la ligne front.

Pour savoir comment définir la ligne front comme disposition par défaut pour une salle ou comment la désactiver, consultez [Gérer à distance les paramètres d’une console Salles Microsoft Teams à l’aide d’un fichier de configuration XML](xml-config-file.md#set-front-row-as-the-default-layout).

Pour plus [d’informations](known-issues.md#Limits) sur la gestion de la ligne front, consultez Problèmes connus.

## <a name="device-restart-options"></a>Options de redémarrage de l’appareil

Les modifications apportées aux paramètres de l’appareil ne prendront effet qu’après le redémarrage de l’appareil. Lorsque vous apportez des modifications qui nécessitent un redémarrage, vous pouvez choisir de redémarrer immédiatement ou de planifier un redémarrage. Voici les options de redémarrage disponibles :

- **Redémarrage immédiat** Si vous choisissez cette option, tous les appareils sur lesquels vous apportez des modifications redémarrent dès que vous sélectionnez cette option.
- **Redémarrage planifié** Si vous choisissez cette option, vous pouvez redémarrer les appareils sur lesquels vous apportez des modifications à un moment qui perturbe moins votre organisation.
  - **Sélectionner la date et l’heure** : choisissez la date et l’heure spécifiques pour redémarrer l’appareil. La date et l’heure que vous choisissez sont locales pour l’appareil en cours de redémarrage. 
  - **Laissez la mise à jour pour un redémarrage nocturne** Les appareils sont redémarrés la nuit pour effectuer la maintenance. Les modifications que vous apportez aux appareils seront appliquées pendant ce redémarrage.

> [!CAUTION]
> salles Teams et les Surface Hubs en cours d’utilisation au moment d’un redémarrage deviennent indisponibles pendant la durée du processus de redémarrage. Ils seront déconnectés des réunions en cours et ne seront pas disponibles pour participer à de nouvelles réunions pendant le redémarrage de l’appareil.

## <a name="remove-device"></a>Supprimer l’appareil

Lorsque vous supprimez un appareil, l’appareil est supprimé de votre organisation et n’apparaît plus dans votre liste de salles Teams sur Windows ou Surface Hubs dans le Centre d’administration Teams.

Si vous supprimez un appareil et qu’il est toujours configuré avec un nom d’utilisateur et un mot de passe valides, il est automatiquement ajouté à votre liste d’salles Teams ou de Surface Hubs s’il se connecte à nouveau à Microsoft 365.

Pour supprimer un ou plusieurs appareils, procédez comme suit :

1. Accédez à **Appareils** >  Teams **salles Teams sur Windows** ou **Surface Hubs**, puis sélectionnez les appareils que vous souhaitez supprimer.
2. Sélectionnez **Supprimer**.

## <a name="download-device-logs"></a>Télécharger les journaux d’activité de l’appareil

Vous pouvez télécharger une copie des fichiers journaux de diagnostic d’un appareil si vous y êtes invité par le support Microsoft. Les fichiers journaux sont compressés dans un fichier zip qui peut être téléchargé à partir du Centre d’administration Teams.

Pour télécharger les journaux d’activité d’un appareil salles Teams sur votre ordinateur, procédez comme suit :

1. Accédez à **Appareils** >  Teams **salles Teams sur Windows** ou **Surface Hubs** et sélectionnez le nom de l’appareil à partir duquel vous souhaitez télécharger les journaux.
1. Sélectionnez **Télécharger les journaux d’activité de l’appareil**. La disponibilité des journaux de l’appareil peut prendre plusieurs minutes.
1. Sélectionnez l’onglet **Historique** , puis sélectionnez le lien Fichier journal sous **Fichier de diagnostics**. Un fichier zip contenant les fichiers journaux de diagnostic de votre appareil est téléchargé dans le dossier Téléchargements par défaut de votre navigateur.

## <a name="view-device-information"></a>Afficher les informations de l’appareil

À partir du Centre d’administration Teams, vous pouvez afficher l’état global de tous les appareils de votre organisation et afficher les détails de chaque appareil individuellement.

### <a name="teams-rooms-system-dashboard"></a>tableau de bord système salles Teams

Le tableau de bord salles Teams système vous montre l’état et l’intégrité de tous vos appareils en un clin d’œil.

### <a name="device-details-view"></a>Vue détails de l’appareil

Pour afficher des informations détaillées sur un appareil, sélectionnez son nom dans la liste des appareils. En mode Détails, vous pouvez voir les informations suivantes sur votre appareil :

- **État d’intégrité** Affiche l’intégrité globale de l’appareil salles Teams ou Surface Hub. L’état d’intégrité peut être **Sain**, **Non urgent**, **Critique** ou **Hors connexion**.
- **Hors connexion depuis** Affiche la dernière fois que Microsoft 365 a pu communiquer avec l’appareil.
- **État d’utilisation** Affiche l’état actuel de l’appareil : **Inactif**, **Occupé** ou **Non disponible**. Uniquement pour salles Teams sur Windows.
- **Périphériques** Affiche les périphériques connectés à votre appareil salles Teams et leur état d’intégrité. L’état d’intégrité peut être **Connecté** ou **Déconnecté**. Uniquement pour salles Teams sur Windows.
- **Santé** Affiche des informations détaillées sur les périphériques connectés à votre appareil salles Teams, la connectivité réseau, l’état de connexion aux services requis et les informations de version du logiciel.
- **Détails** Affiche les informations du fabricant, l’adresse IP réseau et salles Teams’adresse MAC/série de l’appareil.
- **Activité** Affiche les détails de la réunion passée, notamment la date et l’heure de la réunion, le nombre de participants, la durée et la qualité audio. Pour plus d’informations sur les détails de la réunion, consultez la section [Détails de l’activité](#meeting-activity-details) de réunion plus loin dans cet article.
- **Histoire** Affiche un historique de l’activité de gestion sur l’appareil salles Teams ou Surface Hub, y compris les mises à jour de configuration, les redémarrages d’appareils et les liens de téléchargement du journal de l’appareil.

#### <a name="meeting-activity-details"></a>Détails de l’activité de réunion

L’onglet **Activité** dans détails de l’appareil affiche des informations générales et détaillées sur toutes les réunions auxquelles l’appareil a participé au fil du temps. Dans l’onglet **Activité** , vous pouvez voir quand une réunion a eu lieu, le nombre de participants à la réunion et la qualité de l’audio pendant la réunion.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="salles Teams liste récapitulative de l’activité des appareils.":::

Pour afficher les informations détaillées sur une réunion spécifique, sélectionnez la date et l’heure de la réunion sur laquelle vous souhaitez obtenir plus d’informations. Si une réunion n’a que deux participants, vous verrez la page des détails du participant, sinon vous verrez une page de résumé des participants.

##### <a name="participant-summary"></a>Résumé du participant

La page de résumé des participants affiche tous les participants qui ont assisté à la réunion. Vous pouvez voir quand chaque participant a rejoint la réunion, son nom, sa qualité audio et les fonctionnalités utilisées pendant sa session. Pour afficher les détails de la session d’un participant, sélectionnez l’heure de début de la session pour ce participant.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="salles Teams détails de la conférence de l’appareil.":::

##### <a name="participant-details"></a>Détails du participant

La page détails du participant affiche des informations de diagnostic de bout en bout pour la session de ce participant. Comme indiqué dans le graphique suivant, les informations **relatives à l’appareil**, **au système** et à la **connectivité** sont fournies pour le participant et pour l’appareil salles Teams. **Des** informations de diagnostic réseau sont également fournies entre le participant et l’appareil salles Teams. Sélectionnez l’icône correspondant au contexte sur lequel vous souhaitez obtenir plus d’informations. Pour obtenir des informations de diagnostic supplémentaires, sélectionnez l’onglet **Avancé** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="salles Teams détails de l’appel de l’appareil.":::
