---
title: Présentation du service de journalisation centralisée
TOCTitle: Présentation du service de journalisation centralisée
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49891456
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation du service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le service de journalisation centralisée est conçu pour permettre la collecte contrôlée de données, que ce soit avec une portée étroite ou étendue. Vous pouvez recueillir des données simultanément à partir de tous les serveurs du déploiement, définir des éléments spécifiques à suivre, définir des indicateurs de suivi et renvoyer des résultats de recherche à partir d’un ordinateur unique ou un agrégat de toutes les données de tous les serveurs. Le service de journalisation centralisée s’exécute sur tous les serveurs de votre déploiement. L’architecture du service de journalisation centralisée comprend les agents et services suivants :

  - *Agent du Service de journalisation centralisée*   ClsAgent.exe est l’exécutable du service qui communique avec le contrôleur et reçoit les commandes envoyées au contrôleur par l’administrateur. L’agent est exécuté en tant que service sur chaque ordinateur Lync Server. Lorsque l’agent reçoit une commande, il l’exécute, envoie des messages aux composants définis pour le suivi et écrit les journaux de suivi sur disque. Il lit également les journaux de suivi pour son ordinateur et renvoie les données de suivi au contrôleur en cas de demande. ClsAgent écoute les commandes sur les ports suivants : **TCP 50001**, **TCP 50002** et **TCP 50003**.

  - *Contrôleur du service de journalisation centralisée*   ClsControllerLib.dll est le moteur d’exécution de commande pour Lync Server Management Shell et pour ClsController.exe. CLSControllerLib.dll envoie des commandes Start, Stop, Flush et Search à ClsAgent. Lorsque des commandes de recherche sont envoyées, les journaux résultants sont envoyés à ClsControllerLib.dll et agrégés. Le contrôleur est responsable de l’envoi de commandes à l’agent, de la réception de l’état de ces commandes, de la gestion des données des fichiers journaux de recherche renvoyées par tous les agents sur tout ordinateur dans l’étendue de recherche et de l’agrégation des données de journaux en un ensemble de sortie significatif et ordonné. Les informations des rubriques suivantes sont axées sur l’utilisation de Lync Server Management Shell. ClsController.exe est limité à un sous-ensemble des fonctionnalités et fonctions disponibles dans Lync Server Management Shell. Une aide pour ClsController.exe est disponible depuis la ligne de commande en tapant `ClsController` dans le répertoire par défaut C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.

**Communications entre ClsController et ClsAgent**

