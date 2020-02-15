---
title: 'Lync Server 2013 : utilisation du service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565c71a2a4e52b50b4807d7a5c5673e24c0a1a71
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Utilisation du service de journalisation centralisée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le service de journalisation centralisée est une nouvelle fonctionnalité de Lync Server 2013. Elle remplace et améliore les outils **OCSLogger** et **OCSTracer** qui étaient fournis dans les versions antérieures. Vous pouvez utiliser le service de journalisation centralisée pour effectuer les tâches suivantes :

  - Démarrer la journalisation sur un ou plusieurs ordinateurs et pools à partir d’un seul emplacement et d’une seule commande.

  - Arrêter la journalisation sur un ou plusieurs ordinateurs et pools à partir d’un seul emplacement et d’une seule commande.

  - Rechercher, dans les journaux situés sur un ou plusieurs ordinateurs et pools, un seul emplacement et une seule commande. Vous pouvez ajuster la commande de recherche afin de renvoyer l’ensemble des journaux capturés et stockés sur tous les ordinateurs, ou pour renvoyer un résultat affiné qui capture des données spécifiques.

  - Configurer les sessions de journalisation comme suit :
    
      - Définir un **scénario** ou en utiliser un par défaut. Un *scénario* dans le service de journalisation centralisée est composé de l’étendue (globale ou de site), d’un nom de scénario pour identifier l’objectif du scénario et d’un ou plusieurs fournisseurs. Vous pouvez exécuter deux scénarios à un moment donné sur un ordinateur.
    
      - Utiliser un *fournisseur* existant ou en créer un nouveau. Un *fournisseur* définit ce que la session de journalisation collecte, le niveau de détails, les composants à suivre et les indicateurs à appliquer.
        
        <div>
        

        > [!TIP]  
        > Si vous connaissez bien OCSLogger, le terme <EM>fournisseur</EM> fait référence à la collection de <STRONG>composants</STRONG> (par exemple, S4, SIPStack), à un <STRONG>type de journalisation</STRONG> (par exemple, un fichier journal WPP, EventLog ou IIS), à un <STRONG>niveau de suivi</STRONG> (par exemple, intégral, détaillé, débogage) et à des <STRONG>indicateurs</STRONG> (par exemple, TF_COMPONENT, TF_DIAG). Ces éléments sont définis dans le fournisseur (une variable Windows PowerShell) et transmis à la commande du service de journalisation centralisée.

        
        </div>
    
      - Configurer les ordinateurs et pools auprès desquels vous voulez collecter des journaux.
    
      - Définir l’étendue de la session de journalisation à partir des options **Site** (exécuter la capture de journalisation sur les ordinateurs de ce site uniquement) ou **Globale** (exécuter la capture de journalisation sur tous les ordinateurs du déploiement).

Le service de journalisation centralisée est extrêmement puissant et peut répondre à quasiment tous les besoins en matière de résolution des problèmes (grande ou petite). De l’analyse des causes principales aux problèmes de performances, le service de journalisation centralisée peut être un outil important pour tous les administrateurs. Tous les exemples sont affichés à l’aide de Lync Server Management Shell. Il existe un composant de ligne de commande pour le service de journalisation centralisée appelé **CLSController. exe**. Une aide est fournie pour l’outil en ligne de commande via l’outil lui-même. En revanche, il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. À l’aide de Lync Server Management Shell, vous avez accès à un ensemble de fonctionnalités plus grand et plus configurable. Vous devez toujours envisager Lync Server Management Shell comme première et première méthode lors de l’utilisation du service de journalisation centralisée.

Les rubriques de cette section expliquent comment utiliser le service de journalisation centralisée et des exemples d’utilisation de ses nombreuses fonctionnalités.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gestion des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Présentation des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Utilisation de Start pour le service de journalisation centralisée pour la capture des journaux dans Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Utilisation de stop pour le service de journalisation centralisée dans Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Utilisation de la recherche sur les journaux de capture créés par le service de journalisation centralisée dans Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lecture des journaux de capture à partir du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

