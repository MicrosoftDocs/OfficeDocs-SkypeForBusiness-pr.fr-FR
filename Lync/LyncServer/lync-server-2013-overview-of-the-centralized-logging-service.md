---
title: 'Lync Server 2013 : vue d’ensemble du service de journalisation centralisée'
description: 'Lync Server 2013 : vue d’ensemble du service de journalisation centralisée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a357063ff80611789981f5e98a69899ea5cd27a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560910"
---
# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Le service de journalisation centralisée est conçu pour fournir un moyen de contrôler la collecte de données, avec une portée large ou étroite. Vous pouvez collecter des données à partir de tous les serveurs du déploiement simultanément, définir des éléments spécifiques à suivre, définir des indicateurs de suivi et renvoyer des résultats de recherche à partir d’un ordinateur unique ou agréger toutes les données de tous les serveurs. Le service de journalisation centralisée s’exécute sur tous les serveurs de votre déploiement. L’architecture du service de journalisation centralisée est constituée des agents et services suivants :

  - Agent du service de *journalisation centralisée*    ClsAgent.exe est le service exécutable qui communique avec le contrôleur et reçoit les commandes émises par l’administrateur. L’agent est exécuté en tant que service sur chaque ordinateur Lync Server. Lorsque l’agent reçoit une commande, il exécute la commande, envoie des messages aux composants définis pour le suivi et écrit les journaux de suivi sur le disque. Il lit également les journaux de suivi pour son ordinateur et renvoie les données de suivi au contrôleur lorsque cela est demandé. Le ClsAgent écoute les commandes sur les ports suivants : **tcp 50001**, **TCP 50002**et **TCP 50003**.

  - Contrôleur de service de *journalisation centralisée*    ClsControllerLib.dll est le moteur d’exécution de commandes pour Lync Server Management Shell et pour ClsController.exe. CLSControllerLib.dll envoie les commandes Démarrer, arrêter, vider et Rechercher au ClsAgent. Lorsque les commandes de recherche sont envoyées, les journaux résultants sont renvoyés au ClsControllerLib.dll et regroupés. Le contrôleur est responsable de l’envoi de commandes à l’agent, de la réception de l’état de ces commandes et de la gestion des données du fichier journal de recherche tel qu’il est renvoyé par tous les agents sur un ordinateur de l’étendue de recherche et de l’agrégation des données du journal dans un ensemble de résultats significatif et ordonné. Les informations contenues dans les rubriques suivantes portent sur l’utilisation de Lync Server Management Shell. ClsController.exe est limité à un sous-ensemble de fonctionnalités et de fonctions disponibles dans Lync Server Management Shell. L’aide relative à ClsController.exe est disponible sur la ligne de commande en tapant `ClsController` dans le répertoire par défaut C : \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ ClsAgent.

**Communications ClsController vers ClsAgent**

