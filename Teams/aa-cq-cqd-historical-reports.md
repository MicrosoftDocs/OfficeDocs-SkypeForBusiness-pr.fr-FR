---
title: Mise à jour des rapports d’historique du standard automatique et de la file d’attente d’appels
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
description: Découvrez comment utiliser le rapport Power BI du standard automatique Teams & rapport historique de file d’attente d’appels mis à jour pour afficher les données d’historique du standard automatique et de la file d’attente des appels.
ms.openlocfilehash: 780d6057960c96713ac67be3e189d7982fd2fa46
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176691"
---
# <a name="updated-auto-attendant-and-call-queue-historical-reports"></a>Mise à jour des rapports d’historique du standard automatique et de la file d’attente d’appels

>[!NOTE]
> Les clients GCC HIgh et DOD doivent continuer à utiliser la version V1.63 du [standard automatique & les rapports historiques de file d’attente d’appels (CQD).](aa-cq-cqd-historical-reports-v163.md)

Ce modèle Power BI fournit trois rapports qui permettent aux organisations de créer des rapports sur le nombre d’appels traités par les standards automatiques et les files d’attente d’appels.  Il fournit également des insights sur les performances de l’agent.

## <a name="v304-published-on-november-18-2022"></a>V3.0.4 publiée le 18 novembre 2022

Le modèle Power BI rapport d’historique de file d’attente de la file d’attente teams & fournit les trois rapports suivants :

- Le rapport [Standard automatique](media/aa-cq-historical-report-sample-aa-v304.png) affiche l’analytique des appels entrants dans vos standards automatiques.
- Le rapport [File d’attente](media/aa-cq-historical-report-sample-cq-v304.png) des appels affiche l’analytique des appels entrants dans vos files d’attente d’appels.
- Le rapport [Chronologie de l’agent](media/aa-cq-historical-report-sample-at-v304.png) affiche une vue chronologique des agents actifs dans les appels de file d’attente d’appels.

Ces rapports utilisent les données du service VaAC (Voice Applications Analytics Collector).

## <a name="v3xx-prerequisites"></a>Prérequis v3.x.x

### <a name="power-bi-desktop"></a>Power BI Desktop

