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
description: Découvrez comment développer et exécuter une maintenance et des opérations continues pour vous assurer que vos systèmes Salles Microsoft Teams sont disponibles pour vos utilisateurs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47f1c170fd0c41331dfaffa2d81386ac3c2fb722
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106269"
---
# <a name="manage-microsoft-teams-rooms"></a>Gérer les Salles Microsoft Teams

Si vous avez Salles Microsoft Teams dans votre organisation, vous disposez d’options de gestion flexibles.  Vous pouvez gérer les appareils vous-même dans le même emplacement central que celui où vous gérez toutes vos solutions Teams, Microsoft Teams centre d’administration. Vous pouvez également transférer la responsabilité de la gestion à des experts dédiés à l’aide [de Salles Microsoft Teams Services managés](https://portal.rooms.microsoft.com).  Vous pouvez également déléguer l’accès de gestion à un partenaire de votre choix pour l’une des options.

Avec Microsoft Teams centre d’administration, vous pouvez :

- Effectuer la gestion des appareils, comme le redémarrage des appareils et le téléchargement des journaux d’activité des appareils
- Appliquer des paramètres spécifiques à Teams
- Vérifier l’état d’intégrité des Salles Microsoft Teams et de leurs périphériques, notamment les caméras, les écrans, les microphones, et ainsi de suite
- Passez en revue les activités de réunion actuelles et passées (telles que des détails sur la qualité des appels, l’intégrité et la connectivité du réseau et le nombre de participants)
- Voir les périphériques (tels que les caméras et les projecteurs) connectés à Salles Microsoft Teams

Pour gérer salles Teams appareils, ouvrez le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com) et accédez à **Teams Appareils** >  **salles Teams sur Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="salles Teams page récapitulative dans Teams centre d’administration.":::


> [!IMPORTANT]
> Pour gérer les appareils à l’aide du centre d’administration Teams, vous devez disposer des rôles Administrateur général, Administrateur Teams ou Teams Administrateur d’appareils.

## <a name="make-changes-to-teams-rooms-devices"></a>Apporter des modifications à salles Teams appareils

Si vous avez plusieurs salles Teams, vous pouvez effectuer la plupart des actions sur plusieurs appareils en même temps. Par exemple, vous pouvez définir Teams paramètres d’application sur toutes vos salles Teams en même temps.

### <a name="device-settings"></a>Paramètres de l’appareil

Vous pouvez modifier les paramètres sur un ou plusieurs salles Teams de votre organisation. Pour modifier les paramètres, sélectionnez l’appareil ou les appareils que vous souhaitez gérer, puis **sélectionnez Modifier Paramètres**. Un nouveau volet s’ouvre avec tous les paramètres que vous pouvez modifier. Le tableau suivant répertorie les paramètres que vous pouvez modifier à l’aide du centre d’administration Teams. Certains paramètres ne sont disponibles que lorsque vous sélectionnez un seul salles Teams.

Si vous en sélectionnez plusieurs, les paramètres qui prennent en charge la modification en bloc affichent les deux options suivantes.

