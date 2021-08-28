---
title: Standard automatique & historique de la file d’attente d’appels
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment utiliser le tableau de bord de qualité des appels Power BI rapport pour afficher les données historiques Standard automatique de la file d’attente d’appels.
ms.openlocfilehash: cd32c732162c15cdaf4cfeac4c83cb53ebd5fe10
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598618"
---
# <a name="auto-attendant--call-queue-historical-report"></a>Standard automatique & historique de la file d’attente d’appels

Le tableau de Teams Standard automatique & de la file d Power BI d’appels fournit les trois rapports suivants :

- [Standard automatique](media/cqd-teams-aa-cq-historical-report-sample-aa.png) pour afficher les données d’analyse des appels qui arrivent dans vos attendants automatiques.
- [File d’attente](media/cqd-teams-aa-cq-historical-report-sample-cq.png) d’appels affichant les données d’analyse des appels qui arrivent dans vos files d’attente.
- [Chronologie de l’agent](media/cqd-teams-aa-cq-historical-report-sample-at.png) : affichage chronologique des agents actifs dans les appels de la file d’attente d’appels.

Ces rapports utilisent des données du magasin de données Du tableau de [bord](CQD-Power-BI-query-templates.md) de qualité des appels. Ils permettent aux organisations de signaler le nombre d’appels en cours de traitement par les travailleurs automatiques et les files d’attente d’appels.  Ils fournissent également des informations sur les performances de l’agent dans les files d’attente d’appels.

## <a name="prerequisites"></a>Conditions préalables

