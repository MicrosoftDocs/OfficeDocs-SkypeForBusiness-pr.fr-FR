---
title: Service de journalisation centralisée pour Skype Entreprise 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Résumé : Découvrez les composants de service et les paramètres de configuration pour le Service centralisé de journalisation dans Skype pour Business Server 2015.'
ms.openlocfilehash: 922d1f24e2d57c4908744462eb1b3c8335255cfd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Service de journalisation centralisée pour Skype Entreprise 2015
 
**Résumé :** Obtenir des informations sur les composants de service et les paramètres de configuration pour le Service centralisé de journalisation dans Skype pour Business Server 2015.
  
Le Service de journalisation centralisée peut : 
  
- Démarrer ou arrêter l’enregistrement sur un ou plusieurs ordinateurs et pools avec une seule commande à partir d’un emplacement central.
    
- Rechercher des journaux sur un ou plusieurs ordinateurs et pools. Vous pouvez personnaliser la recherche pour retourner tous les journaux sur tous les ordinateurs, ou retourner des résultats plus précis.
    
- Configurer les sessions de journalisation comme suit :
    
  - Définir un **Scenario** ou utiliser un scénario par défaut. Un scénario dans le Service de journalisation centralisée est constitué de la portée (global ou de site), un nom de scénario pour identifier l’objectif du scénario et un ou plusieurs fournisseurs. Vous pouvez exécuter le scénario par défaut et un scénario défini à un moment donné sur un ordinateur.
    
  - Utiliser un fournisseur existant ou créer un nouveau fournisseur. Aprovider définit ce que la session de consignation collecte, quel est le niveau de détail, les composants à la trace et les identificateurs sont appliqués.
    
    > [!TIP]
    >  Si vous êtes familiarisé avec OCSLogger, le termproviders fait référence à la collection de **composants** (par exemple, S4, SIPStack), un **enregistrement de type** (par exemple, IIS, journal des événements ou WPP logfile), un **niveau de suivi** (par exemple, All, débogage détaillé) et les **indicateurs** (par exemple, TF_COMPONENT, TF_DIAG). Ces éléments sont définies dans le fournisseur (une variable Windows PowerShell) et passées dans la commande de Service de journalisation centralisée.
  
  - Configurer des journaux pour des ordinateurs spécifiques et les pools.
    
  - Définir lʼétendue de la session de journalisation à partir des options **Site** (pour exécuter des captures de journalisation sur des ordinateurs de ce site uniquement), ou **Global** (pour exécuter des captures de journalisation sur tous les ordinateurs du déploiement).
    
Le Service de journalisation centralisée est un puissant outil de dépannage pour des problèmes de petites ou grandes, à partir de l’analyse des causes premières des problèmes de performances. Tous les exemples sont affichés à l’aide de la Skype pour Business Server Management Shell. L’aide est disponible pour l’outil de ligne de commande via l’outil lui-même, mais il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. À l’aide de Skype pour Business Server Management Shell, vous avez accès à un ensemble beaucoup plus volumineux et plus configurable de fonctionnalités, qui doit toujours être votre premier choix. 
  
## <a name="logging-service-components"></a>Composants du service de journalisation

 Le Service de journalisation centralisée s’exécute sur tous les serveurs dans votre déploiement et est constitué par les agents et les services suivants :
  
- Service de journalisation centralisée Agent des ClsAgent s’exécute sur chaque ordinateur avec Skype pour Business Server déployés. Il est à l’écoute (sur les ports **TCP 50003-50001**) pour les commandes à partir de ClsController sur WCF et envoie les réponses vers le contrôleur. Il gère les sessions de connexion (Démarrer/arrêter/mettre à jour) et recherche des journaux. Il exécute également des opérations de nettoyage telles que lʼarchivage et la purge de journaux. 
    
- Centralisée enregistrement Service contrôleur applets de commande du Skype pour Business Server Management Shell envoie des commandes Démarrer, arrêter, vidage et la recherche à la ClsAgent. Lorsque les commandes de recherche sont envoyées, les journaux qui en résultent sont retournés à la ClsControllerLib.dll et agrégées. Le contrôleur envoie des commandes à l’agent, il reçoit le statut de ces commandes et gère les données de fichier journal recherche tel qu’il est retourné à partir de tous les agents sur n’importe quel ordinateur dans la zone de recherche et regroupe les données du journal dans un jeu de résultat significatif et ordonnée. Les informations contenues dans les rubriques suivantes se concentre sur l’utilisation de la Skype pour Business Server Management Shell.
    
**Communications de ClsController à ClsAgent**

