---
title: Scénarios de performances pour le Skype pour Business Server 2015 Stress et l’outil performances
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches que vous devez faire pour configurer Skype pour 2015 de serveur d’entreprise faire des performances et test de charge, à l’aide de l’outil de performances et le Stress.
ms.openlocfilehash: 6b60d403e0a440e544874a8ed877a0b98e3e92ae
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scénarios de performances pour le Skype pour Business Server 2015 Stress et l’outil performances
 
Tâches que vous devez faire pour configurer Skype pour 2015 de serveur d’entreprise faire des performances et test de charge, à l’aide de l’outil de performances et le Stress.
  
Pour exécuter le Skype pour Business Server 2015 Stress et des performances, outil (LyncPerfTool), le Skype pour Business Server 2015 topologie doit d’abord être configuré pour les scénarios qui vous intéressent. Si Skype pour 2015 de serveur d’entreprise n’est pas configuré ou est mal configuré, votre simulation de charge est très susceptible d’échouer. Avec le Skype pour Business Server 2015 Stress et l’outil performances, nous vous fournissons exemple Skype pour les scripts de Business Server Management Shell et des fichiers de ressources de base dans le cadre de l' [outil de téléchargement](https://www.microsoft.com/download/details.aspx?id=50367). Ces peuvent être utilisées comme point de départ pour configurer votre Skype pour le déploiement du serveur de l’entreprise. Cet article décrit les exemples de Windows PowerShell.
  
> [!NOTE]
> Cette rubrique ne vous permet pas de décrire comment configurer Skype pour Business Server 2015, généralement, nous avons des autres rubriques de planification et de déploiement pour cela. Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype pour Business Server 2015, consultez le Skype pour la documentation Business Server Management Shell introduction insérer ici. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Sur l’exécution de scripts de shell Skype pour la gestion de serveur de l’entreprise

Nous vous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer votre simulations de charge. Dans la mesure où ces scripts sont destinés à la simulation de charge, vous les trouverez simple et permissive. Qui peut ne pas convenir à votre environnement de production. Nouveau nous Insistez sur le fait que ces scripts sont des exemples, vous devez les passer en revue et dans de nombreux cas apporter des modifications pertinentes pour votre environnement avant d’être en mesure de rendre leur utilisation pratique. Nous attendre au minimum, que vous devez modifier le script de réponse Service groupe (RSG) avec la topologie de votre esprit (pour spécifier les agents affectés aux groupes de l’agent). Mais vous ne devez exécuter qui, si vous n’avez pas besoin.
  
> [!CAUTION]
> Veuillez prendre en charge dans la révision et la compréhension de ces exemples. Remplacent tous les paramètres existants dans la topologie lors de l’exécution de scripts. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Noms de version de client stress et l’outil performances

Vous devrez peut-être configurer la stratégie de vérification de Version du Client si vous avez déjà modifié les paramètres par défaut. Si vous ne savez pas à ce sujet, consultez la [documentation de vérification de Version du Client](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
Le Stress et l’outil de Performance utilise les versions suivantes de l’Agent utilisateur par défaut lors de la communication avec Skype pour Business Server 2015 :
  
- LSPT/15.0.0.0 (Skype pour Business Server 2015 Stress et l’outil de Performance)
    
- OCPHONE/.0.522
    
Pour le client de mobilité (UCWA) dans LyncPerfTool :
  
- Conférence Web/outil de performance UCWA
    
- Outil de performance UCWA/mobiles
    

