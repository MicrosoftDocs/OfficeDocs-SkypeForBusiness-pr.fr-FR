---
title: 'Lync Server 2013: utilisation du service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b5e4e2582c7b1738f0a6072197643f4df99238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Utiliser le service de journalisation centralisé dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Le service de journalisation centralisé est une nouvelle fonctionnalité de Lync Server 2013. Il s’agit d’un remplacement amélioré pour les outils **OCSLogger** et **OCSTracer** fournis dans les versions précédentes. Vous pouvez utiliser le service de journalisation centralisé pour effectuer les tâches suivantes:

  - Commencez à vous connecter sur un ou plusieurs ordinateurs et pools à partir d’un emplacement et d’une commande uniques.

  - Arrêtez la journalisation sur un ou plusieurs ordinateurs et pools à partir d’un emplacement et d’une commande uniques.

  - Recherchez les journaux sur un ou plusieurs ordinateurs et pools pour un emplacement et une commande uniques. Vous pouvez personnaliser la commande de recherche pour renvoyer l’ensemble d’agrégats de journaux qui ont été capturés et stockés sur tous les ordinateurs, ou renvoyer un résultat ajusté pour capturer des données spécifiques.

  - Configurer les sessions de journalisation comme suit :
    
      - Définir un **Scenario** ou utiliser un scénario par défaut. Dans le cadre du service de journalisation centralisé, un *scénario* est constitué d’une étendue (globale ou de site), d’un nom de scénario permettant d’identifier l’objet du scénario et d’un ou de plusieurs fournisseurs. Vous pouvez exécuter deux scénarios à tout moment sur un ordinateur.
    
      - Utiliser un *fournisseur* existant ou créer un nouveau fournisseur. Un *fournisseur* définit ce que la session de journalisation collecte, le niveau de détail, les composants à suivre et les indicateurs à appliquer.
        
        <div>
        

        > [!TIP]  
        > Si vous connaissez lʼoutil OCSLogger, le terme <EM>fournisseurs</EM> fait référence à la collection de <STRONG>composants</STRONG> (par exemple, S4, SIPStack), à un <STRONG>type de journalisation</STRONG> (par exemple, WPP, EventLog ou fichier journal IIS), à un <STRONG>niveau de suivi</STRONG> (par exemple, All, verbose, debug) et aux <STRONG>indicateurs</STRONG> (par exemple, TF_COMPONENT, TF_DIAG). Ces éléments sont définis dans le fournisseur (une variable Windows PowerShell) et transférés dans la commande service de journalisation centralisée.

        
        </div>
    
      - Configurez les ordinateurs et les pools à partir desquels vous voulez collecter les journaux.
    
      - Définissez l’étendue de la session de journalisation à partir du **site** d’options (exécuter les captures d’enregistrement sur les ordinateurs de ce site uniquement) ou **globale** (exécuter la capture de journalisation sur tous les ordinateurs du déploiement).

Le service de journalisation centralisé est extrêmement puissant et peut répondre à la plupart des besoins en matière de résolution des problèmes (grande ou petite). D’une analyse de cause initiale aux problèmes de performances, le service de journalisation centralisé peut être un outil important pour tous les administrateurs. Tous les exemples sont affichés avec Lync Server Management Shell. Un composant de ligne de commande est associé au service de journalisation centralisé appelé **CLSController. exe**. L’outil de ligne de commande est fourni à l’aide de l’outil proprement dit. Néanmoins, il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. À l’aide de Lync Server Management Shell, vous avez accès à un ensemble de fonctionnalités plus volumineux et beaucoup plus configurable. Il est recommandé de toujours considérer Lync Server Management Shell comme première et première méthode lors de l’utilisation du service de journalisation centralisé.

Les rubriques de cette section expliquent comment utiliser le service de journalisation centralisé et des exemples illustrant comment utiliser ses nombreuses fonctionnalités.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Présentation du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gestion des paramètres de configuration du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Présentation des paramètres de configuration du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Utiliser démarrer pour le service de journalisation centralisé pour capturer les journaux dans Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Utiliser le service de journalisation centralisé dans Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Utilisation de la recherche dans les journaux de capture créés par le service de journalisation centralisé dans Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lecture de journaux de capture à partir du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

