---
title: Rapport d’historique de la file d’attente d’appels & standard automatique
author: CarolynRowe
ms.author: crowe
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
description: Découvrez comment utiliser le tableau de bord qualité des appels Power BI rapport pour afficher les données historiques du standard automatique et de la file d’attente des appels.
ms.openlocfilehash: 57552af3a1df108dbbf86172793bb9ea86ed1b10
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2022
ms.locfileid: "63711488"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Rapport d’historique de la file d’attente d’appels & standard automatique

Le Teams standard automatique & modèle de rapport historique de file d’attente d’appels Power BI fournit les trois rapports suivants :

- [Standard automatique](media/cqd-teams-aa-cq-historical-report-sample-aa.png) : affichage de l’analytique des appels entrants dans vos standards automatiques.
- [File d’attente d’appels](media/cqd-teams-aa-cq-historical-report-sample-cq.png) : analyse des appels entrant dans vos files d’attente d’appels.
- [Chronologie de l’agent](media/cqd-teams-aa-cq-historical-report-sample-at.png) : affichage de la chronologie des agents actifs dans les appels de file d’attente d’appels.

Ces rapports utilisent les données du magasin de données [Tableau de bord qualité des appels](CQD-Power-BI-query-templates.md) . Les rapports permettent aux organisations de signaler le nombre d’appels traités par les standards automatiques et les files d’attente d’appels.  Les rapports fournissent également des insights sur les performances de l’agent dans les files d’attente d’appels.

## <a name="prerequisites"></a>Conditions préalables

