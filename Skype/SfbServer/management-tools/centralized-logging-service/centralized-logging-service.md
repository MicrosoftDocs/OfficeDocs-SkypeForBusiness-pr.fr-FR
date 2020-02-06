---
title: Service de journalisation centralisée pour Skype Entreprise 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Résumé : en savoir plus sur les composants et les paramètres de configuration du service de journalisation centralisé dans Skype entreprise Server 2015.'
ms.openlocfilehash: 6d3ac969e5d9e5898acfe2a95c6fc08e115ab545
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816623"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Service de journalisation centralisée pour Skype Entreprise 2015
 
**Résumé :** En savoir plus sur les composants de service et les paramètres de configuration pour le service de journalisation centralisé dans Skype entreprise Server 2015.
  
Le service de journalisation centralisé peut : 
  
- Démarrez ou arrêtez la journalisation sur un ou plusieurs ordinateurs et pools avec une seule commande à partir d’un emplacement centralisé.
    
- Rechercher des journaux sur un ou plusieurs ordinateurs et pools. Vous pouvez personnaliser la recherche pour renvoyer tous les journaux sur tous les ordinateurs ou renvoyer des résultats plus concis.
    
- Configurer les sessions de journalisation comme suit :
    
  - Définir un **Scenario** ou utiliser un scénario par défaut. Dans le cadre du service de journalisation centralisé, un scénario est constitué d’une étendue (globale ou de site), d’un nom de scénario permettant d’identifier l’objet du scénario et d’un ou de plusieurs fournisseurs. Vous pouvez exécuter le scénario par défaut et un scénario défini à tout moment sur un ordinateur.
    
  - Utiliser un fournisseur existant ou créer un nouveau fournisseur. Aprovider définit ce que la session de journalisation collecte, le niveau de détail, les composants à suivre et les indicateurs appliqués.
    
    > [!TIP]
    >  Si vous avez l’habitude d’utiliser OCSLogger, termproviders fait référence à la collection de **composants** (par exemple, S4, SIPStack), un **type de journalisation** (par exemple, WPP, EventLog ou journal d’information d’IIS), un **niveau de suivi** (par exemple, tous, détaillés, débogage) et des **indicateurs** (par exemple, TF_COMPONENT TF_DIAG). Ces éléments sont définis dans le fournisseur (une variable Windows PowerShell) et transférés dans la commande service de journalisation centralisée.
  
  - Configurez les journaux pour des ordinateurs et des groupes spécifiques.
    
  - Définir lʼétendue de la session de journalisation à partir des options **Site** (pour exécuter des captures de journalisation sur des ordinateurs de ce site uniquement), ou **Global** (pour exécuter des captures de journalisation sur tous les ordinateurs du déploiement).
    
Le service de journalisation centralisé est un outil puissant qui vous permet de résoudre les problèmes de performances, d’une analyse de cause racine aux problèmes de performances. Tous les exemples sont affichés avec Skype entreprise Server Management Shell. Vous pouvez obtenir de l’aide pour l’outil de ligne de commande par le biais de l’outil proprement dit, mais il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. L’utilisation de Skype entreprise Server Management Shell vous permet d’accéder à un ensemble de fonctionnalités plus volumineux et beaucoup plus configurable ; il devrait donc toujours s’avérer votre premier choix. 
  
## <a name="logging-service-components"></a>Composants du service de journalisation

 Le service de journalisation centralisé s’exécute sur tous les serveurs dans votre déploiement et est constitué des agents et services suivants :
  
- Le ClsAgent agent de connexion centralisé s’exécute sur tous les ordinateurs sur lesquels Skype entreprise Server est déployé. Il écoute (sur les ports **TCP 50001-50003**) les commandes de CLSCONTROLLER sur WCF et renvoie les réponses au contrôleur. Il gère les sessions du journal (Démarrer/arrêter/mettre à jour), ainsi que les journaux de recherche. Il exécute également des opérations de nettoyage telles que lʼarchivage et la purge de journaux. 
    
- Applets de commande de service de journalisation centralisée le shell de gestion de l’interface du serveur Skype entreprise Server Management Shell envoie des commandes de démarrage, d’arrêt, de vidage et de recherche à ClsAgent. Lorsque les commandes de recherche sont envoyées, les journaux obtenus sont renvoyés à ClsControllerLib. dll et agrégés. Le contrôleur envoie des commandes à l’agent, reçoit l’état de ces commandes et gère les données du fichier du journal de recherche tel qu’il est renvoyé par tous les agents sur n’importe quel ordinateur dans l’étendue de la recherche, et agrège les données du journal dans un ensemble de sorties ordonné et réglé. Les informations contenues dans les rubriques suivantes portent sur l’utilisation de Skype entreprise Server Management Shell.
    
