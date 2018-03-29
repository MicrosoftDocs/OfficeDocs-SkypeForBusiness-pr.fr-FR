---
title: Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype pour les modifications de la topologie Business Server 2015 ou la mise en service pour permettre aux utilisateurs d’exécuter l’outil de Stress et de performances.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances
 
Skype pour les modifications de la topologie Business Server 2015 ou la mise en service pour permettre aux utilisateurs d’exécuter l’outil de Stress et de performances.
  
Selon vos paramètres existants et la configuration de votre déploiement de Skype pour Business Server 2015, vous devrez peut-être effectuer des modifications dans votre environnement. Voici une liste de ces modifications :
  
1. Définir la stratégie d’exécution Windows PowerShell non restreint. Si vous n’êtes pas sûr qu’il est la valeur actuellement, vous pouvez ouvrir le Skype pour Business Server Management Shell et exécutez cette commande :
    
  ```
  Get-ExecutionPolicy
  ```

  Si la valeur non restreint n’est pas retournée, vous devez exécuter ce suivant :
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. Pour configurer efficacement Skype pour Business Server, vous devez :
    
    - Être familiarisé avec votre Skype pour la topologie 2015 de serveur d’entreprise (par exemple, les noms d’ordinateur, les instances de service, les noms de site et stratégies).
    
    - Affecter certains utilisateurs qui sont créées à des groupes, tels que les groupes (par exemple, URI SIP) de recherche de groupe de la réponse.
    
3. Pour exécuter un script à partir de la ligne de commande, vous pouvez utiliser :
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. En général, après avoir exécuté un script à partir de ce package, les traces qui en résulte seront stockées dans un fichier dans le même chemin d’accès à partir duquel le script a été exécuté. Il existe également un format de dénomination \<nom_script\>$h$m$s.txt. Par conséquent, si vous exécutez le ArchivingPolicy.ps1 à 12 h 15, vous obtiendrez un fichier journal nommé ArchivingPolicy121500.txt.
    
5. Alors que nous vous avons fourni ces exemples de configuration de votre serveur, c’est à vous des modifier votre configuration et restaurer ou déployer une fois vous avez fini d’exécuter le test de charge.
    