### <a name="power-bi-desktop"></a>Power BI Desktop
Vous devez avoir installé Power BI Desktop. Vous pouvez l’installer à partir du [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Vous pouvez utiliser la version gratuite de Power BI Desktop. La version minimale compatible est 2.85.681.0 (septembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline CQD

Le compte que vous utilisez pour afficher le rapport d’historique doit disposer d’autorisations pour accéder au pipeline de données CQD. Pour plus d’informations, consultez [le rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

## <a name="installation"></a>Installation 

Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur l’ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données CQD.

Effectuez les étapes suivantes :

- Téléchargez les [modèles de requête CQD Power BI](https://www.microsoft.com/download/details.aspx?id=102291) et enregistrez le fichier zip dans un répertoire sur votre ordinateur.

- Double-cliquez sur le fichier zip pour l’ouvrir.

- Double-cliquez sur le fichier de modèle « CQ and AA combined Analytics 20201105.pbit ». Le Power BI Desktop doit être lancé.

- Vous êtes invité à sélectionner la région de pipeline de données CQD. Sélectionnez la région où se trouve votre locataire.

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

- Vous serez alors invité à vous connecter. Sélectionnez **Compte d’organisation** , puis **Connectez-vous**.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Capture d’écran montrant la connexion.":::

- Sélectionnez **Connecter** et observez l’actualisation des données.

## <a name="data-latency-and-aa--cq-analytics"></a>Latence des données et analytique AA & CQ

Les données seront disponibles dans le pipeline de données CQD dans un délai de 30 minutes.

Vous devrez actualiser les données pour voir les nouvelles données analytiques. 

## <a name="customization"></a>Personnalisation 

Vous pouvez personnaliser certains aspects de visualisation des rapports, tels que l’ajout ou la suppression de champs à afficher dans les différentes visualisations, la modification du type de graphique, etc.

Vous ne pouvez pas ajouter de champs de données supplémentaires au rapport.

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
|Source d’appel <sup>entrant1</sup>        |Distribution des appels par source d’appel interne/externe             |
|Totaux de la méthode de recherche d’annuaire          |Distribution des appels par type de recherche                               |
|Action de l’appelant                           |Distribution des appels par récepteur d’appels                             |
|Résultat de l’appel                             |Distribution des appels par état d’appel final                          |
|Nombre d’actions de l’appelant                     |Distribution des appels par action de numéro utilisée pendant l’appel        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport            |Nom de la table de rapports     |Filtre global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Standard automatique        |fAutoAttendant        |AAStartTime se situe dans les 28 derniers jours |


|Nom de la table de rapports            |Nom de la table source            |Traitement       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Lignes filtrées » = Table.SelectRows(Source, each true), <br>#"Standard automatique » = Table.AddColumn(#"Lignes filtrées », « Nom AA », chaque List.First(Text.Split([AAIdentity], « @ »))), <br>#"Changed Type » = Table.TransformColumnTypes(#"Auto Attendant »,{{"AAStartTime », type datetime}}), <br>#"Colonnes supprimées » = Table.RemoveColumns(#"Type modifié »,{"AAIdentity"}) |


|Section Rapport                                  |Champs utilisés                              |Filtres appliqués     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Sélecteur de dates                                   |AAStartTime                                |Aucun                |
|Standard automatique                                  |Nom AA                                    |Aucun                |
|Source d’appel <sup>entrant1</sup>                |Type d'appel<br>TotalCallCount                |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Totaux de la méthode de recherche d’annuaire                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod est abs_search_dtmf ou abs_search_name    |
|Actions de l’appelant                                  |AATransferAction<br>TotalCallCount         |Aucun                                                             |
|Secondes moyennes dans AA<br>Actions moyennes de l’appelant |AAChainDuration<br>AACallerActionCount     |Aucun                                                             |
|Résultats des appels                                    |AACallResult<br>TotalCallCount             |Aucun                                                             |
|Nombre d’actions de l’appelant                            |AACallerActionCount<br>TotalCallCount      |Aucun                                                             |
|Section inférieure du rapport                         |Nom AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Type d'appel<br>TotalCallCount |Aucun                |

#### <a name="fautoattendant-cqd-fields-description"></a>Description des champs CQD fAutoAttendant

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nom AA                                 |Texte                     |Nom du compte de ressource attaché au standard automatique<br><br>Si le nom complet du compte de ressource est **aa_test@microsoft.com** cette valeur est : **aa_test** |
|AACallerActionCount                     |Nombre entier             |Résumer : Somme<br>Nombre d’actions sélectionnées par l’appelant dans le standard automatique pendant l’appel  |
|AACallFlow                              |Texte                     |Encapsule les différents états de l’appel du standard automatique : valeurs possibles :<br><br>§ abs_search<br>§ annonce<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |Texte                     |Résultat de l’appel final : valeurs possibles :<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ inconnu<br>§ user_terminated |
|AAChainDuration                         |Nombre décimal           |Résumer : Somme<br>Durée de l’appel dans le standard automatique                     |
|AAChainIndex                            |Texte                     |                                                                         |
|AAConnectivityType                      |Texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |Texte                     |Nombre de standards automatiques impliqués dans l’appel                               |
|AADirectorySearchMethod                 |Texte                     |Méthode de recherche du dernier carnet d’adresses : valeurs possibles :<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |Date/heure                |Heure de début de l’appel du standard automatique                                           |
|AATransferAction                        |Texte                     |Type de cible de transfert d’appel : valeurs possibles :<br><br>***§ application - entité** _<br>d’application vocale§ external_pstn<br>_*_§ hunt_group - Entité de file d’attente d’appels_*_<br>_*_§ orgaa - Entité de standard automatique de l’organisation_**<br>§ shared_voicemail<br>§ inconnu<br>§ utilisateur |
|Type <sup>d’appel1</sup>                   |Texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne         |
|IsAAInvolved                            |Texte                     |Toujours 1                                                                 |
|PSTNMinutes                             |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes                                     |
|TotalCallCount                          |Nombre entier             |Résumer : Somme<br>Toujours 1 - utilisé pour fournir la somme de tous les appels            |


### <a name="cloud-call-queue-analytics"></a>Analyse de file d’attente des appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Source d’appel <sup>entrant1</sup>        |Distribution de l’appel par source d’appel interne/externe              |
|Volume d’appels                             |Distribution des appels par files d’attente d’appels                                |
|Résultat de l’appelant                           |Distribution de l’appel par résultat d’appel                                |
|Timeout/Overflow call total action      |Distribution de l’appel NON transféré (abandonné) par résultat d’appel       |
|Totaux des cibles de transfert/transfert          |Distribution de l’appel transféré par résultat d’appel                      |
|Taux d’appels abandonnés                   |Rapport entre le nombre d’appels réussis et les appels abandonnés                        |
|Longueur moyenne de la session (secondes)        |Longueur des appels en secondes regroupées par appels abandonnés/réussis       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport         |Noms des tables de rapports                                                          |Filtre global |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|File d’attente d’appels         |Dates<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Aucun          |
 
|Nom de la table de rapports            |Nom de la table source            |Traitement       |
|:----------------------------|:----------------------------|:----------------|
|Dates                        |Dates                        |Aucun             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns » = Table.RemoveColumns(Source,{"Call Count », « Call Queue Call Result », « Date », « PSTN Connectivity Type », « Call Queue Target Type », « PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Colonnes supprimées ») |
|fCallQueueAnalytics          |CallQueueAnalytics           |Aucun             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Aucun             |

|Section Rapport                      |Tableau -> champs utilisés                |Filtres appliqués       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de dates                       |Dates -> DateTime                     |Aucun                  |
|Identité de file d’attente d’appels                 |dCQ-CQIdentity ->'identité de file d’attente d’appels |Aucun                  |
|Source d’appel <sup>entrant1</sup>    |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Type d’appel    |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Temps d’attente moyen                    |fCallQueueFinalStateAction -> durée moyenne d’appel (secondes) |Avant le transfert : le résultat de l’appel de file d’attente d’appels est agent_joined_conference ou transferred_to_agent<br>Avant raccrocher : le résultat de l’appel de file d’attente d’appels n’est pas agent_joined_conference ou transferred_to_agent |
|Résultat de l’appel                         |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Call Queue Call Call Result | Aucun |
|Timeout/Overflow appelle l’action totale |fCallQueueFinalStateAction -> Nombre d’appels<br>fCallQueueFinalStateAction -> Action d’état final de la file d’attente d’appels |L’action d’état final de la file d’attente d’appels n’est pas transférée |
|Totaux cibles de transfert/forard       |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> type cible de file d’attente d’appels |Aucun |
|Volumes d’appels                        |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Call Queue Identify<br>fCallQueueAnalytics -> Date |Aucun |
|Appels abandonnés                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned a la valeur True |
|Longueur moyenne de la session (secondes)    |fCallQueueFinalStateAction -> durée moyenne de l’appel<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Aucun |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>description des champs CQD dCQ-CQIdenity

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identité de file d’attente d’appels                     |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com** cette valeur est : **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>Description des champs CQD fCallQueueAnalytics

|Nom                                    |Type de données                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                          |
|Résultat de l’appel de file d’attente d’appels                  |Texte                     |État final de l’appel de file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference<br>§ refusé<br>§ déconnecté<br>§ error<br>§ a échoué<br>§ non valide<br>§ survolé<br>§ timed_out<br>§ transferred_to_agent |
|Identité de file d’attente d’appels                     |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com** cette valeur est : **cq_test** |
|Type de cible de file d’attente d’appels                  |Texte                     |***Type cible de redirection d’appel : valeurs possibles :***<br><br>§ ApplicationEndpoint<br>§ Boîte aux lettres<br>§ Autre<br>§ Utilisateur |
|Type <sup>d’appel1</sup>                   |Texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne           |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente d’appels (heure) (UTC)                           | 
|IsAbandoned                             |True/false               |True si l’appel n’est pas répondu par un agent                                   |
|Type de connectivité RTC                  |Texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall   |
|Nombre total de minutes RTC                      |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes pour les appels RTC                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics measures description

|Nom                                    |Type de données                |Description                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% d’appels abandonnés***                 |Pourcentage               |Mesure : Nombre d’appels abandonnés / Nombre total d’appels    |
|Nombre total d’appels                             |Nombre entier             |Mesure : Somme des appels répondus à l’agent        |
|TotalCallCount                          |Nombre entier             |Mesure : Sum(Call Count)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>Description des champs CQD fCallQueueFinalStateAction

|Nom                                    |Type de données                |Description                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durée moyenne de l’appel (secondes)         |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels en secondes |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                  |
|Résultat de l’appel de file d’attente d’appels                  |Texte                     |État final de l’appel de file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference<br>§ refusé<br>§ déconnecté<br>§ error<br>§ a échoué<br>§ non valide<br>§ survolé<br>§ timed_out<br>§ transferred_to_agent |
|Action d’état final de la file d’attente d’appels           |Texte                     |Action finale de la file d’attente des appels : valeurs possibles :<br><br>§ disconnect (appels timed_out)<br>§ disconnect_with_busy (appels survolés)<br>§ failed_to_accept_call<br>§ vers l’avant<br>§ shared_voicemail<br>§ autre<br>§ messagerie vocale |
|Identité de file d’attente d’appels                     |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com** cette valeur est : **cq_test** |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente d’appels (heure) (UTC)   |
|IsAbandoned                             |True/false               |True si l’appel n’est pas répondu par un agent           |


### <a name="cloud-call-queue-agent-timeline"></a>Chronologie de l’agent de file d’attente d’appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                                          |Description                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# appels par agent                                        |Distribution des appels par file d’attente d’appels et agent                 |
|Durée totale des appels (secondes) par agent et file d’attente d’appels   |Durée totale (secondes) d’appel par agent et file d’attente d’appels     |
|Durée moyenne des appels (secondes) par nom d’agent           |Durée moyenne (secondes) d’appel par agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport au mappage de table et de champ CQD

|Onglet Rapport         |Noms des tables de rapports        |Filtre global |
|:------------------|:-------------------------|:-------------|
|Chronologie de l’agent     |fAgentTimelineAnalytics   |Aucun          |
 
|Nom de la table de rapports            |Nom de la table source            |Traitement       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type » = Table.TransformColumnTypes(Source,{{"Call Count », Int64.Type}, {"Call Duration (Minute) », Int64.Type}, {"Average Call Duration (Second) », type number}, {"Date », type date}})|

|Section Rapport                                |Champs utilisés                         |Filtres appliqués       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nom de l’agent                                    |Nom de l’agent                            |Aucun                  |
|Nom de la file d’attente d’appels                               |Nom de la file d’attente d’appels                       |Aucun                  |
|#Calls par agent                               |Nom de l’agent<br>Nombre d’appels<br>Date      |Aucun                  |
|Distribution par agent et file d’attente d’appels          |Nom de l’agent<br>Nombre d’appels<br>Durée de l’appel (minutes)<br>Nom de la file d’attente d’appels |Aucun                      |
|Bas à gauche                                   |Nom de l’agent<br>Durée moyenne de l’appel (deuxième)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom de la file d’attente d’appels | Aucun |
|Durée moyenne de l’appel (secondes) par nom d’agent |Nom de l’agent<br>Durée moyenne de l’appel (deuxième)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom de la file d’attente d’appels | Aucun |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>Description des champs CQD fAgentTimelineAnalytics

|Nom                                    |Type de données                |Description                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nom de l’agent                              |Texte                     |UPN utilisateur<br>Si le nom d’utilisateur complet est **user@microsoft.com** cette valeur est : **utilisateur** |
|Durée moyenne de l’appel (deuxième)          |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels de file d’attente d’appels répondus en secondes |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d’appels présentés et répondus par l’agent     |
|Durée de l’appel (minute)                  |Nombre entier             |Résumer : Somme<br>Durée totale des appels de file d’attente d’appels répondus en minutes (arrondi à la minute la plus proche)  |
|Nom de la file d’attente d’appels                         |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com** cette valeur est : **cq_test** |
|Date                                    |Date                     |                                                    |


> [!NOTE]
> 1) Ce rapport affiche le nombre d’appels du point de vue des agents. Par conséquent, le nombre total d’appels sur ce rapport est généralement supérieur au nombre total d’appels sur le rapport Analyse de file **d’attente** des appels cloud. Chaque appel dans la file d’attente peut être présenté à un ou plusieurs agents au moins une fois avant d’être répondu. Chaque appel de file d’attente d’appels présenté à un agent est comptabilisé dans ce rapport, même s’il n’a pas été répondu par l’agent. La différence entre les nombres d’appels entre ces deux rapports est plus marquée avec l’option de **routage attendant** qui sonne chaque agent pour chaque appel. 
> 2) Lorsqu’un appel arrive pour la première fois à la première file d’attente d’appels, si le nombre d’appels déjà en attente dans cette file d’attente dépasse la limite de **gestion du dépassement** de capacité d’appel et si l’option de redirection envoie des appels à une deuxième file d’attente d’appels, les agents de la deuxième file d’attente d’appels apparaissent comme étant dans la première file d’attente d’appels de ce rapport. 

## <a name="known-issues"></a>Problèmes connus

- La file d’attente des appels et les standards automatiques sont affichés par l’ID du compte de ressource au lieu des noms de file d’attente d’appels/standard automatique.  Pour afficher tout le trafic d’un standard automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources affectés au standard automatique ou à la file d’attente d’appels.

- Seuls 28 jours d’historique sont disponibles dans le tableau de bord, car les données de file d’attente d’appels/standard automatique sont considérées comme des données personnelles et sont soumises à des stratégies de rétention de la confidentialité des données.

- Dans certains scénarios, le nombre d’appels répondus par l’agent dans le rapport chronologie de l’agent de file d’attente d’appels cloud peut être différent du nombre d’appels indiqué dans l’historique des appels client Teams. L’historique des appels du client Teams est correct. Le support est en cours d’examen, mais il n’y a pas de temps estimé pour la réparation disponible pour l’instant.

- <sup>1</sup> **La source d’appel entrante** dans le standard automatique et les graphiques de file d’attente des appels indiquent la source de la jambe d’appel finale plutôt que la source de la jambe d’appel initiale. Par exemple, si un standard automatique reçoit un appel externe et transfère l’appel à un autre standard automatique ou file d’attente d’appels, la **source d’appel entrante** est signalée comme interne.
