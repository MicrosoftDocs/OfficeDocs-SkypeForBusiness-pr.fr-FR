---
title: Service de journalisation centralisée Skype Entreprise 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Résumé : Découvrez les composants de service et les paramètres de configuration du service de journalisation centralisée Skype Entreprise Server 2015.'
ms.openlocfilehash: 457740b04a331d701ce991e696fa7cf88b57230c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854268"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Service de journalisation centralisée Skype Entreprise 2015
 
**Résumé :** Découvrez les composants de service et les paramètres de configuration du service de journalisation centralisée Skype Entreprise Server 2015.
  
Le service de journalisation centralisée peut : 
  
- Démarrez ou arrêtez la journalisation sur un ou plusieurs ordinateurs et pools à l’aide d’une seule commande à partir d’un emplacement central.
    
- Rechercher des journaux sur un ou plusieurs ordinateurs et pools. Vous pouvez adapter la recherche pour renvoyer tous les journaux sur tous les ordinateurs ou renvoyer des résultats plus concis.
    
- Configurer les sessions de journalisation comme suit :
    
  - Définir un **scénario** ou en utiliser un par défaut. Un scénario dans le service de journalisation centralisée est composé de l’étendue (globale ou site), d’un nom de scénario pour identifier l’objectif du scénario et d’un ou plusieurs fournisseurs. Vous pouvez exécuter le scénario par défaut et un scénario défini à tout moment sur un ordinateur.
    
  - Utiliser un fournisseur existant ou en créer un nouveau. Aprovider définit ce que la session de journalisation collecte, quel niveau de détail, quels composants suivre et quels indicateurs sont appliqués.
    
    > [!TIP]
    >  Si vous êtes familiarisé avec OCSLogger, les termproviders font référence à la collection de **composants** (par exemple, S4, SIPStack), un **type** de journalisation (par exemple, WPP, EventLog ou iiS logfile), un niveau de suivi **(par** exemple, Tous, détaillé, débogage) et des indicateurs **(par** exemple, TF_COMPONENT, TF_DIAG). Ces éléments sont définis dans le fournisseur (variable Windows PowerShell) et transmis à la commande du service de journalisation centralisée.
  
  - Configurez les journaux pour des ordinateurs et des pools spécifiques.
    
  - Définissez l’étendue de la session de journalisation à partir des options **Site** (pour exécuter les captures de journalisation sur les ordinateurs de ce site uniquement) ou **Globale** (pour exécuter les captures de journalisation sur tous les ordinateurs du déploiement).
    
Le service de journalisation centralisée est un outil puissant de dépannage pour les problèmes de grande ou petite taille, de l’analyse des causes premières aux problèmes de performances. Tous les exemples sont présentés à l’aide Skype Entreprise Server Management Shell. L’aide est fournie pour l’outil en ligne de commande par le biais de l’outil lui-même, mais il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. En utilisant Skype Entreprise Server Management Shell, vous avez accès à un ensemble de fonctionnalités beaucoup plus large et beaucoup plus configurable, ce qui doit toujours être votre premier choix. 
  
## <a name="logging-service-components"></a>Journalisation des composants du service

 Le service de journalisation centralisée s’exécute sur tous les serveurs de votre déploiement et est composé des agents et services suivants :
  
- L’agent clsAgent du service de journalisation centralisée s’exécute sur chaque ordinateur Skype Entreprise Server déployé. Il écoute ( sur les ports **TCP 50001-50003**) les commandes de ClsController sur WCF et renvoie des réponses au contrôleur. Il gère les sessions de journal (démarrage/arrêt/mise à jour) et recherche les journaux. Il effectue également des opérations de nettoyage telles que l’archivage des journaux et les purges. 
    
- Cmdlets du contrôleur de service de journalisation centralisée L’Skype Entreprise Server Management Shell envoie les commandes Start, Stop, Flush et Search au ClsAgent. Lorsque des commandes de recherche sont envoyées, les journaux résultants sont renvoyés à l'ClsControllerLib.dll et agrégés. Le contrôleur envoie des commandes à l’agent, reçoit l’état de ces commandes et gère les données du fichier journal de recherche telles qu’elles sont renvoyées par tous les agents sur n’importe quel ordinateur de l’étendue de recherche, et agrège les données du journal dans un jeu de sorties significatif et ordonné. Les informations des rubriques suivantes sont axées sur l’utilisation de Skype Entreprise Server Management Shell.
    
**Communications ClsController avec ClsAgent**

