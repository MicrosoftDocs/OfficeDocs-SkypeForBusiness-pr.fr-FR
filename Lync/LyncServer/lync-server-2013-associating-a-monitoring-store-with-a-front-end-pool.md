---
title: 'Lync Server 2013: Association d’un magasin d’analyse avec un pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Association d’un magasin d’analyse à un pool frontal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-04-22_

Dans Microsoft Lync Server 2013, les données d’analyse ne peuvent être collectées que sur les pools front-end qui ont été associés à un magasin d’analyse, une tâche en général réalisée lors de la définition d’un pool frontal dans le générateur de topologie. Pour associer un magasin d’analyse à un nouveau pool frontal, veillez à sélectionner l’option **analyse (enregistrement des détails des appels et journalisation de la qualité de** l’évaluation) dans la page Sélectionner des **fonctionnalités** de l’Assistant définir un nouveau pool frontal. Notez que si vous sélectionnez cette option, vous devez également spécifier un magasin SQL pour pouvoir terminer l’Assistant. Néanmoins, il n’est pas nécessaire d’exister au moment de l’exécution de l’Assistant. Cela signifie que vous pouvez d’abord associer un pool à un magasin d’analyse, puis configurer et configurer ce Windows Store plus tard.

Vous pouvez également associer un pool frontal existant à un nouveau magasin d’analyse ou à un autre en effectuant la procédure suivante :

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

3.  Dans la boîte de dialogue **Enregistrer sous**, entrez un nom de fichier pour votre topologie actuelle, puis cliquez sur **Enregistrer**. La topologie enregistrée peut être récupérée et republiée plus tard en cas de problèmes avec la nouvelle topologie.

4.  Dans le générateur de topologie, développez **Lync Server 2013**, développez le nom du site contenant le pool frontal, puis cliquez sur développer les **Pools front-end Enterprise Edition**.

5.  Cliquez avec le bouton droit sur le nom du pool à associer au magasin d’analyse, puis cliquez sur **Modifier les propriétés**.

6.  Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, sélectionnez l’option **Surveillance (mesures CDR et QoE)**, puis sélectionnez une base de données SQL Server existante dans la liste déroulante **Magasin d’analyse SQL Server**. (Vous pouvez également cliquer sur **Nouveau** pour associer le pool à un nouveau magasin de bases de données.) Si vous décidez d’utiliser un nouveau magasin de bases de données, dans la boîte de dialogue **Définir un nouveau magasin SQL**, entrez le nom de domaine complet de l’ordinateur SQL Server dans la zone **Nom de domaine complet du serveur SQL Server**. Si vous choisissez d’utiliser l’instance SQL Server par défaut pour ce magasin, sélectionnez **Instance par défaut**, sinon, sélectionnez **Instance nommée**, puis entrez le nom de l’instance dans la zone **Instance nommée**.
    
    La boîte de dialogue **Modifier les propriétés** vous permet également de créer un miroir SQL pour votre base de données d’analyse (un miroir SQL vous permet de conserver deux copies de votre base de données d’analyse : une copie est stockée sur l’ordinateur du magasin d’analyse et l’autre copie sur l’ordinateur du miroir SQL). Pour activer la mise en miroir, sélectionnez **Cette instance SQL est dans une relation de mise en miroir**, puis entrez le numéro du port pour le serveur miroir dans la zone **Numéro de port pour la mise en miroir**.

7.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **OK**.

Après avoir associé le magasin d’analyse au pool frontal, vous devez publier la nouvelle topologie pour que les modifications prennent effet. Pour publier votre nouvelle topologie, suivez les étapes suivantes dans le générateur de topologie:

1.  Cliquez sur **Action**, pointez sur **Topologie**, puis cliquez sur **Publier**.

2.  Dans la page **Publier la topologie** de l’Assistant Publication de topologie, cliquez sur **Suivant**.

3.  Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.

Après avoir publié la topologie, vous pouvez installer la base de données d’analyse sur l’ordinateur qui va héberger le magasin d’analyse. La base de données de surveillance peut être installée à l’aide de Lync Server Management Shell et de Windows PowerShell. Pour installer la base de données en local (c’est-à-dire pour installer la base de données sur le même ordinateur que vous exécutez Lync Server Management Shell), démarrez Management Shell sur l’ordinateur approprié, puis tapez la commande suivante et appuyez sur entrée:

    Install-CsDatabase -LocalDatabases

Lors de l’exécution de la commande précédente, install-CsDatabase lira la topologie actuelle de Lync Server, déterminez les bases de données qui doivent être installées sur l’ordinateur local, puis installez et configurez automatiquement chacune de ces bases de données.

Pour installer la base de données sur un ordinateur distant (c’est-à-dire, un ordinateur autre que l’ordinateur sur lequel Management Shell est exécuté), vous devez inclure au moins deux paramètres : les paramètres ConfiguredDatabases et SqlServerFqdn. Ces paramètres indiquent à l’applet de demande install-CsDatabase de récupérer la topologie du serveur Lync, puis d’installer et de configurer les bases de données requises sur l’ordinateur spécifié par le paramètre SqlServerFqdn. Le paramètre SqlServerFqdn doit utiliser une valeur représentant le nom de domaine complet de l’ordinateur sur lequel les bases de données doivent être installées.

Par exemple, cette commande permet d’installer la base de données d’analyse sur l’ordinateur atl-sql-001.litwareinc.com :

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Vous pouvez également installer la base de données de surveillance en exécutant l’Assistant Déploiement de Lync Server sur l’ordinateur qui héberge le Windows Store. Pour ce faire, ouvrez une session sur l’ordinateur approprié, puis effectuez la procédure suivante :

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement de Lync Server**.

2.  Dans l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système serveur Lync**.

3.  Dans la page **déployer** , sous **étape 2: installer ou supprimer les composants Lync Server**, cliquez de **nouveau sur exécuter**.

4.  Dans l’Assistant Configuration des composants Lync Server, dans la page **Configuration des composants du serveur Lync** , cliquez sur **suivant**.

5.  Dans la page spécifiez le **chemin d’accès à MSIS** , tapez le chemin d’accès au fichier OCSCore. msi (un fichier inclus sur votre support d’installation de Lync Server), puis cliquez sur **suivant**.

6.  Dans la page **Exécution de commandes**, cliquez sur **Terminer**.

Pour vous assurer que tous les services Lync Server requis ont démarré, cliquez sur **exécuter** sous le titre **étape 4: démarrer les services** dans la page de **déploiement**

</div>

<span> </span>

</div>

</div>

</div>

