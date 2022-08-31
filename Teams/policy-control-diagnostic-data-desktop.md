---
title: Données de diagnostic du client de bureau requises pour Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Une liste des propriétés de bureau et des événements de contrôles des stratégies pour Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bb9e4dfd604728ea1714d3ab2e663dab3b5c3c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608921"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Données de diagnostic de bureau requises pour Microsoft Teams

L’article suivant contient une liste des événements de bureau Microsoft Teams et les listes des propriétés collectées par chaque événement.

Pour plus d’informations sur les données de diagnostic, notamment sur la façon de contrôler les données de diagnostic envoyées à Microsoft, consultez [Données de diagnostic envoyées de l’application Teams à Microsoft](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft). Pour afficher les données de diagnostic envoyées à Microsoft, vous pouvez utiliser la [Visionneuse de données de diagnostic](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="events"></a>Événements

> [!NOTE]
> Il existe des propriétés communes pour tous les événements répertoriés ci-dessous, pour les découvrir, consulter la section [Propriétés envoyées avec tous les événements](#properties-sent-with-all-events).

### <a name="logging"></a>Journalisation

> [!NOTE]
> Si vous souhaitez en savoir plus sur les propriétés des événements de journalisation, consultez la section [Propriétés envoyées avec les événements de journalisation](#properties-sent-with-logging-events).

- **adal-anonymous-mac.ts: this.logger.logError** : enregistre le fait qu’une erreur sso générique se soit produite lors de la connexion anonyme sur un appareil Mac.
- **adalAnonymousUtil.ts:loggingService.getInstance** : enregistre une déclaration d’erreur dans la journalisation selon laquelle l’application n’a pas pu lancer l’authentification utilisateur anonyme.
- **adal-anonymous-windows.ts:this.logger.logError** : enregistre le fait qu’une erreur sso générique se soit produite lors de la connexion anonyme sur un appareil Windows.
- **adalBase.ts:this.loggingService.logError** : enregistre les informations nécessaires pour déterminer si le profil utilisateur est null ou vide.
- **adal-impl-mac.ts:this.loggingService.logError** : enregistre l’occurrence d’un problème pendant l’analyse de la télémétrie, reçue lors de l’authentification ou une erreur sso générique apparue lors de la connexion sur un appareil Mac.
- **adal-rigel-windows.ts:this.logger.logError** : une déclaration de journalisation générale indiquant qu’une erreur sso générique s’est produite lors de la connexion à notre appareil de salle de réunion.
- **adal-sso-windows.ts:this.loggingService.logError** : enregistre une erreur sso générique apparue lors de la connexion à un appareil Windows, des erreurs lors du lancement du service de discussion ou des informations d’échec de connexion.
- **appOnlineService.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur due à des paramètres qui n’ont pas pu être analysés au démarrage ou lors du téléchargement de l’authentification pré-utilisateur ou des paramètres préautorisés.
- **appStart.ts:loggingService.logError** : enregistre l’occurrence d’une erreur lorsque l’application n’a pas pu se lancer, une erreur d’espace disque, une erreur de certificat valide ou lorsque le certificat correct n’a pas été trouvé et que l’application redémarre.
- **browserWindowHttp.ts:this.loggingService.logError** : enregistre des informations pour indiquer que l’application n’a pas pu être mise à jour en raison de problèmes liés au système de fichiers.
- **contextInstallService.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur dans les cas suivants :
  - tentative d’analyse, de lecture d’un fichier ou de résolution d’une URL essentielle pour la fonctionnalité d’installation contextuelle.
  - le raccourcisseur d’URL tente d’exécuter la fonctionnalité d’installation contextuelle.
- **crashManager.ts:loggingService.logError** : enregistre des informations pour déterminer la cause d’une erreur lorsque l’application se bloque.
- **localStorageService.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur lorsque les données de démarrage essentielles ne se chargent pas correctement pour exécuter l’application.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance** : enregistre les informations concernant l’erreur lorsque l’application se bloque.
- **multiWindowManager.ts:this.logError** : enregistre l’occurrence d’une erreur lorsque les données de démarrage essentielles ne se chargent pas correctement pour exécuter l’application.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError** : cet événement enregistre l’occurrence d’une erreur lors de la tentative de lancement d’une notification d’échec.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur lors de la tentative de connexion à une réunion à l’aide du complément de réunion Outlook.
- **recoveryManager.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur lors des annulations de mise à jour.
- **renderer\startPage\startPage.ts:this.logger.logError** : enregistre l’occurrence d’une erreur avec la page de démarrage de l’application.
- **settingsService.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur avec les paramètres de l’application.
- **updateInfo.ts:loggingService.getInstance** : enregistre l’occurrence d’une erreur lors de la transmission des mises à jour.
- **updatenotification.js:this._loggingService.logError** : enregistre l’occurrence des problèmes d’espace disque.
- **utility.ts:loggingService.logError** : enregistre une erreur d’accès à un fichier local (un fichier dans l’application).
- **utility.ts:loggingService.getInstance** : enregistre une erreur dans l’espace disque disponible, des problèmes d’affichage, des problèmes d’URL, des problèmes de cookies, des protocoles ou des problèmes de clé de registre sur la machine pour charger l’application.
- **windowmanager.js:this._loggingService.logError** : enregistre l’occurrence des problèmes de cookies, des problèmes d’écran blanc, des problèmes de communication entre le bureau et shell, des problèmes d’URL, des erreurs de chargement des messages de page, des erreurs de rendu de processus et des problèmes de connectivité réseau.
- **windowmanager.js:loggingService.getInstance** : enregistre des informations pour indiquer quand la fenêtre de récupération ne peut pas être affichée.

### <a name="outlook-addin"></a>Complément Outlook

> [!NOTE]
> Si vous souhaitez en savoir plus sur les propriétés des événements de complément Outlook, consultez la section [Propriétés envoyées avec les événements de complément Outlook](#properties-sent-with-outlook-addin-events).

- **joinmeetingoperation** : enregistre les informations nécessaires pour joindre un utilisateur à une réunion.
- **meetingaddinapplifecycle** : enregistre des informations sur l’état de l’application, telles que Lancer ou Quitter.
- **meetingaddinloadtime** : enregistre le temps nécessaire pour le chargement des informations de réunion à partir d’Outlook.
- **openmeetingoperation** : enregistre les informations nécessaires pour ouvrir une réunion programmée.
- **savemeetingoperation** : enregistre les informations nécessaires pour enregistrer la réunion lors de sa planification.

### <a name="scenario"></a>Scénario

> [!NOTE]
> Si vous souhaitez en savoir plus sur les propriétés des événements de scénario, consultez la section [Propriétés envoyées avec les événements de scénario](#properties-sent-with-scenario-events).

- **desktop_app_load** : enregistre les informations nécessaires pour déterminer si l’application de bureau a été lancée, si le service doit être initialisé et s’il peut être initialisé.
- **desktop_app_not_ready** : enregistre les informations nécessaires qui permettent de déterminer que l’application de bureau n’est pas prête à fonctionner.
- **desktop_install** : enregistre les informations nécessaires pour déterminer si l’application de bureau a correctement été installée ou si son installation a échoué.
- **desktop_previous_lifecycle_invalid** : enregistre les informations nécessaires qui permettent de déterminer que l’application de bureau a redémarré après son exécution précédente, puis s’est bloquée.

### <a name="tracking"></a>Suivi

> [!NOTE]
> Si vous souhaitez en savoir plus sur les propriétés des événements de suivi, consultez la section [Propriétés envoyées avec les événements de suivi](#properties-sent-with-tracking-events).

- **deeplink_scenario_missing** : Teams a été lancé à partir d’un lien profond, mais la télémétrie ou le diagnostic n’est pas présent.
- **desktop_app_initialized** : enregistre les informations nécessaires pour déterminer si l’application démarre correctement lorsque l’application de bureau est initialisée.
- **desktop_app_quit_exception** : l’application a cessé de fonctionner lors de la tentative de fermeture.
- **desktop_blankScreenDetected** : enregistre les informations nécessaires qui permettent de déterminer les erreurs lorsque l’application de bureau affiche un écran vide.
- **desktop_blankScreenDetectedAfterRepaint** : détecte que la page est vide lors de la détection d’une tentative de rendu.
- **desktop_blankScreenRecoveredAfterRepaint** : récupère un problème de rendu pour lequel l’écran n’a pas été rendu plus tôt.
- **desktop_configuration_failed_to_save** : collecte les informations nécessaires pour déterminer les erreurs de configuration lorsque les paramètres du bureau n’ont pas pu être enregistrés.
- **desktop_navigation_error_recovery** : collecte les informations nécessaires pour déterminer les erreurs de navigation sur le bureau lorsqu’une page ne se charge pas après cinq tentatives.
- **desktop_previous_gpu_crashed** : enregistre les informations nécessaires pour déterminer les erreurs de l’unité de traitement graphique lorsque le bureau se bloque.
- **desktop_previous_plugin_host_crashed** : collecte les informations nécessaires pour déterminer les problèmes de pile de supports associés aux pannes des applications de bureau.
- **desktop_recovery_cleared_user_data** : enregistre que l’application s’est bloquée plusieurs fois et que l’application a dû vider le cache local pour effectuer une récupération.
- **desktop_settings_blank_on_load** : erreur qui indique que les paramètres de l’application ne sont pas présents.
- **desktop_settings_failed_to_load** : collecte les informations nécessaires pour déterminer la cause de l’échec du chargement des paramètres du bureau.
- **desktop_silent_restart** : la mise à jour du client est effectuée et le client est mis à jour sans déranger l’utilisateur.
- **desktop_terminated** : enregistre les informations nécessaires pour déterminer si la communication inter-processus est déconnectée lorsque l’utilisateur ferme l’application de bureau.
- **desktop_uncaught_exception** : appel de fonction sur un objet non défini, qui entraînera un blocage ou un redémarrage de l’application.
- **desktop_write_storage_failed** : enregistre les informations nécessaires pour déterminer les erreurs de disque lorsque l’application de bureau ne parvient pas à écrire sur le stockage.
- **registration_failed** : enregistre les informations nécessaires pour résoudre les échecs d’inscription des compléments.
- **registration_success** : enregistre les informations nécessaires pour déterminer si les inscriptions de compléments ont abouti.
- **security_unsupported_ipc_channel** : le message interprocessus non autorisé était un message entrant.
- **sfb_running_not_connected** : détecte que l’application Skype Entreprise n’est pas en cours d’exécution.
- **sfb_not_running** : enregistre le fait que « l’attente de la réponse » de l’appel à Skype Entreprise a expiré.
- **sfb_never_replied** : ne détecte aucune réponse d’API lors de la communication avec Skype Entreprise.
- **server_error_hit** : détecte une erreur des canaux ipc communiquant avec Skype Entreprise.
- **unexpected_sfb_ipc_disconnection** : enregistre les informations nécessaires pour déterminer un échec de connexion au service.
- **unregister_failed** : enregistre les informations nécessaires pour déterminer les erreurs lors de la désinscription du complément de réunion Outlook.

## <a name="userbi-panelaction"></a>UserBI panelaction

> [!NOTE]
> Si vous souhaitez en savoir plus sur les propriétés des événements panelaction UserBI, consultez la section [Propriétés envoyées avec les événements panelaction UserBI](#properties-sent-with-userbi-panelaction-events).

- **inlinereply** : enregistre des informations pour déterminer si un utilisateur a répondu à partir de la notification.
- **toastclick** : enregistre le clic d’un utilisateur pour accéder à l’entrée de message des notifications toast pour surveiller le SLA de service et pour charger la réponse appropriée à la notification toast.
- **toastdismiss** : enregistre les informations nécessaires pour déterminer les erreurs et les retards lorsque l’utilisateur rejette le rendu d’une notification toast.

- **toast_skip** : enregistre les informations nécessaires pour éviter de transmettre une notification toast différée.
- **toasttimeout** : enregistre les informations nécessaires pour déterminer les erreurs et les retards lorsque le rendu d’une notification toast a expiré.

### <a name="userbi-panelview"></a>UserBI panelview

> [!NOTE]
> Si vous souhaitez en savoir plus sur les propriétés des événements panelview UserBI, consultez la section [Propriétés envoyées avec les événements panelview UserBI](#properties-sent-with-userbi-panelview-events).

- **toastshow** : enregistre les informations nécessaires pour déterminer si une notification toast a été rendue.

## <a name="property-lists"></a>Listes des propriétés

### <a name="properties-sent-with-all-events"></a>Propriétés envoyées avec tous les événements

| Nom de la propriété                              | Description                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | Heure de création de l’événement                                              |
| EventInfo_Name                             | Nom de l’événement : utilisé pour différencier les types d’événements             |
| EventInfo_BaseType/name                    | Type d’événement : utilisé pour différencier les types d’événements dans un événement |
| EventInfo_Sequence                         | Séquence de l’événement                                              |
| userAgent                                  | Chaîne de l’agent navigateur                                               |
| userpdclevel                               | Paramètre de contrôle des données de confidentialité de l’utilisateur                           |
| eventpdclevel                              | Niveau de catégorisation du contrôle des données de confidentialité de l’événement             |
| AppInfo_Language                           | Langue de l’application                                                       |
| clientType/AppInfo_ClientType              | Type de client sur lequel l’application s’exécute                               |
| environment/AppInfo_Environment            | Environnement technique qui a répondu à la demande de l’utilisateur               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | Version de l’application                               |
| buildtime                                  | horodatage de la création de l’application dans les systèmes techniques            |
| osversion/DeviceInfo_OsVersion             | Version du système d’exploitation                                                         |
| AppInfo_ProcessArchitecture                | Architecture système (32 bits/64 bits)                                  |
| preferredLocales                           | Paramètres régionaux préférés de l’utilisateur                                      |
| locale/AppInfo_Locale                      | Paramètres régionaux de l’application                                                         |
| os/DeviceInfo_OsName                       | Nom du système d’exploitation                                                            |
| UserInfo_Language                          | Langue utilisateur sélectionnée                                             |
| UserInfo_Id                                | ID de l’utilisateur                                                            |
| UserInfo_TenantId/TenantId                 | Identifiant du client                                                          |
| ring/UserInfo_Ring                         | Concept qui permet de fournir une application de manière progressive          |
| region                                     | Zone du centre des données ayant répondu à la demande de l’utilisateur                       |
| UserInfo_ConfigIds/UserInfo_Etag           | Identifiant qui permet d’identifier les utilisateurs dans différentes expériences ou déploiements     |
| DeviceInfo_BrowserName                     | Nom du navigateur                                                       |
| DeviceInfo_BrowserVersion                  | Version du navigateur                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | Identifiant qui permet d’identifier l’appareil                                  |
| totalMemory                                | Mémoire matérielle de l’appareil                                      |
| cores                                      | Cœurs matériels de l’appareil                                       |
| cpuspeed                                   | Vitesse du processeur de l’appareil                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | Architecture du processeur de l’appareil                                     |
| UserRole                                   | Permet d’identifier le rôle de l’utilisateur dans un client                               |
| DeviceInfo_WindowsMode                     | Permet d’identifier le mode de sécurité Windows                               |
| desktopSession/Session_Id                  | Permet d’identifier une session                                           |
| dbOpen                                     | Capture l’état de la base de données locale                               |
| UserInfo_Upn                               | Hachage unilatéral de l’identifiant de l’utilisateur                                  |

### <a name="properties-sent-with-logging-events"></a>Propriétés envoyées avec les événements de journalisation

| Nom de la propriété         | Description                                                        |
|-----------------------|--------------------------------------------------------------------|
| message               | Capture un message détaillé concernant le journal                          |

### <a name="properties-sent-with-scenario-events"></a>Propriétés envoyées avec les événements de scénario

| Nom de la propriété                     | Description                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | État d’un scénario                                                               |
| Scenario_Step                     | Étape d’un scénario                                                                 |
| sequence                          | Numéro de séquence du scénario                                                    |
| delta                             | Temps nécessaire pour effectuer les différentes étapes d’un scénario                               |
| elapsed                           | Temps écoulé depuis le début du scénario                                                    |
| scenario                          | Identifiant unique d’un scénario                                                       |
| Scenario_Name                     | Nom du scénario                                                               |
| errorInfo                         | Informations sur l’erreur qui aurait pu survenir lors d’un scénario                       |
| session                           | Identifiant de session unique                                                                  |
| freeMemory                        | Capture la quantité de mémoire disponible                                                     |
| processMemory                     | Capture la mémoire du processus                                                            |
| scenarioDelta                     | Capture la différence de temps entre deux étapes du scénario                                   |
| Session_DesktopId                 | Identifiant de session unique                                                                  |
| machineLocked                     | Détecte si la machine était verrouillée ou non                                          |
| windowIsVisible                   | Détecte si la fenêtre de l’application était visible pour être utilisée                                      |
| appStates/webAppStates            | enregistre une liste des états d’application que l’application a rencontrés. Cela permet d’examiner les incidents, car nous pouvons voir dans quel état l’application se trouvait |
| crashDesktopSession               | Capture l’identifiant de la session bloquée                                                 |
| appRuntime                        | Capture le temps d’exécution de l’application                                                        |
| diagnosticEvents                  | Les 50 derniers événements de diagnostic d’application web avant le blocage de l’application                                 |
| activities                        | Les 50 derniers noms de scénario utilisateur qui se sont produits avant le blocage                            |
| crashSession                      | Capture l’identifiant de la session bloquée                                                 |
| crashId                           | Capture l’identifiant de la session bloquée                                                 |
| isPreviousLifecycleValid          | Détermine si l’application précédente a été entièrement initialisée et terminée avec succès             |
| isSettingValid                    | Détermine si les paramètres de préautorisation sont valides                                                 |
| rollbackReason                    | Raison pour laquelle l’application a été annulée                                            |
| deeplinkType                      | Type de lien profond                                                               |
| watchdogCrash                     | Détermine si l’application a cessé de fonctionner en raison d’un blocage                                                    |
| protocols                         | Protocole utilisé pour lancer l’application                                                    |
| electronBuild                     | La version build de l’application Electron                                                      |
| distribution                      |  Détermine si Teams a été installé via un fichier exe, msi, dmg, pkg, etc.                    |
| updateTimeOfDay                   | Heure à laquelle l’application a été mise à jour                                                           |
| launchPath                        | Détermine si Teams est installé dans %LOCALAPPDATA%, %PROGRAMFILES% ou dans d’autres emplacements   |
| loggedIn                          | Détermine si l’utilisateur était connecté                                                          |
| envType/complianceEnvironmentType | Cloud commercial ou privé (par exemple DoD, GCC-High, etc.)                              |
| cpuusage                          | Utilisation du processeur                                                                          |
| installationSource                | Type d’installation utilisée par l’utilisateur                                                      |
| adalVersion                       | Version de la bibliothèque d’authentification                                                        |
| asyncStart                        | Détermine si l’application utilise un démarrage synchrone ou asynchrone                                 |
| attempts                          | Nombre de tentatives de vérification en ligne effectuées pour l’utilisateur avant d’afficher un écran de blocage |

### <a name="properties-sent-with-tracking-events"></a>Propriétés envoyées avec les événements de suivi

| Nom de la propriété                      | Description                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | Capture le nom de l’événement de suivi                                              |
| numVisibleNotifications            | Nombre de notifications d’application visibles                                      |
| giphyEnabled                       | Détermine si le service giphy a été activé                                                |
| error                              | Capture les informations sur l’erreur liée à l’événement de suivi                             |
| method                             | Méthode de protocole GET ou POST                                                      |
| channel                            | Capture le canal de communication inter-processus dans l’application                      |
| windowTitle                        | Type de fenêtre d’affichage associée à l’événement                                     |
| message                            | Le type de message d’erreur                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | Capture l’identifiant unique à des fins de débogage de session |
| responseCode                       | Capture le code de réponse pour l’appel de service                                      |
| errorUrl                           | L’URL dont le chargement a échoué                                                      |
| errorCode                          | Capture le code d’erreur                                                              |
| ssoEventData                       | État et statut d’authentification                                                  |
| correlationId                      | ID pour corréler les événements avec le côté service à des fins de débogage                      |
| errorDescription                   | Capture la description du code d’erreur                                            |
| source                             | Méthode pour obtenir l’application Teams et à partir de quel type de package Teams a été installé       |
| windowIsDestroyed                  | État True/False des fenêtres d’application pendant l’événement                             |
| windowIsFocused                    | État True/False des fenêtres d’application pendant l’événement                             |
| windowIsVisible                    | Détermine si l’application était visible lorsque l’événement s’est produit                                  |
| windowIsMinimized                  | État True/False des fenêtres d’application pendant l’événement                             |
| windowIsMaximized                  | État True/False des fenêtres d’application pendant l’événement                             |
| windowIsFullscreen                 | État True/False des fenêtres d’application pendant l’événement                             |
| distSrc                            | Capture la source de distribution de l’utilisateur qui utilise l’application                    |
| retries                            | Nombre de tentatives de connexion à un point de terminaison                            |
| uses_slimcore                      | True ou False si l’appel web utilise Slimcore                                      |
| persistCookieExpiresIn             | Temps de validité restant du cookie d’application web                             |
| tenantName                         | Nom du client pour l’utilisateur de l’application                                       |
| appStartReason                     | Détermine comment la session d’application a démarré, par exemple initiée par l’utilisateur, après la mise à jour, etc. |
| machineLocked                      | Détermine si la machine a été verrouillée ou non pendant l’événement                        |
| data                               | Capture des données techniques pour l’enquête concernant les scénarios                               |
| appRuntime                         | Capture le temps d’exécution de l’application                                                      |
| activities                         | Les 50 derniers noms de scénario utilisateur qui se sont produits avant le blocage                          |
| timeSinceActivity                  | Temps écoulé depuis la dernière activité de l’utilisateur                                                    |
| appStates                          | Enregistre une liste des différents états d’application de l’application de bureau, ce qui facilite les enquêtes sur les pannes car cela indique l’état dans lequel se trouvait l’application de bureau |
| timeSinceAppState                  | Temps écoulé depuis le dernier changement de l’état de l’application                                                 |
| webAppStates                       | Enregistre une liste des différents états d’application du client web, ce qui facilite les enquêtes sur les pannes car cela indique l’état dans lequel se trouvait l’application client web |
| timeSinceWebAppState               | Temps écoulé depuis le dernier changement de l’état de l’application web                                             |
| diagnosticEvents                   | Les 50 derniers événements de diagnostic d’application web avant le blocage de l’application                               |
| timeSinceLastDiagnosticEvent       | Temps écoulé depuis le dernier événement de diagnostic envoyé                                            |
| timeSinceSecondLastDiagnosticEvent | Temps écoulé depuis l’envoi de l’avant-dernier événement de diagnostic                                     |
| appInitialized                     | Détermine si l’application web a démarré                                               |
| targetVersion                      | La version de l’application va être mise à jour vers                                    |
| port                               | Numéro de port de messagerie Internet                                                     |
| originalUrl                        | Emplacement d’origine de la page en cours de rendu                                         |
| deeplinkId                         | GUID pour le type de destination du lien Teams                                          |
| appSessionEnd                      | Détermine si l’événement s’est produit à la fin de la session d’application                             |
| eventData                          | Capture l’état de la machine et la configuration de l’application pour permettre le débogage en cas de problèmes        |
| deeplinkType                       | Type de lien profond (chat, réunion, canal)                                    |
| previousUpdateUrl                  | Emplacement dans lequel l’application a récupéré dernière mise à jour                        |
| previousUpdateVersion              | La dernière version de l’application a été mise à jour vers                                          |
| previousUpdateTime                 | Date de la dernière mise à jour des binaires de l’application                                      |
| protocol                           | Type de gestionnaire pour le lien, comme un fichier ou une image                                     |
| files                              | Type de fichier associé à un événement, comme le cache d’application ou le cache GPU    |
| Perf_WorkingSetSizeKB              | Taille de la mémoire cache                                                             |
| isTimeboxingWebAppInitialize       | Détermine si l’application a été initialisée avant que le compteur de la zone de temps ne soit épuisé                          |
| isExp                              | Détermine si la version de l’application utilisée fait partie d’un test                          |
| deviceType                         | Capture le type d’appareil                                                      |
| sanitizedErr                       | Capture la version épurée des informations concernant les erreurs                              |
| rigelVersion                       | Capture la version de l’appareil rigel                                                 |
| DeviceInfo_OsSku                   | Capture les informations concernant la référence SKU du système d’exploitation                                                      |
| isLoggedOut                        | Détecte si l’utilisateur est déconnecté                                               |
| complianceEnvironmentType          | Cloud commercial ou privé (par exemple DoD, GCC-High, etc.)                           |
| restartTimes                       | Heures exactes des redémarrages précédents                                                 |
| Skype_ResultCode                   | Capture le résultat de la communication d’interopérabilité entre Skype et Teams                 |
| cpumodel                           | Capture le modèle de processeur                                                            |
| isSlimCoreRunningOutproc           | Détermine si le composant Slimcore fonctionne dans son propre processus                         |
| isSlimCoreStartedAsync             | Type de lancement de la pile audio/vidéo (A/V) interne                               |
| networkState                       | Capture l’état du réseau                                                    |
| desktopBuildAge                    | Quelle est la version de l’application au moment de l’événement                                   |
| vdiMode                            | Détecte si l’application s’exécute en mode VDI                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>Propriétés envoyées avec les événements PanelView UserBI

| Propriété           | Description                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | URI du panneau livré à l’utilisateur                   |
| Panel_Type         | Type de panneau auquel l’utilisateur accède                          |
| Team_Id            | ID de l’équipe dans laquelle l’action a été effectuée par l’utilisateur |
| Thread_Id          | ID du thread auquel l’utilisateur a accédé               |
| Panel_PreviousUri  | URI du panneau précédent                                |
| Panel_Region       | Zone dans laquelle le panneau était hébergé dans l’application             |
| Panel_LaunchMethod | méthode par laquelle le panneau été démarré              |
| Panel_PreviousType | Type du panneau précédent                               |
| Thread_Type        | Type de thread auquel l’utilisateur a accédé                          |
| Panel_LaunchSource | information de source du panneau démarré        |
| Tab_Type           | Type de l’onglet auquel l’utilisateur a accédé                         |
| Team_Type          | Type d’équipe à laquelle l’utilisateur a accédé                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>Propriétés envoyées avec les événements panelaction UserBI

| Nom de la propriété         | Description                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | URI de la ressource accédée par l’action de l’utilisateur                  |
| Panel_Uri             | URI du panneau livré à l’utilisateur                             |
| Action_Gesture        | Type de mouvement effectué par l’utilisateur sur l’application                       |
| Action_ScenarioType   | Regroupement de fonctionnalités liées à la métrique commerciale pour la fonctionnalité       |
| Panel_Type            | Type de panneau auquel l’utilisateur accède                                    |
| Action_Outcome        | Résultat de l’action effectuée par l’utilisateur                            |
| Team_Id               | ID de l’équipe dans laquelle l’action a été effectuée par l’utilisateur           |
| Module_Type           | Type de module qui a hébergé l’action de l’utilisateur                        |
| Module_Name           | Nom du module qui a hébergé l’action de l’utilisateur                        |
| Module_Summary        | Résumé du module qui a lancé l’action de l’utilisateur                       |
| Thread_Id             | ID du thread auquel l’utilisateur a accédé                         |
| Panel_PreviousUri     | URI du panneau précédent                                          |
| Panel_Region          | Zone dans laquelle le panneau était hébergé dans l’application                       |
| Panel_LaunchMethod    | méthode par laquelle le panneau été démarré                        |
| Panel_PreviousType    | Type du panneau précédent                                         |
| Thread_Type           | Type de thread auquel l’utilisateur a accédé                                    |
| Module_State          | État du module auquel l’utilisateur a accédé                               |
| Action_Scenario       | Fonctionnalité dans un groupe de fonctionnalités liées à la métrique commerciale |
| Panel_LaunchSource    | information de source du panneau démarré                  |
| Tab_Type              | Type de l’onglet auquel l’utilisateur a accédé                                   |
| Team_Type             | Type d’équipe à laquelle l’utilisateur a accédé                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>Propriétés envoyées avec les événements de complément Outlook

| Nom de la propriété                   | Description                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | Le complément compare le compte avec le compte Teams pour déterminer si la création est autorisée. Cet événement est envoyé si la comparaison échoue |
| AccountComparisonSuccessful     | Le complément compare le compte avec le compte Teams pour voir si la création est autorisée. Cet événement est envoyé si la comparaison réussit |
| AdalVersion                     | Version de la bibliothèque d’authentification utilisée                               |
| AddinBitness                    | Version du complément                                                         |
| AddinLanguage                   | Langue des chaînes de complément utilisées                                     |
| AggregatorSetupCompletedTime    | Temps de configuration du chargeur de complément                                              |
| AppDomainCreatedTime            | Heure à laquelle le chargeur de compléments initialise le domaine d’application                            |
| AppointmentDisplayTime          | Heure à laquelle l’élément de rendez-vous a été affiché lors de la création de la réunion |
| AuthenticationCompletedTime     | Heure à laquelle l’authentification a été fournie pour une demande donnée            |
| ConnectionMode                  | Indique le mode de connexion du compte Exchange principal de l’utilisateur     |
| ConnectionStartedTime           | Heure à laquelle Outlook appelle OnConnection                                     |
| ErrorDetails                    | Capture les informations concernant l’erreur                                            |
| ErrorName                       | Capture le nom de l’erreur                                               |
| ExchangeVersion                 | Capture la version d’Exchange                                             |
| IsSmtpFormatError               | Erreur dans l’adresse SMTP                                                    |
| IsTeamsRunning                  | Détecte si un processus Teams est en cours d’exécution                             |
| IsTeamsUserLoggedOut            | Détecte si l’utilisateur est déconnecté de Teams                              |
| LanguageSetupCompletedTime      | Heure à laquelle la configuration de la langue s’est terminée                               |
| ManagedConnectTime              | Heure à laquelle le complément géré a reçu le rappel de connexion               |
| ManagedOnStartupTime            | Heure à laquelle la gestion a effectué le démarrage                                    |
| MTFetchCompleted                | Heure à laquelle la demande d’options de réunion MT est terminée                        |
| NetFrameworkVersion             | Framework .nET utilisé                                                      |
| NetworkAvailable                | Détermine si le réseau est disponible                                                     |
| OperationStartTime              |  Heure à laquelle différentes opérations ont commencé                                  |
| OsBitness                       | Nombre de bits du système d’exploitation                                                            |
| OutlookLanguage                 | Capture la langue de l’application Outlook                                     |
| OutlookVersion                  | Capture la version de l’application Outlook                                          |
| OwnerResolutionTime             | Temps nécessaire pour identifier le propriétaire de la réunion                                        |
| ParseResponseCompletedTime      | Heure à laquelle l’analyse de la réponse est terminée                                  |
| RecipientResolutionError        | Informations concernant une erreur lors de l’identification d’un destinataire                                 |
| RecipientsResolutionTime        | Temps total nécessaire pour identifier tous les destinataires                                     |
| RehydrateCompletedTime          | Heure à laquelle les propriétés sont lues à partir d’Outlook                               |
| SaveToOutlookCompletedTime      | Heure à laquelle les propriétés sont enregistrées dans Outlook                                |
| ServiceRequestStartTime         | Heure de début de la demande de service                                        |
| ServiceResponseReceiveTime      | Temps de réponse du service                                        |
| SettingsInitializeCompletedTime | Heure à laquelle les paramètres sont initialisés                                           |
| SetupLoggingCompletedTime       | Heure à laquelle la journalisation a été configurée                                             |
| ShutdownBeginTime               | Heure à laquelle l’arrêt du complément commence                                       |
| ShutdownCompletedTime           | Heure à laquelle l’arrêt s’est terminé                                             |
| StartupBeginTime                | Heure à laquelle le démarrage du complément commence                                        |
| StartupCompletedTime            | Heure à laquelle le démarrage est terminé                                              |
| TeamsDeployment                 | Déploiement du client Teams (Dev, Prod)                                   |
| TeamsRing                       | Sonnerie de l’utilisateur actuel connecté au client Teams                            |
| TeamsVersion                    | Capture la version de l’application Teams                                            |
| TelemetrySetupCompletedTime     | Heure à laquelle la configuration de la télémétrie s’est terminée                                   |
| UpnMismatch                     | Indique s’il existe une incompatibilité d’upn entre Outlook et Teams                  |
| UserDomain                      | Domaine de l’utilisateur                                                       |
| ViewUpdatedTime                 | Heure à laquelle l’affichage a été mis à jour                                           |
