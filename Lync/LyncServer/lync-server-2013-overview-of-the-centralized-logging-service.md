---
title: 'Lync Server 2013 : vue d’ensemble du service de journalisation centralisé'
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
ms.openlocfilehash: 1460699b6516ab4e510c9715b2464ce442466faa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Présentation du service de journalisation centralisé dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Le service de journalisation centralisé a pour but de fournir un moyen de contrôler la collecte de données, avec une étendue générale ou étroite. Vous pouvez recueillir des données à partir de tous les serveurs dans le déploiement de façon simultanée, définir des éléments spécifiques pour suivre, définir des indicateurs de trace et retourner des résultats de recherche à partir d’un ordinateur unique ou d’une agrégation de toutes les données de tous les serveurs. Le service de journalisation centralisé s’exécute sur tous les serveurs dans votre déploiement. L’architecture du service de journalisation centralisé est composée des agents et services suivants :

  - *Agent de service de journalisation centralisé*   ClsAgent. exe est l’exécutable du service qui communique avec le contrôleur et reçoit les commandes émises par l’administrateur. L’agent s’exécute en tant que service sur chaque ordinateur Lync Server. Lorsque l’agent reçoit une commande, il exécute la commande, envoie des messages aux composants définis pour le suivi et écrit les journaux de suivi sur le disque. Il lit également les journaux de suivi pour son ordinateur et renvoie les données de suivi au contrôleur lorsque cela est demandé. Le ClsAgent écoute les commandes sur les ports suivants : **tcp 50001**, **TCP 50002**et **TCP 50003**.

  - *Contrôleur de service de journalisation centralisé*   ClsControllerLib. dll est le moteur d’exécution de commandes pour Lync Server Management Shell et ClsController. exe. CLSControllerLib. dll envoie des commandes de démarrage, d’arrêt, de vidage et de recherche à ClsAgent. Lorsque les commandes de recherche sont envoyées, les journaux obtenus sont renvoyés à ClsControllerLib. dll et agrégés. Le contrôleur est chargé d’envoyer des commandes à l’agent, de recevoir l’état de ces commandes et de gérer les données du fichier du journal de recherche tel qu’il est renvoyé par tous les agents sur n’importe quel ordinateur dans l’étendue de la recherche, puis de regrouper les données du journal dans un ordre significatif et indiqué. jeu de sorties. Les informations des rubriques suivantes portent sur l’utilisation de Lync Server Management Shell. ClsController. exe est limité à un sous-ensemble des fonctions et fonctions disponibles dans Lync Server Management Shell. Pour obtenir de l’aide sur ClsController. exe, accédez à la `ClsController` ligne de commande en tapant dans\\le répertoire\\par défaut\\C : fichiers fichiers\\communs Microsoft Lync Server 2013 ClsAgent.

**Communications entre ClsController et ClsAgent**