Vous devez avoir Power BI Desktop installé. Vous pouvez installer et utiliser la version gratuite à partir de [l’Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La version minimale compatible est 2.85.681.0 (septembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline CQD

Bien que cette version des rapports n’utilise pas le pipeline de données CQD (Tableau de bord de qualité des appels), le compte utilisé pour afficher les données historiques nécessite toujours un accès au tableau de bord de qualité des appels. Pour plus d’informations, consultez [Rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

- Cette exigence sera supprimée dans une version ultérieure.

## <a name="v3xx-installation"></a>Installation de V3.x.x 

Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur votre ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données CQD.

Procédez comme suit :

1. Téléchargez et enregistrez le fichier V3.0.4.ziprapports [d’historique des & de la file d’attente d’appels teams ](https://www.microsoft.com/download/details.aspx?id=104623) sur votre ordinateur.

2. Ouvrez le fichier zip.

3. Ouvrez le `Teams Auto Attendant & Call Queue Historical Reports V3.0.4.pbit` fichier de modèle. Power BI Desktop doit être lancé.

4. Vous serez invité à sélectionner la **source de données**.  Sélectionnez l’entrée `api.interfaces.records.teams.microsoft.com` .

  :::image type="content" source="media/aa-cq-historical-report-01-v304.png" alt-text="Capture d’écran de la sélection du api.interfaces.records.teams.microsoft.com Data Soure":::

5. Vous serez invité à vous connecter avec un compte. Sélectionnez **Compte d’organisation**, puis **Se connecter**.

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="Capture d’écran montrant la connexion pour V3.0.0.":::

6. Sélectionnez **Se connecter** pour que les données s’actualisent.

> [!NOTE]
> Si vous utilisiez la version 1.63 ou une version antérieure, vous pouvez rencontrer une erreur lorsque v3.x.x tente de récupérer les données à partir de VAAC.  Pour résoudre cette erreur, il est nécessaire d’effacer les informations d’identification précédentes de Power BI.
> 
> 1. Ouvrez le modèle v3.x.x pour effacer l’erreur. 
> 1. Sélectionnez **Options de fichier** > **& Paramètres Paramètres** > **de la source de données**.
> 1. Sélectionnez la liste déroulante **Effacer les autorisations**, puis **effacer toutes les autorisations**.
> 1. Fermez le modèle une fois qu’ils sont effacés, puis redémarrez Power BI. Vous serez invité à autoriser à nouveau. 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>Latence des données pour l’analyse du standard automatique et de la file d’attente des appels

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
  
## <a name="dimensions-and-measurements"></a>Dimensions et mesures

### <a name="common-dimensions"></a>Dimensions courantes

Ces dimensions sont communes aux standards automatiques et aux files d’attente d’appels :

|Nom (type)                                            |Valeurs possibles                |Description                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|Id de conférence<br>(Texte)                                 |GUID                           |Identificateur d’appel                                                   |
|Date<br>(DateTime)                                     |                               |Date de l’appel (UTC)                                                |
|DialogId<br>(Texte)                                     |GUID                           |Identificateur d’appel                                                   |
|DocumentId<br>(Texte)                                   |GUID                           |Identificateur d’appel                                                   |
|Durée<br>(Nombre entier)                             |                               |Durée de l’appel, en secondes                                      |
|EndTime<br>(DateTime)                                  |                               |Heure de fin de l’appel (UTC)                                             |
|FirstIsCaller<br>(Booléen)                             |                               |                                                                  |
|FirstUPN<br>(Texte)                                     |                               |                                                                  |
|Hour<br>(Texte)                                         |                               |Appel d’heure démarré (UTC)                                           |
|Minute<br>(Texte)                                       |                               |Appel par minute démarré (UTC)                                         |
|PSTNCallDuration<br>(Nombre entier)                     |                               |                                                                  |
|PSTNCallType<br>(Texte)                                 |                               |                                                                  |
|                                                       |Externe                       |                                                                  |
|                                                       |Interne                       |                                                                  |
|PSTNConnectivityType<sup>1</sup><br>(Texte)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|Second<br>(Texte)                                       |                               |Deuxième appel démarré (UTC)                                         |
|SecondUPN<br>(Texte)                                    |                               |                                                                  |
|TenantId<br>(Texte)                                     |                               |ID du locataire                                                         |
|Timestamp<br>(DateTime)                                |                               |Enregistrement de l’heure écrite (UTC)                                     |
|UserStartTimeUTC<br>(DateTime)                         |                               |Heure de démarrage de l’appel (UTC)                                           |

- <sup>1</sup> **PSTNConnectivityType** affiche la source du tronçon d’appel final plutôt que la source du tronçon d’appel initial. Par exemple, si un standard automatique reçoit un appel externe et transfère l’appel vers un autre standard automatique ou file d’attente d’appels, la **source d’appel entrant** est signalée comme **interne**.


### <a name="auto-attendant-dimensions"></a>Dimensions du standard automatique

|Nom (type)                                            |Valeurs possibles                |Description                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br>(Texte)                        |                               |Encapsule les différents états de l’appel du standard automatique          |
|                                                       |abs_search                     |                                                                  |
|                                                       |Annonce                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br>(Texte)                      |                               |Résultat final de l’appel                                                 |
|                                                       |failed_to_establish_media      |La partie média de l’appel n’a pas pu être établie             |
|                                                       |failover_to_operator           |Appel transféré vers l’opérateur généralement en raison d’une erreur système      |
|                                                       |oaa_chain_too_long             |Trop de jambes dans l’AA                                           |
|                                                       |oaa_session_too_long           |La session AA a duré trop longtemps                                    |
|                                                       |service_declined               |AA n’a pas accepté l’appel                                         |
|                                                       |service_terminated             |La configuration AA déconnecte l’appel ou l’appel suspendu             |
|                                                       |terminated_automatic_selection |La configuration AA déconnecte les appels                           |
|                                                       |terminated_no_operator         |Tout s’est arrêté en raison de l’erreur aucun opérateur défini                   |
|                                                       |terminated_transfer_failed     |Appel terminé en cas d’échec du transfert - généralement vers un numéro externe |
|                                                       |transfer_in_progress           |Transfert AA->AA                                                   |
|                                                       |transferred_to_operator        |L’appel a été transféré à l’opérateur                                  |
|                                                       |transferred_to_cq              |L’appel a été transféré vers la file d’attente des appels                                |
|                                                       |transferred_to_receptionist    |Identique à transferred_to_operator                                   |
|                                                       |transferred_to_self            |L’appel a été retourné au début de l’AA                          |
|                                                       |transferred_to_shared_voicemail |L’appel a été transféré vers la messagerie vocale partagée                         |
|                                                       |transferred_to_user            |L’appel a été transféré à un utilisateur                                    |
|                                                       |Inconnu                        |Une condition inconnue s’est produite                                 |
|                                                       |user_terminated                |L’appelant a raccroché                                                    |
|AutoAttendantCallerActionCounts<br>(Nombre entier)      |                               |                                                                  |
|AutoAttendantChairDurationInSecs<br>(Nombre réel)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(Nombre entier)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(Nombre entier)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(Texte)           |                               |Méthode de recherche d’annuaire                                           |
|                                                       |abs_search_dtmf                |Tonalité tactile                                                        |
|                                                       |abs_search_voice               |Voix                                                             |
|AutoAttendantIdentity<br>(Texte)                        |                               |L’appel d’URI de compte de ressource est arrivé le                              |
|AutoAttendantTransferAction<br>(Texte)                  |                               |Type de cible de transfert d’appel                                         |
|                                                       |Aa                             |Transféré vers un AA                                              |
|                                                       |Cq                             |Transféré vers un CQ                                               |
|                                                       |external_pstn                  |Transféré vers un numéro externe                                 |
|                                                       |messagerie vocale partagée               |Transféré vers la messagerie vocale partagée                                   |
|                                                       |Inconnu                        |Action inconnue                                                    |
|HasAA<br>(Booléen)                                     |                               |AA est-il impliqué dans l’appel                                            |


### <a name="call-queue-dimensions"></a>Dimensions de la file d’attente des appels

|Nom (type)                                            |Valeurs possibles                |Description                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br>(Nombre entier)                  |                               |Nombre d’agents dans la file d’attente des appels                                    |
|CallQueueAgentOptInCount<br>(Nombre entier)             |                               |Nombre d’agents qui ont choisi d’appeler la file d’attente                           |
|CallQueueCallResult<br>(Texte)                          |                               |État final de l’appel de file d’attente d’appels                                       |
|                                                       |agent_joined_conference        |Appel répondu - mode conférence CQ                                |
|                                                       |Refusé                       |                                                                  |
|                                                       |Déconnecté                   |                                                                  |
|                                                       |error                          |                                                                  |
|                                                       |Échoué                         |                                                                  |
|                                                       |Non valide                        |                                                                  |
|                                                       |Survolé                      |Condition de dépassement de capacité remplie                                            |
|                                                       |timed_out                      |Condition de délai d’expiration remplie                                             |
|                                                       |transferred_to_agent           |Appel répondu - CQ en mode de transfert                                  |
|CallQueueDurationSeconds<br>(Nombre réel)              |                               |                                                                  |
|CallQueueFinaleStateAction<br>(Texte)                   |                               |Action finale de la file d’attente d’appels                                           |
|                                                       |Débrancher                     |appels time_out                                                    |
|                                                       |disconnect_with_busy           |appels débordés                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |Avant                        |                                                                  |
|                                                       |shared_voicemail               |                                                                  |
|                                                       |Autres                          |                                                                  |
|                                                       |Messagerie vocale                      |                                                                  |
|CallQueueIdentity<br>(Texte)                            |                               |L’appel d’URI de compte de ressource est arrivé le                              |
|CallQueueTargetType<br>(Texte)                          |                               |Cible de redirection d’appel                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |Boîte aux lettres                        |                                                                  |
|                                                       |Autres                          |                                                                  |
|                                                       |Téléphone                          |                                                                  |
|                                                       |Utilisateur                           |                                                                  |
|HasCQ<br>(Booléen)                                     |                               |Le CQ est-il impliqué dans l’appel                                            |
|TransferredFromCallQueueIdentity<br>(Texte)             |                               |                                                                  |

### <a name="measurements"></a>Mesures

|Nom (type)                                            |Valeurs possibles                |Description                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br>(Nombre réel)  |                               |                                                                  |
|AvgCallDuration<br>(Nombre réel)                       |                               |                                                                  |
|AvgCallQueueDurationSeconds<br>(Nombre réel)           |                               |                                                                  |
|PSTNTotalMinutes<br>(Nombre réel)                      |                               |                                                                  |
|TotalAudioStreamDuration<br>(Nombre réel)              |                               |                                                                  |
|TotalCallCount<br>(Nombre entier)                       |                               |                                                                  |

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>Définitions des rapports d’historique du standard automatique et de la file d’attente d’appels

### <a name="cloud-auto-attendant-analytics-report"></a>Rapport Cloud Auto Standard Analytics

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|Source d’appel entrant                    |Distribution des appels par source d’appel interne/externe            |
|Directory Search, méthode                 |Distribution des appels par type de recherche                              |
|Nombre d’actions de l’appelant                     |Distribution des appels par action de numéro utilisée pendant l’appel       |
|Moyenne des secondes dans AA                   |Nombre moyen de secondes que les appelants passent dans l’AA                 |
|Actions moyennes de l’appelant                  |Nombre moyen d’actions effectuées par les appelants dans l’AA               |
|Résultats de l’appel                            |Distribution des appels par état d’appel final                         |
|Section inférieure du rapport                 |Répartition du flux d’appels                                               |

#### <a name="report-visual-and-field-mapping"></a>Mappage de visuels et de champs de rapport

|Onglet Rapport            |Nom de la table de rapport     |Filtre global                          |
|:---------------------|:---------------------|:--------------------------------------|
|Standard automatique        |fAutoAttendant        |Aucun                                   |

|Section Rapport                               |Champ(s) utilisé(s)                                                                                    |Filtres appliqués |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|Sélecteur de date                                |AAStartTime                                                                                      |Aucun       |
|Sélecteur d’intervalle de temps                          |AAStartHour                                                                                      |Aucun       |
|Comptes de ressources de standard automatique             |Nom AA                                                                                          |Aucun       |
|Source d’appel entrant                         |Type d'appel<br>Somme de TotalCallCount         |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Directory Search, méthode                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod est abs_search_dtmf ou abs_search_name    |
|Nombre d’actions de l’appelant                          |AACallerActionCount<br>TotalCallCount                                                            |Aucun       |
|Moyenne des secondes dans AA                        |AAChainDuration                                                                                  |Aucun       |
|Actions moyennes de l’appelant                       |AACallerActionCount                                                                              |Aucun       |
|Résultats de l’appel                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |Aucun       |
|Section inférieure du rapport                      |MM-DD<br>Nom AA<br>AACallFlow<br>Type d'appel<br>AACallResult<br>TotalCallCount<br>AAChainDuration |Aucun       |

#### <a name="fautoattendant-field-description"></a>Description du champ fAutoAttendant

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nom AA                                 |Texte                     |Nom du compte de ressource attaché au standard automatique<br><br>Si le nom complet du compte de ressource est **aa_test@microsoft.com**, cette valeur est **: aa_test** |
|AACallerActionCount                     |Nombre entier             |Résumer : Somme<br>Nombre d’actions sélectionnées par l’appelant dans le standard automatique pendant l’appel  |
|AACallerActionCount (Measure)           |Nombre entier             |Identique à ce qui précède, sauf que sera égal à 0 si aucun appel au lieu de vide                              |
|AACallFlow                              |Texte                     |Consultez Dimensions du standard automatique -> AutoAttendantCallFlow                                   |
|AACallResult                            |Texte                     |Voir Dimensions du standard automatique -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |Texte                     |Configure les éléments de légende basés sur AACallResult                                               |
|AAChainDuration                         |Nombre décimal           |Résumer : Somme<br>Durée de l’appel dans le standard automatique                                     |
|AAChainDuration (Measure)               |Nombre décimal           |Identique à ce qui précède, sauf que sera égal à 0 si aucun appel au lieu de vide                              |
|AAChainIndex                            |Texte                     |                                                                                         |
|AAConnectivityType                      |Texte                     |                                                                                         |
|AACount                                 |Texte                     |Nombre de standards automatiques impliqués dans l’appel                                               |
|AADirectorySearchMethod                 |Texte                     |Voir Dimensions du standard automatique -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |Texte                     |Configure les éléments de légende basés sur AADirectorySearchMethod                                    |
|AAStartHour                             |Nombre décimal           |Heure de début de l’appel du standard automatique                                                           |
|AAStartTime                             |Date/heure                |Heure de début de l’appel du standard automatique                                                           |
|AATransferAction                        |Texte                     |Voir Dimensions du standard automatique -> AutoAttendantTransferAction                             |
|Type<sup>d’appel 1</sup>                   |Texte                     |Voir Dimensions communes -> PSTNCallType                                                    |
|MM-DD                                   |Texte                     |Appel du standard automatique mois-jour                                                            |
|PSTNMinutes                             |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes                                                     |
|TotalCallCount                          |Nombre entier             |Résumer : Somme<br>Always 1 : utilisé pour fournir la somme de tous les appels                            |
|Somme de TotalCallCount (Measure)         |Nombre entier             |Identique à ce qui précède, sauf que sera égal à 0 si aucun appel au lieu de vide                              |


### <a name="cloud-call-queue-analytics-report"></a>Rapport Analyse de la file d’attente des appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Source d’appel entrant                    |Distribution des appels par source d’appel interne/externe             |
|Temps d’attente moyen (secondes)             |Temps d’attente pour les appels répondus et abandonnés                          |
|Nombre de volumes d’appels et d’activation de l’agent      |Distribution des appels par files d’attente d’appels / Nombre maximal d’inscriptions d’agent  |
|Résultats de l’appel                            |Distribution des appels par résultat d’appel                               |
|Appels abandonnés                         |Distribution des appels abandonnés par files d’attente d’appels                     |
|Durée moyenne de session (secondes)        |Longueur de l’appel en secondes regroupée par résultat de l’appel                      |
|Destinations de dépassement/délai d’expiration des appels      |Distribution des appels qui ont expiré ou dépassé le délai d’attente                 |


#### <a name="report-visual-and-field-mapping"></a>Mappage de visuels et de champs de rapport

|Onglet Rapport            |Nom de la table de rapport                                   |Filtre global       |
|:---------------------|:---------------------------------------------------|:-------------------|
|File d’attente d’appels            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |Aucun                |

|Section Rapport                      |Table -> Champ(s) utilisé(s)                |Filtres appliqués       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de date                       |fCallQueueAnalytics -> Date           |Aucun                  |
|Sélecteur d’intervalle de temps                 |fCallQueueAnalytics -> CQHour         |Aucun                  |
|Compte de ressource de file d’attente d’appels         |fCallQueueAnalytics -> nom CQ        |Aucun                  |
|Source d’appel entrant                |fCallQueueAnalytics -> somme du nombre d’appels (mesure)  |Appels externes : le type d’appel est externe<br>Appels internes : le type d’appel est interne |
|Délai d’attente moyen (secondes)-Avant réponse |fCallQueueFinalStateAction -> moyenne de la durée moyenne du CQ (mesure) |Le résultat de l’appel de file d’attente est agent_joined_conference ou transferred_to_agent|
|Délai d’attente moyen (secondes)-Avant abandon |fCallQueueFinalStateAction -> moyenne de la durée moyenne des appels (mesure) |Le résultat de l’appel de file d’attente n’est pas agent_joined_conference, transferred_to_agent, dépassé, timed_out |
|Nombre de Opt-In d’agents et de volume d’appels   |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> Call Queue Agent Opt In Count<br>fCallQueueAnalytics -> nom CQ<br>fCallQueueAnalytics -> Date |Aucun |
|Appels abandonnés                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | La légende du résultat de l’appel de la file d’attente d’appels est abandonnée |
|Durée moyenne de session (secondes)    |fCallQueueFinalStateAction -> Durée moyenne de la file d’attente des appels (s)<br>Légende du résultat de l’appel de file d’attente |Durée moyenne de la file d’attente des appels (s) > 0 |
|Destinations de dépassement/délai d’expiration des appels  |fCallQueueAnalytics -> Nombre d’appels<br>fCallQueueAnalytics -> type de cible de file d’attente d’appels<br>fCallQueue Target Type Legend |La légende du type de cible de file d’attente d’appels ne contient pas abandonné et l’agent a répondu |


#### <a name="fcallqueueanalytics-field-description"></a>Description du champ fCallQueueAnalytics

|Nom                                    |Type de données                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                          |
|Nombre d’agents de file d’attente des appels                  |Nombre entier             |Résumer : Somme<br>Nombre d’agents configurés dans la file d’attente des appels            |
|Nombre d’inscriptions de l’agent de file d’attente des appels           |Nombre entier             |Résumer : Somme<br>Nombre d’agents abonnés à la file d’attente des appels              |
|Résultat de l’appel de file d’attente                  |Texte                     |Voir Dimensions de file d’attente des appels -> CallQueueCallResult                           |
|Légende du résultat de l’appel de file d’attente           |Texte                     |Configure les éléments de légende en fonction du résultat de la file d’attente des appels                            |
|Type de cible de file d’attente d’appels                  |Texte                     |Voir Dimensions de file d’attente des appels -> CallQueueTargetType                           |
|Légende du type de cible de file d’attente d’appels           |Texte                     |Configure les éléments de légende en fonction du type de cible de file d’attente d’appels                       |
|Type d'appel                               |Texte                     |Voir Dimensions communes -> PSTNCallType                              |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Heure CQ                                 |Nombre entier             |Heure de début de l’appel de la file d’attente d’appels                                                 |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente (heure)                                 | 
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                     |
|Type de connectivité RTC                  |Texte                     |Voir Dimensions communes -> PSTNConnectivityType                              |
|PSTN Total Minutes                      |Nombre entier             |Résumer : Somme<br>Utilisation du nombre total de minutes pour les appels RTC                       |
|Somme du nombre d’appels (mesure)             |Nombre entier             |Identique au nombre d’appels, toutefois, sera égal à 0 quand aucun appel                          |
|TotalCallCount (Measure)                |Nombre entier             |Résumer : Somme<br>Nombre d’appels                                               |


#### <a name="fcallqueuefinalstateaction-field-description"></a>Description du champ fCallQueueFinalStateAction

|Nom                                    |Type de données                |Description                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|Durée moyenne des appels (secondes)         |Nombre décimal           |Résumer : Somme<br>Durée moyenne des appels en secondes pour les appels abandonnés     |
|Durée moyenne de la file d’attente des appels (s)       |Nombre décimal           |Résumer : Somme<br>Temps d’attente moyen en secondes pour les appels répondus       |
|Moyenne de la durée moyenne de l’appel (mesure)  |Nombre entier             |Identique à la durée moyenne des appels (secondes), toutefois, sera 0 quand aucun appel    |
|Moyenne de la durée moyenne du CQ (mesure)    |Nombre entier             |Identique à la durée moyenne de la file d’attente des appels (s), toutefois, sera de 0 quand aucun appel n’est nécessaire  |
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                          |
|Résultat de l’appel de file d’attente                  |Texte                     |Voir Dimensions de file d’attente des appels -> CallQueueCallResult                           |
|Légende du résultat de l’appel de file d’attente           |Texte                     |Configure les éléments de légende en fonction du résultat de l’appel de la file d’attente d’appels                       |
|Action d’état final d’appel de file d’attente           |Texte                     |Voir Call Queue Dimensions -> CallQueueFinaleStateAction                    |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Heure CQ                                 |Numéro                   |Heure à laquelle l’appel a eu lieu en
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente des appels (heure)                                 |
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                     |
|IsAbandoned                             |True/false               |True si un agent ne répond pas à l’appel                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>Rapport de chronologie de l’agent de file d’attente d’appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                                          |Description                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|Nombre d’appels par agent                                |Distribution des appels par file d’attente d’appels et agent                       |
|Distribution par agent et toutes les files d’attente                     |Distribution des appels par agent et file d’attente d’appels                       |
|Tableau (en bas à gauche)                                     |Distribution des appels par agent avec la durée moyenne et totale des appels |
|Durée moyenne des appels (secondes) par agent (en bas à droite) |Durée moyenne (secondes) de l’appel par agent                         |

#### <a name="report-visual-field-mapping"></a>Mappage des champs visuels de rapport

|Onglet Rapport            |Nom de la table de rapport           |Filtre global       |
|:---------------------|:---------------------------|:-------------------|
|Chronologie de l’agent        |fAgentTimelineAnalytics     |Aucun                |


|Section Rapport                                |Champ(s) utilisé(s)                         |Filtres appliqués       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|Sélecteur de date                                 |Datetime                              |Aucun                  |
|Sélecteur de nom d’utilisateur de l’agent                       |Nom de l’agent                            |Aucun                  |
|Sélecteur de comptes de ressources de file d’attente d’appel         |Nom du CQ                               |Aucun                  |
|Nombre d’appels par agent                      |Nombre d’appels<br>Nom de l’agent<br>Date<br>Hour      |Aucun                  |
|Distribution par agent et file d’attente d’appels          |Nom de l’agent<br>Durée moyenne des appels (secondes)<br>Nombre d’appels<br>Nom du CQ |Aucun                      |
|Bas à gauche                                   |Nom de l’agent<br>Durée moyenne des appels (secondes)<br>Nombre d’appels<br>Durée de l’appel (minute)<br>Nom du CQ<br>Hour<br>MM-DD | Aucun |
|Durée moyenne des appels (secondes) par agent      |Nom de l’agent<br>Durée moyenne des appels (secondes) | Aucun |

#### <a name="fagenttimelineanalytics-field-description"></a>Description du champ fAgentTimelineAnalytics

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

- Les files d’attente d’appels et les standards automatiques sont affichés par l’ID du compte de ressource au lieu des noms de file d’attente/standard automatique des appels.  Pour afficher tout le trafic d’un standard automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources affectés au standard automatique ou à la file d’attente d’appels.

- Seuls 28 jours d’historique sont disponibles dans le tableau de bord, car les données de file d’attente d’appels/standard automatique sont considérées comme des données personnelles et soumises à des stratégies de conservation de la confidentialité des données.

- Dans certains scénarios, le nombre d’appels répondus par l’agent dans le rapport **chronologie de l’agent de file d’attente d’appels** cloud peut être différent du nombre d’appels indiqué dans l’historique des appels du client Teams. L’historique des appels du client Teams est correct. Le support est en cours d’examen, mais il n’y a pas de temps estimé pour la réparation disponible pour l’instant.

## <a name="version-3xx-history"></a>Historique de la version 3.x.x

Reportez-vous à : Standard automatique Teams & Rapports historiques de file d’attente d’appels - Modifier Log.docx dans le fichier zip téléchargé pour obtenir la liste détaillée des modifications 

|Version  |Date de publication     |Fichier                                                           |Description                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|3.0.4    |18 novembre 2022  |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.4        |Correction de l’erreur, amélioration de la classification des appels, ajout de la légende |
|3.0.3    |8 novembre 2022   |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.3        |Correction de l’erreur, ajout d’un lien de documentation, requêtes optimisées |
|3.0.1    |26 octobre 2022   |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.1        |Suppression de l’entrée de source de données de test                   |
|3.0.0    |25 octobre 2022   |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.0        |Nouvelle source de données back-end                             |
