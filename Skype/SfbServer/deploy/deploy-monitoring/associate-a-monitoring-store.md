---
title: Associez un magasin d’analyse à un pool frontal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Résumé: Découvrez comment associer des regroupements front-end à un magasin de surveillance utilisé par Skype entreprise Server.'
ms.openlocfilehash: 66d51e89a41c5e6ce2608b4fe8ecd1c4af336b6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239990"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associez un magasin d’analyse à un pool frontal dans Skype entreprise Server 
**Résumé:** Découvrez comment associer des regroupements front-end à un magasin d’analyse utilisé par Skype entreprise Server.
  
Dans Skype entreprise Server, la surveillance des données ne peut être collectée que sur les pools frontaux qui ont été associés à un magasin de surveillance, une tâche généralement réalisée lors de la définition d’un pool frontal dans le générateur de topologie.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Association d’un magasin d’analyse à un pool frontal

 Pour associer un magasin d’analyse à un nouveau pool frontal, vérifiez que vous avez sélectionné l’option **Surveillance (enregistrement des détails des appels et journalisation des mesures de la qualité de l’expérience)** dans la page **Sélectionner les fonctionnalités** de l’Assistant Définir un nouveau pool frontal. Notez que si vous sélectionnez cette option, vous devez également spécifier un magasin SQL pour terminer l’Assistant. Cependant, il n’est pas nécessaire que ce magasin existe au moment de l’exécution de l’Assistant. Cela signifie que vous pouvez d’abord associer un pool à un magasin d’analyse, puis installer et configurer ce magasin par la suite.
  
Vous pouvez également associer un pool frontal existant à un nouveau magasin d’analyse ou à un autre en effectuant la procédure suivante :
  
1. Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Générateur de topologie Skype entreprise Server**.
    
2. Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer sous**, entrez un nom de fichier pour votre topologie actuelle, puis cliquez sur **Enregistrer**. La topologie enregistrée peut être récupérée et republiée plus tard en cas de problèmes avec la nouvelle topologie.
    
4. Dans le générateur de topologie, développez **Skype entreprise Server**, développez le nom du site contenant le pool frontal, puis cliquez sur développer les **Pools front-end Enterprise Edition**.
    
5. Cliquez avec le bouton droit sur le nom du pool à associer au magasin d’analyse, puis cliquez sur **Modifier les propriétés**.
    
6. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, sélectionnez l’option **Surveillance (mesures CDR et QoE)**, puis sélectionnez une base de données SQL Server existante dans la liste déroulante **Magasin d’analyse SQL Server**. (Vous pouvez également cliquer sur **Nouveau** pour associer le pool à un nouveau magasin de bases de données.) Si vous décidez d’utiliser un nouveau magasin de bases de données, dans la boîte de dialogue **Définir un nouveau magasin SQL**, entrez le nom de domaine complet de l’ordinateur SQL Server dans la zone **Nom de domaine complet du serveur SQL Server**. Si vous choisissez d’utiliser l’instance SQL Server par défaut pour ce magasin, sélectionnez **Instance par défaut**, sinon, sélectionnez **Instance nommée**, puis entrez le nom de l’instance dans la zone **Instance nommée**.
    
    La boîte de dialogue **Modifier les propriétés** vous permet également de créer un miroir SQL pour votre base de données d’analyse (un miroir SQL vous permet de conserver deux copies de votre base de données d’analyse : une copie est stockée sur l’ordinateur du magasin d’analyse et l’autre copie sur l’ordinateur du miroir SQL). Pour activer la mise en miroir, sélectionnez T **son instance SQL est en miroir** et entrez le numéro de port du serveur miroir dans la zone de **numéro de port en miroir** .
    
7. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **OK**.
    
Après avoir associé le magasin d’analyse au pool frontal, vous devez publier la nouvelle topologie pour que les modifications prennent effet. Pour publier votre nouvelle topologie, suivez les étapes suivantes dans le générateur de topologie:
  
1. Cliquez sur **Action**, pointez sur **Topologie**, puis cliquez sur **Publier**.
    
2. Dans la page **Publier la topologie** de l’Assistant Publication de topologie, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
Après avoir publié la topologie, vous pouvez installer la base de données d’analyse sur l’ordinateur qui va héberger le magasin d’analyse. La base de données de surveillance peut être installée à l’aide de Skype entreprise Server Management Shell et de Windows PowerShell. Pour installer la base de données en local (c’est-à-dire pour installer la base de données sur le même ordinateur que vous exécutez Skype entreprise Server Management Shell), démarrez Management Shell sur l’ordinateur approprié, puis tapez la commande suivante et appuyez sur entrée:
  
```
Install-CsDatabase -LocalDatabases
```

Lors de l’exécution de la commande précédente, install-CsDatabase lira la topologie actuelle de Skype entreprise Server, déterminez les bases de données qui doivent être installées sur l’ordinateur local, puis installez et configurez automatiquement chacune de ces bases de données.
  
Pour installer la base de données sur un ordinateur distant (c’est-à-dire, un ordinateur autre que l’ordinateur sur lequel Management Shell est exécuté), vous devez inclure au moins deux paramètres : les paramètres ConfiguredDatabases et SqlServerFqdn. Ces paramètres indiquent à l’applet de demande install-CsDatabase de récupérer la topologie du serveur Skype entreprise, puis installer et configurer les bases de données requises sur l’ordinateur spécifié par le paramètre SqlServerFqdn. Le paramètre SqlServerFqdn doit utiliser une valeur représentant le nom de domaine complet de l’ordinateur sur lequel les bases de données doivent être installées.
  
Par exemple, cette commande permet d’installer la base de données d’analyse sur l’ordinateur atl-sql-001.litwareinc.com :
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Vous pouvez également installer la base de données de surveillance en exécutant l’Assistant Déploiement de Skype entreprise sur l’ordinateur qui héberge le Windows Store. Pour ce faire, ouvrez une session sur l’ordinateur approprié, puis effectuez la procédure suivante :
  
1. Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Assistant Déploiement de Skype entreprise Server**.
    
2. Dans l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.
    
3. Sur la page **déployer** , sous **étape 2: configurer ou supprimer les composants Skype entreprise Server**, cliquez de **nouveau sur exécuter**.
    
4. Dans l’Assistant Configuration des composants du serveur Skype entreprise, sur la page **configurer les composants du serveur Skype entreprise** , cliquez sur **suivant**.
    
5. Dans la page spécifiez le **chemin d’accès à MSIS** , tapez le chemin d’accès au fichier OCSCore. msi (fichier inclus dans votre support d’installation de Skype entreprise Server), puis cliquez sur **suivant**.
    
6. Dans la page **Exécution de commandes**, cliquez sur **Terminer**.
    
Pour vous assurer que tous les services requis de Skype entreprise Server ont démarré, cliquez sur **exécuter** sous le titre **étape 4: démarrer les services** dans la page de **déploiement**
  