### <a name="power-bi-desktop"></a>Power BI Desktop
Vous devez avoir installé Power BI Desktop installées. Vous pouvez l’installer à partir du [Microsoft Windows Store.](https://aka.ms/pbidesktopstore)

Vous pouvez utiliser la version gratuite de Power BI Desktop. La version minimale compatible est la version 2.85.681.0 (septembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline du DQD

Le compte que vous utilisez pour afficher le rapport historique & données de LQ Analytics doit être autorisé à accéder au pipeline de données du CQD. Pour plus d’informations, [voir le rôle Accès du CQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installation 

Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur l’ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données du tableau de bord de qualité des données.

Effectuez les étapes suivantes :

- Téléchargez [le fichier de Power BI modèles](https://www.microsoft.com/download/details.aspx?id=102291) de requête et enregistrez le fichier zip dans un répertoire sur votre ordinateur.

- Double-cliquez sur le fichier zip pour l’ouvrir.

- Double-cliquez sur le fichier de modèle « CQ et AA combined Analytics 20201105.pbit » et Power BI Desktop le lancer.

- Vous serez invité à sélectionner la région du pipeline de données du CQD. Sélectionnez la région dans laquelle se trouve votre client.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Capture d’écran de la sélection de la région du pipeline de données du CQD":::

- La région dans laquelle se trouve votre client peut être obtenue à l’aide de l’cmdlet [Get-CsTenant.](/powershell/module/skype/get-cstenant)

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - La région s’affichera après la zone comme dans l’exemple ci-dessus où se trouve **/** la région : noam

 - Le rapport s’lance avec des exemples de données.
 
 - Pour consulter vos propres données, sélectionnez **Actualiser** sous l’onglet Accueil sous Requêtes Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Capture d’écran de la sélection de l’option d’actualisation":::

- Vous serez alors invité à vous connectez. Sélectionnez **le compte de** l’organisation, puis **connectez-vous.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Capture d’écran montrant la connexion":::

- Sélectionnez **Connecter** et regardez les données s’actualiser.

## <a name="data-latency-and-aa--cq-analytics"></a>Latence des données et analyse du & de qualité des données

Les données seront disponibles dans le pipeline de données du DQD dans les 30 minutes.

Vous devez actualiser les données pour voir les nouvelles données d’analyse. 

## <a name="customization"></a>Personnalisation 

Vous pouvez personnaliser certains aspects de visualisation des rapports, comme l’ajout ou la suppression de champs à visualiser dans les différentes visualisations, la modification du type de graphique, etc.

Vous ne pouvez pas ajouter de champs de données supplémentaires au rapport.

### <a name="change-color-schema"></a>Modifier le schéma de couleurs 

Les étapes suivantes supposent que vous avez déjà effectué les étapes d’installation.

Effectuez les étapes suivantes :
- Sélectionnez **l’onglet** Affichage du ruban.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Capture d’écran de la sélection de l’onglet Affichage pour modifier le modèle de couleurs":::

- Sélectionnez le schéma de couleurs dans la liste drop-down.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Capture d’écran montrant différents modèles de couleurs":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Standard automatique définitions des rapports historiques de la file d’attente d’appels

### <a name="cloud-auto-attendant-analytics"></a>Cloud Standard automatique Analytics

#### <a name="report-description"></a>Description du rapport

|Section État                          |Description                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Source d’appel entrant<sup>1</sup>        |Distribution des appels par source d’appel interne/externe             |
|Totaux des méthodes de recherche dans l’annuaire          |Distribution des appels par type de recherche                               |
|Action de l’appelant                           |Distribution des appels par destinataire d’appel                             |
|Résultat de l’appel                             |Distribution des appels par état d’appel final                          |
|Nombre d’actions de l’appelant                     |Distribution des appels par action de numéro utilisée pendant l’appel        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport sur la table et le mappage de champs du tableau de table des champs du tableau de recherche

|Onglet Rapport            |Nom de la table du rapport     |Filtre global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Standard automatique        |fAutoAttendant        |AAStartTime est au cours des 28 derniers jours |


|Nom de la table du rapport            |Nom de la table source            |Traitement       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Filtered Rows » = Table.SelectRows(Source, each true), <br>#"Standard automatique » = Table.AddColumn(#"Filtered Rows », « AA Name », each List.First(Text.Split([AAIdentity], « @ »))), <br>#"Changed Type » = Table.TransformColumnTypes(#"Standard automatique »,{{"AAStartTime », type datetime}}), <br>#"Removed Columns » = Table.RemoveColumns(#"Changed Type »,{"AAIdentity"}) |


|Section État                                  |Champ(s) utilisé(s)                              |Filtres appliqués     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|Sélecteur de dates                                   |AAStartTime                                |Aucun                |
|Standard automatique                                  |Nom AA                                    |Aucun                |
|Source d’appel entrant<sup>1</sup>                |Type d'appel<br>TotalCallCount                |Appels externes : Le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Totaux des méthodes de recherche dans l’annuaire                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod est abs_search_dtmf ou abs_search_name    |
|Actions de l’appelant                                  |AATransferAction<br>TotalCallCount         |Aucun                                                             |
|Moyenne de secondes dans AA<br>Actions moyennes de l’appelant |AAChainDuration<br>AACallerActionCount     |Aucun                                                             |
|Résultats des appels                                    |AACallResult<br>TotalCallCount             |Aucun                                                             |
|Nombre d’actions de l’appelant                            |AACallerActionCount<br>TotalCallCount      |Aucun                                                             |
|Section inférieure de l’état                         |Nom AA<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>Type d'appel<br>TotalCallCount |Aucun                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD fields description

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nom AA                                 |texte                     |Nom du compte de ressource joint à Standard automatique<br><br>Si le nom complet du compte de **ressource aa_test@microsoft.com** alors cette valeur est : **aa_test** |
|AACallerActionCount                     |nombre entier             |Résumer : Somme<br>Nombre d’actions sélectionnées par l’appelant dans Standard automatique’appel  |
|AACallFlow                              |texte                     |Encapsule les différents états d’un Standard automatique appel (valeurs possibles) :<br><br>§ abs_search<br>§ annonce<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |texte                     |Résultat de l’appel final - valeurs possibles :<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ inconnu<br>§ user_terminated |
|AAChainDuration                         |nombre décimal           |Résumer : Somme<br>Durée de l’appel dans Standard automatique                     |
|AAChainIndex                            |texte                     |                                                                         |
|AAConnectivityType                      |texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |texte                     |Nombre de attendants automatiques impliqués dans un appel                               |
|AADirectorySearchMethod                 |texte                     |Méthode de recherche du dernier carnet d’adresses : valeurs possibles :<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |date/heure                |Standard automatique l’heure de début de l’appel                                           |
|AATransferAction                        |texte                     |Type cible de transfert d’appel : valeurs possibles :<br><br>***application § - entité d’application** vocale _<br> § external_pstn <br>_§ hunt_group - Entité *_entity_* _<br>_ * _§ orgaa - Organizational Standard automatique entity_**<br>§ shared_voicemail<br>§ inconnu<br>utilisateur de § |
|Type<sup>d’appel 1</sup>                   |texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne         |
|IsAAInvolved                            |texte                     |Toujours 1                                                                 |
|PSTNMinutes                             |nombre entier             |Résumer : Somme<br>Utilisation totale des minutes                                     |
|TotalCallCount                          |nombre entier             |Résumer : Somme<br>Toujours 1 - utilisé pour fournir la somme de tous les appels            |


### <a name="cloud-call-queue-analytics"></a>Analyse de la file d’attente d’appels dans le cloud

#### <a name="report-description"></a>Description du rapport

|Section État                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Source d’appel entrant<sup>1</sup>        |Distribution de l’appel par source d’appel interne/externe              |
|Volume d’appels                             |Distribution des appels par files d’attente d’appels                                |
|Résultat de l’appelant                           |Distribution de l’appel par résultat d’appel                                |
|Action du total des appels en dépassement de délai/dépassement de capacité      |Distribution de NON-forwardé(abandonné) appel par résultat d’appel       |
|Total cible de transfert/transfert          |Distribution de l’appel transmis par résultat d’appel                      |
|Taux d’appels abandonnés                   |Ratio du nombre d’appels réussis à l’abandon                        |
|Durée moyenne de la session (secondes)        |Durée des appels en secondes groupées par appels abandonnés/réussis       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport sur la table et le mappage de champs du tableau de table des champs du tableau de recherche

|Onglet Rapport         |Noms de tables de rapports                                                          |Filtre global |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|File d’attente d’appels         |Dates<br>dCQ-CQ Qu’est-ce que c’est ?<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |Aucun          |
 
|Nom de la table du rapport            |Nom de la table source            |Traitement       |
|:----------------------------|:----------------------------|:----------------|
|Dates                        |Dates                        |Aucun             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns » = Table.RemoveColumns(Source,{"Call Count », « Call Queue Call Result », « Date », « PSTN Connectivity Type », « Call Queue Target Type », « PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Colonnes supprimées ») |
|fCallQueueAnalytics          |CallQueueAnalytics           |Aucun             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |Aucun             |

|Section État                      |Table ->(s) utilisée(s)                |Filtres appliqués       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de dates                       |Dates -> DateTime                     |Aucun                  |
|Identité de la file d’attente d’appels                 |dCQ-CQIdentity -> Call Queue Identity |Aucun                  |
|Source d’appel entrant<sup>1</sup>    |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Type    |Appels externes : Le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Avg Waiting Time                    |fCallQueueFinalStateAction -> Durée moyenne des appels (secondes) |Avant transfert : le résultat des appels de la file d’attente agent_joined_conference ou transferred_to_agent<br>Avant de raccrocher : le résultat des appels de la file d’attente n’est agent_joined_conference ou transferred_to_agent |
|Résultat de l’appel                         |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> d’appel dans la file d’attente | Aucun |
|Action totale des appels de dépassement de délai d’dépassement de capacité |fCallQueueFinalStateAction -> Call Count<br>fCallQueueFinalStateAction -> File d’attente d’appels Final State Action |L’action d’état final de la file d’attente d’appels n’est pas en avance |
|Totaux cibles des transferts/forards       |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Type de cible de la file d’attente d’appels |Aucun |
|Volumes d’appel                        |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Identification de la file d’attente d’appels<br>fCallQueueAnalytics -> Date |Aucun |
|Appels abandonnés                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned est True |
|Durée moyenne de la session (secondes)    |fCallQueueFinalStateAction -> Durée moyenne des appels<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |Aucun |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>Description des champs CQD dCQ-CQ Qu’est-ce que c’est ?

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Identité de la file d’attente d’appels                     |texte                     |Nom du compte de ressource joint à la file d’attente d’appels<br><br>Si le nom complet du compte de **ressource cq_test@microsoft.com** alors cette valeur est **: cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD fields description

|Nom                                    |Type de données                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Nombre d’appels                              |nombre entier             |Résumer : Somme<br>Nombre d'appels                                          |
|Résultat des appels de la file d’attente d’appels                  |texte                     |État final de l’appel de la file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference<br>§ refusé<br>§ déconnecté<br>§ erreur<br>§ a échoué<br>§ non valide<br>§ au-dessus<br>§ timed_out<br>§ transferred_to_agent |
|Identité de la file d’attente d’appels                     |texte                     |Nom du compte de ressource joint à la file d’attente d’appels<br><br>Si le nom complet du compte de **ressource cq_test@microsoft.com** alors cette valeur est **: cq_test** |
|Type cible de la file d’attente d’appels                  |texte                     |***Type cible de redirection d’appel : valeurs possibles :***<br><br>§ ApplicationEndpoint<br>§ Boîte aux lettres<br>§ Autre<br>§ Utilisateur |
|Type<sup>d’appel 1</sup>                   |texte                     |Type d’appel : valeurs possibles :<br><br>§ Externe<br>§ Interne           |
|Date                                    |date/heure                |Date et heure de début des appels en file d’attente (heure) (UTC)                           | 
|IsAbandoned                             |true/false               |Vrai si l’appel n’a pas reçu de réponse d’un agent                                   |
|Type de connectivité PSTN                  |texte                     |Type d’appel : valeurs possibles :<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN Total Minutes                      |nombre entier             |Résumer : Somme<br>Utilisation totale des minutes pour les appels PSTN                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics measures description

|Nom                                    |Type de données                |Description                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***% appels abandonnés***                 |pourcentage               |Mesure : TotalCallCount / Total Calls<br>Ratio du nombre d’appels réussis à l’abandon    |
|Nombre total d’appels                             |nombre entier             |Mesure : l’agent somme a répondu à des appels        |
|TotalCallCount                          |nombre entier             |Mesure : Somme(Nombre d’appels)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD description des champs

|Nom                                    |Type de données                |Description                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|Durée moyenne de l’appel (secondes)         |nombre décimal           |Résumer : Somme<br>Durée moyenne de l’appel en secondes |
|Nombre d’appels                              |nombre entier             |Résumer : Somme<br>Nombre d'appels                  |
|Résultat des appels de la file d’attente d’appels                  |texte                     |État final de l’appel de la file d’attente d’appels : valeurs possibles :<br><br>§ agent_joined_conference<br>§ refusé<br>§ déconnecté<br>§ erreur<br>§ a échoué<br>§ non valide<br>§ au-dessus<br>§ timed_out<br>§ transferred_to_agent |
|Action d’état final de la file d’attente d’appels           |texte                     |Action finale de la file d’attente d’appels - valeurs possibles :<br><br>§ déconnecter<br>§ disconnect_with_busy<br>§ failed_to_accept_call<br>§ avancer<br>§ shared_voicemail<br>§ autre<br>§ messagerie vocale |
|Identité de la file d’attente d’appels                     |texte                     |Nom du compte de ressource joint à la file d’attente d’appels<br><br>Si le nom complet du compte de **ressource cq_test@microsoft.com** alors cette valeur est **: cq_test** |
|Date                                    |date/heure                |Date et heure de début des appels en file d’attente (heure) (UTC)   |
|IsAbandoned                             |true/false               |Vrai si l’appel n’a pas reçu de réponse d’un agent           |


### <a name="cloud-call-queue-agent-timeline"></a>Chronologie de l’agent de file d’attente d’appels cloud

#### <a name="report-description"></a>Description du rapport

|Section État                                          |Description                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# appels par l’agent                                        |Distribution de l’appel par file d’attente d’appels et par agent                 |
|Durée totale des appels (secondes) par l’agent et la file d’attente d’appels   |Durée totale (secondes) des appels par l’agent et la file d’attente d’appels     |
|Durée moyenne de l’appel (secondes) par nom de l’agent           |Durée moyenne (secondes) d’un appel par un agent                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>Rapport sur la table et le mappage de champs du tableau de table des champs du tableau de recherche

|Onglet Rapport         |Noms de tables de rapports        |Filtre global |
|:------------------|:-------------------------|:-------------|
|Chronologie de l’agent     |fAgentTimelineAnalytics   |Aucun          |
 
|Nom de la table du rapport            |Nom de la table source            |Traitement       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type » = Table.TransformColumnTypes(Source,{{"Call Count », Int64.Type}, {"Call Duration (Minute) », Int64.Type}, {"Average Call Duration (Second) », type number}, {"Date », type date}})|

|Section État                                |Champ(s) utilisé(s)                         |Filtres appliqués       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Nom de l’agent                                    |Nom de l’agent                            |Aucun                  |
|Nom de la file d’attente d’appels                               |Nom de la file d’attente d’appels                       |Aucun                  |
|#Calls par agent                               |Nom de l’agent<br>Nombre d’appels<br>Date      |Aucun                  |
|Distribution par agent et file d’attente d’appels          |Nom de l’agent<br>Nombre d’appels<br>Durée de l’appel (minutes)<br>Nom de la file d’attente d’appels |Aucun                      |
|Bas à gauche                                   |Nom de l’agent<br>Durée moyenne de l’appel (deuxième)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom de la file d’attente d’appels | Aucun |
|Durée moyenne de l’appel (secondes) par nom de l’agent |Nom de l’agent<br>Durée moyenne de l’appel (deuxième)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom de la file d’attente d’appels | Aucun |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD fields description

|Nom                                    |Type de données                |Description                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|Nom de l’agent                              |texte                     |Nom d’utilisateur utilisateur (UPN)<br>Si le nom **d’utilisateur complet user@microsoft.com** alors cette valeur est : **utilisateur** |
|Durée moyenne de l’appel (deuxième)          |nombre décimal           |Résumer : Somme<br>Durée moyenne des appels de la file d’attente en secondes |
|Nombre d’appels                              |nombre entier             |Résumer : Somme<br>Nombre d’appels gérés par l’agent                    |
|Durée de l’appel (minute)                  |nombre entier             |Résumer : Somme<br>Durée totale des appels de la file d’attente en minutes  |
|Nom de la file d’attente d’appels                         |texte                     |Nom du compte de ressource joint à la file d’attente d’appels<br><br>Si le nom complet du compte de **ressource cq_test@microsoft.com** alors cette valeur est **: cq_test** |
|Date                                    |date                     |                                                    |


> [!NOTE]
> 1) Ce rapport indique le nombre d’appels du point de vue des agents. Par conséquent, le nombre total d’appels dans ce rapport sera généralement supérieur au nombre total d’appels dans le rapport **d’analyse** de la file d’attente d’appels cloud. Chaque appel dans la file d’attente peut être présenté à un ou plusieurs agents au moins une fois avant la réponse. Chaque appel de la file d’attente d’appels présenté à un agent est comptabilisé dans ce rapport, même si l’agent n’a pas répondu à celui-ci. La différence du nombre d’appels entre ces deux rapports est plus prononcé avec l’option de **routage d’Attendant** qui sonne pour chaque agent pour chaque appel. 
> 2) Lorsqu’un appel arrive pour la première fois dans la première file d’attente, si le nombre d’appels déjà en attente dans cette file d’attente dépasse la limite de gestion des appels en dépassement de capacité et si l’option de redirection envoie des appels à une deuxième file d’attente, les agents de la deuxième file d’attente d’appels sont affichés comme étant dans la première file d’attente d’appels de ce rapport.  

## <a name="known-issues"></a>Problèmes connus

- La file d’attente d’appels et les files d’attente automatiques sont indiqués par l’ID du compte de ressource plutôt que par le nom des files d’attente/des files d’attente automatiques.  Pour afficher tout le trafic d’un service de service automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources attribués au attendant automatique ou à la file d’attente d’appels.

- Seuls 28 jours d’historique sont disponibles dans le tableau de bord, car les données de la file d’attente d’appels/du attendant automatique sont considérées comme des données personnelles et sont soumises à des stratégies de rétention des données.

- <sup>1 Source</sup> **d’appel entrant** dans le attendant automatique et les graphiques de la file d’attente d’appels indiquent la source de la partie de l’appel final plutôt que la source initiale de la partie de l’appel. Par exemple, si un attendant automatique reçoit un appel externe et transfère l’appel vers un autre responsable automatique ou file d’attente d’appels, la **source** d’appel entrant est signalée comme interne.
