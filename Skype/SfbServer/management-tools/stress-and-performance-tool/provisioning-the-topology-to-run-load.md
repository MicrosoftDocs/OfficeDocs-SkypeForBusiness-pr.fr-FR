---
title: Mise en service de la topologie pour exécuter la charge dans les scénarios de Stress and Performance
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype pour Business Server 2015 les modifications ou la mise en service pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.
ms.openlocfilehash: 6ff08a3b99f4dc1f05b56c2a1fa86733ccf4f852
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373777"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Mise en service de la topologie pour exécuter la charge dans les scénarios de Stress and Performance
 
Skype pour Business Server 2015 les modifications ou la mise en service pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.
  
En fonction de vos paramètres existants et la configuration de votre déploiement de Skype pour Business Server 2015, vous devrez peut-être apporter quelques modifications dans votre environnement. Voici une liste de ces modifications :
  
1. Définir la stratégie d’exécution Windows PowerShell non restreint. Si vous n’êtes pas certain qu’il est défini sur actuellement, vous pouvez ouvrir le Skype pour Business Server Management Shell et exécutez la commande suivante :
    
   ```
   Get-ExecutionPolicy
   ```

   Si la valeur non restreint n’est pas renvoyée, vous devez exécuter ce suivant :
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. Pour configurer efficacement Skype pour Business Server, vous devez :
    
    - Être familiarisé avec votre Skype pour topologie Business Server 2015 (tels que les noms d’ordinateurs, des instances de service, les noms de site et des stratégies).
    
    - Attribuer certains des utilisateurs qui sont créés à des groupes, tels que des groupes (par exemple, URI SIP) de recherche Response Group.
    
3. Pour exécuter un script de ligne de commande, vous pouvez utiliser :
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. En règle générale, une fois que vous avez exécuter un script à partir de ce package, les suivis résultants seront stockés dans un fichier dans le même chemin d’accès à partir duquel le script a été exécuté. Il existe également un format de dénomination \<scriptname\>$h$m$s.txt. Ainsi, si vous avez exécuté l’ArchivingPolicy.ps1 à 12 h 15, vous obtiendrez un fichier journal nommé ArchivingPolicy121500.txt.
    
5. Pendant que nous avons fourni ces exemples pour la configuration de votre serveur, il est à la fois modifier votre configuration et de restaurer ou de déployer en une fois que vous avez fini de s’exécuter le test de charge.
    