![Relation entre CLSController et CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relation entre CLSController et CLSAgent.")

Vous émettez des commandes à l’aide de l’interface de ligne de commande Windows Server ou de Lync Server Management Shell. Les commandes sont exécutées sur lʼordinateur auquel vous êtes connecté et envoyées au ClsAgent localement ou à dʼautres ordinateurs et pools dans votre déploiement.

ClsAgent maintient un fichier d’index de tous les fichiers .CACHE dont il dispose sur l’ordinateur local. ClsAgent les alloue de sorte qu’ils soient distribuées de manière égale parmi les volumes définis par l’option CacheFileLocalFolders, en ne consommant jamais plus de 80 % de chaque volume (autrement dit, l’emplacement du cache local et le pourcentage sont configurables à l’aide de l’applet de commande  **Set-CsClsConfiguration**). ClsAgent est également responsable de la suppression des anciens fichiers journaux de suivi d’événements mis en cache (.etl) sur l’ordinateur local. Après deux semaines (le délai est configurable à l’aide de l’applet de commande  **Set-CsClsConfiguration**), ces fichiers sont copiés sur un partage de fichiers et supprimés de l’ordinateur local. Pour plus d’informations, voir [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Lors de la réception d’une demande de recherche, les critères de recherche sont utilisés pour sélectionner le jeu de fichiers .etl mis en cache afin d’effectuer la recherche en fonction des valeurs dans l’index conservé par l’agent.

<div>


> [!NOTE]  
> Les fichiers déplacés vers le partage de fichiers à partir de l’ordinateur local peuvent être consultés par ClsAgent. Une fois que ClsAgent a déplacé les fichiers vers le partage, le vieillissement et la suppression des fichiers ne sont pas conservés par ClsAgent. Vous devez définir une tâche d’administration pour contrôler la taille des fichiers sur le partage de fichiers et les supprimer ou les archiver.



</div>

Les fichiers journaux résultants peuvent être lus et analysés à l’aide de divers outils, notamment **Snooper.exe** et tout outil capable de lire un fichier texte, tel que **Notepad.exe**. Snooper. exe fait partie des outils de débogage de Lync Server 2013 et est disponible en téléchargement sur [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)le Web.

Comme OCSLogger, le service de journalisation centralisé dispose de plusieurs composants à suivre, et fournit des options permettant de sélectionner des indicateurs\_, tels que\_le composant TF et TF diag. Le service de journalisation centralisé conserve également les options de niveau de journalisation de OCSLogger.

L’avantage le plus important de l’utilisation de Lync Server Management Shell sur le ClsController de ligne de commande est que vous pouvez configurer et définir de nouveaux scénarios à l’aide de fournisseurs sélectionnés ciblant l’espace problématique, les indicateurs personnalisés et les niveaux de connexion. Les scénarios accessibles à ClsController se limitent à ceux définis pour l’exécutable.

Dans les versions précédentes, OCSLogger.exe était fourni afin de permettre aux administrateurs et au personnel de support technique de recueillir des fichiers de suivi à partir d’ordinateurs du déploiement. Malgré tous ses atouts, il présentait toutefois un inconvénient : on ne pouvait recueillir des journaux que sur un seul ordinateur à la fois. Il était possible de se connecter à plusieurs ordinateurs à l’aide de copies distinctes d’OCSLogger, mais on se retrouvait alors avec plusieurs journaux et nulle méthode aisée pour agréger les résultats.

Quand un utilisateur demande une recherche de journal, ClsController détermine à quel ordinateur envoyer la demande (en fonction des scénarios sélectionnés). Il détermine également si la recherche doit être envoyée au partage de fichiers où les fichiers .etl enregistrés se trouvent. Lorsque les résultats de la recherche sont renvoyés à ClsController, le contrôleur les fusionne en un jeu de résultats unique présenté à l’utilisateur. Les utilisateurs peuvent enregistrer les résultats de recherche sur leur ordinateur local afin d’effectuer une analyse approfondie.

Lorsque vous commencez une session de journalisation, vous spécifiez des scénarios adaptés au problème que vous tentez de résoudre. Vous pouvez exécuter deux scénarios simultanément. L’un d’entre eux doit être le scénario AlwaysOn. Comme son nom l’indique, il doit toujours être en cours d’exécution dans votre déploiement et recueillir des informations sur tous les ordinateurs, pools et composants.

<div>


> [!IMPORTANT]  
> Par défaut, le scénario AlwaysOn ne s’exécute pas dans votre déploiement. Vous devez le démarrer de manière explicite. Une fois démarré, il continue à s’exécuter jusqu’à ce que vous l’arrêtiez de manière explicite et l’état d’exécution est conservé entre les redémarrages de l’ordinateur. Pour plus d’informations sur les scénarios de démarrage et d’arrêt, voir <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">utilisation du menu Démarrer pour le service de journalisation centralisé pour capturer des journaux dans Lync server 2013</A> et <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilisation du service de journalisation centralisé dans Lync Server 2013</A>.



</div>

Lorsqu’un problème survient, démarrez un second scénario en rapport avec le problème signalé. Reproduisez le problème et arrêtez la journalisation pour le second scénario. Commencez vos recherches de journaux relatives au problème signalé. La collection agrégée de journaux génère un fichier journal qui contient des messages de suivi issus de tous les ordinateurs de l’étendue globale ou de site de votre déploiement. Si la recherche renvoie plus de données que vous ne pouvez raisonnablement en analyser (rapport signal-bruit où le bruit est trop élevé), exécutez une autre recherche avec des paramètres affinés. À ce stade, vous commencerez peut-être à remarquer certains modèles qui peuvent vous aider à appréhender plus étroitement le problème. Après deux ou trois recherches affinées, vous finirez par trouver des données pertinentes au problème et en déterminer la cause racine.

<div>


> [!TIP]  
> Lorsque vous avez présenté un scénario de problème dans Lync Server, commencez par vous demander « que dois-je savoir déjà à propos du problème ». Si vous quantifiez les limites du problème, vous pouvez éliminer une partie importante des entités opérationnelles de Lync Server.<BR>Considérez un exemple de scénario dans lequel vous savez que les utilisateurs n’obtiennent pas de résultats à jour lors de la recherche d’un contact. Il n’est pas possible de rechercher les problèmes liés aux composants multimédias, à la voix entreprise, aux conférences et à un certain nombre d’autres composants. Vous ignorez peut-être toutefois où réside réellement le problème : sur le client ou du côté serveur ? Les contacts sont collectés auprès d’Active Directory par le réplicateur d’utilisateurs et remis au client par le biais du serveur du carnet d’adresses. ABServer obtient ses mises à jour à partir de la base de données RTC (où elles ont été écrites par le réplicateur d’utilisateurs) et les rassemble dans des fichiers de carnet d’adresses, par défaut à 01h30. Les clients du serveur Lync récupèrent le nouveau carnet d’adresses sur une planification aléatoire. Étant donné que vous savez le fonctionnement du processus, vous pouvez limiter votre recherche à la cause potentielle d’un problème lié aux données collectées auprès d’Active Directory par le réplicateur d’utilisateurs, l’élément absent ne récupérant pas les fichiers du carnet d’adresses, ou les clients non Téléchargement du fichier du carnet d’adresses.



</div>

</div>

<span> </span>

</div>

</div>

</div>

