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
ms.openlocfilehash: ed267cf2d96f15236aa68339049d2c721249ec00
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763555"
---
# <a name="auto-attendant-and-call-queue-historical-reports"></a>Rapports d’historique du standard automatique et de la file d’attente d’appels

>[!NOTE]
> Les clients GCC HIgh et DOD doivent continuer à utiliser la version V1.63 du [standard automatique & les rapports historiques de file d’attente d’appels (CQD).](aa-cq-cqd-historical-reports-v163.md)

Ce modèle Power BI fournit trois rapports qui permettent aux organisations de créer des rapports sur le nombre d’appels traités par les standards automatiques et les files d’attente d’appels.  Il fournit également des insights sur les performances de l’agent.

## <a name="v305-published-on-january-9-2023"></a>V3.0.5 publiée le 9 janvier 2023

Le modèle Power BI rapport d’historique de file d’attente de la file d’attente teams & fournit les trois rapports suivants :

- Le rapport [Standard automatique](media/aa-cq-historical-report-sample-aa-v305.png) affiche l’analytique des appels entrants dans vos standards automatiques.
- Le rapport [File d’attente](media/aa-cq-historical-report-sample-cq-v305.png) des appels affiche l’analytique des appels entrants dans vos files d’attente d’appels.
- Le rapport [Chronologie de l’agent](media/aa-cq-historical-report-sample-at-v305.png) affiche une vue chronologique des agents actifs dans les appels de file d’attente d’appels.

Ces rapports utilisent les données du service VaAC (Voice Applications Analytics Collector).

## <a name="v3xx-prerequisites"></a>Prérequis v3.x.x

### <a name="power-bi-desktop"></a>Power BI Desktop

