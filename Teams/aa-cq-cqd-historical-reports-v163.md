---
title: Rapports d’historique de standard automatique et de file d’attente d’appels pour GCC High et DoD
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ROBOTS: NOINDEX, NOFOLLOW
description: Découvrez comment utiliser le rapport Power BI du standard automatique teams & rapport historique de la file d’attente des appels pour afficher les données d’historique du standard automatique et de la file d’attente des appels pour les clients GCC High et DoD.
ms.openlocfilehash: 619be6d7f0f78f67ef2db0f0693de82120d128c4
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176754"
---
# <a name="auto-attendant-and-call-queue-historical-reports-for-gcc-high-and-dod"></a>Rapports d’historique de standard automatique et de file d’attente d’appels pour GCC High et DoD

> [!IMPORTANT]
> La prise en charge du cloud public pour le modèle V1.63 prendra fin le 25 novembre 2022.
>
> Les clients du cloud public doivent utiliser la version 3.x.x du [standard automatique & rapports d’historique de file d’attente d’appels](aa-cq-cqd-historical-reports.md)

## <a name="v163-published-on-august-24-2022"></a>V1.63 publiée le 24 août 2022

Le **modèle Power BI de rapport d’historique de file d’attente de la file d’attente Teams &** fournit les trois rapports suivants :

- Le rapport [Standard automatique](media/aa-cq-historical-report-sample-aa-v163.png) affiche l’analytique des appels entrants dans vos standards automatiques.
- Le rapport [File d’attente](media/aa-cq-historical-report-sample-cq-v163.png) des appels affiche l’analytique des appels entrants dans vos files d’attente d’appels.
- Le rapport [Chronologie de l’agent](media/aa-cq-historical-report-sample-at-v163.png) affiche une vue chronologique des agents actifs dans les appels de file d’attente d’appels.

Ces rapports utilisent les données du magasin de données [CQD (Tableau de bord de qualité des](CQD-Power-BI-query-templates.md) appels). 

## <a name="v163-prerequisites"></a>V1.63 Prérequis

