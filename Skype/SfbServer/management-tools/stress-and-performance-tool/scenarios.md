---
title: Scénarios de performances pour l Skype Entreprise Server 2015 Stress and Performance Tool
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
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches à effectuer pour configurer Skype Entreprise Server 2015 afin d’effectuer des tests de performances et de charge à l’aide de l’outil Stress and Performance.
ms.openlocfilehash: 212a6fa1adc49508982e996ecdf61afc183d186b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611903"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scénarios de performances pour l Skype Entreprise Server 2015 Stress and Performance Tool
 
Tâches à effectuer pour configurer Skype Entreprise Server 2015 afin d’effectuer des tests de performances et de charge à l’aide de l’outil Stress and Performance.
  
Pour exécuter l’outil stress and performance Skype Entreprise Server 2015 (LyncPerfTool), la topologie Skype Entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous sont pertinents. Si Skype Entreprise Server 2015 n’est pas configuré ou est mal configuré, votre simulation de charge est très susceptible d’échouer. Avec l’outil Skype Entreprise Server 2015 Stress and Performance, nous fournissons des exemples de scripts Skype Entreprise Server Management Shell et des fichiers de ressources de base dans le cadre du téléchargement de [l’outil.](https://www.microsoft.com/download/details.aspx?id=50367) Ceux-ci peuvent être utilisés comme point de départ pour configurer votre déploiement Skype Entreprise Server déploiement. Cet article décrit les exemples Windows PowerShell fournis.
  
> [!NOTE]
> Cette rubrique ne vous aidera pas à décrire comment configurer Skype Entreprise Server 2015 en général, nous avons d’autres rubriques de planification et de déploiement à ce sujet. Pour plus d’informations sur l’Windows PowerShell de Skype Entreprise Server 2015, consultez la documentation Skype Entreprise Server Management Shell à l’introduction d’Insertion ICI. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>À propos de l’exécution Skype Entreprise Server scripts shell de gestion

Nous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer vos simulations de charge. Étant donné que ces scripts sont conçus pour la simulation de chargement, ils sont simples et permissifs. Cela peut ne pas être approprié pour votre environnement de production. Là encore, nous souligneons que ces scripts sont des exemples, vous devez les examiner et, dans de nombreux cas, apporter des modifications pertinentes à votre environnement avant de pouvoir les utiliser. Au minimum, nous nous attendons à ce que vous devrez modifier le script Response Service Group (RSG) en fonction de votre topologie (pour spécifier les agents affectés aux groupes d’agents). Mais vous n’avez pas besoin d’exécuter cela, si vous n’en avez pas besoin.
  
> [!CAUTION]
> Prenez soin de passer en revue et de comprendre ces exemples. Les scripts riteront tous les paramètres existants de la topologie lors de l’exécuter. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Noms de version du client de l’outil Stress and Performance

Vous devrez peut-être configurer la stratégie de vérification de version du client si vous avez précédemment modifié les paramètres par rapport aux valeurs par défaut. Si vous n’êtes pas sûr de cela, consultez la documentation de vérification [de version du client.](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)
  
L’outil Stress and Performance utilise les versions d’agent utilisateur suivantes par défaut lors de la communication avec Skype Entreprise Server 2015 :
  
- LSPT/15.0.0.0 (Skype Entreprise Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Pour le client mobility (UCWA) dans LyncPerfTool :
  
- Outil de perf UCWA/conférence web
    
- Outil de perf UCWA/Mobile
