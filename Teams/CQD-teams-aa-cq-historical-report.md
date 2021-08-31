---
title: Utilisation du point de Power BI de recherche pour afficher le Standard automatique & historique de la file d’attente d’appels
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Découvrez comment utiliser le tableau de bord de qualité des appels Power BI rapport pour afficher les données historiques des Standard automatique de la file d’attente d’appels.
ms.openlocfilehash: 73ffd8e993a3dacd0412123d49e19c704df0cb8c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731383"
---
# <a name="what-are-the-requirements"></a>Quelles sont les exigences ? 
Vous devez avoir installé Power BI Desktop installées. Vous pouvez l’installer à partir du [Microsoft Windows Store.](https://aka.ms/pbidesktopstore)

Vous pouvez utiliser la version gratuite de Power BI Desktop. La version minimale compatible est la version 2.85.681.0 (septembre 2020).

## <a name="permissions-to-access-the-cqd-pipeline"></a>Autorisations d’accès au pipeline du DQD
Le compte que vous utilisez pour afficher le rapport historique & données de LQ Analytics doit être autorisé à accéder au pipeline de données du CQD. Pour plus d’informations, reportez-vous au rôle Accès du [CQD.](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

## <a name="installation"></a>Installation 
Les étapes suivantes supposent que vous avez déjà installé Power BI Desktop sur l’ordinateur et que votre compte dispose des autorisations nécessaires pour accéder au pipeline de données du tableau de bord de qualité des données.

Effectuez les étapes suivantes :
- Téléchargez le [modèle de rapport historique de la Teams Standard automatique & de](./aa-cq-cqd-historical-reports.md) la file d’attente d’appels et enregistrez-le dans un répertoire sur votre ordinateur.

- Double-cliquez sur le modèle et vous Power BI Desktop le lancer.

- Vous serez invité à sélectionner la région du pipeline de données du CQD. Sélectionnez la région dans laquelle se trouve votre client.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration.":::

 - Vous pouvez voir la région à l’aide de Skype Entreprise de service PS en ligne (Get-CsTenant). Sortie ServiceInstance. 
 La région s’affichera après le / comme dans cet exemple : 
 
   microsoftligne/noam-4a-s7 où la région est noam.
   
 - Le rapport s’lance avec des exemples de données.
 
 - Pour voir vos propres  données, cliquez sur Actualiser sous l’onglet Accueil sous Requêtes Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration.":::

- Vous serez alors invité à vous connectez. Sélectionnez **le compte de** l’organisation, puis **connectez-vous.**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration.":::

- Sélectionnez **Connecter** et regardez les données s’actualiser.

## <a name="data-latency-any-aa--cq-analytics"></a>Latence des données de n’importe quelle analyse de & du groupe de travail
Les données seront disponibles dans le pipeline de données du CQD dans les 30 minutes.

Vous devez actualiser les données pour voir les nouvelles données d’analyse. 

## <a name="customization"></a>Personnalisation 
Vous pouvez personnaliser certains aspects des visualisations des rapports, par exemple en ajoutant ou en supprimant des champs à montrer dans les différentes visualisations, en modifiant le type de graphique, etc.

Vous ne pouvez pas ajouter d’autres champs de données que ceux fournis dans le rapport.

### <a name="change-color-schema"></a>Modifier le schéma de couleurs 
Les étapes suivantes supposent que vous avez déjà effectué les étapes d’installation.

Effectuez les étapes suivantes :
- Sélectionnez **l’onglet** Affichage du ruban.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration.":::

- Sélectionnez le schéma de couleurs dans la liste drop-down.

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration.":::


## <a name="cqd-fields-description"></a>Description des champs du CQD

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Standard automatique identité de l’entreprise                 |chaîne                   |Nom du compte de ressource joint à AA<br>Exemple : aa_test@microsoft.com|
|Standard automatique début de la chaîne         |DateHeure                 |Heure de début d’une chaîne AA                    |
|Standard automatique de recherche dans l’annuaire  |chaîne                   |Méthode de recherche du dernier carnet d’adresses        |
|Standard automatique action de transfert          |chaîne                   |Type cible de transfert d’appel<br>Valeurs possibles ;<br>§ inconnu - Le type d’entité n’a pas été spécifié<br>§ user - user entity<br>§ orgaa - Entité Standard automatique organisation<br>§ hunt_group - Entité de la file d’attente d’appels<br>Application § - entité d’application vocale<br>§ external_pstn - entité PSTN externe<br>§ shared_voicemail - entité de messagerie vocale partagée|
|Standard automatique’appel              |chaîne                   |Résultat de l’appel :<br>§ inconnu - Échec de l’appel de configuration ou de transfert et le service n’a reçu aucun motif d’échec significatif <br>§ transferred_to_user - Appel transféré vers un utilisateur via la numérotation par nom/extension ou une option de menu configurée <br>§ transferred_to_operator - L’appel a été transféré vers un opérateur configuré, par exemple, si AA est configuré avec un opérateur pour les heures de travail supplémentaires <br>§ failover_to_operator : la récupération de l’opérateur en cas d’échec du transfert ou la reconnaissance du nom ne fonctionne pas après trois tentatives<br>§ user_terminated - L’appelant a terminé l’appel <br>§ service_declined - Appel refusé par le service, cela peut se produire si le service ne parvient pas à récupérer Standard automatique configuration <br>§ service_terminated : le service principale a mis fin à l’appel, peut-être en cas d’échec du transfert vers la cible et qu’aucun opérateur n’est configuré comme une récupération. <br>§ failed_to_establish_media - Échec de la mise en place des médias entre l’appelant et le service <br>§ terminated_no_operator - Échec de la reconnaissance des noms après trois tentatives et aucun opérateur n’est configuré <br>§ terminated_transfer_failed - Échec du transfert à la cible et aucun opérateur n’est configuré <br>§ terminated_automatic_selection - Si aucune action n’est configurée pendant ou après les heures d’ouverture, l’appel prend fin par défaut. <br>§ transferred_to_shared_voicemail - Appel transféré vers la messagerie vocale partagée si configuré en tant que cible <br>§ oaa_chain_too_long - Lorsqu’une chaîne de Standard automatique excède cinq attendants automatiques l’un après l’autre, l’appel se termine pour éviter les boucles d’appel possibles <br>§ oaa_session_too_long - L’appel a dépassé la durée maximale de la session et a dépassé le délai d’attente |
|Standard automatique la Flow                |chaîne                   |Encapsule les différents états d’un Standard automatique<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ annonce|
|Is Standard automatique Involved              |Boolean                  |Indiqué si AA participer à l’appel |
|Standard automatique d’action de l’appelant      |int                      |Nombre d’actions utilisées par l’appelant         |
|Standard automatique durée de la chaîne   |int                      |Durée de l’appel dans AA                 |
|Résultat des appels de la file d’attente d’appels                  |String                   |État final de l’appel de la file d’attente d’appels<br>valeurs possibles :<br>§ erreur<br>§ refusé<br>§ au-dessus<br>L’échec de §<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|Action d’état final de la file d’attente d’appels           |String                   |Action finale de la file d’attente d’appels<br>valeurs possibles :<br>§ avancer<br>§ déconnecter<br>§ messagerie vocale<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ autre|
|Identité de la file d’attente d’appels                     |String                   |Nom du compte de ressource joint au QQ<br>Exemple : aa_test@microsoft.com|
|La file d’attente d’appels est en mode conférence           |Boolean                  |Définir sur 1 si le mode conférence est activé sur le QQ |
|Type cible de la file d’attente d’appels                  |String                   |Type cible de redirection d’appel attendu     |
|Transfert de l’identité de la file d’attente d’appels    |Boolean                  |Nom du compte de ressource joint au QQ à partir duquel cet appel a été transféré<br>Exemple : aa_test@microsoft.com|
|Call Queue Agent Opt In Count           |int                      |Nombre d’agents disponibles dans cette file d’attente au moment de l’appel |
|Nombre d’agents de la file d’attente d’appels                  |int                      |Nombre d’agents affectés à cette file d’attente au moment de l’appel |
|La file d’attente d’appels est-elle concernée ?                  |Boolean                  |Si la file d’attente d’appels est impliquée dans cet appel, égalez 1 |


### <a name="powerbi-data-model-dimensions"></a>Dimensions du modèle de données PowerBI

|Nom                                    |Type de données                |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|Nom AA                                   |chaîne                   |Standard automatique ID de compte de ressource |
|AACallFlow                              |chaîne                   |Encapsule les différents états d’un Standard automatique<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>annonce |
|AACallResult                            |chaîne                   |Résultat de l Standard automatique’appel :<br>§ inconnu<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – erreur de configuration AA<br>§ service_terminated – Erreurs internes dans les AA<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |chaîne                   |Durée d’Standard automatique’appel en secondes  |
|AACount                                 |chaîne                   |# des Standard automatique participer à un appel         |
|AADirectorySearchMethod                 |chaîne                   |Méthode de recherche utilisée lors d’un appel :<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |chaîne                   |Heure d’appel au UTC                            |
|AATransferAction                        |chaîne                   |Destinataire de l’appel :<br>§ inconnu - Le type d’entité n’a pas été spécifié<br>§ user - user entity<br>§ AA - Entité Standard automatique’organisation<br>§ CQ - Entité de la file d’attente d’appels<br>Application § - entité d’application vocale<br>§ external_pstn - entité PSTN externe<br>§ shared_voicemail - entité de messagerie vocale partagée      |
|PSTNMinutes                             |int                      |Utilisation totale des minutes                          |
|Résultat des appels de la file d’attente d’appels                  |chaîne                   |État final de l’appel de la file d’attente d’appels<br>valeurs possibles :<br>§ erreur<br>§ refusé<br>§ au-dessus<br>L’échec de §<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|Identité de la file d’attente d’appels                     |chaîne                   |Nom du compte de ressource joint au QQ     |
|Type cible de la file d’attente d’appels                  |chaîne                   |Type cible de redirection d’appel attendu :<br>§ Utilisateur<br>§ Application Endpoint<br>§ Autre     |
|Résultat des appels de la file d’attente d’appels                  |chaîne                   |État final de l’appel de la file d’attente d’appels<br>valeurs possibles :<br>§ erreur<br>§ refusé<br>§ au-dessus<br>L’échec de §<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|Action d’état final de la file d’attente d’appels           |chaîne                   |Action finale de la file d’attente d’appels<br>valeurs possibles :<br>§ avancer<br>§ déconnecter<br>§ messagerie vocale<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ autre             |
|Nom de l’agent                              |chaîne                   |Nom d’utilisateur utilisateur (UPN)               |


### <a name="measures"></a>Mesures

|Nom                                      |Type                       |Description                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |#of action selected by user in AA during the call  |
|PSTNMinutes                             |int                      |Utilisation totale des minutes                                  |
|TotalCallCount                          |int                      |Nombre d’appels                                          |
|Durée moyenne de l’appel( secondes)         |int                      |Durée totale des appels de la file d’attente en secondes     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI description du graphique Standard automatique

|Nom                                      |Description                            |
|:---------------------------------------|:--------------------------------------|
|Source d’appel entrant                    |Distribution de l’appel par source d’appel interne/externe      |
|Totaux des méthodes de recherche dans l’annuaire          |Distribution de l’appel par type de recherche                         |
|Action de l’appelant                           |Distribution de l’appel par récepteur d’appel                       |
|Résultat de l’appel                             |Distribution de l’appel par état final de l’appel                    |
|Nombre d’actions de l’appelant                     |Distribution de l’appel par action de numéro utilisée pendant l’appel  |


### <a name="call-queue"></a>File d’attente d’appels

|Nom                                      |Description                            |
|:---------------------------------------|:--------------------------------------|
|Source d’appel entrant                    |Distribution de l’appel par source d’appel interne/externe         |
|Volume d’appels                             |Distribution des appels par files d’attente d’appels                            |
|Résultat de l’appelant                           |Distribution de l’appel par résultat d’appel                            |
|Action du total des appels en dépassement de délai/dépassement de capacité      |Distribution de NON-forwardé(abandonné) appel par résultat d’appel   |
|Total cible de transfert/transfert          |Distribution de l’appel transmis par résultat d’appel                  |
|Taux d’appels abandonnés                   |Ratio du nombre d’appels réussis à l’abandon                    |
|Durée moyenne de la session (secondes)        |Durée des appels en secondes groupées par appels abandonnés/réussis   |



### <a name="agent-timeline"></a>Chronologie de l’agent

|Nom                                                      |Description                            |
|:-------------------------------------------------------|:--------------------------------------|
|# appels par l’agent                                        |Distribution de l’appel par file d’attente d’appels et par agent                 |
|Durée totale des appels (secondes) par l’agent et la file d’attente d’appels   |Durée totale (secondes) des appels par l’agent et la file d’attente d’appels     |
|Durée moyenne de l’appel (secondes) par nom de l’agent            |Durée moyenne (secondes) d’un appel par un agent                  |



## <a name="known-issues"></a>Problèmes connus
- Pour l’instant, la file d’attente d’appels et le attendant automatique indiquent l’ID des comptes de ressources au lieu des noms de la file d’attente/du personnel de service automatique.  Pour afficher tout le trafic d’un attendant automatique ou d’une file d’attente d’appels, vous devez sélectionner tous les comptes de ressources attribués au attendant automatique ou à la file d’attente d’appels.

- Actuellement, 28 jours d’historique sont disponibles dans le tableau de bord sous la mesure où les données de la file d’attente des appels/du attendant automatique sont considérées comme des informations d’identification de l’utilisateur final et sont soumises à des stratégies de rétention des données.