![Relation entre CLSController et CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relation entre CLSController et CLSAgent.")

Vous émettez des commandes par le biais de l’interface de ligne de commande Windows Server ou de Lync Server Management Shell. Les commandes sont exécutées sur l’ordinateur sur lequel vous êtes connecté et envoyées au ClsAgent local ou à d’autres ordinateurs et pools dans votre déploiement.

ClsAgent maintient un fichier d’index de tous les fichiers .CACHE dont il dispose sur l’ordinateur local. ClsAgent les alloue de sorte qu’ils soient distribuées de manière égale parmi les volumes définis par l’option CacheFileLocalFolders, en ne consommant jamais plus de 80 % de chaque volume (autrement dit, l’emplacement du cache local et le pourcentage sont configurables à l’aide de l’applet de commande **Set-CsClsConfiguration**). ClsAgent est également responsable de la suppression des anciens fichiers journaux de suivi d’événements mis en cache (.etl) sur l’ordinateur local. Après deux semaines (le délai est configurable à l’aide de l’applet de commande **Set-CsClsConfiguration**), ces fichiers sont copiés sur un partage de fichiers et supprimés de l’ordinateur local. Pour plus d’informations, voir [Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration). Lors de la réception d’une demande de recherche, les critères de recherche sont utilisés pour sélectionner le jeu de fichiers .etl mis en cache afin d’effectuer la recherche en fonction des valeurs dans l’index conservé par l’agent.

> [!NOTE]  
> Les fichiers déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être consultés par ClsAgent. Une fois que ClsAgent a déplacé les fichiers vers le partage, le vieillissement et la suppression des fichiers ne sont pas conservés par ClsAgent. Vous devez définir une tâche d’administration pour contrôler la taille des fichiers sur le partage de fichiers et les supprimer ou les archiver.

Les fichiers journaux résultants peuvent être lus et analysés à l’aide de divers outils, notamment **Snooper.exe** et tout outil capable de lire un fichier texte, tel que **Notepad.exe**. Snooper.exe fait partie des outils de débogage de Lync Server 2013 et peut être téléchargé depuis le web.

Comme OCSLogger, le service de journalisation centralisée a plusieurs composants contre lesquels effectuer un suivi et fournit des options pour sélectionner des indicateurs, tels que TF\_COMPONENT et TF\_DIAG. service de journalisation centralisée conserve également les options de niveau de journalisation d’OCSLogger.

Le principal avantage offert par l’utilisation de Windows PowerShell par rapport au ClsController de ligne de commande est le fait que vous pouvez configurer et définir de nouveaux scénarios à l’aide de fournisseurs sélectionnés qui ciblent l’espace à problème, les indicateurs personnalisés et les niveaux de journalisation. Les scénarios accessibles à ClsController se limitent à ceux définis pour l’exécutable.

Dans les versions précédentes, OCSLogger.exe était fourni afin de permettre aux administrateurs et au personnel de support technique de recueillir des fichiers de suivi à partir d’ordinateurs du déploiement. Malgré tous ses atouts, il présentait toutefois un inconvénient : on ne pouvait recueillir des journaux que sur un seul ordinateur à la fois. Il était possible de se connecter à plusieurs ordinateurs à l’aide de copies distinctes d’OCSLogger, mais on se retrouvait alors avec plusieurs journaux et nulle méthode aisée pour agréger les résultats.

Quand un utilisateur demande une recherche de journal, ClsController détermine à quel ordinateur envoyer la demande (en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où les fichiers .etl enregistrés se trouvent. Lorsque les résultats de la recherche sont renvoyés à ClsController, le contrôleur les fusionne en un jeu de résultats unique présenté à l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de recherche sur leur ordinateur local afin d’effectuer une analyse approfondie.

Lorsque vous commencez une session de journalisation, vous spécifiez des scénarios adaptés au problème que vous tentez de résoudre. Vous pouvez exécuter deux scénarios simultanément. L’un d’entre eux doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement et recueillir des informations sur tous les ordinateurs, pools et composants.

> [!IMPORTANT]  
> Par défaut, le scénario AlwaysOn ne s’exécute pas dans votre déploiement. Vous devez le démarrer de manière explicite. Une fois démarré, il continue à s’exécuter jusqu’à ce que vous l’arrêtiez de manière explicite et l’état d’exécution est conservé entre les redémarrages de l’ordinateur. Pour plus d’informations sur le démarrage et l’arrêt de scénarios, voir <a href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Utilisation de la commande Start pour la capture des journaux par le service de journalisation centralisée</a> et <a href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Utilisation de la commande Stop pour le service de journalisation centralisée</a>.

Lorsqu’un problème survient, démarrez un second scénario en rapport avec le problème signalé. Reproduisez le problème et arrêtez la journalisation pour le second scénario. Commencez vos recherches de journaux relatives au problème signalé. La collection agrégée de journaux génère un fichier journal qui contient des messages de suivi issus de tous les ordinateurs de l’étendue globale ou de site de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez raisonnablement en analyser (rapport signal-bruit où le bruit est trop élevé), exécutez une autre recherche avec des paramètres affinés. À ce stade, vous commencerez peut-être à remarquer certains modèles qui peuvent vous aider à appréhender plus étroitement le problème. Après deux ou trois recherches affinées, vous finirez par trouver des données pertinentes au problème et en déterminer la cause racine.

> [!TIP]  
> Face à un scénario de problème dans Lync Server, commencez par vous poser la question suivante : « Que sais-je déjà à propos du problème ? ». La quantification des limites du problème vous permet d’éliminer une grande partie des entités opérationnelles dans Lync Server.<br />
Considérez un exemple de scénario dans lequel vous savez que les utilisateurs n’obtiennent pas de résultats à jour lors de la recherche d’un contact. Rien ne sert de rechercher d’éventuels problèmes dans les composants multimédias, de Voix Entreprise, de conférence et plusieurs autres composants. Vous ignorez peut-être toutefois où réside réellement le problème : sur le client ou du côté serveur ? Les contacts sont recueillis à partir d’Active Directory par le réplicateur d’utilisateurs et remis au client par le biais du serveur de carnet d’adresses (ABServer). ABServer obtient ses mises à jour à partir de la base de données RTC (où elles ont été écrites par le réplicateur d’utilisateurs) et les rassemble dans des fichiers de carnet d’adresses, par défaut à 01h30. Les clients Lync Server extraient le nouveau carnet d’adresses selon un planning aléatoire. Comme vous savez comment ce processus fonctionne, vous pouvez réduire votre recherche de la cause potentielle d’un problème lié à la collecte de données à partir d’Active Directory par le réplicateur d’utilisateurs, à la non-réception et non-création des fichiers de carnet d’adresses par ABServer ou au non-téléchargement du fichier de carnet d’adresses par le client.