Vous devez avoir Power BI Desktop installé. Vous pouvez installer et utiliser la version gratuite à partir du [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

La version minimale compatible est 2.85.681.0 (septembre 2020).

### <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline CQD

Bien que cette version des rapports n’utilise pas le pipeline de données CQD (Tableau de bord de qualité des appels), le compte utilisé pour afficher les données historiques nécessite toujours un accès au tableau de bord de qualité des appels. Pour plus d’informations, consultez [Rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

Tout rôle CQD avec les champs **Afficher les rapports** et **Afficher les champs EUII** définis sur **Oui** fonctionne.

- Cette exigence sera supprimée dans une version ultérieure.

## <a name="v3xx-installation"></a>Installation de V3.x.x 

Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur votre ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données CQD.

Procédez comme suit :

1. Téléchargez et enregistrez le fichier V3.0.5.ziprapports [d’historique des & de la file d’attente d’appels teams ](https://www.microsoft.com/download/details.aspx?id=104623) sur votre ordinateur.

2. Ouvrez le fichier zip.

3. Ouvrez le `Teams Auto Attendant & Call Queue Historical Reports V3.0.5.pbit` fichier de modèle. Power BI Desktop doit être lancé.

4. Vous serez invité à sélectionner la **source de données**.  Sélectionnez l’entrée `api.interfaces.records.teams.microsoft.com` .

  :::image type="content" source="media/aa-cq-historical-report-01-v305.png" alt-text="Capture d’écran de la sélection du api.interfaces.records.teams.microsoft.com Data Soure":::

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
|Heure de début AA UTC                       |Date/heure                |Heure de début de l’appel du standard automatique - UTC                                                     |
|AACallerActionCount                     |Nombre entier             |Résumer : Somme<br>Nombre d’actions sélectionnées par l’appelant dans le standard automatique pendant l’appel  |
|AACallerActionCount (Measure)           |Nombre entier             |Identique à AACallerActionCount, sauf que sera égal à 0 si aucun appel au lieu de vide                |
|AACallFlow                              |Texte                     |Consultez Dimensions du standard automatique -> AutoAttendantCallFlow                                   |
|AACallResult                            |Texte                     |Voir Dimensions du standard automatique -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |Texte                     |Configure les éléments de légende basés sur AACallResult                                               |
|AAChainDuration                         |Nombre décimal           |Résumer : Somme<br>Durée de l’appel dans le standard automatique                                     |
|AAChainDuration (Measure)               |Nombre décimal           |Identique à AAChainDuration, sauf que sera 0 si aucun appel au lieu de vide                    |
|AAChainIndex                            |Nombre entier             |                                                                                         |
|AAConnectivityType                      |Texte                     |Voir Dimensions courantes -> PSTNConnectivityType                                            |
|AACount                                 |Nombre entier             |Nombre de standards automatiques impliqués dans l’appel                                               |
|AADirectorySearchMethod                 |Texte                     |Voir Dimensions du standard automatique -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |Texte                     |Configure les éléments de légende basés sur AADirectorySearchMethod                                    |
|AAStartHour                             |Nombre entier             |Heure de début de l’appel du standard automatique                                                           |
|AAStartTime                             |Date/heure                |Heure de début de l’appel du standard automatique                                                           |
|AATransferAction                        |Texte                     |Voir Dimensions du standard automatique -> AutoAttendantTransferAction                             |
|Durée des appels en secondes                   |Nombre entier             |Durée de l’appel                                                                            |
|Heure de fin de l’appel local                     |Date/heure                |Heure de fin de l’appel : locale (en fonction du fuseau horaire de l’ordinateur exécutant le rapport)                    |
|Heure utc de fin de l’appel                       |Date/heure                |Heure de fin de l’appel - UTC                                                                      |
|Heure de début de l’appel local                   |Date/heure                |Heure de début de l’appel - Local (en fonction du fuseau horaire de l’ordinateur exécutant le rapport)                  |
|Heure de début de l’appel UTC                     |Date/heure                |Heure de début de l’appel - UTC                                                                    |
|Type<sup>d’appel 1</sup>                   |Texte                     |Voir Dimensions communes -> PSTNCallType                                                    |
|Id de conférence                            |Texte                     |Utilisé à des fins de résolution des problèmes : fournissez ces informations lors de l’ouverture d’un ticket       |
|DialogID                                |Texte                     |Utilisé à des fins de résolution des problèmes : fournissez ces informations lors de l’ouverture d’un ticket       |
|DocumentID                              |Texte                     |Utilisé à des fins de résolution des problèmes : fournissez ces informations lors de l’ouverture d’un ticket       |
|MM-DD                                   |Texte                     |Appel du standard automatique mois-jour                                                            |
|PSTNMinutes                             |Nombre entier             |Résumer : Somme<br>Utilisation totale des minutes                                                     |
|Somme de TotalCallCount (Measure)         |Nombre entier             |Identique à TotalCallCount, sauf que sera égal à 0 si aucun appel au lieu de vide                     |
|TotalCallCount                          |Nombre entier             |Résumer : Somme<br>Always 1 : utilisé pour fournir la somme de tous les appels                            |


### <a name="cloud-call-queue-analytics-report"></a>Rapport Analyse de la file d’attente des appels cloud

#### <a name="report-description"></a>Description du rapport

|Section Rapport                          |Description                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|Source d’appel entrant                    |Distribution des appels par source d’appel interne/externe             |
|Temps d’attente moyen (secondes)             |Temps d’attente pour les appels répondus et abandonnés                         |
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

|Nom                                    |Type de données                |Description                                                                              |
|:---------------------------------------|:------------------------|:----------------------------------------------------------------------------------------|
|Nombre d’appels                              |Nombre entier             |Résumer : Somme<br>Nombre d'appels                                                        |
|Durée des appels en secondes                   |Nombre entier             |Durée de l’appel                                                                            |
|Heure de fin de l’appel local                     |Date/heure                |Heure de fin de l’appel : locale (en fonction du fuseau horaire de l’ordinateur exécutant le rapport)                    |
|Heure utc de fin de l’appel                       |Date/heure                |Heure de fin de l’appel - UTC                                                                      |
|Nombre d’agents de file d’attente des appels                  |Nombre entier             |Résumer : Somme<br>Nombre d’agents configurés dans la file d’attente des appels                          |
|Nombre d’inscriptions de l’agent de file d’attente des appels           |Nombre entier             |Résumer : Somme<br>Nombre d’agents abonnés à la file d’attente des appels                            |
|Résultat de l’appel de file d’attente                  |Texte                     |Voir Dimensions de file d’attente des appels -> CallQueueCallResult                                         |
|Légende du résultat de l’appel de file d’attente           |Texte                     |Configure les éléments de légende en fonction du résultat de la file d’attente des appels                                          |
|Type de cible de file d’attente d’appels                  |Texte                     |Voir Dimensions de file d’attente des appels -> CallQueueTargetType                                         |
|Légende du type de cible de file d’attente d’appels           |Texte                     |Configure les éléments de légende en fonction du type de cible de file d’attente d’appels                                     |
|Heure de début de l’appel local                   |Date/heure                |Heure de début de l’appel - Local (en fonction du fuseau horaire de l’ordinateur exécutant le rapport)                  |
|Heure de début de l’appel UTC                     |Date/heure                |Heure de début de l’appel - UTC                                                                    |
|Type d'appel                               |Texte                     |Voir Dimensions communes -> PSTNCallType                                                    |
|Id de conférence                            |Texte                     |Utilisé à des fins de résolution des problèmes : fournissez ces informations lors de l’ouverture d’un ticket       |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Heure CQ                                 |Nombre entier             |Heure de début de l’appel de la file d’attente d’appels                                                               |
|Date                                    |Date/heure                |Date et heure de début de l’appel de file d’attente (heure)                                               | 
|DateTimeCQName                          |Texte                     |Clé unique pour le filtrage sur fCallQueueFinalStateAction                                   |
|DialogID                                |Texte                     |Utilisé à des fins de résolution des problèmes : fournissez ces informations lors de l’ouverture d’un ticket       |
|DocumentID                              |Texte                     |Utilisé à des fins de résolution des problèmes : fournissez ces informations lors de l’ouverture d’un ticket       |
|Type de connectivité RTC                  |Texte                     |Voir Dimensions communes -> PSTNConnectivityType                                            |
|PSTN Total Minutes                      |Nombre entier             |Résumer : Somme<br>Utilisation du nombre total de minutes pour les appels RTC                                     |
|Somme du nombre d’appels (mesure)             |Nombre entier             |Identique au nombre d’appels, toutefois, sera égal à 0 quand aucun appel                                        |
|TotalCallCount (Measure)                |Nombre entier             |Résumer : Somme<br>Nombre d’appels                                                             |


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
|Durée de l’appel (minutes)                 |Nombre entier             |Résumer : Somme<br>Durée totale des appels de file d’attente d’appels répondus en minutes (arrondie à la minute la plus proche)  |
|Appels répondus                          |Nombre entier             |Nombre d’appels traités par l’agent                        |
|Appels sans réponse                      |Nombre entier             |Nombre d’appels non traités par l’agent                    |
|Nom du CQ                                 |Texte                     |Nom du compte de ressource attaché à la file d’attente d’appels<br><br>Si le nom complet du compte de ressource est **cq_test@microsoft.com**, cette valeur est **: cq_test** |
|Date                                    |Date                     |Date de l’appel                                             |
|Datetime                                |Datetime                 |Date de l’appel                                             |
|Hour                                    |Nombre entier             |Heure d’appel                                             |
|MM-DD                                   |Texte                     |Mois et jour de l’appel                                    |
|Nombre total d’appels                        |Nombre entier             |Résumer : Somme<br>Nombre d’appels présentés à l’agent     |

> [!NOTE]
> Lorsqu’un appel arrive à la première file d’attente d’appels, si le nombre d’appels en attente dans cette file d’attente a atteint la limite de **gestion du dépassement de capacité** d’appel et si l’option de redirection envoie de nouveaux appels à une deuxième file d’attente d’appels, les agents de la deuxième file d’attente d’appels apparaissent comme étant dans la première file d’attente d’appels de ce rapport. 

## <a name="known-issues"></a>Problèmes connus

- Les files d’attente d’appels et les standards automatiques sont affichés par l’ID du compte de ressource au lieu des noms de file d’attente/standard automatique des appels.  Pour afficher tout le trafic d’un standard automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources affectés au standard automatique ou à la file d’attente d’appels.

- Seuls 28 jours d’historique sont disponibles dans le tableau de bord, car les données de file d’attente d’appels/standard automatique sont considérées comme des données personnelles et soumises à des stratégies de conservation de la confidentialité des données.

- Dans certains scénarios, le nombre d’appels répondus par l’agent dans le rapport **chronologie de l’agent de file d’attente d’appels** cloud peut être différent du nombre d’appels indiqué dans l’historique des appels du client Teams. L’historique des appels du client Teams est correct. Le support est en cours d’examen, mais il n’y a pas de temps estimé pour la réparation disponible pour l’instant.

## <a name="customization"></a>Personnalisation 

Vous pouvez personnaliser certains aspects de la visualisation des rapports, tels que l’ajout ou la suppression de champs à afficher dans les différentes visualisations, la modification du type de graphique, etc.

### <a name="change-color-schema"></a>Modifier le schéma de couleur 

Les étapes suivantes supposent que vous avez déjà effectué les étapes d’installation.

Procédez comme suit :

1. Sélectionnez **l’onglet Affichage** dans le ruban.

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="Capture d’écran de la sélection de l’onglet affichage pour modifier le jeu de couleurs.":::

2. Sélectionnez le schéma de couleur dans la liste déroulante.

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="Capture d’écran montrant différents modèles de couleurs.":::
  
## <a name="dimensions-and-measurements"></a>Dimensions et mesures

Les dimensions et mesures suivantes peuvent être utilisées.

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
|FirstIsCaller<br>(Booléen)                             |                               |[Classification des premier et deuxième points de terminaison](dimensions-and-measures-available-in-call-quality-dashboard.md)     |
|FirstUPN<br>(Texte)                                     |                               |Nom d’utilisateur principal (UPN) de l’utilisateur du premier point de terminaison        |
|Hour<br>(Texte)                                         |                               |Appel d’heure démarré (UTC)                                           |
|Minute<br>(Texte)                                       |                               |Appel par minute démarré (UTC)                                         |
|PSTNCallDuration<br>(Nombre entier)                     |                               |Durée de l’appel                                              |
|PSTNCallType<br>(Texte)                                 |                               |                                                                  |
|                                                       |Externe                       |L’appel provient de l’extérieur du locataire                            |
|                                                       |Interne                       |L’appel provient du locataire                             |
|PSTNConnectivityType<sup>1</sup><br>(Texte)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|Second<br>(Texte)                                       |                               |Deuxième appel démarré (UTC)                                         |
|SecondUPN<br>(Texte)                                    |                               |Nom d’utilisateur principal (UPN) de l’utilisateur du deuxième point de terminaison       |
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
|AutoAttendantChainDurationInSecs<br>(Nombre réel)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(Nombre entier)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(Nombre entier)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(Texte)           |                               |Méthode de recherche d’annuaire                                           |
|                                                       |abs_search_dtmf                |Tonalité tactile                                                        |
|                                                       |abs_search_voice               |Voix                                                             |
|AutoAttendantIdentity<br>(Texte)                        |                               |L’appel d’URI de compte de ressource est arrivé le                              |
|AutoAttendantTransferAction<br>(Texte)                  |                               |Type de cible de transfert d’appel                                         |
|                                                       |AA                             |Transféré vers un AA                                              |
|                                                       |CQ                             |Transféré vers un CQ                                               |
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
|CallQueueDurationSeconds<br>(Nombre réel)              |                               |Durée de l’appel dans la file d’attente des appels                                   |
|CallQueueFinaleStateAction<br>(Texte)                   |                               |Action finale de la file d’attente d’appels                                           |
|                                                       |Débrancher                     |appels time_out                                                    |
|                                                       |disconnect_with_busy           |appels débordés                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |Avant                        |L’appel a été transféré à un utilisateur ou en externe                        |
|                                                       |shared_voicemail               |L’appel a été envoyé à la messagerie vocale partagée                                 |
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

### <a name="constructing-a-valid-query"></a>Construction d’une requête valide

Une requête valide se compose de plusieurs attributs dans un objet JSON :

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"Power BI Desktop"
   },
   "LimitResultRowsCount":100000
}
```

#### <a name="required-fields"></a>Champs obligatoires

- Filtres : utilisés pour filtrer les données retournées par VAAC
- - DataModelName doit être l’une des dimensions prises en charge
- - La valeur doit être au format correct (datetime, chaîne, nombre, etc.)
- - Opérandes:
- - - 0 - Égal à
- - - 1 - N’est pas égal à
- - - 2 - Contient
- - - 3 - Commence par
- - - 4 - Supérieur à
- - - 5 - Supérieur ou égal à
- - - 6 - Inférieur à
- - - 7 - Inférieur ou égal à
- - - 8 - Ne contient pas
- - - 9 - Ne commence pas par

- Dimensions :
- - DataModelName doit être l’une des dimensions prises en charge

- Mesures:
- - DataModelName doit être l’une des mesures prises en charge

- Paramètres : Actuellement, seul UserAgent est pris en charge.

- LimitResultRowsCount : nombre maximal de lignes retournées par VAAC

## <a name="accessing-vaac-outside-of-power-bi"></a>Accès à VAAC en dehors de Power BI

L’API VAAC est accessible par toute application qui peut accéder aux applications RESTful.  Dans l’exemple ci-dessous, [Postman](https://www.postman.com/) sera utilisé.

### <a name="preparation"></a>Préparation

Téléchargez [Postman](https://www.postman.com/).

Téléchargez le dépôt : [sync_pstn_avs-analytics et décompressez-le](https://skype.visualstudio.com/SBS/_git/sync_pstn_avs-analytics) .

Importez le dossier dans Postman. 

:::image type="content" source="media/aa-cq-historical-report-postman-01.png" alt-text="Capture d’écran montrant l’importation terminée":::

### <a name="accessing-vaac-using-postman"></a>Accès à VAAC à l’aide de Postman

1. Sélectionnez **VAAC - msit** en haut à droite dans la liste déroulante **_Aucun environnement_** .
2. Sélectionnez **Environnements** dans le menu de gauche.
3. Sélectionnez **VAAC - msit** sous **Globals**.
4. Remplacez **userName**, **password** et **tenantId** par les informations d’identification applicables.
5. Cliquez sur **Réinitialiser tout** en haut à droite.
6. Cliquez sur **Enregistrer**.

:::image type="content" source="media/aa-cq-historical-report-postman-02.png" alt-text="Capture d’écran montrant les champs nom d’utilisateur, mot de passe et ID de locataire configurés":::


7. Sélectionnez **Collections** dans le menu de gauche.
8. Sélectionnez **Config API Access Token - Prod** et accédez à l’onglet **Corps** .
9. Cliquez sur **Envoyer**.

Un jeton d’accès sera retourné.

:::image type="content" source="media/aa-cq-historical-report-postman-03.png" alt-text="Capture d’écran montrant le résultat avec le jeton d’accès retourné":::

Si aucun jeton d’accès n’est retourné, vérifiez vos informations d’identification pour qu’elles disposent [des autorisations suffisantes](#permissions-to-access-the-cqd-pipeline).

10. Sélectionnez **VAAC ConfigAPI Prod** et accédez à l’onglet **Paramètres** .

- [Compresser](#compress-the-json-query) la requête comme indiqué ci-dessous
- [Coder](#url-encode-the-compressed-json-query) le résultat compressé de l’URL comme indiqué ci-dessous

11. Renseignez votre chaîne [de requête](#constructing-a-valid-query) .
12. Cliquez sur **Envoyer**.

### <a name="reading-the-result"></a>Lecture du résultat

Une fois que vous aurez soumis votre entrée, vous obtiendrez quelques résultats possibles :

- Si l’entrée n’est pas valide, un message d’erreur avec la raison réelle est retourné.
- Si l’entrée est valide, le résultat se présente comme suit :

:::image type="content" source="media/aa-cq-historical-report-postman-04.png" alt-text="Capture d’écran montrant le résultat de la requête avec le champ dataResult":::

Dans ce cas, les données se trouveront dans le champ « dataResult » dans le même ordre que celui demandé dans les attributs de dimension et de mesure de la requête.


### <a name="compress-the-json-query"></a>Compresser la requête JSON

L’API VAAC accepte uniquement les chaînes compressées en GZip ou encodées en Base64 comme entrée.

Recherchez n’importe quel site web pour compresser l’objet blob JSON à l’aide de GZIP ou Base64.

- GZIP : (https://www.multiutil.com/text-to-gzip-compress/)
- Base64 : (https://www.multiutil.com/text-to-base64-converter/)

La sortie GZIP doit ressembler à ceci :
````
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
````

La sortie Base64 doit ressembler à ceci :
````
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
````

### <a name="url-encode-the-compressed-json-query"></a>URL-Encode la requête JSON compressée

La requête JSON compressée GZIP ou Base64 doit être [encodée url](https://meyerweb.com/eric/tools/dencoder/).

La sortie encodée de l’URL GZIP se présente comme suit :
````
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
````

La sortie encodée d’URL en base64 se présente comme suit :
````
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
````

## <a name="version-3xx-history"></a>Historique de la version 3.x.x

Reportez-vous à : Standard automatique Teams & Rapports historiques de file d’attente d’appels - Modifier Log.docx dans le fichier zip téléchargé pour obtenir la liste détaillée des modifications 

|Version  |Date de publication     |Fichier                                                    |Description                                                             |
|:--------|:------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------|
|3.0.5    |9 janvier 2023    |Rapports d’historique des files d’attente de & de la file d’attente d’appels Teams v3.0.5 |Amélioration des destinations de dépassement/délai d’expiration des appels et des visuels de chronologie de l’agent  |
|3.0.4    |18 novembre 2022  |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.4 |Correction de l’erreur, amélioration de la classification des appels, ajout de la légende             |
|3.0.3    |8 novembre 2022   |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.3 |Correction de l’erreur, ajout d’un lien de documentation, requêtes optimisées            |
|3.0.1    |26 octobre 2022   |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.1 |Suppression de l’entrée de source de données de test                                       |
|3.0.0    |25 octobre 2022   |Rapports d’historique des files d’attente d’appels & du standard automatique Teams v3.0.0 |Nouvelle source de données back-end                                                 |