### <a name="power-bi-desktop"></a>Power BI Desktop
Vous devez avoir Power BI Desktop installé. Vous pouvez installer et utiliser la version gratuite à partir de [l’Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La version minimale compatible est 2.85.681.0 (septembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline CQD

Le compte que vous utilisez pour afficher le rapport d’historique doit disposer des autorisations nécessaires pour accéder au pipeline de données CQD. Pour plus d’informations, consultez [Rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="v163-installation"></a>V1.63 Installation 

Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur votre ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données CQD.

Procédez comme suit :

1. Téléchargez et enregistrez le fichier zip [des modèles de requête Power BI CQD](https://www.microsoft.com/download/details.aspx?id=102291) sur votre ordinateur.

1. Ouvrez le fichier zip.

1. Ouvrez le `CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit` fichier de modèle. Power BI Desktop doit être lancé.

1. Vous serez invité à sélectionner la région du pipeline de données CQD. Sélectionnez la région où se trouve votre locataire.

  :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="Capture d’écran de la sélection de la région du pipeline de données CQD.":::

1. La région où se trouve votre locataire peut être obtenue à l’aide de l’applet de commande [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```powershell
    (Get-CsTenant).ServiceInstance

    microsoftcommunicationsonline/noam-4a-s7
    ```

    1. La région s’affiche après le **/** comme dans l’exemple ci-dessus où la région est `noam`.

 1. Le rapport sera lancé avec des exemples de données.
 
 1. Pour afficher vos propres données, sélectionnez **Actualiser** sous l’onglet **Accueil** sous **Requêtes** dans Power BI Desktop.

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="Capture d’écran de la sélection de l’option d’actualisation.":::

1. Vous serez invité à vous connecter. Sélectionnez **Compte d’organisation**, puis **Se connecter**.

  :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="Capture d’écran montrant la connexion pour la version 1.63.":::

1. Sélectionnez **Se connecter** pour que les données s’actualisent.

## <a name="data-latency-for-aa-and-cq-analytics"></a>Latence des données pour l’analytique AA et CQ

Les données sont généralement disponibles dans les 30 minutes suivant la fin de l’appel . Toutefois, il peut arriver que l’affichage des données prenne plusieurs heures.

Vous devez actualiser les données pour voir les nouvelles données.

## <a name="customization"></a>Personnalisation

Vous pouvez personnaliser certains aspects de la visualisation des rapports, tels que l’ajout ou la suppression de champs à afficher dans les différentes visualisations, la modification du type de graphique, etc.

Le rapport contient toutes les métriques de données actuellement disponibles.

### <a name="change-color-schema"></a>Modifier le schéma de couleur

Les étapes suivantes supposent que vous avez déjà effectué les étapes d’installation.

Procédez comme suit :

1. Sélectionnez **l’onglet Affichage** dans le ruban.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Capture d’écran de la sélection de l’onglet affichage pour modifier le jeu de couleurs.":::

2. Sélectionnez le schéma de couleur dans la liste déroulante.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Capture d’écran montrant différents modèles de couleurs.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Définitions des rapports d’historique du standard automatique et de la file d’attente d’appels

### <a name="cloud-auto-attendant-analytics-report"></a>Rapport Cloud Auto Standard Analytics

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Source d’appel entrant<sup>1</sup>        |Distribution des appels par source d’appel interne/externe            |
|Directory Search, méthode                 |Distribution des appels par type de recherche                              |
|Nombre d’actions de l’appelant                     |Distribution des appels par action de numéro utilisée pendant l’appel       |
|Moyenne des secondes dans AA                   |Nombre moyen de secondes que les appelants passent dans l’AA                 |
|Actions moyennes de l’appelant                  |Nombre moyen d’actions effectuées par les appelants dans l’AA               |
|Résultats de l’appel                            |Distribution des appels par état d’appel final                         |
|Section inférieure du rapport                 |Répartition du flux d’appels                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapport     |Nom de la table source            |Filtre global                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Standard automatique        |fAutoAttendant        |AutoAttendant                |Aucun                                   |

|Section Rapport                                  |Champ(s) utilisé(s)                              |Filtres appliqués     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Sélecteur de date                                   |AAStartTime                                |Aucun                |
|Sélecteur d’intervalle de temps                             |AAStartHour                                |Aucun                |
|Standard automatique                                  |Nom AA                                    |Aucun                |
|Source d’appel entrant<sup>1</sup>                |Type d'appel<br>Somme de TotalCallCount (Measure) |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Directory Search, méthode                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod est abs_search_dtmf ou abs_search_name    |
|Nombre d’actions de l’appelant                             |AACallerActionCount<br>TotalCallCount      |Aucun                                                             |
|Moyenne des secondes dans AA                           |AAChainDuration (Measure)                  |Aucun                                                             |
|Actions moyennes de l’appelant                          |AACallerActionCount (Measure)              |Aucun                                                             |
|Résultats de l’appel                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Aucun                                       |
|Section inférieure du rapport                         |Nom AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Type d'appel<br>MM-DD<br>TotalCallCount |Aucun       |

#### <a name="fautoattendant-cqd-fields-description"></a>Description des champs CQD fAutoAttendant

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nom AA                                 |Texte                     |Nom du compte de ressource attaché au standard automatique<br><br>Si le nom complet du compte de ressource est **aa_test@microsoft.com**, cette valeur est **: aa_test** |
|AACallerActionCount                     |Nombre entier             |Résumer : Somme<br>Nombre d’actions sélectionnées par l’appelant dans le standard automatique pendant l’appel  |
|AACallerActionCount (Measure)          |Nombre entier             |Identique à ce qui précède, sauf que sera égal à 0 si aucun appel au lieu de vide                              |
|AACallFlow                              |Texte                     |Encapsule les différents états de l’appel du standard automatique : valeurs possibles :<br><br>§ abs_search<br>§ annonce<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texte                     |Résultat de l’appel final : valeurs possibles :<br><br>§ failed_to_establish_media (la partie média de l’appel n’a pas pu être établie)<br>§ failover_to_operator (appel transféré vers l’opérateur généralement en raison d’une erreur système)<br>§ oaa_chain_too_long (trop de jambes dans l’AA)<br>§ oaa_session_too_long (la session AA a duré trop longtemps)<br>§ service_declined (AA n’a pas accepté l’appel)<br>§ service_terminated (la configuration AA déconnecte l’appel ou l’appel bloqué)<br>§ terminated_automatic_selection (la configuration AA déconnecte les appels)<br>§ terminated_no_operator (appel arrêté en raison d’une erreur aucun opérateur défini) <br>§ terminated_transfer_failed (l’appel s’est terminé en cas d’échec du transfert , généralement vers un numéro externe)<br>§ transfer_in_progress (transfert AA->AA)<br>§ transferred_to_operator (l’appel a été transféré à l’opérateur , généralement en raison d’une erreur de l’utilisateur)<br>§ transferred_to_receptionist (identique à transferred_to_operator)<br>§ transferred_to_self (l’appel a été retourné au début de l’AA, généralement à partir d’une option d’annonce de menu)<br>§ transferred_to_shared_voicemail (l’appel a été transféré vers la messagerie vocale partagée)<br>§ transferred_to_user (l’appel a été transféré à un utilisateur - y compris les files d’attente d’appels)<br>§ inconnu (une condition inconnue s’est produite)<br>§ user_terminated (l’appelant a raccroché) |
|Légende de l’appel AA                          |Texte                     |Configure les éléments de légende basés sur AACallResult                               |
|AAChainDuration                         |Nombre décimal           |Résumer : Somme<br>Durée de l’appel dans le standard automatique                     |
|AAChainDuration (Measure)               |Nombre décimal           |Identique à ce qui précède, sauf que sera égal à 0 si aucun appel au lieu de vide              |
|AAChainIndex                            |Texte                     |                                                                         |
|AAConnectivityType                      |Texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Texte                     |Nombre de standards automatiques impliqués dans l’appel                               |
|AADirectorySearchMethod                 |Texte                     |Dernière méthode de recherche dans le carnet d’adresses - valeurs possibles :<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Nombre décimal           |Heure de début de l’appel du standard automatique                                           |
|AAStartTime                             |Date/heure                |Heure de début de l’appel du standard automatique                                           |
|AATransferAction                        |Texte                     |Type de cible de transfert d’appel : valeurs possibles :<br><br>§ application - entité d’application vocale<br>§ external_pstn<br>§ hunt_group - Entité File d’attente d’appels<br>§ orgaa - Entité de standard automatique<br>§ shared_voicemail<br>§ inconnu<br>§ utilisateur |
|Type<sup>d’appel 1</sup>                   |Texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne           |
|IsAAInvolved                            |Texte                     |Toujours 1                                                                 |
|MM-DD                                   |Texte                     |Appel du standard automatique mois-jour                                            |
|PSTNMinutes                             |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes                                     |
|TotalCallCount                          |Nombre entier             |Résumer : Somme<br>Always 1 : utilisé pour fournir la somme de tous les appels            |
|Somme de TotalCallCount (Measure)         |Nombre entier             |Identique à ce qui précède, sauf que sera égal à 0 si aucun appel au lieu de vide              |


### <a name="cloud-call-queue-analytics-report"></a>Rapport Analyse de la file d’attente des appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Source d’appel entrant<sup>1</sup>        |Distribution des appels par source d’appel interne/externe             |
|Temps d’attente moyen (secondes)             |Temps d’attente pour les appels répondus et abandonnés                          |
|Nombre de volumes d’appels et d’activation de l’agent      |Distribution des appels par files d’attente d’appels / Nombre maximal d’inscriptions d’agent  |
|Résultats de l’appel                            |Distribution des appels par résultat d’appel                               |
|Appels abandonnés                         |Distribution des appels abandonnés par files d’attente d’appels                     |
|Durée moyenne de session (secondes)        |Longueur de l’appel en secondes regroupée par résultat de l’appel                      |
|Destinations de dépassement/délai d’expiration des appels      |Distribution des appels qui ont expiré ou dépassé le délai d’attente                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapport                                   |Nom de la table source                               |Filtre global       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|File d’attente d’appels            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Aucun                |

|Section Rapport                      |Table -> Champ(s) utilisé(s)                |Filtres appliqués       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de date                       |fCallQueueAnalytics -> Date           |Aucun                  |
|Sélecteur d’intervalle de temps                 |fCallQueueAnalytics -> CQHour         |Aucun                  |
|Compte de ressource de file d’attente d’appels         |fCallQueueAnalytics -> nom CQ        |Aucun                  |
|Source d’appel entrant<sup>1</sup>    |fCallQueueAnalytics -> somme du nombre d’appels (mesure)<br>fCallQueueAnalytics -> Type d’appel    |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Délai d’attente moyen (secondes)-Avant réponse |fCallQueueFinalStateAction -> moyenne de la durée moyenne du CQ (mesure) |Le résultat de l’appel de file d’attente est agent_joined_conference ou transferred_to_agent|
|Délai d’attente moyen (secondes)-Avant abandon |fCallQueueFinalStateAction -> moyenne de la durée moyenne des appels (mesure) |Le résultat de l’appel de file d’attente n’est pas agent_joined_conference, transferred_to_agent, dépassé, timed_out |
|Nombre de Opt-In d’agents et de volume d’appels   |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Call Queue Agent Opt In Count<br>fCallQueueAnalytics -> nom CQ<br>fCallQueueAnalytics -> Date |Aucun |
|Appels abandonnés                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La légende du résultat de l’appel de la file d’attente d’appels est abandonnée |
|Durée moyenne de session (secondes)    |fCallQueueFinalStateAction -> Durée moyenne de la file d’attente des appels (s)<br>Légende du résultat de l’appel de file d’attente |Durée moyenne de la file d’attente des appels (s) > 0 |
|Destinations de dépassement/délai d’expiration des appels  |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> type de cible de file d’attente d’appels<br>fCallQueue Target Type Legend |La légende du type de cible de file d’attente d’appels ne contient pas abandonné et l’agent a répondu |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Description des champs CQD fCallQueueAnalytics

|Nom                                    |Type de données                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                          |
|Nombre d’agents de file d’attente des appels                  |Nombre entier             |Résumer : Somme<br>Nombre d’agents configurés dans la file d’attente des appels            |
|Nombre d’inscriptions de l’agent de file d’attente des appels           |Nombre entier             |Résumer : Somme<br>Nombre d’agents abonnés à la file d’attente des appels              |
|Résultat de l’appel de file d’attente                  |Texte                     |État final de l’appel de file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference (appels en mode conférence avec réponse)<br>§ refusé<br>§ déconnecté<br>Erreur §<br>§ échec<br>§ non valide<br>§ dépassement de capacité (condition de dépassement de capacité remplie)<br>§ timed_out (condition de délai d’expiration remplie)<br>§ transferred_to_agent (appels en mode de transfert ayant répondu {default}) |
|Légende du résultat de l’appel de file d’attente           |Texte                     |Configure les éléments de légende en fonction du résultat de la file d’attente des appels                             |
|Type de cible de file d’attente d’appels                  |Texte                     |***Type de cible de redirection d’appel : valeurs possibles :***<br><br>§ ApplicationEndpoint<br>§ Boîte aux lettres<br>§ Autres<br>§ Utilisateur |
|Légende du type de cible de file d’attente d’appels           |Texte                     |Configure les éléments de légende en fonction du type de cible de file d’attente d’appels                        |
|Type<sup>d’appel 1</sup>                   |Texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne             |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Heure CQ                                 |Nombre entier             |Heure de début de l’appel de la file d’attente d’appels                                                 |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente (heure)                                 | 
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                     |
|Type de connectivité RTC                  |Texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN Total Minutes                      |Nombre entier             |Résumer : Somme<br>Utilisation du nombre total de minutes pour les appels RTC                       |
|Somme du nombre d’appels (mesure)             |Nombre entier             |Identique au nombre d’appels, toutefois, sera égal à 0 quand aucun appel                          |
|TotalCallCount (Measure)                |Nombre entier             |Résumer : Somme<br>Nombre d’appels                                                |


#### <a name="fcallqueuefinalstateaction-cqd-fields-description"></a>Description des champs CQD fCallQueueFinalStateAction

|Nom                                    |Type de données                |Description                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durée moyenne des appels (secondes)         |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels en secondes pour les appels abandonnés    |
|Durée moyenne de la file d’attente des appels (s)       |Nombre décimal           |Résumer : Somme<br>Moyenne en secondes d’attente pour les appels répondus           |
|Moyenne de la durée moyenne de l’appel (mesure)  |Nombre entier             |Identique à la durée moyenne des appels (secondes), toutefois, sera 0 quand aucun appel   |
|Moyenne de la durée moyenne du CQ (mesure)    |Nombre entier             |Identique à la durée moyenne de la file d’attente des appels (s), toutefois, sera de 0 quand aucun appel n’est nécessaire |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                         |
|Résultat de l’appel de file d’attente                  |Texte                     |État final de l’appel de file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference (appels en mode conférence avec réponse)<br>§ refusé<br>§ déconnecté<br>Erreur §<br>§ échec<br>§ non valide<br>§ dépassement de capacité (condition de dépassement de capacité remplie)<br>§ timed_out (condition de délai d’expiration remplie)<br>§ transferred_to_agent (appels en mode de transfert avec réponse {default} |
|Légende du résultat de l’appel de file d’attente           |Texte                     |Configure les éléments de légende en fonction du résultat de l’appel de la file d’attente d’appels                      |
|Action d’état final d’appel de file d’attente           |Texte                     |Action finale de file d’attente d’appel : valeurs possibles :<br><br>§ disconnect (appels timed_out)<br>§ disconnect_with_busy (appels débordés)<br>§ failed_to_accept_call<br>§ vers l’avant<br>§ shared_voicemail<br>§ autres<br>§ messagerie vocale                |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente des appels (heure)                                 |
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                     |
|IsAbandoned                             |True/false               |True si un agent ne répond pas à l’appel                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>Rapport de chronologie de l’agent de file d’attente d’appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                                          |Description                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Nombre d’appels par agent                                |Distribution des appels par file d’attente d’appels et agent                |
|Distribution par agent et toutes les files d’attente                     |Distribution des appels par agent et file d’attente d’appels                |
|Tableau (en bas à droite)                                    |Distribution des appels par agent avec la durée moyenne et totale des appels |
|Durée moyenne des appels (secondes) par agent                |Durée moyenne (secondes) de l’appel par agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapport           |Nom de la table source         |Filtre global       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Chronologie de l’agent        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Aucun                |


|Section Rapport                                |Champ(s) utilisé(s)                         |Filtres appliqués       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de date                                 |Datetime                              |Aucun                  |
|Sélecteur de nom d’utilisateur de l’agent                       |Nom de l’agent                            |Aucun                  |
|Sélecteur de comptes de ressources de file d’attente d’appel          |Nom du CQ                               |Aucun                  |
|Nombre d’appels par agent                      |Nom de l’agent<br>Nombre d’appels<br>Hour      |Aucun                  |
|Distribution par agent et file d’attente d’appels          |Nom de l’agent<br>Durée moyenne des appels (secondes)<br>Nombre d’appels<br>Nom du CQ |Aucun                      |
|Bas à gauche                                   |Nom de l’agent<br>Durée moyenne des appels (secondes)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom du CQ<br>Hour<br>MM-DD | Aucun |
|Durée moyenne des appels (secondes) par agent      |Nom de l’agent<br>Durée moyenne des appels (secondes) | Aucun |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Description des champs CQD fAgentTimelineAnalytics

|Nom                                    |Type de données                |Description                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nom de l’agent                              |Texte                     |UPN utilisateur<br>Si le nom d’utilisateur complet est **user@microsoft.com**, cette valeur est : **utilisateur** |
|Durée moyenne des appels (secondes)         |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels de file d’attente d’appels répondus en secondes |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d’appels traités par l’agent     |
|Durée de l’appel (minutes)                 |Nombre entier             |Résumer : Somme<br>Durée totale des appels de file d’attente d’appels répondus en minutes (arrondie à la minute la plus proche)  |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Date                                    |Date                     |Date de l’appel                                             |
|Datetime                                |Datetime                 |Date de l’appel                                             |
|Hour                                    |Nombre entier             |Heure d’appel                                             |
|MM-DD                                   |Texte                     |Mois et jour de l’appel                                    |


> [!NOTE]
> Lorsqu’un appel arrive à la première file d’attente d’appels, si le nombre d’appels en attente dans cette file d’attente a atteint la limite de **gestion du dépassement de capacité** d’appel et si l’option de redirection envoie de nouveaux appels à une deuxième file d’attente d’appels, les agents de la deuxième file d’attente d’appels apparaissent comme étant dans la première file d’attente d’appels de ce rapport. 

## <a name="known-issues"></a>Problèmes connus

- La file d’attente d’appels et les standards automatiques sont affichés par l’ID du compte de ressource au lieu des noms de file d’attente/standard automatique des appels.  Pour afficher tout le trafic d’un standard automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources affectés au standard automatique ou à la file d’attente d’appels.

- Seuls 28 jours d’historique sont disponibles dans le tableau de bord, car les données de file d’attente d’appels/standard automatique sont considérées comme des données personnelles et soumises à des stratégies de conservation de la confidentialité des données.

- Dans certains scénarios, le nombre d’appels répondus par l’agent dans le rapport **chronologie de l’agent de file d’attente d’appels** cloud peut être différent du nombre d’appels indiqué dans l’historique des appels du client Teams. L’historique des appels du client Teams est correct. Le support est en cours d’examen, mais il n’y a pas de temps estimé pour la réparation disponible pour l’instant.

- <sup>1 La</sup> **source d’appel entrante** dans le standard automatique et les graphiques de file d’attente d’appels affichent la source du tronçon d’appel final plutôt que la source du segment d’appel initial. Par exemple, si un standard automatique reçoit un appel externe et transfère l’appel vers un autre standard automatique ou file d’attente d’appels, la **source d’appel entrant** est signalée comme interne.

## <a name="version-1xx-history"></a>Historique des versions 1.xx

Reportez-vous à : CQD Teams Auto Standard & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a detailed list of changes                         

|Version  |Date de publication     |Fichier                                                           |Description                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |24 août 2022    |CQD Teams Auto Standard & Call Queue Historical Report V1.63.pbit |                                                    |
|1.60     |22 juillet 2022      |CQD Teams Auto Standard & Call Queue Historical Report V1.60.pbit |                                                    |
|1.00     |5 novembre 2020   |CQ et AA combinés Analytics 20201105.pbit                         |Version initiale                                     |