**Communications entre ClsController et ClsAgent**

![Relation entre CLSController et CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Vous émettez des commandes à l’aide de l’interface de ligne de commande Windows Server ou de Skype entreprise Server Management Shell. Les commandes sont exécutées sur lʼordinateur auquel vous êtes connecté et envoyées au ClsAgent localement ou à dʼautres ordinateurs et pools dans votre déploiement.
  
ClsAgent maintient un fichier d’index de tous les fichiers .CACHE dont il dispose sur l’ordinateur local. ClsAgent les alloue de sorte qu’ils soient distribuées de manière égale parmi les volumes définis par l’option CacheFileLocalFolders, en ne consommant jamais plus de 80 % de chaque volume (autrement dit, l’emplacement du cache local et le pourcentage sont configurables à l’aide de l’applet de commande  **Set-CsClsConfiguration**). ClsAgent est également responsable de la suppression des anciens fichiers journaux de suivi d’événements mis en cache (.etl) sur l’ordinateur local. Après deux semaines (le délai est configurable à l’aide de l’applet de commande  **Set-CsClsConfiguration**), ces fichiers sont copiés sur un partage de fichiers et supprimés de l’ordinateur local. Pour plus d’informations, voir [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Lors de la réception d’une demande de recherche, les critères de recherche sont utilisés pour sélectionner le jeu de fichiers .etl mis en cache afin d’effectuer la recherche en fonction des valeurs dans l’index conservé par l’agent.
  
> [!NOTE]
> Les fichiers déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être consultés par ClsAgent. Une fois que ClsAgent a déplacé les fichiers vers le partage, le vieillissement et la suppression des fichiers ne sont pas conservés par ClsAgent. Vous devez définir une tâche d’administration pour contrôler la taille des fichiers sur le partage de fichiers et les supprimer ou les archiver. 
  
Les fichiers journaux résultants peuvent être lus et analysés à l’aide de divers outils, notamment **Snooper.exe** et tout outil capable de lire un fichier texte, tel que **Notepad.exe**. Snooper. exe fait partie des outils de débogage de Skype entreprise Server 2015 et est disponible en [Téléchargement](https://go.microsoft.com/fwlink/p/?LinkId=285257)sur le Web.
  
Comme OCSLogger, le service de journalisation centralisé dispose de plusieurs composants à suivre, et fournit des options permettant de sélectionner des indicateurs, tels que les TF_COMPONENT et les TF_DIAG. Le service de journalisation centralisé conserve également les options de niveau de journalisation de OCSLogger.
  
L’avantage le plus important de l’utilisation de Skype entreprise Server Management Shell par le biais de l’interface de ligne de commande ClsController est que vous pouvez configurer et définir de nouveaux scénarios à l’aide de fournisseurs sélectionnés qui ciblent l’espace problématique, les indicateurs personnalisés et les niveaux de connexion. Les scénarios accessibles à ClsController se limitent à ceux définis pour l’exécutable.
  
Dans les versions précédentes, OCSLogger.exe était fourni afin de permettre aux administrateurs et au personnel de support technique de recueillir des fichiers de suivi à partir d’ordinateurs du déploiement. Malgré tous ses atouts, il présentait toutefois un inconvénient : on ne pouvait recueillir des journaux que sur un seul ordinateur à la fois. Il était possible de se connecter à plusieurs ordinateurs à l’aide de copies distinctes d’OCSLogger, mais on se retrouvait alors avec plusieurs journaux et nulle méthode aisée pour agréger les résultats.
  
Quand un utilisateur demande une recherche de journal, ClsController détermine à quel ordinateur envoyer la demande (en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où les fichiers .etl enregistrés se trouvent. Lorsque les résultats de la recherche sont renvoyés à ClsController, le contrôleur les fusionne en un jeu de résultats unique présenté à l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de recherche sur leur ordinateur local afin d’effectuer une analyse approfondie.
  
Lorsque vous commencez une session de journalisation, vous spécifiez des scénarios adaptés au problème que vous tentez de résoudre. Vous pouvez exécuter deux scénarios simultanément. L’un d’entre eux doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement et recueillir des informations sur tous les ordinateurs, pools et composants.
  
> [!IMPORTANT]
> Par défaut, le scénario AlwaysOn ne s’exécute pas dans votre déploiement. Vous devez le démarrer de manière explicite. Une fois démarré, il continue à s’exécuter jusqu’à ce que vous l’arrêtiez de manière explicite et l’état d’exécution est conservé entre les redémarrages de l’ordinateur. Pour plus d’informations sur les scénarios de démarrage et d’arrêt, voir [Démarrer ou arrêter la capture du journal CLS dans Skype entreprise Server 2015](start-or-stop-log-capture.md). 
  
Lorsqu’un problème survient, démarrez un second scénario en rapport avec le problème signalé. Reproduisez le problème et arrêtez la journalisation pour le second scénario. Commencez vos recherches de journaux relatives au problème signalé. La collection agrégée de journaux génère un fichier journal qui contient des messages de suivi issus de tous les ordinateurs de l’étendue globale ou de site de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez raisonnablement en analyser (rapport signal-bruit où le bruit est trop élevé), exécutez une autre recherche avec des paramètres affinés. À ce stade, vous commencerez peut-être à remarquer certains modèles qui peuvent vous aider à appréhender plus étroitement le problème. Après deux ou trois recherches affinées, vous finirez par trouver des données pertinentes au problème et en déterminer la cause racine.
  
> [!TIP]
> Lorsque vous avez présenté une erreur dans le cadre d’un scénario de Skype entreprise Server, commencez par vous poser la question ci-dessous. Si vous quantifiez les limites du problème, vous pouvez éliminer une partie importante des entités opérationnelles dans Skype entreprise Server. 
  
Considérez un exemple de scénario dans lequel vous savez que les utilisateurs n’obtiennent pas de résultats à jour lors de la recherche d’un contact. Il n’est pas possible de rechercher les problèmes liés aux composants multimédias, à la voix entreprise, aux conférences et à un certain nombre d’autres composants. Vous ignorez peut-être toutefois où réside réellement le problème : sur le client ou du côté serveur ? Les contacts sont collectés auprès d’Active Directory par le réplicateur d’utilisateurs et remis au client par le biais du serveur du carnet d’adresses. La propriété obtient ses mises à jour à partir de la base de données RTC (où le réplicateur d’utilisateurs les a écrits) et les recueille dans les fichiers du carnet d’adresses, par défaut-1:30 AM. Les clients Skype entreprise Server récupèrent le nouveau carnet d’adresses sur une planification aléatoire. Étant donné que vous savez le fonctionnement du processus, vous pouvez limiter votre recherche à la cause potentielle d’un problème lié aux données collectées auprès d’Active Directory par le réplicateur d’utilisateurs, l’élément absent ne récupérant pas les fichiers du carnet d’adresses, ou les clients non Téléchargement du fichier du carnet d’adresses.
  
## <a name="current-configuration"></a>Configuration actuelle

Le service de journalisation centralisé est configuré pour définir ce que le service de journalisation doit collecter, la manière dont il recueille l’emplacement et les paramètres de journalisation. Ces paramètres sont définis de manière globale (cʼest-à-dire pour lʼensemble du déploiement) ou au niveau d’un site (c’est-à-dire un site déterminé dans votre déploiement). La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Pour afficher la configuration actuelle du service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Tapez ce qui suit dans une invite de ligne de commande :
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Vous pouvez réduire ou développer l’étendue des paramètres de configuration renvoyés par la définition `-Identity` et une étendue, par exemple, « site : Redmond » pour renvoyer uniquement le CsClsConfiguration pour le site Redmond. Si vous souhaitez obtenir des détails sur une partie donnée de la configuration, vous pouvez canaler la sortie dans une autre applet de cmdlet Windows PowerShell. Par exemple, pour obtenir des informations sur les scénarios définis dans la configuration du site « Redmond », tapez :`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Le résultat de l’applet de connexion affiche la configuration actuelle du service de journalisation centralisé.
    
|**Paramètre de configuration**|**Description**|
|:-----|:-----|
|**Identity** <br/> |Identifie lʼétendue et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.  <br/> |
|**Scenarios** <br/> |Liste de tous les scénarios définis pour cette configuration.  <br/> |
|**SearchTerms** <br/> |Termes de recherche définis pour la configuration. Office 365, et non des déploiements sur site.  <br/> |
|**SecurityGroups** <br/> |Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent. Le site, dans ce contexte, est le site tel qu’il est défini dans le générateur de topologie.  <br/> |
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
   

