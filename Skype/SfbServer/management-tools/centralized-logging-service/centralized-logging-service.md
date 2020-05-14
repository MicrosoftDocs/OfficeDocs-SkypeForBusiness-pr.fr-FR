---
title: Service de journalisation centralisée dans Skype entreprise 2015
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
description: 'Résumé : Découvrez les composants de service et les paramètres de configuration du service de journalisation centralisée dans Skype entreprise Server 2015.'
ms.openlocfilehash: e65ea3a0a5ed4d86591b630df6d84e436a7efd66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221888"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Service de journalisation centralisée dans Skype entreprise 2015
 
**Résumé :** Découvrez les composants de service et les paramètres de configuration du service de journalisation centralisée dans Skype entreprise Server 2015.
  
Le service de journalisation centralisée peut : 
  
- Démarrez ou arrêtez la journalisation sur un ou plusieurs ordinateurs et pools à l’aide d’une seule commande à partir d’un emplacement central.
    
- Recherchez des journaux sur un ou plusieurs ordinateurs et pools. Vous pouvez personnaliser la recherche pour renvoyer tous les journaux sur toutes les machines ou renvoyer des résultats plus concis.
    
- Configurer les sessions de journalisation comme suit :
    
  - Définir un **scénario** ou en utiliser un par défaut. Un scénario dans le service de journalisation centralisée est composé de l’étendue (globale ou de site), d’un nom de scénario pour identifier l’objectif du scénario et d’un ou plusieurs fournisseurs. Vous pouvez exécuter le scénario par défaut et un scénario défini à un moment donné sur un ordinateur.
    
  - Utiliser un fournisseur existant ou en créer un nouveau. Aprovider définit ce que collecte la session de journalisation, le niveau de détail, les composants à suivre et les indicateurs appliqués.
    
    > [!TIP]
    >  Si vous êtes familiarisé avec OCSLogger, le termproviders fait référence à la collection de **composants** (par exemple, S4, SIPStack), un **type de journalisation** (par exemple, WPP, EventLog ou journal des services Internet), un niveau de **suivi** (par exemple, All, Verbose, Debug) et **Flags** (par exemple, TF_COMPONENT, TF_DIAG). Ces éléments sont définis dans le fournisseur (une variable Windows PowerShell) et transmis à la commande du service de journalisation centralisée.
  
  - Configurez les journaux pour des ordinateurs et des pools spécifiques.
    
  - Définissez l’étendue de la session de journalisation à partir du **site** d’options (pour exécuter des captures de journal sur les ordinateurs de ce site uniquement) ou **Global** (pour exécuter des captures de journal sur tous les ordinateurs du déploiement).
    
Le service de journalisation centralisée est un outil de dépannage puissant pour les problèmes de grande ou de petite taille, de l’analyse de cause principale aux problèmes de performances. Tous les exemples sont illustrés à l’aide de Skype entreprise Server Management Shell. L’aide est fournie pour l’outil de ligne de commande par le biais de l’outil lui-même, mais il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. À l’aide de Skype entreprise Server Management Shell, vous avez accès à un ensemble de fonctionnalités bien plus volumineux et plus configurable, de sorte qu’il doit toujours être votre premier choix. 
  
## <a name="logging-service-components"></a>Composants du service de journalisation

 Le service de journalisation centralisée s’exécute sur tous les serveurs de votre déploiement et est composé des services et des agents suivants :
  
- L’agent de service de journalisation centralisée ClsAgent s’exécute sur chaque ordinateur sur lequel Skype entreprise Server est déployé. Il écoute (sur les ports **TCP 50001-50003**) pour les commandes de CLSCONTROLLER sur WCF et renvoie des réponses au contrôleur. Il gère les sessions de journalisation (Démarrer/arrêter/mettre à jour) et les journaux de recherche. Il effectue également des opérations de maintenance telles que l’archivage et les purges des journaux. 
    
- Cmdlets de contrôleur de service de journalisation centralisée Skype entreprise Server Management Shell envoie les commandes Démarrer, arrêter, vider et Rechercher au ClsAgent. Lorsque les commandes de recherche sont envoyées, les journaux résultants sont renvoyés à ClsControllerLib. dll et regroupés. Le contrôleur envoie des commandes à l’agent, reçoit l’état de ces commandes et gère les données du fichier journal de recherche tel qu’il est renvoyé de tous les agents sur n’importe quel ordinateur de l’étendue de recherche et regroupe les données du journal dans un ensemble de résultats significatif et ordonné. Les informations contenues dans les rubriques suivantes portent sur l’utilisation de Skype entreprise Server Management Shell.
    
**Communications ClsController vers ClsAgent**