![Relation entre CLSController et CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Vous émettez des commandes à l’aide de l’interface de ligne de commande de Windows Server ou le Skype pour Business Server Management Shell. Les commandes sont exécutées sur lʼordinateur auquel vous êtes connecté et envoyées au ClsAgent localement ou à dʼautres ordinateurs et pools dans votre déploiement.
  
ClsAgent maintient un fichier d’index de tous les fichiers .CACHE dont il dispose sur l’ordinateur local. ClsAgent les alloue de sorte qu’elles sont réparties uniformément sur les volumes définis par l’option CacheFileLocalFolders, jamais consommer plus de 80 % de chaque volume (autrement dit, l’emplacement du cache local et le pourcentage est configurable à l’aide de la ** Set-CsClsConfiguration** applet de commande). ClsAgent est également responsable de la suppression des anciens fichiers journaux de suivi d’événements mis en cache (.etl) sur l’ordinateur local. Après deux semaines (c'est-à-dire, le délai est configurable à l’aide de l’applet de commande **Set-CsClsConfiguration** ) ces fichiers sont copiés dans un partage de fichier et supprimés de l’ordinateur local. Pour plus d’informations, voir [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Lors de la réception d’une demande de recherche, les critères de recherche sont utilisés pour sélectionner le jeu de fichiers .etl mis en cache afin d’effectuer la recherche en fonction des valeurs dans l’index conservé par l’agent.
  
> [!NOTE]
> Les fichiers déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être consultés par ClsAgent. Une fois que ClsAgent a déplacé les fichiers vers le partage, le vieillissement et la suppression des fichiers ne sont pas conservés par ClsAgent. Vous devez définir une tâche d’administration pour contrôler la taille des fichiers sur le partage de fichiers et les supprimer ou les archiver. 
  
Les fichiers journaux résultants peuvent être lus et analysés à l’aide de divers outils, notamment **Snooper.exe** et tout outil capable de lire un fichier texte, tel que **Notepad.exe**. Snooper.exe fait partie de la Skype pour les outils de débogage Microsoft Business Server 2015 et est disponible en [téléchargement Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Comme OCSLogger, le Service de journalisation centralisée a plusieurs composants à suivre par rapport aux et fournit des options permettant de sélectionner des indicateurs, tels que TF_COMPONENT et TF_DIAG. Service de journalisation centralisée conserve également les options de niveau d’enregistrement de OCSLogger.
  
Le principal avantage de l’utilisation de la Skype pour Business Server Management Shell sur le ClsController de ligne de commande est que vous pouvez configurer et définir de nouveaux scénarios à l’aide des fournisseurs sélectionnés qui ciblent le problème, des indicateurs personnalisés et les niveaux d’enregistrement. Les scénarios accessibles à ClsController se limitent à ceux définis pour l’exécutable.
  
Dans les versions précédentes, OCSLogger.exe était fourni afin de permettre aux administrateurs et au personnel de support technique de recueillir des fichiers de suivi à partir d’ordinateurs du déploiement. Malgré tous ses atouts, il présentait toutefois un inconvénient : on ne pouvait recueillir des journaux que sur un seul ordinateur à la fois. Il était possible de se connecter à plusieurs ordinateurs à l’aide de copies distinctes d’OCSLogger, mais on se retrouvait alors avec plusieurs journaux et nulle méthode aisée pour agréger les résultats.
  
Quand un utilisateur demande une recherche de journal, ClsController détermine à quel ordinateur envoyer la demande (en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où les fichiers .etl enregistrés se trouvent. Lorsque les résultats de la recherche sont renvoyés à ClsController, le contrôleur les fusionne en un jeu de résultats unique présenté à l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de recherche sur leur ordinateur local afin d’effectuer une analyse approfondie.
  
Lorsque vous commencez une session de journalisation, vous spécifiez des scénarios adaptés au problème que vous tentez de résoudre. Vous pouvez exécuter deux scénarios simultanément. L’un d’entre eux doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement et recueillir des informations sur tous les ordinateurs, pools et composants.
  
> [!IMPORTANT]
> Par défaut, le scénario AlwaysOn ne s’exécute pas dans votre déploiement. Vous devez le démarrer de manière explicite. Une fois démarré, il continue à s’exécuter jusqu’à ce que vous l’arrêtiez de manière explicite et l’état d’exécution est conservé entre les redémarrages de l’ordinateur. Pour plus d’informations sur le démarrage et l’arrêt des scénarios, consultez [Démarrer ou arrêter la capture de journaux CLS dans Skype pour Business Server 2015](start-or-stop-log-capture.md). 
  
Lorsqu’un problème survient, démarrez un second scénario en rapport avec le problème signalé. Reproduisez le problème et arrêtez la journalisation pour le second scénario. Commencez vos recherches de journaux relatives au problème signalé. La collection agrégée de journaux génère un fichier journal qui contient des messages de suivi issus de tous les ordinateurs de l’étendue globale ou de site de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez raisonnablement en analyser (rapport signal-bruit où le bruit est trop élevé), exécutez une autre recherche avec des paramètres affinés. À ce stade, vous commencerez peut-être à remarquer certains modèles qui peuvent vous aider à appréhender plus étroitement le problème. Après deux ou trois recherches affinées, vous finirez par trouver des données pertinentes au problème et en déterminer la cause racine.
  
> [!TIP]
> Lorsque vous présente un scénario de problème dans Skype pour Business Server, commencez par vous demandez « Quel déjà savoir sur le problème ? » Si vous commencez les limites du problème, vous pouvez éliminer une grande partie des entités opérationnelles dans Skype pour Business Server. 
  
Considérez un exemple de scénario dans lequel vous savez que les utilisateurs n’obtiennent pas de résultats à jour lors de la recherche d’un contact. Il n’y a aucun intérêt à rechercher les problèmes dans les composants de support, de Voix Entreprise, conférences et un certain nombre d’autres composants. Vous ignorez peut-être toutefois où réside réellement le problème : sur le client ou du côté serveur ? Les contacts sont collectées à partir d’Active Directory par le réplicateur d’utilisateurs et remis au client par le serveur de carnet d’adresses (ABServer). Le ABServer obtient ses mises à jour à partir de la base de données RTC (où le réplicateur d’utilisateurs écrit les) et leur collecte dans les fichiers de carnet d’adresses, par défaut - 1 h 30. Le nouveau carnet d’adresses sur une planification aléatoire d’extraire le Skype pour clients Business Server. Parce que vous savez comment fonctionne le processus, vous pouvez réduire votre recherche de l’origine d’un problème lié à des données collectées à partir d’Active Directory par le réplicateur d’utilisateurs, le ABServer pas de récupération et de créer les fichiers de carnet d’adresses, ou les clients de ne pas téléchargement du fichier de carnet d’adresses.
  
## <a name="current-configuration"></a>Configuration actuelle

Le Service de journalisation centralisée est configuré pour définir ce qu’est le service de journalisation destinés à collecter, comment il collecte, où il collecte à partir de, et quels sont les paramètres du journal. Ces paramètres sont définis de manière globale (cʼest-à-dire pour lʼensemble du déploiement) ou au niveau d’un site (c’est-à-dire un site déterminé dans votre déploiement). La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Pour afficher la configuration du Service de journalisation centralisée en cours

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit dans une invite de ligne de commande :
    
  ```
  Get-CsClsConfiguration
  ```

    > [!TIP]
    > Vous pouvez réduire ou développer la portée des paramètres de configuration qui sont retournées par la définition de `-Identity` et une portée, par exemple « Site : Redmond » pour renvoyer uniquement la CsClsConfiguration pour le site de Redmond. Si vous souhaitez des détails sur une partie donnée de la configuration, vous pouvez rediriger la sortie dans une autre applet de commande Windows PowerShell. Par exemple, pour obtenir des détails sur les scénarios définis dans la configuration du site « Redmond », tapez : `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Le résultat de l’applet de commande affiche la configuration actuelle du Service de journalisation centralisée.
    
|**Paramètre de configuration**|**Description**|
|:-----|:-----|
|**Identity** <br/> |Identifie lʼétendue et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.  <br/> |
|**Scenarios** <br/> |Liste de tous les scénarios définis pour cette configuration.  <br/> |
|**SearchTerms** <br/> |Termes de recherche définis pour la configuration. Office 365, pas les déploiements sur site.  <br/> |
|**SecurityGroups** <br/> |Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent. Site, dans ce contexte, est le site tel que défini dans le Générateur de topologies.  <br/> |
|**Regions** <br/> |Les régions définies servent à collecter les groupes de sécurité (SecurityGroups) dans une région, par exemple, EMEA (Europe/Moyen-Orient/Afrique).  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Ce paramètre indique la taille maximale du fichier journal au-delà de laquelle un nouveau fichier journal de suivi d’événements (.etl) est créé. Un nouveau fichier journal est créé quand la taille définie est atteinte, même si la durée maximale définie dans EtlFileRolloverMinutes n’a pas encore été atteinte.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Durée maximale définie en minutes au-delà de laquelle un nouveau fichier .etl est créé. Un nouveau fichier local est créé quand le minuteur arrive à expiration, même si la taille maximale définie dans EtlFileRolloverSizeMB n’a pas encore été atteinte.  <br/> |
|**TmfFileSearchPath** <br/> |Emplacement dans lequel rechercher les fichiers au format de message de suivi.  <br/> |
|**CacheFileLocalFolders** <br/> |Chemin d’accès défini à l’emplacement où sont écrits les fichiers cache sur les ordinateurs. CLSAgent écrit les fichiers cache et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Par défaut, les fichiers cache et les fichiers journaux sont écrits dans le même répertoire.  <br/> |
|**CacheFileNetworkFolder** <br/> |Vous pouvez définir un chemin d’accès UNC (Universal Naming Convention) pour recevoir les fichiers cache lors des opérations de journalisation.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Définit la durée maximale de conservation des fichiers cache, en jours.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Définit le pourcentage d’espace disque pouvant être utilisé par les fichiers cache.  <br/> |
|**ComponentThrottleLimit** <br/> |Définit le nombre maximal de traces par seconde pouvant être créées par un composant avant le déclenchement du limiteur automatique.  <br/> |
|**ComponentThrottleSample** <br/> |Nombre de fois que la limite ComponentThrottleLimit peut être dépassée en l’espace de 60 secondes.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |La version minimale du CLSAgent dont lʼexécution est autorisée. Cet élément est destiné à Office 365.  <br/> |
   

