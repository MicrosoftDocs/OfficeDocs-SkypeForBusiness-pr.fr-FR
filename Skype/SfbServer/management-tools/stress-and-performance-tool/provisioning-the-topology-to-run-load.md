---
title: Approvisionnement de la topologie pour exécuter des scénarios de stress et de performance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Les modifications ou la mise en service de la topologie de Skype entreprise Server 2015 pour permettre aux utilisateurs d’exécuter avec succès l’outil de stress et de performance.
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816163"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Approvisionnement de la topologie pour exécuter des scénarios de stress et de performance
 
Les modifications ou la mise en service de la topologie de Skype entreprise Server 2015 pour permettre aux utilisateurs d’exécuter avec succès l’outil de stress et de performance.
  
Selon vos paramètres et votre configuration existants pour votre déploiement de Skype entreprise Server 2015, vous devrez peut-être apporter quelques modifications à votre environnement. Voici une liste de ces modifications :
  
1. Définissez la stratégie d’exécution Windows PowerShell sur non restreinte. Si vous n’êtes pas sûr de l’option définie pour le moment, vous pouvez ouvrir Skype entreprise Server Management Shell et exécuter cette commande :
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Si la valeur Unrestricted n’est pas renvoyée, vous devez l’exécuter suivante :
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Pour configurer efficacement Skype entreprise Server, vous devez :
    
    - Familiarisez-vous avec la topologie de Skype entreprise Server 2015 (par exemple, les noms d’ordinateurs, les instances de service, les noms de sites et les stratégies).
    
    - Assignez certains utilisateurs créés à des groupes, tels que les groupes de recherche de Response Group (par exemple, URI SIP).
    
3. Pour exécuter le script à partir de la ligne de commande, vous pouvez utiliser les éléments suivants :
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. En règle générale, une fois que vous avez exécuté un script depuis ce package, les traces obtenues seront stockées dans un fichier dans le même chemin à partir duquel le script est exécuté. Il existe également un format d’appellation \<scriptname\>$h $ m $ s. txt. Par conséquent, si vous avez exécuté ArchivingPolicy. ps1 au 12:15 PM, vous obtiendrez un fichier journal nommé ArchivingPolicy121500. txt.
    
5. Même si vous avez fourni ces exemples pour la configuration de votre serveur, vous devez modifier votre configuration et le restaurer ou le réactiver une fois que vous avez terminé d’exécuter le test de charge.
    

