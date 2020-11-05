---
title: Utilisation de bord dans le rapport Power BI pour afficher le standard automatique & rapport historique de la file d’attente des appels
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Apprenez-en davantage sur l’utilisation du tableau de bord de qualité des appels dans le rapport Power BI pour afficher les données de l’historique des files d’attente et des appels.
ms.openlocfilehash: 874bb87a32895bdec29aab1b0aaee20bdecb0fc2
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908785"
---
# <a name="what-are-the-requirements"></a>Quelle est la configuration requise ? 
Vous devez disposer de Power BI Desktop. Vous pouvez l’installer à partir de [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

Vous pouvez utiliser la version gratuite de Power BI Desktop. La version compatible minimum est 2.85.681.0 (2020 de septembre).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline bord
Le compte que vous utilisez pour afficher le rapport historique de l’analyse de l’état de la fonction AA & doit être autorisé à accéder au pipeline de données bord Pour plus d’informations, reportez-vous au [rôle d’accès bord](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) .

## <a name="installation"></a>Installation 
Les étapes suivantes partent du principe que vous avez déjà installé Power BI Desktop sur l’ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données bord.

Suivez la procédure ci-dessous :
- Téléchargez le [standard automatique d’équipes de bord & le modèle de rapport historique de la file d’attente d’appels](https://aka.ms/TAPAACQAnalytics) , puis enregistrez-le dans un répertoire sur votre ordinateur.
- Double-cliquez sur le modèle et Power BI Desktop doit être lancé.
- Vous serez invité à sélectionner la région de pipeline de données bord. Sélectionnez la région où se trouve votre locataire.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::

 - Vous pouvez voir la région à l’aide de l’applet de requête PS de Skype entreprise Online (Get-CsTenant). Sortie ServiceInstance. 
 La région s’affichera après la mention/like dans cet exemple : microsoftcommunicationsonline/Noam-4a-S7 où la région est Noam.
 - Le rapport s’ouvre avec des exemples de données.
 - Pour afficher vos données, cliquez sur **Actualiser** dans l’onglet Accueil, sous requêtes dans Power bi Desktop.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::

- Vous serez alors invité à vous connecter. Sélectionnez **compte d’organisation** , puis sélectionnez **se connecter**.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::

- Sélectionnez **connexion** et observez l’actualisation des données.

## <a name="data-latency-any-aa--cq-analytics"></a>Latence des données de n’importe quelle analyse CQ & CQ
Les données seront disponibles dans le pipeline de données bord dans un délai de 30 minutes.

Vous devez actualiser les données pour afficher les nouvelles données d’analyse. 

## <a name="customization"></a>Personnalisation 
Vous pouvez personnaliser certains aspects de visualisation des rapports, par exemple en ajoutant ou en supprimant des champs à afficher dans les différentes visualisations, en modifiant le type de graphique, etc.

Vous ne pouvez pas ajouter d’autres champs de données que ceux indiqués dans le rapport.

### <a name="change-color-schema"></a>Modifier le schéma de couleurs 
Les étapes suivantes partent du principe que vous avez déjà effectué les étapes d’installation.

Suivez la procédure ci-dessous :
- Dans le ruban, sélectionnez l' **onglet Affichage** .

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::

- Sélectionnez le modèle de couleurs dans la liste déroulante.

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::


## <a name="cqd-fields-description"></a>Description des champs de bord

|Nom                                    |Type de données                |Description                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|Identité standard automatique                 |chaînes                   |Nom du compte de ressources associé à AA<br>Par exemple : aa_test@microsoft.com|
|Heure de début de la chaîne de standard automatique         |DateHeure                 |Heure de début de la chaîne AA                    |
|Méthode de recherche dans l’annuaire de standard automatique  |chaînes                   |Méthode de recherche du carnet d’adresses la plus récente        |
|Action de transfert de standard automatique          |chaînes                   |Type de destination du transfert d’appel<br>Valeurs possibles ;<br>§ inconnu-le type d’entité n’a pas été spécifié.<br>§ entité utilisateur-utilisateur<br>§ orgaa-entité standard automatique de l’Organisation<br>§ hunt_group-entité de file d’attente des appels<br>§ entité-application voix application<br>§ external_pstn-entité RTC externe<br>§ shared_voicemail-entité de boîte vocale partagée|
|Résultat de l’appel standard automatique              |chaînes                   |Résultat de l’appel :<br>§ inconnu<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|Flux d’appels de standard automatique                |chaînes                   |Encapsule les différents États de l’appel standard automatique.<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ annonce|
|Le standard automatique est-il impliqué              |Boolean                  |Indiqué si AA est impliqué dans l’appel |
|Nombre d’actions d’appelant du standard automatique      |int                      |Nombre d’actions utilisées par l’appelant         |
|Durée en chaîne du standard automatique   |int                      |Durée de l’appel de AA                 |
|Résultat de la file d’attente d’appels                  |String                   |État final appel de la file d’attente<br>valeurs possibles :<br>erreur §<br>§ refusé<br>§ overflown<br>§ a échoué<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Action de l’état final de la file d’attente d’appels           |String                   |Action finale de la file d’attente d’appels<br>valeurs possibles :<br>§ transférer<br>§ déconnexion<br>§ boîte vocale<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ autres|
|Identité de la file d’attente des appels                     |String                   |Nom du compte de ressource joint à la CQ<br>Par exemple : aa_test@microsoft.com|
|La file d’attente d’appels est en mode conférence           |Boolean                  |Définissez sur 1 si le mode conférence est activé sur CQ. |
|Type de cible de file d’attente d’appels                  |String                   |Type de cible de redirection d’appel attendu     |
|Transféré de l’identité de la file d’attente    |Boolean                  |Nom du compte de ressources associé à la CQ à partir de laquelle cet appel a été transféré.<br>Par exemple : aa_test@microsoft.com|
|Nombre d’activations de l’agent de file d’attente d’appels           |int                      |Nombre d’agents disponibles pour cette file d’attente au moment de l’appel |
|Nombre d’agents de file d’attente d’appels                  |int                      |Nombre d’agents affectés à cette file d’attente au moment de l’appel |
|La file d’attente d’appels est-elle impliquée                  |Boolean                  |Si la file d’attente d’appels est liée à cet appel, il est égal à 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensions du modèle de données PowerBI

|Nom                                    |Type de données                |Description                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|Nom AA                                   |chaînes                   |ID standard automatique (ID du compte de ressources) |
|AACallFlow                              |chaînes                   |Encapsule les différents États de l’appel standard automatique.<br> abs_search<br> call_termination<br> call_transfer<br> main_menu<br> user_selection<br> speech_input_confirmation<br> first_level_menu<br> automatic_menu<br>annonce |
|AACallResult                            |chaînes                   |Résultat de l’appel standard automatique :<br> inconnu<br> transferred_to_user<br> transferred_to_operator<br> failover_to_operator<br> user_terminated<br>service_declined  – erreur de configuration AA<br>service_terminated  – Erreurs AA internes<br> failed_to_establish_media<br> terminated_no_operator<br> terminated_transfer_failed<br> terminated_automatic_selection<br> transferred_to_shared_voicemail<br> oaa_chain_too_long<br> oaa_session_too_long          |
|AAChainDuration                         |chaînes                   |Durée de l’appel standard automatique en secondes  |
|AACount                                 |chaînes                   |nombre de standard automatique impliqué dans un appel         |
|AADirectorySearchMethod                 |chaînes                   |Méthode de recherche utilisée dans l’appel :<br> abs_search_dtmf<br> abs_search_extension<br> abs_search_name<br>Temps d’appel de chaîne AAStartTime en UTC      |
|AATransferAction                        |chaînes                   |Destinataire de l’appel :<br> inconnu-le type d’entité n’a pas été spécifié.<br> utilisateur-entité utilisateur<br> AA-entité de standard automatique de l’Organisation<br> CQ-entité de file d’attente d’appels<br>application  application-voix entreprise<br> external_pstn-entité RTC externe<br>shared_voicemail-entité de boîte vocale partagée      |
|PSTNMinutes                             |int                      |Utilisation totale des minutes                          |
|Résultat de la file d’attente d’appels                  |chaînes                   |État final appel de la file d’attente<br>valeurs possibles :<br>erreur <br> refusé<br> overflown<br> a échoué<br> timed_out<br> transferred_to_agent<br>agent_joined_conference    |
|Identité de la file d’attente des appels                     |chaînes                   |Nom du compte de ressource joint à la CQ     |
|Type de cible de file d’attente d’appels                  |chaînes                   |Type de cible de redirection d’appel attendu :<br>utilisateur <br>Point de terminaison d’application <br> autre     |
|Résultat de la file d’attente d’appels                  |chaînes                   |État final appel de la file d’attente<br>valeurs possibles :<br>erreur <br> refusé<br> overflown<br> a échoué<br> timed_out<br> transferred_to_agent<br>agent_joined_conference           |
|Action de l’état final de la file d’attente d’appels           |chaînes                   |Action finale de la file d’attente d’appels<br>valeurs possibles :<br> transférer<br>déconnexion de <br>boîte vocale <br> disconnect_with_busy<br> shared_voicemail<br> failed_to_accept_call<br>ailleurs             |
|Nom de l’agent                              |chaînes                   |Nom d’utilisateur principal               |


### <a name="measures"></a>Mesures

|Nom                                      |Type                       |Description                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|AACallerActionCount                     |int                        |# d’action sélectionnée par l’utilisateur dans AA lors de l’appel  |
|PSTNMinutes                             |int                      |Utilisation totale des minutes                                  |
|TotalCallCount                          |int                      |nombre d’appels                                          |
|Durée d’appel moyenne (secondes)         |int                      |Durée totale des appels dans la file d’attente d’appels en quelques secondes     |


### <a name="power-bi-graph-description-auto-attendant"></a>Standard automatique Description dans Graph Power BI

|Nom                                      |Description                            |
|---------------------------------------:|:-------------------------------------:|
|Source d’appel entrant                    |Répartition des appels par source d’appel interne/externe      |
|Totaux de la méthode de recherche d’annuaires          |Répartition de l’appel par type de recherche                         |
|Action de l’appelant                           |Distribution de l’appel par le destinataire de l’appel                       |
|Résultat de l’appel                             |Répartition de l’appel par état final de l’appel                    |
|Nombre d’actions d’appelant                     |Répartition de l’appel par action au numéro utilisée pendant l’appel  |


### <a name="call-queue"></a>File d’attente d’appels

|Nom                                      |Description                            |
|---------------------------------------:|:-------------------------------------:|
|Source d’appel entrant                    |Répartition des appels par source d’appel interne/externe         |
|Volume d’appels                             |Répartition des appels par file d’attente d’appels                            |
|Résultat de l’appelant                           |Répartition de l’appel par le résultat de l’appel                            |
|Action de total des appels d’expiration/de dépassement de capacité      |Distribution de l’appel non transféré (abandonné) par le résultat de l’appel   |
|Totaux des cibles de transfert/transfert          |Répartition des appels transférés par le résultat d’un appel                  |
|Taux d’appels abandonnés                   |Rapport de réussite au nombre d’appels abandonnés                    |
|Durée de session moyenne (secondes)        |Durée de l’appel en secondes groupées par appels abandonnés/réussis   |



### <a name="agent-timeline"></a>Chronologie de l’agent

|Nom                                                      |Description                            |
|-------------------------------------------------------:|:-------------------------------------:|
|# appels par agent                                        |Répartition de l’appel par file d’attente et par agent                 |
|Durée totale de l’appel (secondes) par agent et file d’attente d’appels   |Durée totale (secondes) d’appel par agent et file d’attente d’appels     |
|Durée d’appel moyenne (secondes) par nom d’agent            |Durée moyenne (secondes) d’un appel par agent                  |



## <a name="known-issues"></a>Problèmes connus
- Pour l’instant, les appels d’attente et de standard automatique affichent l’ID de comptes de ressources à la place des noms de file d’attente/standard automatique.  Pour afficher tout le trafic d’un standard automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources affectés au standard automatique ou à la file d’attente d’appels.
- Pour l’instant, un seul 28 jours d’historique est disponible dans le tableau de bord en tant que données d’identification de l’utilisateur final et sont soumises aux politiques de rétention de confidentialité des données.
