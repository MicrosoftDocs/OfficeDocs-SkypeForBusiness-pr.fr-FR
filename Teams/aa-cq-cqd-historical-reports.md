---
title: Rapport d’historique de la file d’attente d’appels & standard automatique
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
description: Découvrez comment utiliser le rapport Power BI du tableau de bord qualité des appels pour afficher les données historiques du standard automatique et de la file d’attente des appels.
ms.openlocfilehash: 23ce3663492ae84175825af4acc3772850935d3b
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614207"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Rapport d’historique de la file d’attente d’appels & standard automatique

Le standard automatique Teams & modèle Power BI de rapport historique de file d’attente d’appels fournit les trois rapports suivants :

- [Standard automatique](media/cqd-teams-aa-cq-historical-report-sample-aa.png) : affichage de l’analytique des appels entrants dans vos standards automatiques.
- [File d’attente d’appels](media/cqd-teams-aa-cq-historical-report-sample-cq.png) : analyse des appels entrant dans vos files d’attente d’appels.
- [Chronologie de l’agent](media/cqd-teams-aa-cq-historical-report-sample-at.png) : affichage de la chronologie des agents actifs dans les appels de file d’attente d’appels.

Ces rapports utilisent les données du magasin de données [Tableau de bord qualité des appels](CQD-Power-BI-query-templates.md) . Les rapports permettent aux organisations de signaler le nombre d’appels traités par les standards automatiques et les files d’attente d’appels.  Les rapports fournissent également des insights sur les performances de l’agent dans les files d’attente d’appels.

### <a name="v163-published-on-august-24-2022"></a>V1.63 publié le 24 août 2022

## <a name="prerequisites"></a>Conditions préalables

