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
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Apprenez-en davantage sur la création et l’exécution de maintenance et d’opérations en continu pour vous assurer que vos systèmes de salle Microsoft teams sont disponibles pour vos utilisateurs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2339967d6d7705266c13dbc65fb689c49c8e8279
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202920"
---
# <a name="manage-microsoft-teams-rooms"></a>Gérer les Salles Microsoft Teams

Si vous disposez de périphériques certifiés par Microsoft teams dans votre organisation, vous pouvez les gérer depuis un emplacement central à l’aide du centre d’administration Microsoft Teams. Vous pouvez :

- Effectuer une gestion des périphériques telle que le redémarrage ou le blocage des appareils, et le téléchargement des journaux de périphériques
- Appliquer des paramètres spécifiques aux équipes
- Vérification de l’état d’intégrité des appareils de salle Microsoft teams et de leurs périphériques, y compris des appareils photo, des écrans, des microphones, etc.
- Passer en revue l’activité actuelle d’une réunion (par exemple, détails relatifs à la qualité des appels, état du réseau et connectivité et nombre de participants);
- Voir les périphériques (par exemple, appareils photo et projecteurs) connectés à un appareil de salle Microsoft teams

Pour gérer les appareils de salle d’équipe, ouvrez le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com) et accédez à **périphériques**  >  **équipes**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Pages de synthèse des salles de teams dans le centre d’administration teams":::

> [!IMPORTANT]
> Pour gérer les appareils à l’aide du centre d’administration Teams, vous devez disposer de l’administrateur du service équipes ou des rôles d’administrateur général.

## <a name="make-changes-to-teams-rooms-devices"></a>Apporter des modifications à des appareils de salle d’équipe

Si vous avez plusieurs périphériques d’équipe, vous pouvez effectuer la plupart des actions sur plusieurs appareils en même temps. Par exemple, vous pouvez définir les paramètres de l’application équipes sur l’ensemble de vos appareils en même temps.

### <a name="device-settings"></a>Paramètres de l’appareil

Vous pouvez modifier les paramètres d’un ou de plusieurs appareils de votre organisation. Pour modifier les paramètres, sélectionnez le ou les appareils que vous voulez gérer, puis sélectionnez **modifier les paramètres**. Un nouveau volet s’ouvre et vous permet de modifier les paramètres de vos appareils. Le tableau suivant répertorie les paramètres que vous pouvez modifier à l’aide du centre d’administration Teams. Certains paramètres ne sont disponibles que lorsque vous sélectionnez un seul appareil.

Si vous sélectionnez plusieurs appareils, les paramètres qui prennent en charge la modification en bloc présentent les deux options suivantes.