- **Conserver la valeur existante** Si vous choisissez cette option, aucune modification n’est apportée au paramètre du salles Teams que vous avez sélectionné.
- **Remplacer la valeur existante par** Si vous choisissez cette option, vous pouvez mettre à jour le paramètre sur le salles Teams que vous avez sélectionné avec la valeur que vous fournissez.
    > [!CAUTION]
    > Les valeurs existantes sur les paramètres que vous choisissez de mettre à jour seront remplacées par la valeur que vous fournissez. Si vous souhaitez ajouter à une liste de valeurs existantes, vous devez inclure les valeurs existantes avec la valeur que vous souhaitez ajouter. Par exemple, si un paramètre a une liste de domaines existante de `contoso.com, fabrikam.com`, et que vous souhaitez ajouter `northwindtraders.com`, la valeur que vous devez fournir serait `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Si vous sélectionnez plusieurs salles Teams, le paramètre sur tous les appareils que vous sélectionnez est remplacé par la valeur que vous fournissez. Si salles Teams ont des valeurs différentes pour un paramètre, elles sont toutes mises à jour vers la même valeur.

| Paramètres                                                      | Valeurs acceptées                                        | Prend en charge la modification en bloc |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Compte*                                                    |                                                        |                    |
| **Email**                                                    | Adresse e-mail                                          | Non                 |
| **Mode de réunion pris en charge**                                   | Microsoft Teams uniquement<br>Skype Entreprise (par défaut) et Microsoft Teams<br>Skype Entreprise et Microsoft Teams (par défaut)<br>Skype Entreprise uniquement|Oui|
| **Authentification moderne**                                    | Activé<br>Désactivé                                              | Oui                |
| **adresse Exchange**                                         | Adresse e-mail                                          | Non                 |
| **Domain\username (facultatif)**                               | Domaine de compte et nom d’utilisateur                           | Non                 |
| **Configurer un domaine**                                         | Liste séparée par des virgules                                   | Oui                |
| *Réunions*                                                   |                                                        |                    |
| **Partage automatique d’écran**                                 | Activé<br>Désactivé                                              | Oui                |
| **HdMI ingère le partage audio**                                 | Activé<br>Désactivé                                              | Oui                |
| **Afficher les noms des réunions**                                       | Activé<br>Désactivé                                              | Oui                |
| **Quitter automatiquement si tout le monde a quitté la réunion**                 | Activé<br>Désactivé                                              | Oui                |
| **Participer à des réunions tierces**                 | Cisco Webex<br>Zoom                                              | Oui                |
| **Rejoindre avec des informations sur la salle**                 | Sélectionné<br>Non sélectionné                                              | Oui                |
| **Joindre avec des informations personnalisées**                 | Sélectionné<br>Non sélectionné                                              | Oui                |
| **Nom (obligatoire)**                 | Nom de la pièce ou de l’espace                                              | Oui                |
| **E-mail (obligatoire)**                 | Adresse e-mail                                              | Oui                |
| *Device*                                                     |                                                        |                    |
| **Mode Double moniteur**                                        | Activé<br>Désactivé                                              | Oui                |
| **Autoriser la duplication de contenu** | Sélectionné<br>Non sélectionné                                 | Oui                |
| **Bluetooth balises**                                      | Activé<br>Désactivé                                              | Oui                |
| **Accepter automatiquement les invitations aux réunions basées sur la proximité** | Sélectionné<br>Non sélectionné                                 | Oui                |
| **Envoyer des journaux avec des commentaires**                                  | Activé<br>Désactivé                                              | Oui                |
| **Adresse e-mail pour les journaux d’activité et les commentaires**                      | Adresse e-mail                                          | Oui                |
| *Coordonner les réunions*                                                     |                                                        |                    |
| **Réunions coordonnées** | Activé<br>Désactivé                                 | Non                |
| **Activer le microphone de cet appareil** | Activé<br>Désactivé                                 | Non                |
| **Permettre aux utilisateurs de s’activer lors de la participation à une réunion** | Sélectionné<br>Non sélectionné                                 | Non                |
| **Activer l’appareil photo de cet appareil** | Activé<br>Désactivé                                 | Non                |
| **Permettre aux utilisateurs de s’activer lors de la participation à une réunion** | Sélectionné<br>Non sélectionné                                 | Non                |
| **Activer le tableau blanc pour cet appareil** | Activé<br>Désactivé                                 | Non                |
| **Comptes d’appareil approuvés (séparés par des virgules)** | Liste des appareils                              | Non                |
| *Périphériques*                                                |                                                        |                    |
| **Microphone de conférence**                                  | Liste des microphones disponibles                          | Non                 |
| **Haut-parleur de conférence**                                     | Liste des haut-parleurs disponibles                             | Non                 |
| **Volume par défaut**                                           | 0-100                                                  | Non                 |
| **Haut-parleur par défaut**                                          | Liste des haut-parleurs disponibles                             | Non                 |
| **Volume par défaut**                                           | 0-100                                                  | Non                 |
| **Caméra de contenu**                                           | Liste des caméras disponibles                              | Non                 |
| **Améliorations apportées à la caméra de contenu**                              | Activé<br>Désactivé                                              | Non                 |
| **Faire pivoter la caméra de contenu de 180 degrés**                        | Activé<br>Désactivé                                              | Non                 |
| *Thématisation*                                                    |                                                        |                    |
|                                                              | Par défaut<br>Aucun thème<br>Personnalisé<br>Liste des thèmes intégrés   | Oui                |

### <a name="cortana-settings"></a>paramètres de Cortana

Vous pouvez activer Cortana pour que _l’activation vocale_ ou _push communique à_ l’aide de PowerShell pour tous les appareils de votre organisation ou pour chaque appareil séparément.

Consultez [Salles Microsoft Teams sur Windows](../cortana-in-teams.md) dans l’article « assistance vocale Cortana dans Teams ».

### <a name="front-row-layout-settings"></a>Paramètres de disposition de la ligne frontale

La première ligne est l’option de disposition d’affichage de réunion pour salles Teams sur Windows.

| appareil Teams | Version de l’application | Devant l’affichage de la salle |
|--------------|-------------|-----------------------|
|Salles Microsoft Teams sur Windows | 4.11.12.0 ou version ultérieure (la dernière version est recommandée) | Prend en charge les affichages unique et double ; Taille minimale : 46 pouces; Proportion 16:9 avec résolution 1920x1080 ou 21:9 avec résolution 2560x1080 ; Tous les affichages doivent être définis à une mise à l’échelle de 100 % dans Windows paramètres |

Consultez [Salles Microsoft Teams maintenance et opérations](rooms-operations.md#scale-and-resolution) pour ajuster vos paramètres d’affichage afin de répondre aux exigences de la ligne front.

Pour savoir comment définir la ligne frontale comme disposition par défaut d’une salle ou comment la désactiver, consultez [Gérer les paramètres d’une console Salles Microsoft Teams à distance avec un fichier de configuration XML](xml-config-file.md#set-front-row-as-the-default-layout).

Pour plus d’informations sur la gestion des lignes frontales, consultez [Problèmes connus](known-issues.md#Limits) .

## <a name="device-restart-options"></a>Options de redémarrage de l’appareil

Les modifications apportées aux paramètres de l’appareil prennent effet uniquement après le redémarrage de salles Teams. Lorsque vous apportez des modifications qui nécessitent un redémarrage, vous pouvez choisir de redémarrer immédiatement ou de planifier un redémarrage. Voici les options de redémarrage disponibles :

- **Redémarrage immédiat** Si vous choisissez cette option, tous les appareils pour lesquels vous apportez des modifications redémarreront dès que vous sélectionnez cette option.
- **Redémarrage planifié** Si vous choisissez cette option, vous pouvez redémarrer les appareils auxquels vous apportez des modifications à un moment moins perturbateur pour votre organisation.
  - **Sélectionner la date et l’heure** : choisissez la date et l’heure spécifiques pour redémarrer l’appareil. La date et l’heure que vous choisissez sont locales sur l’appareil en cours de redémarrage. 
  - **Laisser la mise à jour pour le redémarrage nocturne** Les appareils sont redémarrés tous les soirs pour effectuer la maintenance. Les modifications que vous apportez aux appareils seront appliquées pendant ce redémarrage.

> [!CAUTION]
> salles Teams qui sont en cours d’utilisation au moment d’un redémarrage ne seront plus disponibles pendant la durée du processus de redémarrage. Ils seront déconnectés des réunions en cours et ne seront pas disponibles pour participer à de nouvelles réunions.

## <a name="remove-device"></a>Supprimer un appareil

Lorsque vous supprimez un appareil, celui-ci est supprimé de votre organisation et n’apparaît plus dans votre liste de salles Teams sur Windows dans le centre d’administration Teams.

Si vous supprimez un appareil et qu’il est toujours configuré avec un nom d’utilisateur et un mot de passe valides, il est automatiquement ajouté à votre liste salles Teams s’il se connecte à Microsoft 365 à nouveau.

Pour supprimer un ou plusieurs appareils, procédez comme suit :

1. Accédez à **Teams Appareils** >  **salles Teams sur Windows** et sélectionnez les appareils que vous souhaitez supprimer.
2. Sélectionnez **Supprimer**.

## <a name="download-device-logs"></a>Télécharger les journaux d’activité des appareils

Vous pouvez télécharger une copie des fichiers journaux de diagnostic d’un appareil si vous y êtes invité par le support Microsoft. Les fichiers journaux sont compressés dans un fichier zip qui peut être téléchargé à partir du centre d’administration Teams.

Pour télécharger les journaux d’activité à partir d’un appareil salles Teams sur votre ordinateur, procédez comme suit :

1. Accédez à **Teams Appareils** >  **salles Teams sur Windows** et sélectionnez le nom de l’appareil à partir duquel vous souhaitez télécharger les journaux d’activité.
1. Sélectionnez **Télécharger les journaux d’activité des appareils**. La disponibilité des journaux d’activité des appareils peut prendre plusieurs minutes.
1. Sélectionnez l’onglet **Historique** , puis sélectionnez le lien du fichier journal sous **Fichier de diagnostics**. Un fichier zip contenant les fichiers journaux de diagnostic de votre appareil est téléchargé dans le dossier Téléchargements par défaut de votre navigateur.

## <a name="view-device-information"></a>Afficher les informations sur l’appareil

À partir du centre d’administration Teams, vous pouvez afficher l’état global de tous les appareils de votre organisation et afficher les détails de chaque appareil individuellement.

### <a name="teams-rooms-system-dashboard"></a>tableau de bord système salles Teams

Le tableau de bord salles Teams système vous montre en un clin d’œil l’état et l’intégrité de tous vos appareils.

### <a name="device-details-view"></a>Vue détails de l’appareil

Pour afficher des informations détaillées sur un appareil, sélectionnez son nom dans la liste des appareils. En mode Détails, vous pouvez voir les informations suivantes sur votre appareil :

- **État d’intégrité** Affiche l’intégrité globale de l’appareil Teams Room. L’état d’intégrité peut être **sain** ou **non sain**.
- **Hors connexion depuis** Affiche la dernière fois que Microsoft 365 a pu communiquer avec l’appareil.
- **État de l’appareil** Affiche l’état actuel de l’appareil : **inactif**, **réunion Teams**, **réunion Skype** ou **ingestion**.
- **Périphériques** Affiche les périphériques connectés à votre appareil Teams Room et leur état d’intégrité. L’état d’intégrité peut être **Connecté** ou **Déconnecté**.
- **Santé** Affiche des informations détaillées sur les périphériques connectés à votre appareil Teams Room, la connectivité réseau, l’état de connexion aux services requis et les informations de version logicielle.
- **Détails** Affiche les informations du fabricant, l’adresse IP réseau et Teams l’adresse MAC/série de l’appareil Room.
- **Activité** Affiche les détails de la réunion précédente, notamment la date et l’heure de la réunion, le nombre de participants, la durée et la qualité audio. Pour plus d’informations sur les détails de la réunion, consultez la section [Détails de l’activité](#meeting-activity-details) de réunion plus loin dans cet article.
- **Histoire** Affiche un historique de l’activité de gestion sur l’appareil Teams Room, y compris les mises à jour de configuration, les redémarrages de l’appareil et les liens de téléchargement du journal des appareils.

#### <a name="meeting-activity-details"></a>Détails de l’activité de réunion

**L’onglet Activité** de Teams Détails de l’appareil room affiche des informations détaillées et générales sur toutes les réunions aux cours des laquelle l’appareil a participé au fil du temps. Dans **l’onglet Activité** , vous pouvez voir quand une réunion a eu lieu, combien de participants ont participé à la réunion et la qualité de l’audio pendant la réunion.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Liste récapitulative de l’activité de l’appareil Room.":::

Pour afficher les informations détaillées sur une réunion spécifique, sélectionnez la date et l’heure de la réunion dont vous souhaitez plus d’informations. Si une réunion ne compte que deux participants, la page des détails du participant s’affiche. Sinon, une page récapitulative du participant s’affiche.

##### <a name="participant-summary"></a>Résumé des participants

La page récapitulative des participants montre tous les participants qui ont assisté à la réunion. Vous pouvez voir quand chaque participant a rejoint la réunion, son nom, sa qualité audio et les fonctionnalités qui ont été utilisées pendant sa session. Pour afficher les détails de la session d’un participant, sélectionnez l’heure de début de la session pour ce participant.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams détails de la conférence sur les appareils room.":::

##### <a name="participant-details"></a>Détails du participant

La page de détails du participant affiche des informations de diagnostic de bout en bout pour la session de ce participant. Comme indiqué dans le graphique suivant, les informations **sur l’appareil**, **le système** et la **connectivité** sont fournies pour le participant et pour l’appareil salles Teams. **Des informations de diagnostic réseau** entre le participant et l’appareil salles Teams sont également fournies. Sélectionnez l’icône du contexte sur lequel vous souhaitez plus d’informations. Pour plus d’informations de diagnostic, sélectionnez l’onglet **Avancé** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams Détails de l’appel de l’appareil Room.":::
