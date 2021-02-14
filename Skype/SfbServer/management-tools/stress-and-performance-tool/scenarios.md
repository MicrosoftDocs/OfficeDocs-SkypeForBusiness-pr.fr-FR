---
title: Scénarios de performances pour l’outil Stress and Performance de Skype Entreprise Server 2015
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches à effectuer pour configurer Skype Entreprise Server 2015 afin d’effectuer des tests de performances et de charge à l’aide de l’outil Stress and Performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814704"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scénarios de performances pour l’outil Stress and Performance de Skype Entreprise Server 2015
 
Tâches à effectuer pour configurer Skype Entreprise Server 2015 afin d’effectuer des tests de performances et de charge à l’aide de l’outil Stress and Performance.
  
Pour exécuter l’outil Stress and Performance de Skype Entreprise Server 2015 (LyncPerfTool), la topologie Skype Entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous sont pertinents. Si Skype Entreprise Server 2015 n’est pas configuré ou n’est pas configuré de manière incorrecte, votre simulation de charge est très susceptible d’échouer. Avec l’outil Stress and Performance de Skype Entreprise Server 2015, nous fournissons des exemples de scripts Skype Entreprise Server Management Shell et des fichiers de ressources de base dans le cadre du téléchargement de [l’outil.](https://www.microsoft.com/download/details.aspx?id=50367) Ceux-ci peuvent servir de point de départ pour la configuration de votre déploiement de Skype Entreprise Server. Cet article décrit les exemples Windows PowerShell fournis.
  
> [!NOTE]
> Cette rubrique ne vous aidera pas à décrire comment configurer Skype Entreprise Server 2015 en général. Nous avons d’autres rubriques de planification et de déploiement à ce sujet. Pour plus d’informations sur l’Windows PowerShell dans Skype Entreprise Server 2015, consultez la documentation de Skype Entreprise Server Management Shell à l’adresse Insert introduction HERE. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>À propos de l’exécution des scripts de l’shell de gestion de Skype Entreprise Server

Nous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer vos simulations de charge. Étant donné que ces scripts sont conçus pour la simulation de chargement, ils sont simples et permissifs. Cela peut ne pas être approprié pour votre environnement de production. Là encore, nous souligneons que ces scripts sont des exemples, vous devez les examiner et, dans de nombreux cas, apporter des modifications pertinentes à votre environnement avant de pouvoir les utiliser. Au minimum, nous nous attendions à ce que vous devrez modifier le script Response Service Group (RSG) en fonction de votre topologie (pour spécifier les agents affectés aux groupes d’agents). Mais vous n’avez pas besoin d’exécuter cela, si vous n’en avez pas besoin.
  
> [!CAUTION]
> Prenez soin de passer en revue et de comprendre ces exemples. Les scripts riteront tous les paramètres existants de la topologie lors de l’exécuter. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Noms de version du client de l’outil Stress and Performance

Vous devrez peut-être configurer la stratégie de vérification de version du client si vous avez précédemment modifié les paramètres par rapport aux valeurs par défaut. Si vous n’êtes pas sûr de cela, consultez la [documentation de vérification de version du client.](https://msdn.microsoft.com/vsto/jj923060)
  
L’outil Stress and Performance utilise les versions d’agent utilisateur suivantes par défaut lors de la communication avec Skype Entreprise Server 2015 :
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Pour le client mobility (UCWA) dans LyncPerfTool :
  
- Outil de perf UCWA/conférence web
    
- Outil de perf UCWA/Mobile
    