![Relation entre CLSController et CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Vous émettez des commandes à l’aide de l’interface de ligne de commande de Windows Server ou de Skype entreprise Server Management Shell. Les commandes sont exécutées sur l’ordinateur auquel vous êtes connecté et envoyées au ClsAgent localement ou aux autres ordinateurs et pools de votre déploiement.
  
ClsAgent conserve un fichier d’index de tous les fichiers. Mettre en CACHE les fichiers qu’il possède sur l’ordinateur local. ClsAgent les alloue de sorte qu’elles soient réparties uniformément sur plusieurs volumes définis par l’option CacheFileLocalFolders, ne consomment jamais plus de 80% de chaque volume (c’est-à-dire, l’emplacement du cache local et le pourcentage est configurable à l’aide de la cmdlet **Set-CsClsConfiguration** ). ClsAgent est également responsable de la datation des anciens fichiers journaux de suivi des événements mis en cache (. ETL) sur l’ordinateur local. Après deux semaines (le délai est configurable à l’aide de la cmdlet **Set-CsClsConfiguration** ), ces fichiers sont copiés sur un partage de fichiers et supprimés de l’ordinateur local. Pour plus d’informations, consultez la rubrique [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Lors de la réception d’une demande de recherche, les critères de recherche sont utilisés pour sélectionner l’ensemble des fichiers. etl mis en cache pour effectuer la recherche en fonction des valeurs de l’index géré par l’agent.
  
> [!NOTE]
> Les fichiers qui sont déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être recherchés par ClsAgent. Une fois que ClsAgent déplace les fichiers vers le partage de fichiers, le vieillissement et la suppression des fichiers ne sont pas gérés par ClsAgent. Vous devez définir une tâche d’administration pour surveiller la taille des fichiers dans le partage de fichiers et les supprimer ou les archiver. 
  
Les fichiers journaux résultants peuvent être lus et analysés à l’aide de divers outils, notamment **Snooper. exe** et tout outil capable de lire un fichier texte, tel que **notepad. exe**. Snooper. exe fait partie des outils de débogage Skype entreprise Server 2015 et est disponible sous forme de [téléchargement Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Comme OCSLogger, le service de journalisation centralisée dispose de plusieurs composants sur lesquels effectuer le suivi, et fournit des options permettant de sélectionner des indicateurs, tels que TF_COMPONENT et TF_DIAG. Le service de journalisation centralisée conserve également les options de niveau de journalisation de OCSLogger.
  
Le principal avantage de l’utilisation de Skype entreprise Server Management Shell par rapport à la ligne de commande ClsController est que vous pouvez configurer et définir de nouveaux scénarios à l’aide de fournisseurs sélectionnés ciblant l’espace problématique, les indicateurs personnalisés et les niveaux de journalisation. Les scénarios disponibles pour ClsController sont limités à ceux qui sont définis pour le fichier exécutable.
  
Dans les versions précédentes, OCSLogger. exe était fourni pour permettre aux administrateurs et au personnel du support technique de collecter des fichiers de suivi sur les ordinateurs du déploiement. OCSLogger, pour toutes ses forces, a rencontré un manque. Vous pouvez uniquement collecter les journaux sur un seul ordinateur à la fois. Vous pouvez vous connecter à plusieurs ordinateurs à l’aide de copies distinctes de OCSLogger, mais vous avez terminé avec plusieurs journaux et pas de façon simple de regrouper les résultats.
  
Lorsqu’un utilisateur demande une recherche de journal, le ClsController détermine les ordinateurs vers lesquels envoyer la demande (c’est-à-dire, en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où se trouvent les fichiers. etl enregistrés. Lorsque les résultats de la recherche sont renvoyés au ClsController, le contrôleur fusionne les résultats en un seul jeu de résultats de la commande de l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de la recherche sur leur ordinateur local pour une analyse plus poussée.
  
Lorsque vous démarrez une session de journalisation, vous spécifiez des scénarios relatifs au problème que vous tentez de résoudre. Vous pouvez avoir deux scénarios en cours d’exécution à tout moment. L’un de ces deux scénarios doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement, en collectant des informations sur tous les ordinateurs, les pools et les composants.
  
> [!IMPORTANT]
> Par défaut, le scénario AlwaysOn n’est pas en cours d’exécution dans votre déploiement. Vous devez démarrer le scénario de manière explicite. Une fois démarrée, elle continue de s’exécuter jusqu’à ce qu’elle soit explicitement arrêtée, et l’état d’exécution est conservé par les redémarrages des ordinateurs. Pour plus d’informations sur le démarrage et l’arrêt des scénarios, voir [Start or Stop CLS log capture in Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Lorsqu’un problème survient, démarrez un deuxième scénario qui se rapporte au problème signalé. Reproduisez le problème et arrêtez la journalisation pour le deuxième scénario. Commencez vos recherches de journaux par rapport au problème signalé. La collection agrégée de journaux génère un fichier journal qui contient les messages de suivi de tous les ordinateurs de votre site ou une étendue globale de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez en analyser (rapport signal/bruit, dont le bruit est trop élevé), vous exécutez une autre recherche avec des paramètres plus étroits. À ce stade, vous pouvez commencer à remarquer des modèles qui s’affichent et qui peuvent vous aider à mieux se concentrer sur le problème. Enfin, après avoir effectué quelques recherches affinées, vous pouvez trouver des données pertinentes pour le problème et déterminer la cause principale.
  
> [!TIP]
> Lorsqu’il s’agit d’un scénario de problème dans Skype entreprise Server, commencez par vous poser la question « que dois-je savoir ? ». Si vous quantifiez les limites des problèmes, vous pouvez éliminer une grande partie des entités opérationnelles dans Skype entreprise Server. 
  
Prenons l’exemple d’un scénario dans lequel vous êtes conscient que les utilisateurs n’obtiennent pas de résultats actuels lors de la recherche d’un contact. Il n’y a aucun point à trouver des problèmes dans les composants multimédias, voix entreprise, Conférence et un certain nombre d’autres composants. Ce que vous ignorez est l’endroit où le problème est réellement : sur le client, ou est-ce un problème côté serveur ? Les contacts sont collectés à partir d’Active Directory par le réplicateur d’utilisateurs et remis au client par le biais du serveur de carnet d’adresses (ABServer). La base de données de RTC obtient ses mises à jour à partir de la base de données RTC (où le réplicateur d’utilisateurs les a écrites) et les collecte dans les fichiers de carnet d’adresses, par défaut : 1:30 AM. Les clients Skype entreprise Server extraient le nouveau carnet d’adresses selon un calendrier aléatoire. Étant donné que vous êtes conscient de la façon dont le processus fonctionne, vous pouvez réduire votre recherche pour la cause potentielle d’un problème lié aux données collectées à partir d’Active Directory par le réplicateur d’utilisateurs, l’erreur de non récupération et de création des fichiers de carnet d’adresses, ou les clients qui ne téléchargent pas le fichier de carnet d’adresses.
  
## <a name="current-configuration"></a>Configuration actuelle

Le service de journalisation centralisée est configuré pour définir ce que le service de journalisation doit collecter, le mode de collecte, l’emplacement à partir duquel il sera collecté et les paramètres de journalisation. Vous définissez ces paramètres globalement (c’est-à-dire pour l’ensemble du déploiement) ou pour un site (autrement dit, un site nommé dans votre déploiement). La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Pour afficher la configuration actuelle du service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.
    
2. Tapez ce qui suit dans une invite de ligne de commande :
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Vous pouvez réduire ou développer l’étendue des paramètres de configuration qui sont renvoyés par la définition `-Identity` et une étendue, telle que « site : Redmond » pour renvoyer uniquement le CsClsConfiguration pour le site Redmond. Si vous souhaitez obtenir des détails sur une partie donnée de la configuration, vous pouvez rediriger la sortie vers une autre cmdlet Windows PowerShell. Par exemple, pour obtenir des détails sur les scénarios définis dans la configuration du site "Redmond", tapez :`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Le résultat de l’applet de commande affiche la configuration actuelle du service de journalisation centralisée.
    
|**Paramètre de configuration**|**Description**|
|:-----|:-----|
|**Identity** <br/> |Identifie la portée et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.  <br/> |
|**Scenarios** <br/> |Liste de tous scénarios définis pour cette configuration.  <br/> |
|**SearchTerms** <br/> |Termes de recherche définis pour la configuration. Microsoft 365 ou Office 365, pas les déploiements locaux.  <br/> |
|**SecurityGroups** <br/> |Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent. Site, dans ce contexte, est le site tel qu’il est défini dans le générateur de topologies.  <br/> |
|**Régions** <br/> |Les régions définies servent à collecter les groupes de sécurité (SecurityGroups) dans une région, par exemple, EMEA (Europe/Moyen-Orient/Afrique).  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Ce paramètre indique la taille maximale du fichier journal au-delà de laquelle un nouveau fichier journal de suivi d’événements (.etl) est créé. Un nouveau fichier journal est créé quand la taille définie est atteinte, même si la durée maximale définie dans EtlFileRolloverMinutes n’a pas encore été atteinte.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Durée maximale définie en minutes au-delà de laquelle un nouveau fichier .etl est créé. Un nouveau fichier local est créé quand le minuteur arrive à expiration, même si la taille maximale définie dans EtlFileRolloverSizeMB n’a pas encore été atteinte.  <br/> |
|**TmfFileSearchPath** <br/> |Emplacement dans lequel rechercher les fichiers au format de message de suivi.  <br/> |
|**CacheFileLocalFolders** <br/> |Chemin d’accès défini à l’emplacement où sont écrits les fichiers cache sur les ordinateurs. CLSAgent écrit les fichiers cache et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Par défaut, les fichiers cache et les fichiers journaux sont écrits dans le même répertoire.  <br/> |
|**CacheFileNetworkFolder** <br/> |Vous pouvez définir un chemin d’accès UNC (Universal Naming Convention) pour recevoir les fichiers cache lors des opérations de journalisation.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Définit la durée maximale de conservation des fichiers cache, en jours.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Définit le pourcentage d’espace disque pouvant être utilisé par les fichiers cache.  <br/> |
|**Limite componentthrottlelimit** <br/> |Définit le nombre maximal de traces par seconde pouvant être créées par un composant avant le déclenchement du limiteur automatique.  <br/> |
|**ComponentThrottleSample** <br/> |Nombre de fois que la limite ComponentThrottleLimit peut être dépassée en l’espace de 60 secondes.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |Version minimale de CLSAgent autorisée à s’exécuter. Cet élément est destiné à Microsoft 365 ou Office 365.  <br/> |
   