### <a name="power-bi-desktop"></a>Power BI Desktop
Vous devez avoir installé Power BI Desktop. Vous pouvez l’installer à partir du [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Vous pouvez utiliser la version gratuite de Power BI Desktop. La version minimale compatible est 2.85.681.0 (septembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline CQD

Le compte que vous utilisez pour afficher le rapport d’historique doit disposer d’autorisations pour accéder au pipeline de données CQD. Pour plus d’informations, consultez [le rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Installation 

Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur votre ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données CQD.

Effectuez les étapes suivantes :

- Téléchargez les [modèles de requête Power BI CQD](https://www.microsoft.com/download/details.aspx?id=102291) et enregistrez le fichier zip dans un répertoire sur votre ordinateur.

- Double-cliquez sur le fichier zip pour l’ouvrir.

- Double-cliquez sur le fichier de modèle « Standard automatique CQD Teams & Rapport historique de file d’attente d’appels V1.60.pbit ». Le Power BI Desktop doit être lancé.

- Vous êtes invité à sélectionner la région du pipeline de données CQD. Sélectionnez la région où se trouve votre locataire.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Capture d’écran sélection de la région du pipeline de données CQD.":::

- La région où se trouve votre locataire peut être obtenue à l’aide de l’applet de commande [Get-CsTenant](/powershell/module/skype/get-cstenant) .

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - La région s’affiche après l’exemple **/** ci-dessus, où la région est : noam

 - Le rapport sera lancé avec des exemples de données.
 
 - Pour afficher vos propres données, sélectionnez **Actualiser** sous l’onglet Accueil sous Requêtes dans Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Capture d’écran sélectionnant l’option d’actualisation.":::

- Vous serez invité à vous connecter. Sélectionnez **Compte d’organisation** , puis **Connectez-vous**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Capture d’écran montrant la connexion.":::

- Sélectionnez **Se connecter** et regardez l’actualisation des données.

## <a name="data-latency-and-aa--cq-analytics"></a>Latence des données et analytique AA & CQ

Les données sont généralement disponibles dans les 30 minutes suivant la fin de l’appel ; toutefois, il peut arriver que l’apparition des données prenne plusieurs heures. 

Vous devrez actualiser les données pour voir les nouvelles données.

## <a name="customization"></a>Personnalisation 

Vous pouvez personnaliser certains aspects de visualisation des rapports, tels que l’ajout ou la suppression de champs à afficher dans les différentes visualisations, la modification du type de graphique, etc.

Le rapport contient toutes les métriques de données actuellement disponibles.

### <a name="change-color-schema"></a>Modifier le schéma de couleur 

Les étapes suivantes supposent que vous avez déjà effectué les étapes d’installation.

Effectuez les étapes suivantes :
- Sélectionnez **l’onglet Affichage** dans le ruban.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Capture d’écran sélection de l’onglet Affichage pour modifier le jeu de couleurs.":::

- Sélectionnez le schéma de couleur dans la liste déroulante.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Capture d’écran montrant différents jeux de couleurs.":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Définitions des rapports historiques du standard automatique et de la file d’attente d’appels

### <a name="cloud-auto-attendant-analytics"></a>Analyse du standard automatique cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Source d’appel<sup>entrant 1</sup>        |Distribution des appels par source d’appel interne/externe            |
|Méthode de recherche d’annuaire                 |Distribution des appels par type de recherche                              |
|Nombre d’actions de l’appelant                     |Distribution des appels par action de numéro utilisée pendant l’appel       |
|Secondes moyennes dans AA                   |Nombre moyen de secondes passées par les appelants dans l’AA                 |
|Actions moyennes de l’appelant                  |Nombre moyen d’actions effectuées par les appelants dans l’AA               |
|Résultats de l’appel                            |Distribution des appels par état d’appel final                         |
|Section inférieure du rapport                 |Répartition du flux d’appels                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapports     |Nom de la table source            |Filtre global                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|Standard automatique        |fAutoAttendant        |AutoAttendant                |Aucun                                   |

|Section Rapport                                  |Champs utilisés                              |Filtres appliqués     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Sélecteur de dates                                   |AAStartTime                                |Aucun                |
|Sélecteur d’intervalle de temps                             |AAStartHour                                |Aucun                |
|Standard automatique                                  |Nom AA                                    |Aucun                |
|Source d’appel<sup>entrant 1</sup>                |Type d'appel<br>Somme de TotalCallCount (Mesure) |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Méthode de recherche d’annuaire                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod est abs_search_dtmf ou abs_search_name    |
|Nombre d’actions de l’appelant                             |AACallerActionCount<br>TotalCallCount      |Aucun                                                             |
|Secondes moyennes dans AA                           |AAChainDuration (Mesure)                  |Aucun                                                             |
|Actions moyennes de l’appelant                          |AACallerActionCount (Measure)              |Aucun                                                             |
|Résultats de l’appel                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |Aucun                                       |
|Section inférieure du rapport                         |Nom AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Type d'appel<br>MM-DD<br>TotalCallCount |Aucun       |

#### <a name="fautoattendant-cqd-fields-description"></a>Description des champs CQD fAutoAttendant

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nom AA                                 |Texte                     |Nom du compte de ressource attaché au standard automatique<br><br>Si le nom complet du compte de ressource est **aa_test@microsoft.com**, cette valeur est : **aa_test** |
|AACallerActionCount                     |Nombre entier             |Résumer : Somme<br>Nombre d’actions sélectionnées par l’appelant dans le standard automatique pendant l’appel  |
|AACallerActionCount (Measure)          |Nombre entier             |Identique à ce qui précède, sauf s’il n’y a pas d’appels au lieu d’un appel vide                              |
|AACallFlow                              |Texte                     |Encapsule les différents états de l’appel du standard automatique : valeurs possibles :<br><br>§ abs_search<br>§ annonce<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texte                     |Résultat de l’appel final : valeurs possibles :<br><br>§ failed_to_establish_media (la partie média de l’appel n’a pas pu être établie)<br>§ failover_to_operator (appel transféré à l’opérateur généralement en raison d’une erreur système)<br>§ oaa_chain_too_long (trop de jambes dans l’AA)<br>§ oaa_session_too_long (la session AA a duré trop longtemps)<br>§ service_declined (AA n’a pas accepté l’appel)<br>§ service_terminated (la configuration AA déconnecte l’appel ou l’appel raccroché)<br>§ terminated_automatic_selection (la configuration AA déconnecte les appels)<br>§ terminated_no_operator (appel arrêté en raison de l’erreur aucun opérateur défini) <br>§ terminated_transfer_failed (l’appel s’est arrêté car le transfert a échoué , généralement vers un numéro externe)<br>§ transfer_in_progress (transfert AA->AA)<br>§ transferred_to_operator (l’appel a été transféré à l’opérateur - généralement en raison d’une erreur de l’utilisateur)<br>§ transferred_to_receptionist (identique à transferred_to_operator)<br>§ transferred_to_self (l’appel a été retourné au début de l’AA , généralement à partir d’une option d’annonce de menu)<br>§ transferred_to_shared_voicemail (l’appel a été transféré vers la messagerie vocale partagée)<br>§ transferred_to_user (l’appel a été transféré à un utilisateur - inclut les files d’attente d’appels)<br>§ inconnu (une condition inconnue s’est produite)<br>§ user_terminated (appelant raccroché) |
|Légende d’appel AA                          |Texte                     |Configure des éléments de légende basés sur AACallResult                               |
|AAChainDuration                         |Nombre décimal           |Résumer : Somme<br>Durée de l’appel dans le standard automatique                     |
|AAChainDuration (Mesure)               |Nombre décimal           |Identique à ce qui précède, sauf s’il n’y a pas d’appels au lieu d’un appel vide              |
|AAChainIndex                            |Texte                     |                                                                         |
|AAConnectivityType                      |Texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Texte                     |Nombre de standards automatiques impliqués dans l’appel                               |
|AADirectorySearchMethod                 |Texte                     |Méthode de recherche du dernier carnet d’adresses : valeurs possibles :<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |Nombre décimal           |Heure de début de l’appel du standard automatique                                           |
|AAStartTime                             |Date/heure                |Heure de début de l’appel du standard automatique                                           |
|AATransferAction                        |Texte                     |Type de cible de transfert d’appel : valeurs possibles :<br><br>§ application - entité d’application vocale<br>§ external_pstn<br>§ hunt_group - Entité de file d’attente d’appels<br>§ orgaa - Entité Standard automatique<br>§ shared_voicemail<br>§ inconnu<br>§ utilisateur |
|Type d’appel<sup>1</sup>                   |Texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne           |
|IsAAInvolved                            |Texte                     |Toujours 1                                                                 |
|MM-DD                                   |Texte                     |Appel du standard automatique le jour du mois                                            |
|PSTNMinutes                             |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes                                     |
|TotalCallCount                          |Nombre entier             |Résumer : Somme<br>Toujours 1 - utilisé pour fournir la somme de tous les appels            |
|Somme de TotalCallCount (Mesure)         |Nombre entier             |Identique à ce qui précède, sauf s’il n’y a pas d’appels au lieu d’un appel vide              |


### <a name="cloud-call-queue-analytics"></a>Analyse de file d’attente des appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Source d’appel<sup>entrant 1</sup>        |Distribution des appels par source d’appel interne/externe             |
|Temps d’attente moyen (secondes)             |Temps d’attente pour les appels répondus et abandonnés                          |
|Nombre de volumes d’appels et d’acceptation de l’agent      |Distribution des appels par files d’attente d’appels / Nombre maximal d’acceptations de l’agent  |
|Résultats de l’appel                            |Distribution des appels par résultat d’appel                               |
|Appels abandonnés                         |Distribution des appels abandonnés par les files d’attente d’appels                     |
|Longueur moyenne de la session (secondes)        |Longueur de l’appel en secondes regroupée par résultat d’appel                      |
|Destinations de dépassement de capacité/délai d’expiration des appels      |Distribution des appels qui ont expiré ou qui ont dépassé le délai d’attente                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapports                                   |Nom de la table source                               |Filtre global       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|File d’attente d’appels            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |Aucun                |

|Section Rapport                      |Tableau -> champs utilisés                |Filtres appliqués       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de dates                       |fCallQueueAnalytics -> Date           |Aucun                  |
|Sélecteur d’intervalle de temps                 |fCallQueueAnalytics -> CQHour         |Aucun                  |
|Compte de ressource de file d’attente d’appels         |fCallQueueAnalytics -> nom CQ        |Aucun                  |
|Source d’appel entrant<sup>1</sup>    |fCallQueueAnalytics -> somme du nombre d’appels (mesure)<br>fCallQueueAnalytics -> Type d’appel    |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Temps d’attente moyen (secondes)-Avant réponse |fCallQueueFinalStateAction -> Moy de durée moyenne de CQ (mesure) |Le résultat de l’appel de file d’attente d’appels est agent_joined_conference ou transferred_to_agent|
|Temps d’attente moyen (secondes)-Avant abandonné |fCallQueueFinalStateAction -> Moy de durée moyenne d’appel (mesure) |Le résultat de l’appel de file d’attente d’appels n’est pas agent_joined_conference, transferred_to_agent, survolé, timed_out |
|Nombre de volumes d’appels et de Opt-In d’agent   |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Call Queue Agent Opt In Count<br>fCallQueueAnalytics -> nom CQ<br>fCallQueueAnalytics -> Date |Aucun |
|Appels abandonnés                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La légende du résultat de l’appel de file d’attente d’appels est abandonnée |
|Longueur moyenne de la session (secondes)    |fCallQueueFinalStateAction -> durée moyenne de la file d’attente des appels (s)<br>Légende des résultats des appels de file d’attente d’appels |Durée moyenne de la file d’attente d’appels (s) > 0 |
|Destinations de dépassement de capacité/délai d’expiration des appels  |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> type cible de file d’attente d’appels<br>fCallQueue Target Type Legend |La légende du type cible de file d’attente d’appels ne contient pas abandonné et l’agent a répondu |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Description des champs CQD fCallQueueAnalytics

|Nom                                    |Type de données                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                          |
|Nombre d’agents de file d’attente d’appels                  |Nombre entier             |Résumer : Somme<br>Nombre d’agents configurés dans la file d’attente des appels            |
|Nombre d’inscriptions de l’agent de file d’attente d’appels           |Nombre entier             |Résumer : Somme<br>Nombre d’agents ayant choisi d’accéder à la file d’attente d’appels              |
|Résultat de l’appel de file d’attente d’appels                  |Texte                     |État final de l’appel de file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference (appels en mode conférence répondus)<br>§ refusé<br>§ déconnecté<br>§ error<br>§ a échoué<br>§ non valide<br>§ survolé (condition de dépassement remplie)<br>§ timed_out (condition de délai d’expiration remplie)<br>§ transferred_to_agent (appels en mode de transfert répondus {default}) |
|Légende des résultats des appels de file d’attente d’appels           |Texte                     |Configure les éléments de légende en fonction du résultat de la file d’attente d’appels                             |
|Type de cible de file d’attente d’appels                  |Texte                     |***Type cible de redirection d’appel : valeurs possibles :***<br><br>§ ApplicationEndpoint<br>§ Boîte aux lettres<br>§ Autre<br>§ Utilisateur |
|Légende du type cible de file d’attente d’appels           |Texte                     |Configure des éléments de légende basés sur le type cible de file d’attente d’appels                        |
|Type d’appel<sup>1</sup>                   |Texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne             |
|Nom de la CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est la suivante : **cq_test** |
|Heure CQ                                 |Nombre entier             |Heure de début de l’appel de file d’attente d’appels                                                 |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente d’appels (heure)                                 | 
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                     |
|Type de connectivité RTC                  |Texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall     |
|Nombre total de minutes RTC                      |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes pour les appels RTC                       |
|Somme du nombre d’appels (mesure)             |Nombre entier             |Toutefois, le nombre d’appels est identique à 0 lorsqu’aucun appel n’est                          |
|TotalCallCount (Measure)                |Nombre entier             |Résumer : Somme<br>Nombre d’appels                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Description des champs CQD fCallQueueFinalStateAction

|Nom                                    |Type de données                |Description                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durée moyenne de l’appel (secondes)         |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels en secondes pour les appels abandonnés    |
|Durée moyenne de la file d’attente d’appels (s)       |Nombre décimal           |Résumer : Somme<br>Moyenne d’attente en secondes pour les appels répondus           |
|Avg of Average Call Duration (Measure)  |Nombre entier             |Identique à la durée moyenne de l’appel (secondes), toutefois, est égal à 0 lorsqu’aucun appel n’est effectué   |
|Avg of Average CQ Duration (Measure)    |Nombre entier             |Identique à la durée moyenne de la file d’attente d’appels (s). Toutefois, elle est de 0 si aucun appel n’est effectué |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                         |
|Résultat de l’appel de file d’attente d’appels                  |Texte                     |État final de l’appel de file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference (appels en mode conférence répondus)<br>§ refusé<br>§ déconnecté<br>§ error<br>§ a échoué<br>§ non valide<br>§ survolé (condition de dépassement remplie)<br>§ timed_out (condition de délai d’expiration remplie)<br>§ transferred_to_agent (appels en mode de transfert avec réponse {default} |
|Légende des résultats des appels de file d’attente d’appels           |Texte                     |Configure les éléments de légende en fonction du résultat de l’appel de file d’attente d’appels                      |
|Action d’état final de la file d’attente d’appels           |Texte                     |Action finale de la file d’attente des appels : valeurs possibles :<br><br>§ disconnect (appels timed_out)<br>§ disconnect_with_busy (appels survolés)<br>§ failed_to_accept_call<br>§ vers l’avant<br>§ shared_voicemail<br>§ autre<br>§ messagerie vocale                |
|Nom de la CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est la suivante : **cq_test** |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente d’appels (heure)                                 |
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                     |
|IsAbandoned                             |True/false               |True si l’appel n’est pas répondu par un agent                                   |


### <a name="cloud-call-queue-agent-timeline"></a>Chronologie de l’agent de file d’attente d’appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                                          |Description                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|Nombre d’appels par agent                                |Distribution des appels par file d’attente d’appels et agent                |
|Distribution par agent et toutes les files d’attente                     |Distribution des appels par agent et file d’attente d’appels                |
|Tableau (en bas à droite)                                    |Distribution des appels par agent avec la durée moyenne et totale des appels |
|Durée moyenne de l’appel (secondes) par agent                |Durée moyenne (secondes) d’appel par agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapports           |Nom de la table source         |Filtre global       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|Chronologie de l’agent        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |Aucun                |


|Section Rapport                                |Champs utilisés                         |Filtres appliqués       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de dates                                 |Datetime                              |Aucun                  |
|Sélecteur de nom d’utilisateur de l’agent                       |Nom de l’agent                            |Aucun                  |
|Sélecteur de comptes de ressources de file d’attente d’appels          |Nom de la CQ                               |Aucun                  |
|Nombre d’appels par agent                      |Nom de l’agent<br>Nombre d’appels<br>Hour      |Aucun                  |
|Distribution par agent et file d’attente d’appels          |Nom de l’agent<br>Durée moyenne des appels (secondes)<br>Nombre d’appels<br>Nom de la CQ |Aucun                      |
|Bas à gauche                                   |Nom de l’agent<br>Durée moyenne de l’appel (secondes)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom de la CQ<br>Hour<br>MM-DD | Aucun |
|Durée moyenne de l’appel (secondes) par agent      |Nom de l’agent<br>Durée moyenne de l’appel (secondes) | Aucun |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Description des champs CQD fAgentTimelineAnalytics

|Nom                                    |Type de données                |Description                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nom de l’agent                              |Texte                     |UPN utilisateur<br>Si le nom d’utilisateur complet est **user@microsoft.com**, cette valeur est : **utilisateur** |
|Durée moyenne de l’appel (secondes)         |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels de file d’attente d’appels répondus en secondes |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d’appels répondus par l’agent     |
|Durée de l’appel (minutes)                 |Nombre entier             |Résumer : Somme<br>Durée totale des appels de file d’attente d’appels répondus en minutes (arrondi à la minute la plus proche)  |
|Nom de la CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est la suivante : **cq_test** |
|Date                                    |Date                     |Date d’appel                                             |
|Datetime                                |Datetime                 |Date d’appel                                             |
|Hour                                    |Nombre entier             |Heure d’appel                                             |
|MM-DD                                   |Texte                     |Mois et jour d’appel                                    |


> [!NOTE]
> Lorsqu’un appel arrive à la première file d’attente d’appels, si le nombre d’appels déjà en attente dans cette file d’attente a atteint la limite de **gestion du dépassement** de capacité des appels et si l’option de redirection envoie de nouveaux appels à une deuxième file d’attente d’appels, les agents de la deuxième file d’attente d’appels apparaissent comme étant dans la première file d’attente d’appels de ce rapport. 

## <a name="known-issues"></a>Problèmes connus

- La file d’attente des appels et les standards automatiques sont affichés par l’ID du compte de ressource au lieu des noms de file d’attente d’appels/standard automatique.  Pour afficher tout le trafic d’un standard automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources affectés au standard automatique ou à la file d’attente d’appels.

- Seuls 28 jours d’historique sont disponibles dans le tableau de bord, car les données de file d’attente d’appels/standard automatique sont considérées comme des données personnelles et sont soumises à des stratégies de rétention de la confidentialité des données.

- Dans certains scénarios, le nombre d’appels répondus par l’agent dans le rapport chronologie de l’agent de file d’attente d’appels cloud peut être différent du nombre d’appels indiqué dans l’historique des appels du client Teams. L’historique des appels du client Teams est correct. Le support est en cours d’examen, mais il n’y a pas de temps estimé pour la réparation disponible pour l’instant.

- <sup>1</sup> **La source d’appel entrante** dans le standard automatique et les graphiques de file d’attente des appels indiquent la source de la jambe d’appel finale plutôt que la source de la jambe d’appel initiale. Par exemple, si un standard automatique reçoit un appel externe et transfère l’appel à un autre standard automatique ou file d’attente d’appels, la **source d’appel entrante** est signalée comme interne.

## <a name="version-history"></a>Historique des versions
|Version  |Date de publication     |Fichier                                                           |Description                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.63     |24 août 2022    |Standard automatique CQD Teams & rapport historique de file d’attente d’appels V1.63.pbit |Reportez-vous à :<br>Standard automatique CQD Teams & rapports historiques de file d’attente d’appels - Modifier Log.docx dans le fichier zip téléchargé pour obtenir la liste des modifications                                                                             |
|1.60     |22 juillet 2022      |Standard automatique CQD Teams & rapport historique de file d’attente d’appels V1.60.pbit |Reportez-vous à :<br>Standard automatique CQD Teams & rapports historiques de file d’attente d’appels - Modifier Log.docx dans le fichier zip téléchargé pour obtenir la liste des modifications                                                                             |
|1.00     |5 novembre 2020   |CQ et AA combined Analytics 20201105.pbit                         |Version initiale                                     |



