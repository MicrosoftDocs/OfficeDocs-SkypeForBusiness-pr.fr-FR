---
title: Association d’un magasin de surveillance à un pool frontal dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Résumé : Apprenez à associer des pools de Front-End à un magasin de surveillance utilisé par Skype pour Business Server 2015.'
ms.openlocfilehash: 6706185264df4220b723f72c0863f11d84e2dc05
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server-2015"></a>Association d’un magasin de surveillance à un pool frontal dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment associer des pools de Front-End avec un magasin de surveillance utilisé par Skype pour Business Server 2015.
  
Dans Skype pour Business Server 2015, analyse les données peut uniquement être collecté sur pools de Front-End qui ont été associées à une banque de surveillance, une tâche généralement effectuée lorsque vous définissez un pool frontal dans le Générateur de topologie.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Association d’un magasin d’analyse à un pool frontal

 Pour associer un magasin d’analyse à un nouveau pool frontal, vérifiez que vous avez sélectionné l’option **Surveillance (enregistrement des détails des appels et journalisation des mesures de la qualité de l’expérience)** dans la page **Sélectionner les fonctionnalités** de l’Assistant Définir un nouveau pool frontal. Notez que si vous sélectionnez cette option, vous devez également spécifier un magasin SQL pour terminer l’Assistant. Cependant, il n’est pas nécessaire que ce magasin existe au moment de l’exécution de l’Assistant. Cela signifie que vous pouvez d’abord associer un pool à un magasin d’analyse, puis installer et configurer ce magasin par la suite.
  
Vous pouvez également associer un pool frontal existant à un nouveau magasin d’analyse ou à un autre en effectuant la procédure suivante :
  
1. Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de topologies Business Server**.
    
2. Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer sous**, entrez un nom de fichier pour votre topologie actuelle, puis cliquez sur **Enregistrer**. La topologie enregistrée peut être récupérée et republiée plus tard en cas de problèmes avec la nouvelle topologie.
    
4. Dans le Générateur de topologies, développez **Skype pour Business Server**, développez le nom du site contenant le pool frontal, puis cliquez sur développer **les pools Enterprise Edition Front-End**.
    
5. Cliquez avec le bouton droit sur le nom du pool à associer au magasin d’analyse, puis cliquez sur **Modifier les propriétés**.
    
6. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, sélectionnez l’option **Surveillance (mesures CDR et QoE)**, puis sélectionnez une base de données SQL Server existante dans la liste déroulante **Magasin d’analyse SQL Server**. (Vous pouvez également cliquer sur **Nouveau** pour associer le pool à un nouveau magasin de bases de données.) Si vous décidez d’utiliser un nouveau magasin de bases de données, dans la boîte de dialogue **Définir un nouveau magasin SQL**, entrez le nom de domaine complet de l’ordinateur SQL Server dans la zone **Nom de domaine complet du serveur SQL Server**. Si vous choisissez d’utiliser l’instance SQL Server par défaut pour ce magasin, sélectionnez **Instance par défaut**, sinon, sélectionnez **Instance nommée**, puis entrez le nom de l’instance dans la zone **Instance nommée**.
    
    La boîte de dialogue **Modifier les propriétés** vous permet également de créer un miroir SQL pour votre base de données d’analyse (un miroir SQL vous permet de conserver deux copies de votre base de données d’analyse : une copie est stockée sur l’ordinateur du magasin d’analyse et l’autre copie sur l’ordinateur du miroir SQL). Pour activer la mise en miroir, sélectionnez T **son instance SQL est mise en relation de miroir** et entrez le numéro de port pour le serveur miroir, dans la zone **numéro de port de la mise en miroir** .
    
7. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **OK**.
    
Après avoir associé le magasin d’analyse au pool frontal, vous devez publier la nouvelle topologie pour que les modifications prennent effet. Pour publier votre nouvelle topologie, procédez comme suit dans le Générateur de topologie :
  
1. Cliquez sur **Action**, pointez sur **Topologie**, puis cliquez sur **Publier**.
    
2. Dans la page **Publier la topologie** de l’Assistant Publication de topologie, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
Après avoir publié la topologie, vous pouvez installer la base de données d’analyse sur l’ordinateur qui va héberger le magasin d’analyse. La surveillance de la base de données peut être installé à l’aide de la Skype pour Business Server Management Shell et de Windows PowerShell. Pour installer la base de données localement (c'est-à-dire, pour installer la base de données sur le même ordinateur que celui sur lequel vous exécutez le Skype pour Business Server Management Shell), démarrer le Shell de gestion de l’ordinateur approprié, puis tapez la commande suivante et appuyez sur ENTRÉE :
  
```
Install-CsDatabase -LocalDatabases
```

Lorsque vous exécutez la commande précédente, Install-CsDatabase va lire le Skype en cours pour la topologie de serveur d’entreprise, déterminer les bases de données doivent être installés sur l’ordinateur local, puis automatiquement installer et configurer chacune de ces bases de données.
  
Pour installer la base de données sur un ordinateur distant (c’est-à-dire, un ordinateur autre que l’ordinateur sur lequel Management Shell est exécuté), vous devez inclure au moins deux paramètres : les paramètres ConfiguredDatabases et SqlServerFqdn. Ces paramètres indiquent l’applet de commande Install-CsDatabase pour récupérer le Skype pour la topologie de serveur d’entreprise, puis installer et configurer les bases de données requis sur l’ordinateur spécifié par le paramètre SqlServerFqdn. Le paramètre SqlServerFqdn doit utiliser une valeur représentant le nom de domaine complet de l’ordinateur sur lequel les bases de données doivent être installées.
  
Par exemple, cette commande permet d’installer la base de données d’analyse sur l’ordinateur atl-sql-001.litwareinc.com :
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Vous pouvez également installer la surveillance de la base de données en exécutant la Skype pour l’Assistant de déploiement de Business Server sur l’ordinateur qui hébergera le magasin de contrôle. Pour ce faire, ouvrez une session sur l’ordinateur approprié, puis effectuez la procédure suivante :
  
1. Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour l’Assistant de déploiement de Business Server**.
    
2. Dans l’Assistant déploiement, cliquez sur **installation ou mise à jour des Skype pour système de serveur d’entreprise**.
    
3. Dans la page **déployer** , sous **étape 2 : installation ou suppression de Skype pour les composants du serveur Business**, cliquez sur **Exécuter à nouveau**.
    
4. Dans l’installation Skype pour Assistant composants Business Server, dans la page **Skype le programme d’installation pour les composants serveur de l’entreprise** , cliquez sur **suivant**.
    
5. Dans la page **Spécifiez les chemin d’accès vers msi** , tapez le chemin d’accès au fichier Ocscore.msi (un fichier inclus avec votre Skype pour le support d’installation Business Server), puis sur **suivant**.
    
6. Dans la page **Exécution de commandes**, cliquez sur **Terminer**.
    
Pour vous assurer que tous le Skype requis pour les services de serveur d’entreprise ont démarré, cliquez sur **exécuter** sous le titre **étape 4 : démarrez les Services** dans la page **déployer**
  

