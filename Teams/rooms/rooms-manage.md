---
title: Gérer les Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: Découvrez comment développer et exécuter la maintenance et les opérations continues pour vous assurer que vos systèmes Salles Microsoft Teams sont disponibles pour vos utilisateurs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82725093e67b0f7619ea97837b53fd841b965146
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504101"
---
# <a name="manage-microsoft-teams-rooms"></a>Gérer les Salles Microsoft Teams

Si vous avez des Salles Microsoft Teams dans votre organisation, vous avez des options de gestion flexibles.  Vous pouvez gérer les appareils vous-même dans le même emplacement central que celui où vous gérez toutes Teams solutions, et Microsoft Teams centre d’administration. Vous pouvez également transférer la responsabilité de la gestion à des experts dédiés à l’aide [Salles Microsoft Teams services gérés](https://portal.rooms.microsoft.com).  Vous pouvez également déléguer l’accès de gestion à un partenaire de votre choix pour l’une ou l’autre des options.

Avec Microsoft Teams centre d’administration, vous pouvez :

- Effectuer une gestion des appareils telle que le redémarrage des appareils et le téléchargement des journaux des appareils
- Appliquer Teams paramètres spécifiques
- Vérifier l’état d’Salles Microsoft Teams des périphériques, y compris les caméras, les écrans, les microphones, et ainsi de suite
- Passer en revue l’activité en cours et passée des réunions (par exemple, détails sur la qualité des appels, l’état du réseau et la connectivité, et nombre de participants)
- Voir les périphériques (tels que les caméras et les projecteurs) connectés à Salles Microsoft Teams

Pour gérer salles Teams appareils mobiles [, ouvrez](https://admin.teams.microsoft.com)  >  Microsoft Teams centre d’administration et Teams appareils mobiles **salles Teams sur Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="salles Teams de synthèse dans Teams centre d’administration.":::


> [!IMPORTANT]
> Pour gérer les appareils à l’aide Teams d’administration, vous devez avoir les rôles Administrateur général, Administrateur Teams de périphériques ou Administrateur d Teams périphériques.

## <a name="make-changes-to-teams-rooms-devices"></a>Apporter des modifications à salles Teams appareils

Si vous avez plusieurs salles Teams, vous pouvez faire la plupart des actions sur plusieurs appareils en même temps. Par exemple, vous pouvez définir Teams de l’application sur tous vos salles Teams en même temps.

### <a name="device-settings"></a>Paramètres de l’appareil

Vous pouvez modifier les paramètres sur un ou plusieurs salles Teams de votre organisation. Pour modifier les paramètres, sélectionnez le ou les appareils que vous voulez gérer, puis **sélectionnez Modifier Paramètres**. Un nouveau volet s’ouvre avec tous les paramètres que vous pouvez modifier. Le tableau suivant répertorie les paramètres que vous pouvez modifier à l’aide du Teams d’administration. Certains paramètres ne sont disponibles que lorsque vous sélectionnez une seule salles Teams.

Si vous en sélectionnez plusieurs, les paramètres qui supportent la modification en bloc s’afficheront avec les deux options suivantes.

- **Conserver la valeur existante** Si vous choisissez cette option, aucune modification n’est apportée au paramètre sur la salles Teams que vous avez sélectionnée.
- **Remplacer la valeur existante par** Si vous choisissez cette option, vous pouvez mettre à jour le paramètre du salles Teams sélectionné avec la valeur que vous fournissez.
    > [!CAUTION]
    > Les valeurs existantes des paramètres que vous choisissez de mettre à jour seront remplacées par la valeur que vous fournissez. Si vous voulez ajouter des valeurs à une liste de valeurs existantes, vous devez inclure les valeurs existantes avec la valeur que vous voulez ajouter. Par exemple, si un `contoso.com, fabrikam.com``northwindtraders.com`paramètre possède une liste de domaines existante et que vous voulez ajouter, la valeur que vous devez fournir serait `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Si vous sélectionnez plusieurs salles Teams, le paramètre de tous les appareils sélectionnés sera modifié en fonction de la valeur que vous fournissez. Si salles Teams ont des valeurs différentes pour un paramètre, elles sont toutes mises à jour avec la même valeur.

| Paramètres                                                      | Valeurs acceptées                                        | Prend en charge la modification en bloc |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Compte*                                                    |                                                        |                    |
| **Email**                                                    | Adresse e-mail                                          | Non                 |
| **Mode réunion pris en charge**                                   | Microsoft Teams uniquement<br>Skype Entreprise (par défaut) et Microsoft Teams<br>Skype Entreprise et Microsoft Teams défaut<br>Skype Entreprise Uniquement|Oui|
| **Authentification moderne**                                    | Activé<br>Désactivé                                              | Oui                |
| **Exchange de l’adresse de l’équipe**                                         | Adresse e-mail                                          | Non                 |
| **Domaine \nom d’utilisateur (facultatif)**                               | Nom d’utilisateur et domaine du compte                           | Non                 |
| **Configurer le domaine**                                         | Liste séparée par des virgules                                   | Oui                |
| *Réunions*                                                   |                                                        |                    |
| **Partage d’écran automatique**                                 | Activé<br>Désactivé                                              | Oui                |
| **Partage audio HDMI ingest**                                 | Activé<br>Désactivé                                              | Oui                |
| **Afficher les noms des réunions**                                       | Activé<br>Désactivé                                              | Oui                |
| **Quitter automatiquement une réunion si tous les autres personnes ont quitté la réunion**                 | Activé<br>Désactivé                                              | Oui                |
| **Participer à des réunions tierces**                 | Cisco Webex<br>Zoom                                              | Oui                |
| **Participer avec les informations de la salle**                 | Sélectionné<br>Non sélectionné                                              | Oui                |
| **Participer avec des informations personnalisées**                 | Sélectionné<br>Non sélectionné                                              | Oui                |
| **Nom (obligatoire)**                 | Nom de la salle ou de l’espace                                              | Oui                |
| **Courrier électronique (obligatoire)**                 | Adresse e-mail                                              | Oui                |
| *Device*                                                     |                                                        |                    |
| **Mode à deux moniteurs**                                        | Activé<br>Désactivé                                              | Oui                |
| **Autoriser la duplication de contenu** | Sélectionné<br>Non sélectionné                                 | Oui                |
| **Bluetooth balises de balise**                                      | Activé<br>Désactivé                                              | Oui                |
| **Accepter automatiquement les invitations aux réunions de proximité** | Sélectionné<br>Non sélectionné                                 | Oui                |
| **Envoyer des journaux avec commentaires**                                  | Activé<br>Désactivé                                              | Oui                |
| **Adresse e-mail pour les journaux et les commentaires**                      | Adresse e-mail                                          | Oui                |
| *Coordonner des réunions*                                                     |                                                        |                    |
| **Réunions coordonnées** | Activé<br>Désactivé                                 | Non                |
| **Activer le microphone de cet appareil** | Activé<br>Désactivé                                 | Non                |
| **Permettre aux utilisateurs d’activer lorsque vous rejoignez une réunion** | Sélectionné<br>Non sélectionné                                 | Non                |
| **Activer l’appareil photo de cet appareil** | Activé<br>Désactivé                                 | Non                |
| **Permettre aux utilisateurs d’activer lorsque vous rejoignez une réunion** | Sélectionné<br>Non sélectionné                                 | Non                |
| **Activer le tableau blanc pour cet appareil** | Activé<br>Désactivé                                 | Non                |
| **Comptes d’appareils de confiance (séparés par des virgules)** | Liste des appareils                              | Non                |
| *Périphériques*                                                |                                                        |                    |
| **Microphone de conférence**                                  | Liste des microphones disponibles                          | Non                 |
| **Haut-parleur conférence**                                     | Liste des haut-parleurs disponibles                             | Non                 |
| **Volume par défaut**                                           | 0-100                                                  | Non                 |
| **Haut-parleur par défaut**                                          | Liste des haut-parleurs disponibles                             | Non                 |
| **Volume par défaut**                                           | 0-100                                                  | Non                 |
| **Caméra de contenu**                                           | Liste des caméras disponibles                              | Non                 |
| **Améliorations apportées aux caméras de contenu**                              | Activé<br>Désactivé                                              | Non                 |
| **Faire pivoter la caméra de contenu de 180 degrés**                        | Activé<br>Désactivé                                              | Non                 |
| *Avec le theming*                                                    |                                                        |                    |
|                                                              | Par défaut<br>Aucun thème<br>Personnalisé<br>Liste des thèmes intégrés   | Oui                |

### <a name="cortana-settings"></a>Cortana paramètres

Vous pouvez activer Cortana _activation vocale_ ou _Push_ pour parler à l’aide de PowerShell pour tous les appareils de votre organisation, ou pour chaque appareil séparément.

[Consultez Salles Microsoft Teams le Windows](../cortana-in-teams.md) dans l’article « Cortana’assistance vocale vocale Teams ».

### <a name="front-row-layout-settings"></a>Paramètres de disposition de la ligne frontale

La ligne de première ligne est l’option de disposition du salles Teams réunion sur Windows.

| Teams appareil | Version de l’application | Affichage à l’avant de la salle |
|--------------|-------------|-----------------------|
|Salles Microsoft Teams sur Windows | 4.11.12.0 ou version supérieure (la dernière version est recommandée) | Prend en charge les affichages simples et doubles ; Taille minimale : 46 pouces ; Proportions 16:9 avec 1920*1080 résolution ou 21:9 avec 2560 x 1080 résolution ; Tous les affichages doivent être mis à l’échelle de 100 % dans Windows paramètres |

[Consultez Salles Microsoft Teams maintenance et les opérations](rooms-operations.md#change-scale-and-resolution) pour ajuster vos paramètres d’affichage afin de répondre aux besoins de la première ligne.

Pour découvrir comment définir la disposition Première ligne comme disposition par défaut d’une salle ou la désactiver, voir Gérer les paramètres d’une console Salles Microsoft Teams à distance avec un fichier [de configuration XML](xml-config-file.md#set-front-row-as-the-default-layout).

Pour plus [d’informations sur](known-issues.md#Limits) la gestion des premières lignes, voir Problèmes connus.

## <a name="device-restart-options"></a>Options de redémarrage de l’appareil

Les modifications apportées aux paramètres de l’appareil ne prennent effet qu’après salles Teams redémarrage. Lorsque vous a apporter des modifications qui ont besoin d’un redémarrage, vous pouvez choisir de redémarrer immédiatement ou de planifier un redémarrage. Voici les options de redémarrage disponibles :

- **Redémarrage immédiat** Si vous choisissez cette option, tous les appareils que vous modifiez redémarreront dès que vous aurez sélectionné cette option.
- **Redémarrage prévu** Si vous choisissez cette option, vous pouvez redémarrer les appareils sur qui vous a apporter des modifications à un moment moins perturbateur pour votre organisation.
  - **Sélectionnez la date et l’heure** : choisissez la date et l’heure spécifiques pour redémarrer l’appareil. La date et l’heure choisies sont locales pour l’appareil en cours de redémarrage. 
  - **Laisser la mise à jour pour le redémarrage nocturne** Les appareils sont redémarrés chaque nuit pour effectuer une maintenance. Les modifications que vous a apportées aux appareils seront appliquées pendant ce redémarrage.

> [!CAUTION]
> salles Teams en cours d’utilisation au moment du redémarrage deviennent indisponibles pendant toute la durée du processus de redémarrage. Ils seront déconnectés des réunions en cours et ne pourront pas participer à de nouvelles réunions.

## <a name="remove-device"></a>Supprimer l’appareil

Lorsque vous supprimez un appareil, celui-ci est supprimé de votre organisation et n’apparaît plus dans votre liste de salles Teams sur Windows dans le Teams d’administration.

Si vous supprimez un appareil alors qu’il est toujours configuré avec un nom d’utilisateur et un mot de passe valides, il est automatiquement rajouté à votre liste de salles Teams s’il se connecte à Microsoft 365 nouveau.

Pour supprimer un ou plusieurs appareils, vous pouvez :

1. Sélectionnez **Teams périphériques** >  **salles Teams sur Windows** et sélectionnez les appareils que vous voulez supprimer.
2. Sélectionnez **Supprimer**.

## <a name="download-device-logs"></a>Télécharger les journaux de l’appareil

Vous pouvez télécharger une copie des fichiers journaux de diagnostic d’un appareil si le support Microsoft vous le demande. Les fichiers journaux sont compressés dans un fichier zip qui peut être téléchargé à partir du Teams d’administration.

Pour télécharger les journaux d salles Teams appareil sur votre ordinateur, vous pouvez :

1. Sélectionnez **Teams périphériques** >  salles Teams **sur Windows** et sélectionnez le nom de l’appareil à partir de qui vous voulez télécharger les journaux.
1. **Sélectionnez Télécharger les journaux de l’appareil**. L’accès aux journaux de l’appareil peut prendre plusieurs minutes.
1. Sélectionnez **l’onglet** Historique, puis sélectionnez le lien du fichier journal sous **Fichier diagnostics**. Un fichier zip contenant les fichiers journaux de diagnostic de votre appareil est téléchargé dans le dossier Téléchargements par défaut de votre navigateur.

## <a name="view-device-information"></a>Afficher les informations sur l’appareil

À partir Teams centre d’administration, vous pouvez afficher l’état global de tous les appareils de votre organisation et afficher les détails de chaque appareil individuellement.

### <a name="teams-rooms-system-dashboard"></a>salles Teams tableau de bord système

Le salles Teams tableau de bord système vous présente l’état et l’état de tous vos appareils en un coup d’œil.

### <a name="device-details-view"></a>Affichage des détails de l’appareil

Pour afficher des informations détaillées sur un appareil, sélectionnez son nom dans la liste des périphériques. Dans l’affichage détaillé, vous pouvez voir les informations suivantes sur votre appareil :

- **État d’état** Présente l’état global de l’appareil Teams salle. L’état de santé peut **être sain** **ou défectueux**.
- **Hors connexion depuis** Indique la dernière fois que Microsoft 365 pu communiquer avec l’appareil.
- **État de l’appareil** Indique l’état actuel de l’appareil : **Idle**, Teams **réunion**, **Skype réunion** ou **Ingest**.
- **Périphériques** Affiche les périphériques connectés à votre Teams de salle et leur état d’état. L’état d’état peut **être Connecté** **ou Déconnecté**.
- **État d’santé** Affiche des informations détaillées sur les périphériques connectés à votre appareil Teams Room, la connectivité réseau, l’état de connexion aux services requis et les informations de version logicielle.
- **Détails** Affiche les informations du fabricant, l’adresse IP réseau et l Teams d’un appareil de salle en série/MAC.
- **Activité** Affiche les détails de la réunion passée, notamment la date et l’heure de la réunion, le nombre de participants, la durée et la qualité audio. Pour plus d’informations sur les détails de la réunion, voir la section détails sur l’activité [de la](#meeting-activity-details) réunion plus loin dans cet article.
- **Historique** Présente un historique de l’activité de gestion sur l Teams de salle, y compris les mises à jour de configuration, les redémarrages d’appareil et les liens de téléchargement du journal des appareils.

#### <a name="meeting-activity-details"></a>Détails de l’activité de réunion

**L’onglet** Activité Teams détails de l’appareil de salle affiche des informations détaillées et générales sur toutes les réunions à qui l’appareil a participé au fil du temps. Dans **l’onglet** Activité, vous pouvez voir quand une réunion a été tenue, le nombre de participants à la réunion participé à la réunion et la qualité de l’audio pendant la réunion.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams résumé de l’activité sur les appareils de salle.":::

Pour voir les informations détaillées sur une réunion spécifique, sélectionnez la date et l’heure de la réunion pour plus d’informations. Si une réunion ne compte que deux participants, vous verrez la page des détails des participants, sans quoi vous verrez une page de résumé des participants.

##### <a name="participant-summary"></a>Résumé des participants

La page de résumé des participants affiche tous les participants qui ont participé à la réunion. Vous pouvez voir quand chaque participant a rejoint la réunion, son nom, sa qualité audio et les fonctionnalités utilisées pendant la session. Pour afficher les détails de la session d’un participant, sélectionnez l’heure de début de la session pour ce participant.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams de conférence de l’appareil de salle.":::

##### <a name="participant-details"></a>Détails du participant

La page des détails du participant affiche des informations de diagnostic de bout en bout pour la session de ce participant. Comme illustré dans le graphique **suivant, les** informations sur les  périphériques **, le** système et la connectivité sont fournies pour le participant et pour l salles Teams appareil. **Les informations** de diagnostic réseau entre le participant et le salles Teams appareil sont également fournies. Sélectionnez l’icône du contexte pour lequel vous souhaitez plus d’informations. Pour plus d’informations de diagnostic, sélectionnez **l’onglet** Avancé.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams d’appel de l’appareil de salle.":::
