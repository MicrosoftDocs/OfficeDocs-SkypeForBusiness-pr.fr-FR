---
title: Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype Entreprise Server la topologie 2015 ou la mise en service pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.
ms.openlocfilehash: 224a2c1afde71ce94b69826ee0222dce729d22d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611913"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances
 
Skype Entreprise Server la topologie 2015 ou la mise en service pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.
  
En fonction de vos paramètres existants et de la configuration de votre déploiement de Skype Entreprise Server 2015, vous devrez peut-être apporter des modifications à votre environnement. Voici une liste de ces modifications :
  
1. Définissez la stratégie Windows PowerShell’exécution sur Non restreint. Si vous ne savez pas exactement ce qu’il est actuellement, vous pouvez ouvrir l’Skype Entreprise Server Management Shell et exécuter la commande ci-après :
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Si la valeur Unrestricted n’est pas renvoyée, vous devez exécuter cette suivante :
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Pour configurer efficacement Skype Entreprise Server, vous devez :
    
    - Familiarisez-vous avec votre topologie Skype Entreprise Server 2015 (telle que les noms d’ordinateur, les instances de service, les noms de site et les stratégies).
    
    - Attribuez certains des utilisateurs créés à des groupes, tels que des groupements de recherche Response Group (par exemple, des URI SIP).
    
3. Pour exécuter un script à partir d’une ligne de commande, vous pouvez utiliser :
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. En règle générale, une fois que vous avez exécuté un script à partir de ce package, les suivis qui en résultent sont stockés dans un fichier dans le même chemin d’accès à partir de l’endroit où le script a été exécuté. Il existe également un format d’attribution de noms, \<scriptname\> $h$m$s.txt. Ainsi, si vous avez ArchivingPolicy.ps1 à 12:15 PM, vous obtenez un fichier journal nommé ArchivingPolicy121500.txt.
    
5. Même si nous avons fourni ces exemples pour la configuration de votre serveur, il vous revient à la fois de modifier votre configuration et de la restaurer ou de la restaurer une fois que vous avez terminé l’exécution du test de charge.
    

