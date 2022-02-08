---
title: Associer un magasin d’analyse à un pool frontal dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Résumé : Découvrez comment associer des pools frontux à un magasin d’analyse utilisé par Skype Entreprise Server.'
ms.openlocfilehash: 0092b75d35f97a7224e8946e24257c5f8ee6ea0d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385232"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associer un magasin d’analyse à un pool frontal dans Skype Entreprise Server 
**Résumé :** Découvrez comment associer des pools frontux à un magasin d’analyse utilisé par les Skype Entreprise Server.
  
Dans Skype Entreprise Server, les données de surveillance peuvent uniquement être collectées sur les pools frontux qui ont été associés à un magasin d’analyse, une tâche généralement effectuée lorsque vous définissez un pool frontal dans le Générateur de topologies.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associer un magasin d’analyse à un pool frontal

 Pour associer un magasin d’analyse à un nouveau pool frontal, veillez à sélectionner l’option Surveillance (enregistrement des détails des appels et enregistrement des mesures de qualité de l’expérience) sur **la page Sélectionner** des **fonctionnalités** de l’Assistant Définir un nouveau pool frontal. Notez que si vous sélectionnez cette option, vous devez également spécifier un magasin SQL pour terminer l’Assistant ; toutefois, ce magasin n’a pas besoin d’exister au moment où vous exécutez l’Assistant. Cela signifie que vous pouvez d’abord associer un pool à un magasin d’analyse, puis configurer et configurer ce magasin ultérieurement.
  
Vous pouvez également associer un pool frontal existant à un nouveau magasin d’analyse ou à un autre en effectuant la procédure suivante :
  
1. Cliquez **sur** Démarrer, sur Tous les **programmes, sur Skype Entreprise Server 2015**, puis sur Skype Entreprise Server **Générateur de topologies**.
    
2. Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
3. Dans la boîte de dialogue **Enregistrer sous**, entrez un nom de fichier pour votre topologie actuelle, puis cliquez sur **Enregistrer**. La topologie enregistrée peut être récupérée et republiée plus tard en cas de problèmes avec la nouvelle topologie.
    
4. Dans le Générateur de topologie, développez **Skype Entreprise Server**, développez le nom du site contenant le pool frontal, puis cliquez sur développer Êdition Entreprise **pools frontux**.
    
5. Cliquez avec le bouton droit sur le nom du pool à associer au magasin d’analyse, puis cliquez sur **Modifier les propriétés**.
    
6. Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, sélectionnez l’option **Surveillance (mesures CDR et QoE)**, puis sélectionnez une base de données SQL Server existante dans la liste déroulante **Magasin d’analyse SQL Server**. (Vous pouvez également cliquer sur **Nouveau** pour associer le pool à un nouveau magasin de bases de données.) Si vous décidez d’utiliser un nouveau magasin de bases de données, dans la boîte de dialogue **Définir un nouveau magasin SQL**, entrez le nom de domaine complet de l’ordinateur SQL Server dans la zone **Nom de domaine complet du serveur SQL Server**. Si vous choisissez d’utiliser l’instance SQL Server par défaut pour ce magasin, sélectionnez **Instance par défaut**, sinon, sélectionnez **Instance nommée**, puis entrez le nom de l’instance dans la zone **Instance nommée**.
    
    La boîte de dialogue **Modifier les propriétés** vous permet également de créer un miroir SQL pour votre base de données d’analyse (un miroir SQL vous permet de conserver deux copies de votre base de données d’analyse : une copie est stockée sur l’ordinateur du magasin d’analyse et l’autre copie sur l’ordinateur du miroir SQL). Pour activer la mise en miroir, sélectionnez T son **instance SQL est** dans une relation de mise en miroir et entrez le numéro de port du serveur miroir dans la zone numéro de **port de mise en** miroir.
    
7. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **OK**.
    
Après avoir associé le magasin d’analyse au pool frontal, vous devez publier la nouvelle topologie pour que les modifications prennent effet. Pour publier votre nouvelle topologie, effectuez les étapes suivantes dans le générateur de topologies :
  
1. Cliquez sur **Action**, pointez sur **Topologie**, puis cliquez sur **Publier**.
    
2. Dans l’Assistant Publication de topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
3. Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.
    
Après avoir publié la topologie, vous pouvez installer la base de données d’analyse sur l’ordinateur qui va héberger le magasin d’analyse. La base de données de surveillance peut être installée à l’aide Skype Entreprise Server Management Shell et Windows PowerShell. Pour installer la base de données localement (c’est-à-dire, pour installer la base de données sur l’ordinateur sur lequel vous exécutez l’Skype Entreprise Server Management Shell), démarrez Management Shell sur l’ordinateur approprié, puis tapez la commande suivante et appuyez sur Entrée :
  
```powershell
Install-CsDatabase -LocalDatabases
```

Lorsque vous exécutez la commande précédente, Install-CsDatabase lit la topologie Skype Entreprise Server actuelle, détermine les bases de données à installer sur l’ordinateur local, puis installe et configure automatiquement chacune de ces bases de données.
  
Pour installer la base de données sur un ordinateur distant (c’est-à-dire, un ordinateur autre que l’ordinateur sur lequel Management Shell est exécuté), vous devez inclure au moins deux paramètres : les paramètres ConfiguredDatabases et SqlServerFqdn. Ces paramètres indiquent à l'Install-CsDatabase de récupérer la topologie Skype Entreprise Server, puis d’installer et de configurer les bases de données requises sur l’ordinateur spécifié par le paramètre SqlServerFqdn. Le paramètre SqlServerFqdn doit utiliser une valeur représentant le nom de domaine complet de l’ordinateur sur lequel les bases de données doivent être installées.
  
Par exemple, cette commande permet d’installer la base de données d’analyse sur l’ordinateur atl-sql-001.litwareinc.com :
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Vous pouvez également installer la base de données de surveillance en exécutant l’Assistant Déploiement Skype Entreprise Server sur l’ordinateur qui hébergera le magasin d’analyse. Pour ce faire, ouvrez une session sur l’ordinateur approprié, puis effectuez la procédure suivante :
  
1. Cliquez **sur** Démarrer, sur Tous les **programmes,** **Skype Entreprise Server 2015**, puis sur Skype Entreprise Server **Déploiement**.
    
2. Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour Skype Entreprise Server système**.
    
3. Dans la page **Déployer**, sous **Étape 2** : Installer ou Skype Entreprise Server composants, cliquez sur **Exécuter à nouveau**.
    
4. Dans l’Assistant Skype Entreprise Server composants du programme d’installation, dans la page **Skype Entreprise Server composants**, cliquez sur **Suivant**.
    
5. Dans la page Spécifier le chemin d’accès aux **MSI**, tapez le chemin d’accès au Ocscore.msi de fichier (fichier inclus dans votre support d’installation Skype Entreprise Server), puis cliquez sur **Suivant**.
    
6. Dans la page de **Exécution de commandes**, cliquez sur **Terminer**.
    
Pour vous assurer que tous les services Skype Entreprise Server ont démarré, cliquez sur Exécuter sous  l’en-tête **Étape 4 : Démarrer les services** sur la page **Déployer**
  

