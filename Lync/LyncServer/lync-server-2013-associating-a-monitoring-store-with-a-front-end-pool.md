---
title: "Asso. d’un magasin de surveillance à un pool frontal dans Lync Server 2013"
TOCTitle: Association d’un magasin de surveillance à un pool frontal
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205271(v=OCS.15)
ms:contentKeyID: 49298949
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Association d’un magasin de surveillance à un pool frontal dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-04-22_

Dans Microsoft Lync Server 2013, les données d’analyse peuvent uniquement être recueillies sur les pools frontaux qui ont été associés à un magasin d’analyse. Cette tâche est généralement effectuée lors de la définition d’un pool frontal dans le générateur de topologies. Pour associer un magasin d’analyse à un nouveau pool frontal, vérifiez que vous avez sélectionné l’option **Surveillance (enregistrement des détails des appels et journalisation des mesures de la qualité de l’expérience)** dans la page **Sélectionner les fonctionnalités** de l’Assistant Définir un nouveau pool frontal. Notez que si vous sélectionnez cette option, vous devez également spécifier un magasin SQL pour terminer l’Assistant. Cependant, il n’est pas nécessaire que ce magasin existe au moment de l’exécution de l’Assistant. Cela signifie que vous pouvez d’abord associer un pool à un magasin d’analyse, puis installer et configurer ce magasin par la suite.

Vous pouvez également associer un pool frontal existant à un nouveau magasin d’analyse ou à un autre en effectuant la procédure suivante :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

3.  Dans la boîte de dialogue **Enregistrer sous**, entrez un nom de fichier pour votre topologie actuelle, puis cliquez sur **Enregistrer**. La topologie enregistrée peut être récupérée et republiée plus tard en cas de problèmes avec la nouvelle topologie.

4.  Dans le générateur de topologies, développez **Lync Server 2013**, développez le nom du site contenant le pool frontal, puis développez **Pools frontaux Enterprise Edition**.

5.  Cliquez avec le bouton droit sur le nom du pool à associer au magasin d’analyse, puis cliquez sur **Modifier les propriétés**.

6.  Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, sélectionnez l’option **Surveillance (mesures CDR et QoE)**, puis sélectionnez une base de données SQL Server existante dans la liste déroulante **Magasin d’analyse SQL Server**. (Vous pouvez également cliquer sur **Nouveau** pour associer le pool à un nouveau magasin de bases de données.) Si vous décidez d’utiliser un nouveau magasin de bases de données, dans la boîte de dialogue **Définir un nouveau magasin SQL**, entrez le nom de domaine complet de l’ordinateur SQL Server dans la zone **Nom de domaine complet du serveur SQL Server**. Si vous choisissez d’utiliser l’instance SQL Server par défaut pour ce magasin, sélectionnez **Instance par défaut**, sinon, sélectionnez **Instance nommée**, puis entrez le nom de l’instance dans la zone **Instance nommée**.
    
    La boîte de dialogue **Modifier les propriétés** vous permet également de créer un miroir SQL pour votre base de données d’analyse (un miroir SQL vous permet de conserver deux copies de votre base de données d’analyse : une copie est stockée sur l’ordinateur du magasin d’analyse et l’autre copie sur l’ordinateur du miroir SQL). Pour activer la mise en miroir, sélectionnez **Cette instance SQL est dans une relation de mise en miroir**, puis entrez le numéro du port pour le serveur miroir dans la zone **Numéro de port pour la mise en miroir**.

7.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **OK**.

Après avoir associé le magasin d’analyse au pool frontal, vous devez publier la nouvelle topologie pour que les modifications prennent effet. Pour publier votre nouvelle topologie, effectuez les étapes suivantes dans le générateur de topologies :

1.  Cliquez sur **Action**, pointez sur **Topologie**, puis cliquez sur **Publier**.

2.  Dans l’Assistant Publication de topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.

3.  Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.

Après avoir publié la topologie, vous pouvez installer la base de données d’analyse sur l’ordinateur qui va héberger le magasin d’analyse. Vous pouvez installer la base de données d’analyse à l’aide de Lync Server Management Shell et de Windows PowerShell. Pour installer la base de données en local (c’est-à-dire, pour installer la base de données sur le même ordinateur sur lequel vous exécutez Lync Server Management Shell), démarrez Management Shell sur l’ordinateur approprié, tapez la commande suivante, puis appuyez sur Entrée :

    Install-CsDatabase -LocalDatabases

Quand vous exécutez cette commande, Install-CsDatabase lit la topologie Lync Server actuelle, détermine quelles bases de données doivent être installées sur l’ordinateur local, puis installe et configure automatiquement chacune de ces bases de données.

Pour installer la base de données sur un ordinateur distant (c’est-à-dire, un ordinateur autre que l’ordinateur sur lequel Management Shell est exécuté), vous devez inclure au moins deux paramètres : les paramètres ConfiguredDatabases et SqlServerFqdn. Ces paramètres indiquent à la cmdlet Install-CsDatabase de récupérer la topologie Lync Server, puis d’installer et de configurer les bases de données nécessaires sur l’ordinateur spécifié par le paramètre SqlServerFqdn. Le paramètre SqlServerFqdn doit utiliser une valeur représentant le nom de domaine complet de l’ordinateur sur lequel les bases de données doivent être installées.

Par exemple, cette commande permet d’installer la base de données d’analyse sur l’ordinateur atl-sql-001.litwareinc.com :

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Vous pouvez également installer la base de données d’analyse en exécutant l’Assistant Déploiement Lync Server sur l’ordinateur qui va héberger le magasin d’analyse. Pour ce faire, ouvrez une session sur l’ordinateur approprié, puis effectuez la procédure suivante :

1.  Cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013** et **Assistant Déploiement de Lync Server**.

2.  Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.

3.  Dans la page **Déployer**, sous **Étape 2 : installer ou supprimer des composants Lync Server**, cliquez sur **Réexécuter**.

4.  Dans l’Assistant Installation des composants Lync Server, dans la page **Installer les composants Lync Server**, cliquez sur **Suivant**.

5.  Dans la page **Spécifier le chemin des MSI**, tapez le chemin d’accès au fichier Ocscore.msi (il s’agit d’un fichier fourni avec votre support d’installation Lync Server), puis cliquez sur **Suivant**.

6.  Dans la page **Exécution de commandes**, cliquez sur **Terminer**.

Pour vérifier que tous les services Lync Server nécessaires ont été démarrés, cliquez sur **Exécuter** sous le titre **Étape 4 : démarrer les services** dans la page **Déployer**.

