---
title: Scénarios de performances pour le Skype pour Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches que vous devez faire pour configurer Skype pour Business Server 2015 faire des performances et test de charge, à l’aide du Stress and Performance Tool.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874590"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scénarios de performances pour le Skype pour Business Server 2015 Stress and Performance Tool
 
Tâches que vous devez faire pour configurer Skype pour Business Server 2015 faire des performances et test de charge, à l’aide du Stress and Performance Tool.
  
Pour exécuter le Skype pour Business Server 2015 Stress and Performance Tool (LyncPerfTool), le Skype pour Business Server 2015 topologie doit d’abord être configuré pour les scénarios qui vous intéressent. Si Skype pour Business Server 2015 n’est pas configuré ou est mal configuré, votre simulation de la charge est très risque d’échouer. Avec Skype pour Business Server 2015 Stress and Performance Tool, nous vous fournissons exemple Skype pour les scripts de Business Server Management Shell et des fichiers de ressources de base dans le cadre de l' [outil de téléchargement](https://www.microsoft.com/download/details.aspx?id=50367). Ces utilisable comme point de départ pour la configuration de votre Skype pour le déploiement de serveur d’entreprise. Cet article décrit les exemples de Windows PowerShell fournis.
  
> [!NOTE]
> Cette rubrique ne vous aidera à expliquent comment configurer Skype pour Business Server 2015 en règle générale, nous disposons d’autres rubriques de planification et de déploiement qui. Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype pour Business Server 2015, voir le Skype pour la documentation Business Server Management Shell insérer introduction ici. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sur l’exécution de scripts de shell Skype pour la gestion de serveur d’entreprise

Nous vous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer votre simulations de charge. Étant donné que ces scripts sont destinés à la simulation de charge, vous trouverez les simple et permissif. Qui peut ne pas convenir pour votre environnement de production. Nous une contrainte à nouveau que ces scripts sont des exemples, vous devez les consulter et dans de nombreux cas apporter des modifications appropriées à votre environnement avant de pouvoir les utiliser. Nous attendriez au minimum, que vous devez modifier le script de groupe de Service Response Group (récupération) avec votre topologie esprit (pour spécifier les agents affectés à des groupes d’agents). Mais vous n’avez à exécuter, si vous n’avez pas besoin.
  
> [!CAUTION]
> Veuillez prendre en charge dans la révision et de présentation de ces exemples. Scripts remplacera tous les paramètres existants dans la topologie lors de l’exécution. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Noms de version de client Stress and Performance Tool

Vous devrez peut-être configurer la stratégie de vérification de Version du Client si vous avez précédemment modifié les paramètres par défaut. Si vous avez des doutes quant à ce sujet, consultez la [documentation de vérification de Version du Client](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
Le Stress and Performance Tool utilise les versions suivantes de l’Agent utilisateur par défaut lors de la communication avec Skype pour Business Server 2015 :
  
- LSPT/15.0.0.0 (Skype pour Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Pour le client de mobilité (UCWA) dans LyncPerfTool :
  
- Conférence Web/outil Performance UCWA
    
- Outil de performances UCWA/Mobile
    

