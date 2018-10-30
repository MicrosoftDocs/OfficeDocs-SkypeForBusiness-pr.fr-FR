---
title: Utilisation du service de journalisation centralisée dans Lync Server 2013
TOCTitle: Utilisation du service de journalisation centralisée dans Lync Server 2013
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49891406
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation du service de journalisation centralisée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Le service de journalisation centralisée est une nouvelle fonctionnalité dans Lync Server 2013. Elle remplace et améliore les outils **OCSLogger** et **OCSTracer** qui étaient fournis dans les versions antérieures. Vous pouvez utiliser le service de journalisation centralisée pour effectuer les tâches suivantes :

  - Démarrer la journalisation sur un ou plusieurs ordinateurs et pools à partir d’un seul emplacement et d’une seule commande.

  - Arrêter la journalisation sur un ou plusieurs ordinateurs et pools à partir d’un seul emplacement et d’une seule commande.

  - Rechercher, dans les journaux situés sur un ou plusieurs ordinateurs et pools, un seul emplacement et une seule commande. Vous pouvez ajuster la commande de recherche afin de renvoyer l’ensemble des journaux capturés et stockés sur tous les ordinateurs, ou pour renvoyer un résultat affiné qui capture des données spécifiques.

  - Configurer les sessions de journalisation comme suit :
    
      - Définir un **scénario** ou en utiliser un par défaut. Un *scénario* dans le service de journalisation centralisée est constitué d’une étendue (globale ou site), d’un nom permettant d’identifier son objectif, ainsi que d’un ou plusieurs fournisseurs. Vous pouvez exécuter deux scénarios à un moment donné sur un ordinateur.
    
      - Utiliser un *fournisseur* existant ou en créer un nouveau. Un *fournisseur* définit ce que la session de journalisation collecte, le niveau de détails, les composants à suivre et les indicateurs à appliquer.
        
        > [!TIP]  
        > Si vous connaissez bien OCSLogger, le terme <em>fournisseur</em> fait référence à la collection de <strong>composants</strong> (par exemple, S4, SIPStack), à un <strong>type de journalisation</strong> (par exemple, un fichier journal WPP, EventLog ou IIS), à un <strong>niveau de suivi</strong> (par exemple, intégral, détaillé, débogage) et à des <strong>indicateurs</strong> (par exemple, TF_COMPONENT, TF_DIAG). Ces éléments sont définis dans le fournisseur (une variable Windows PowerShell) et transmis à la commande du service de journalisation centralisée.    
      - Configurer les ordinateurs et pools auprès desquels vous voulez collecter des journaux.
    
      - Définir l’étendue de la session de journalisation à partir des options **Site** (exécuter la capture de journalisation sur les ordinateurs de ce site uniquement) ou **Globale** (exécuter la capture de journalisation sur tous les ordinateurs du déploiement).

Le service de journalisation centralisée s’avère extrêmement puissant et peut répondre à presque tous les besoins en matière de résolution de problèmes, qu’ils soient grands ou petits. De l’analyse de la cause première aux problèmes de performances, le service de journalisation centralisée peut constituer un outil important pour tout administrateur. Tous les exemples sont indiqués avec Lync Server Management Shell. Il existe un composant en ligne de commande pour le service de journalisation centralisée appelé **CLSController.exe**. Une aide est fournie pour l’outil en ligne de commande via l’outil lui-même. En revanche, il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. À l’aide de Lync Server Management Shell, vous avez accès à un ensemble de fonctionnalités beaucoup plus large et plus configurable. Vous devez toujours considérer Lync Server Management Shell comme la première et plus éminente méthode lorsque vous utilisez le service de journalisation centralisée.

Les rubriques de cette section expliquent comment utiliser le service de journalisation centralisée et fournit des exemples d’utilisation de ses nombreuses fonctionnalités.

## Dans cette section

  - [Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gestion des paramètres de configuration du service de journalisation centralisée à l’aide de PowerShell](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Présentation des paramètres de configuration du service de journalisation centralisée](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Utilisation de la commande Start pour la capture des journaux par le service de journalisation centralisée](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Utilisation de la commande Stop pour le service de journalisation centralisée](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Utilisation de la recherche sur les journaux de capture créés par le service de journalisation centralisée](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lecture des journaux de capture à partir du service de journalisation centralisée](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