![Relation entre CLSController et CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relation entre CLSController et CLSAgent.")

Vous émettez des commandes à l’aide de l’interface de ligne de commande de Windows Server ou à l’aide de Lync Server Management Shell. Les commandes sont exécutées sur l’ordinateur auquel vous êtes connecté et envoyées au ClsAgent localement ou aux autres ordinateurs et pools de votre déploiement.

ClsAgent conserve un fichier d’index de tous les fichiers. Mettre en CACHE les fichiers qu’il possède sur l’ordinateur local. ClsAgent les alloue de sorte qu’elles soient réparties uniformément sur plusieurs volumes définis par l’option CacheFileLocalFolders, ne consomment jamais plus de 80% de chaque volume (c’est-à-dire, l’emplacement du cache local et le pourcentage est configurable à l’aide de la cmdlet **Set-CsClsConfiguration** ). ClsAgent est également responsable de la datation des anciens fichiers journaux de suivi des événements mis en cache (. ETL) sur l’ordinateur local. Après deux semaines (le délai est configurable à l’aide de la cmdlet **Set-CsClsConfiguration** ), ces fichiers sont copiés sur un partage de fichiers et supprimés de l’ordinateur local. Pour plus d’informations, consultez la rubrique [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Lors de la réception d’une demande de recherche, les critères de recherche sont utilisés pour sélectionner l’ensemble des fichiers. etl mis en cache pour effectuer la recherche en fonction des valeurs de l’index géré par l’agent.

<div>


> [!NOTE]  
> Les fichiers qui sont déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être recherchés par ClsAgent. Une fois que ClsAgent déplace les fichiers vers le partage de fichiers, le vieillissement et la suppression des fichiers ne sont pas gérés par ClsAgent. Vous devez définir une tâche d’administration pour surveiller la taille des fichiers dans le partage de fichiers et les supprimer ou les archiver.



</div>

Les fichiers journaux qui en résultent peuvent être lus et analysés à l’aide d’un large éventail d’outils, y compris **Snooper.exe** et tout outil capable de lire un fichier texte, comme **Notepad.exe**. Snooper.exe fait partie des outils de débogage Lync Server 2013 et peut être téléchargé sur le Web à partir de [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) .

Comme OCSLogger, le service de journalisation centralisée dispose de plusieurs composants à suivre et fournit des options permettant de sélectionner des indicateurs, tels que le \_ composant TF et TF \_ diag. Le service de journalisation centralisée conserve également les options de niveau de journalisation de OCSLogger.

L’avantage le plus important de l’utilisation de Lync Server Management Shell par rapport à la ligne de commande ClsController est que vous pouvez configurer et définir de nouveaux scénarios à l’aide de fournisseurs sélectionnés ciblant l’espace problématique, les indicateurs personnalisés et les niveaux de journalisation. Les scénarios disponibles pour ClsController sont limités à ceux qui sont définis pour le fichier exécutable.

Dans les versions précédentes, OCSLogger.exe était fourni pour permettre aux administrateurs et au personnel du support technique de collecter des fichiers de suivi sur les ordinateurs du déploiement. OCSLogger, pour toutes ses forces, a rencontré un manque. Vous pouvez uniquement collecter les journaux sur un seul ordinateur à la fois. Vous pouvez vous connecter à plusieurs ordinateurs à l’aide de copies distinctes de OCSLogger, mais vous avez terminé avec plusieurs journaux et pas de façon simple de regrouper les résultats.

Lorsqu’un utilisateur demande une recherche de journal, le ClsController détermine les ordinateurs vers lesquels envoyer la demande (c’est-à-dire, en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où se trouvent les fichiers. etl enregistrés. Lorsque les résultats de la recherche sont renvoyés au ClsController, le contrôleur fusionne les résultats en un seul jeu de résultats de la commande de l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de la recherche sur leur ordinateur local pour une analyse plus poussée.

Lorsque vous démarrez une session de journalisation, vous spécifiez des scénarios relatifs au problème que vous tentez de résoudre. Vous pouvez avoir deux scénarios en cours d’exécution à tout moment. L’un de ces deux scénarios doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement, en collectant des informations sur tous les ordinateurs, les pools et les composants.

<div>


> [!IMPORTANT]  
> Par défaut, le scénario AlwaysOn n’est pas en cours d’exécution dans votre déploiement. Vous devez démarrer le scénario de manière explicite. Une fois démarrée, elle continue de s’exécuter jusqu’à ce qu’elle soit explicitement arrêtée, et l’état d’exécution est conservé par les redémarrages des ordinateurs. Pour plus d’informations sur le démarrage et l’arrêt des scénarios, reportez-vous <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">à la rubrique utilisation du bouton Démarrer pour le service de journalisation centralisée pour capturer des journaux dans Lync server 2013</A> et <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilisation de stop pour le service de journalisation centralisée dans Lync Server 2013</A>.



</div>

Lorsqu’un problème survient, démarrez un deuxième scénario qui se rapporte au problème signalé. Reproduisez le problème et arrêtez la journalisation pour le deuxième scénario. Commencez vos recherches de journaux par rapport au problème signalé. La collection agrégée de journaux génère un fichier journal qui contient les messages de suivi de tous les ordinateurs de votre site ou une étendue globale de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez en analyser (rapport signal/bruit, dont le bruit est trop élevé), vous exécutez une autre recherche avec des paramètres plus étroits. À ce stade, vous pouvez commencer à remarquer des modèles qui s’affichent et qui peuvent vous aider à mieux se concentrer sur le problème. Enfin, après avoir effectué quelques recherches affinées, vous pouvez trouver des données pertinentes pour le problème et déterminer la cause principale.

<div>


> [!TIP]  
> Lorsque vous avez présenté un scénario de problème dans Lync Server, commencez par vous demander « que dois-je savoir déjà sur le problème ? ». Si vous quantifiez les limites des problèmes, vous pouvez éliminer une grande partie des entités opérationnelles dans Lync Server.<BR>Prenons l’exemple d’un scénario dans lequel vous êtes conscient que les utilisateurs n’obtiennent pas de résultats actuels lors de la recherche d’un contact. Il n’y a aucun point à trouver des problèmes dans les composants multimédias, voix entreprise, Conférence et un certain nombre d’autres composants. Ce que vous ignorez est l’endroit où le problème est réellement : sur le client, ou est-ce un problème côté serveur ? Les contacts sont collectés à partir d’Active Directory par le réplicateur d’utilisateurs et remis au client par le biais du serveur de carnet d’adresses (ABServer). L’abactiveur obtient ses mises à jour à partir de la base de données RTC (où le réplicateur d’utilisateurs les a écrites) et les collecte dans les fichiers de carnet d’adresses, par défaut, à 1:30 AM. Les clients Lync Server extraient le nouveau carnet d’adresses selon un calendrier aléatoire. Étant donné que vous êtes conscient de la façon dont le processus fonctionne, vous pouvez réduire votre recherche pour la cause potentielle d’un problème lié aux données collectées à partir d’Active Directory par le réplicateur d’utilisateurs, l’erreur de non récupération et de création des fichiers de carnet d’adresses, ou les clients qui ne téléchargent pas le fichier de carnet d’adresses.



</div>

</div>

<span> </span>

</div>

</div>

</div>