![Relation entre CLSController et CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Vous pouvez émettre des commandes à l’aide Windows’interface de ligne de commande Skype Entreprise Server Management Shell. Les commandes sont exécutées sur l’ordinateur sur qui vous êtes connecté et envoyées au ClsAgent localement ou aux autres ordinateurs et pools de votre déploiement.
  
ClsAgent conserve un fichier d’index de tous les . Fichiers CACHE qu’il possède sur l’ordinateur local. ClsAgent les alloue afin qu’ils soient uniformément répartis sur les volumes définis par l’option CacheFileLocalFolders, ne consommant jamais plus de 80 % de chaque volume (c’est-à-dire, l’emplacement du cache local et le pourcentage sont configurables à l’aide de l';cmdlet **Set-CsClsConfiguration).** ClsAgent est également responsable de l’ancien fichier journal de suivi des événements mis en cache (.etl) sur l’ordinateur local. Après deux semaines (autrement dit, la période est configurable à l’aide de l’cmdlet **Set-CsClsConfiguration),** ces fichiers sont copiés sur un partage de fichiers et supprimés de l’ordinateur local. Pour plus d’informations, [voir Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Lorsqu’une demande de recherche est reçue, les critères de recherche sont utilisés pour sélectionner l’ensemble des fichiers .etl mis en cache pour effectuer la recherche en fonction des valeurs de l’index maintenu par l’agent.
  
> [!NOTE]
> Les fichiers déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être recherchés par ClsAgent. Une fois que ClsAgent déplace les fichiers vers le partage de fichiers, l’âge et la suppression des fichiers ne sont pas conservés par ClsAgent. Vous devez définir une tâche administrative pour surveiller la taille des fichiers dans le partage de fichiers et les supprimer ou les archiver. 
  
Les fichiers journaux qui en résultent peuvent être lus et analysés à l’aide de divers outils, notamment **Snooper.exe** et tout outil qui peut lire un fichier texte, tel que **Notepad.exe**. Snooper.exe fait partie des outils de débogage Skype Entreprise Server 2015 et est disponible en téléchargement [Web.](https://go.microsoft.com/fwlink/p/?LinkId=285257)
  
Comme OCSLogger, le service de journalisation centralisée dispose de plusieurs composants pour le suivi et fournit des options pour sélectionner des indicateurs, tels que TF_COMPONENT et TF_DIAG. Le service de journalisation centralisée conserve également les options de niveau de journalisation d’OCSLogger.
  
L’avantage le plus important de l’utilisation de l’Skype Entreprise Server Management Shell par rapport à la ligne de commande ClsController est que vous pouvez configurer et définir de nouveaux scénarios à l’aide de fournisseurs sélectionnés qui ciblent l’espace à problème, les indicateurs personnalisés et les niveaux de journalisation. Les scénarios disponibles pour ClsController sont limités à ceux définis pour l’exécutable.
  
Dans les versions précédentes, OCSLogger.exe était fourni pour permettre aux administrateurs et au personnel de support technique de collecter des fichiers de suivi à partir d’ordinateurs dans le déploiement. OCSLogger, pour tous ses points forts, a connu un raccourci. Vous ne pouviez collecter les journaux que sur un seul ordinateur à la fois. Vous pouvez vous connecter à plusieurs ordinateurs à l’aide de copies distinctes d’OCSLogger, mais vous avez fini par avoir plusieurs journaux et aucun moyen simple d’agréger les résultats.
  
Lorsqu’un utilisateur demande une recherche dans le journal, clsController détermine les ordinateurs vers lesquels envoyer la demande (en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où se trouvent les fichiers .etl enregistrés. Lorsque les résultats de la recherche sont renvoyés au ClsController, le contrôleur fusionne les résultats dans un jeu de résultats unique et ordonné présenté à l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de la recherche sur leur ordinateur local pour une analyse plus approfondie.
  
Lorsque vous démarrez une session de journalisation, vous spécifiez des scénarios relatifs au problème que vous essayez de résoudre. Vous pouvez avoir deux scénarios en cours d’exécution à tout moment. L’un de ces deux scénarios doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement, en collectant des informations sur tous les ordinateurs, pools et composants.
  
> [!IMPORTANT]
> Par défaut, le scénario AlwaysOn n’est pas en cours d’exécution dans votre déploiement. Vous devez explicitement démarrer le scénario. Une fois démarré, il continue à s’exécuter jusqu’à ce qu’il soit explicitement arrêté, et l’état d’exécution est persistant par le redémarrage des ordinateurs. Pour plus d’informations sur les scénarios de démarrage et d’arrêt, voir Démarrer ou arrêter la capture du journal [CLS dans Skype Entreprise Server 2015.](start-or-stop-log-capture.md) 
  
Lorsqu’un problème se produit, démarrez un deuxième scénario lié au problème signalé. Reproduisez le problème et arrêtez la journalisation pour le deuxième scénario. Commencez vos recherches de journal par rapport au problème signalé. La collection agrégée de journaux produit un fichier journal qui contient les messages de suivi de tous les ordinateurs de votre site ou de l’étendue globale de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez l’analyser (généralement appelé rapport signal/bruit, où le bruit est trop élevé), vous exécutez une autre recherche avec des paramètres plus étroits. À ce stade, vous pouvez commencer à remarquer les modèles qui s’afficheront et vous aideront à mieux vous concentrer sur le problème. En fin de compte, après avoir effectué quelques recherches affinées, vous pouvez trouver des données pertinentes pour le problème et déterminer la cause première.
  
> [!TIP]
> Lorsqu’un scénario de problème est présenté dans Skype Entreprise Server, commencez par vous poser la question « Que sais-je déjà sur le problème ? » Si vous quantifiez les limites du problème, vous pouvez éliminer une grande partie des entités opérationnelles dans Skype Entreprise Server. 
  
Prenons un exemple de scénario dans lequel vous savez que les utilisateurs n’ont pas de résultats actuels lors de la recherche d’un contact. Il n’est pas important de chercher des problèmes dans les composants multimédias, les Voix Entreprise, les conférences et un certain nombre d’autres composants. Vous ne savez peut-être pas où se trouve réellement le problème : sur le client, ou s’agit-il d’un problème côté serveur ? Les contacts sont collectés à partir d’Active Directory par le réplicateur d’utilisateurs et remis au client par le serveur de carnet d’adresses (ABServer). AbServer obtient ses mises à jour à partir de la base de données RTC (où le réplicateur d’utilisateurs les a écrites) et les collecte dans des fichiers de carnet d’adresses, par défaut - 1 h 30. Les Skype Entreprise Server récupèrent le nouveau carnet d’adresses selon une planification aléatoire. Étant donné que vous savez comment fonctionne le processus, vous pouvez réduire votre recherche de la cause potentielle d’un problème lié à la collecte des données à partir d’Active Directory par le réplicateur d’utilisateurs, au serveur ABServer qui ne récupère pas et ne crée pas les fichiers de carnet d’adresses ou aux clients qui ne téléchargent pas le fichier de carnet d’adresses.
  
## <a name="current-configuration"></a>Configuration actuelle

Le service de journalisation centralisée est configuré pour définir ce que le service de journalisation est destiné à collecter, la façon dont il collecte, l’origine de la collecte et les paramètres du journal. Vous définissez ces paramètres globalement (c’est-à-dire, pour l’ensemble du déploiement) ou pour un site (c’est-à-dire, un site nommé dans votre déploiement). La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Pour afficher la configuration actuelle du service de journalisation centralisée

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Tapez ce qui suit dans une invite de ligne de commande :
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Vous pouvez affiner ou développer l’étendue des paramètres de configuration renvoyés par la définition et une étendue, telle que « Site:Redmond » pour renvoyer uniquement  `-Identity` la configuration CsClsConfiguration pour le site Redmond. Si vous souhaitez obtenir des détails sur une partie donnée de la configuration, vous pouvez canaler la sortie vers une autre Windows PowerShell cmdlet. Par exemple, pour obtenir des détails sur les scénarios définis dans la configuration du site « Redmond », tapez : `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Le résultat de la cmdlet affiche la configuration actuelle du service de journalisation centralisée.
    
|**Paramètre de configuration**|**Description**|
|:-----|:-----|
|**Identity** <br/> |Identifie la portée et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.  <br/> |
|**Scenarios** <br/> |Liste de tous scénarios définis pour cette configuration.  <br/> |
|**SearchTerms** <br/> |Termes de recherche définis pour la configuration. Microsoft 365 ou Office 365, pas les déploiements locaux.  <br/> |
|**SecurityGroups** <br/> |Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent. Dans ce contexte, le site est défini dans le Générateur de topologies.  <br/> |
|**Régions** <br/> |Les régions définies servent à collecter les groupes de sécurité (SecurityGroups) dans une région, par exemple, EMEA (Europe/Moyen-Orient/Afrique).  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Ce paramètre indique la taille maximale du fichier journal au-delà de laquelle un nouveau fichier journal de suivi d’événements (.etl) est créé. Un nouveau fichier journal est créé quand la taille définie est atteinte, même si la durée maximale définie dans EtlFileRolloverMinutes n’a pas encore été atteinte.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Durée maximale définie en minutes au-delà de laquelle un nouveau fichier .etl est créé. Un nouveau fichier local est créé quand le minuteur arrive à expiration, même si la taille maximale définie dans EtlFileRolloverSizeMB n’a pas encore été atteinte.  <br/> |
|**TmfFileSearchPath** <br/> |Emplacement dans lequel rechercher les fichiers au format de message de suivi.  <br/> |
|**CacheFileLocalFolders** <br/> |Chemin d’accès défini à l’emplacement où sont écrits les fichiers cache sur les ordinateurs. CLSAgent écrit les fichiers cache et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Par défaut, les fichiers cache et les fichiers journaux sont écrits dans le même répertoire.  <br/> |
|**CacheFileNetworkFolder** <br/> |Vous pouvez définir un chemin d’accès UNC (Universal Naming Convention) pour recevoir les fichiers cache lors des opérations de journalisation.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Définit la durée maximale de conservation des fichiers cache, en jours.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Définit le pourcentage d’espace disque pouvant être utilisé par les fichiers cache.  <br/> |
|**ComponentThrottleLimit** <br/> |Définit le nombre maximal de traces par seconde pouvant être créées par un composant avant le déclenchement du limiteur automatique.  <br/> |
|**ComponentThrottleSample** <br/> |Nombre de fois que la limite ComponentThrottleLimit peut être dépassée en l’espace de 60 secondes.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |Version minimale de CLSAgent autorisée à s’exécuter. Cet élément est destiné aux Microsoft 365 ou Office 365.  <br/> |