- **Conserver la valeur existante** Si vous choisissez cette option, aucune modification n’est apportée au paramétrage sur les appareils sélectionnés.
- **Remplacer la valeur existante par** Si vous choisissez cette option, vous pouvez mettre à jour le paramètre sur les appareils que vous avez sélectionnés avec la valeur que vous spécifiez.
    > [!CAUTION]
    > Les valeurs existantes des paramètres que vous choisissez de mettre à jour seront remplacées par la valeur que vous spécifiez. Si vous souhaitez ajouter à une liste de valeurs existantes, vous devez inclure les valeurs existantes à la valeur que vous voulez ajouter. Par exemple, si un paramètre dispose d’une liste de domaines existante `contoso.com, fabrikam.com` et que vous voulez ajouter `northwindtraders.com` , la valeur que vous devez fournir est `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Si vous sélectionnez plusieurs appareils, le paramètre de tous les appareils que vous sélectionnez sera changé en fonction de la valeur que vous spécifiez. Si les appareils ont des valeurs différentes pour un paramètre, celles-ci sont toutes mises à jour avec la même valeur.

| Paramètres                                                      | Valeurs acceptées                                        | Prend en charge la modification en bloc |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Compte*                                                    |                                                        |                    |
| **Email**                                                    | Adresse de messagerie                                          | Non                 |
| **Mode de réunion pris en charge**                                   | Skype entreprise (par défaut) et Microsoft teams<br>Skype entreprise et Microsoft Teams (par défaut)<br>Skype entreprise uniquement|Oui|
| **Authentification moderne**                                    | Activé<br>Désactivé                                              | Oui                |
| **Adresse Exchange**                                         | Adresse de messagerie                                          | Non                 |
| **Domaine\nomutilisateur (facultatif)**                               | Nom de domaine et nom d’utilisateur du compte                           | Non                 |
| **Configurer un domaine**                                         | Liste séparée par des virgules                                   | Oui                |
| *Réunions*                                                   |                                                        |                    |
| **Partage d’écran automatique**                                 | Activé<br>Désactivé                                              | Oui                |
| **Afficher les noms des réunions**                                       | Activé<br>Désactivé                                              | Oui                |
| **Départ automatique si le reste de la réunion**                 | Activé<br>Désactivé                                              | Oui                |
| *Device*                                                     |                                                        |                    |
| **Double mode moniteur**                                        | Activé<br>Désactivé                                              | Oui                |
| **Signalisation Bluetooth**                                      | Activé<br>Désactivé                                              | Oui                |
| **Accepter automatiquement les invitations aux réunions en fonction de la proximité** | Sélectionné<br>Non activée                                 | Oui                |
| **Envoi de journaux avec commentaires**                                  | Activé<br>Désactivé                                              | Oui                |
| **Adresse e-mail pour les journaux et les commentaires**                      | Adresse de messagerie                                          | Oui                |
| *Périphériques*                                                |                                                        |                    |
| **Microphone de conférence**                                  | Liste des microphones disponibles                          | Non                 |
| **Intervenant de la Conférence**                                     | Liste des haut-parleurs disponibles                             | Non                 |
| **Volume par défaut**                                           | 0-100                                                  | Non                 |
| **Intervenant par défaut**                                          | Liste des haut-parleurs disponibles                             | Non                 |
| **Volume par défaut**                                           | 0-100                                                  | Non                 |
| **Caméra de contenu**                                           | Liste des caméras disponibles                              | Non                 |
| **Améliorations apportées à l’appareil photo**                              | Activé<br>Désactivé                                              | Non                 |
| **Faire pivoter la caméra de contenu 180 degrés**                        | Activé<br>Désactivé                                              | Non                 |
| *Thèmes*                                                    |                                                        |                    |
|                                                              | Par défaut<br>Aucun thème<br>Personnels<br>Liste des thèmes intégrés   | Oui                |

### <a name="device-restart-options"></a>Options de redémarrage de l’appareil

Les modifications apportées aux paramètres de l’appareil ne prennent effet qu’après le redémarrage des appareils. Lorsque vous apportez des modifications nécessitant un redémarrage, vous pouvez choisir si vous voulez redémarrer les appareils immédiatement ou planifier un redémarrage. Voici les options de redémarrage disponibles :

- **Redémarrage immédiat** Si vous choisissez cette option, tous les appareils sur lesquels vous apportez des modifications seront redémarrés dès que vous sélectionnez cette option.
- **Redémarrage prévu** Si vous choisissez cette option, vous pouvez redémarrer les appareils sur lesquels vous apportez des modifications à un moment qui ne perturbe pas votre organisation.
  - **Sélectionnez Date et heure** , puis choisissez une date et une heure spécifiques pour redémarrer l’appareil. La date et l’heure que vous choisissez est locale sur l’appareil redémarré. 
  - **Laisser la mise à jour pour réinitialisation nocturne** Les appareils sont redémarrés de façon nocturne pour effectuer la maintenance. Les modifications que vous apportez aux appareils seront appliquées au redémarrage.

> [!CAUTION]
> Les appareils utilisés au moment du redémarrage ne seront plus disponibles pendant la durée du processus de redémarrage. Ils seront déconnectés d’une réunion en cours et ne seront pas disponibles pour joindre de nouvelles réunions.

### <a name="remove-or-block-a-device"></a>Supprimer ou bloquer un appareil

Lorsque vous **supprimez** un appareil, celui-ci est supprimé de votre organisation et ne s’affiche plus dans la liste des appareils de salle d’équipes dans le centre d’administration Teams. 

Lorsque vous **bloquez** un périphérique, Teams ne communique plus le périphérique. Les appareils bloqués ne seront pas envoyés, même s’ils sont inclus dans un groupe de périphériques en cours de modification en bloc. Il apparaît toujours dans la liste des appareils de salle d’équipe dont le statut est **bloqué**.

Qu’il s’agisse d’un appareil bloqué ou supprimé, s’il est toujours configuré avec un nom d’utilisateur et un mot de passe valides, il sera automatiquement rajouté à votre liste d’appareils de salle d’équipe s’il est connecté à Microsoft 365.

Pour supprimer un ou plusieurs appareils, procédez comme suit :

1. Accédez à **périphériques**  >  **équipes** et sélectionnez les appareils que vous voulez supprimer.
1. Sélectionnez **Supprimer**.

Pour bloquer un appareil, procédez comme suit :

1. Accédez à **périphériques**  >  **équipes** et sélectionnez le nom de l’appareil que vous voulez bloquer.
1. Dans la page Détails de l’appareil, sélectionnez **actions** dans le coin supérieur droit de la page.
1. Sélectionnez **bloquer**.

Pour déverrouiller un appareil, procédez comme suit :

1. Accédez à **périphériques**  >  **équipes** et sélectionnez le nom de l’appareil que vous voulez bloquer.
1. Dans la page Détails de l’appareil, sélectionnez **actions** dans le coin supérieur droit de la page.
1. Sélectionnez **débloquer**.

## <a name="download-device-logs"></a>Télécharger les journaux de périphériques

Vous pouvez télécharger une copie des fichiers journaux de diagnostic d’un appareil, le cas échéant, à l’aide du support Microsoft. Les fichiers journaux sont comprimés dans un fichier zip qui peut être téléchargé à partir du centre d’administration Teams.

Pour télécharger les journaux à partir d’un appareil de salle d’équipe sur votre ordinateur, procédez comme suit :

1. Accédez à **périphériques**  >  **équipes** et sélectionnez le nom de l’appareil à partir duquel vous voulez télécharger les journaux.
1. Sélectionnez **Télécharger les journaux de périphériques**. Quelques minutes peuvent s’écouler avant que les journaux de périphériques deviennent disponibles.
1. Sélectionnez l’onglet **historique** , puis sélectionnez le lien fichier journal sous **fichier de diagnostic**. Un fichier zip contenant les fichiers journaux de diagnostic de votre appareil est téléchargé dans le dossier téléchargements par défaut de votre navigateur.

## <a name="view-device-information"></a>Afficher les informations sur l’appareil

Dans le centre d’administration Teams, vous pouvez afficher l’état global de tous les appareils de votre organisation et afficher les détails de chacun d’eux individuellement.

### <a name="teams-rooms-system-dashboard"></a>Tableau de bord du système de salle teams

Le tableau de bord du système salles d’équipes montre l’État et l’état de tous vos appareils en un clin d’œil.

### <a name="device-details-view"></a>Affichage des détails de l’appareil

Pour afficher des informations détaillées sur un appareil, sélectionnez son nom dans la liste des appareils. Le mode Détails vous permet d’accéder aux informations suivantes sur votre appareil :

- **État d’intégrité** Indique l’état global de l’appareil de salle de salle. L’état d’intégrité peut être **sain** ou **défectueux**.
- **Hors connexion depuis** Affiche la dernière fois que Microsoft 365 a pu communiquer avec l’appareil.
- **État** de l’appareil Affiche l’état actuel de l’appareil : **inactif**, **réunion teams**, **réunion Skype**ou **acquisition**.
- **Périphériques** Affiche les périphériques connectés à votre appareil de salle d’équipe ainsi que leur état d’intégrité. L’état d’intégrité peut être **connecté** ou **déconnecté**.
- **État d’intégrité** Affiche des informations détaillées sur les périphériques connectés à votre appareil de salle d’équipe, la connectivité réseau, le statut de connexion aux services requis et les informations de version du logiciel.
- **Informations détaillées** Affiche des informations sur le fabricant, une adresse IP réseau et une adresse de série/MAC.
- **Activité** Affiche les détails de la réunion, y compris la date et l’heure de la réunion, le nombre de participants, la durée et la qualité audio. Pour plus d’informations sur les détails de la réunion, voir la section Détails de l’activité de la [réunion](#meeting-activity-details) , plus loin dans cet article.
- **Historique des** appels Affiche un historique de l’activité de gestion de l’appareil de salle Teams, y compris les mises à jour de configuration, les redémarrages de périphériques et les liens de téléchargement du journal des appareils.

#### <a name="meeting-activity-details"></a>Détails sur l’activité de la réunion

L’onglet **activité** des détails de l’appareil salle de réunion affiche des informations de haut niveau et détaillées sur toutes les réunions auxquelles l’appareil a participé dans le temps. Dans l’onglet **activité** , vous pouvez voir le moment de la réunion, le nombre de participants ayant participé à la réunion et la qualité audio pendant la réunion.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Liste récapitulative de l’activité des périphériques de salle teams":::

Pour afficher des informations détaillées sur une réunion spécifique, sélectionnez la date et l’heure de la réunion à laquelle vous voulez obtenir plus d’informations. Si une réunion ne compte que deux participants, la page des détails des participants s’affiche, faute de quoi vous verrez une page de résumé du participant.

##### <a name="participant-summary"></a>Résumé du participant

La page Résumé du participant montre tous les participants ayant participé à la réunion. Vous pouvez voir à quel moment chaque participant a rejoint la réunion, son nom, sa qualité audio et les fonctionnalités utilisées au cours de sa session. Pour afficher les détails de la session d’un participant, sélectionnez l’heure de début de la session pour ce participant.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Détails de la Conférence sur les appareils de salle teams":::

##### <a name="participant-details"></a>Détails du participant

La page Détails du participant affiche des informations de diagnostic de bout en bout pour la session de ce participant. Comme indiqué dans l’illustration suivante, les informations relatives aux **périphériques**, au **système**et à la **connectivité** sont fournies pour le participant et l’appareil de salle de l’équipe. Des informations de diagnostic **réseau** sont également fournies entre le participant et l’appareil de salle de l’équipe. Sélectionnez l’icône du contexte pour lequel vous souhaitez plus d’informations. Pour obtenir des informations de diagnostic supplémentaires, sélectionnez l’onglet **Options avancées** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Détails de l’appel d’appareil de salle teams":::
