---
title: Scénarios de performances de l’outil de stress et de performances de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 de façon à effectuer des opérations de performance et de test de charge à l’aide de l’outil stress et performance.
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299382"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scénarios de performances de l’outil de stress et de performances de Skype entreprise Server 2015
 
Tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 de façon à effectuer des opérations de performance et de test de charge à l’aide de l’outil stress et performance.
  
Pour exécuter l’outil de stress et de performance 2015 de Skype entreprise Server (LyncPerfTool), la topologie de Skype entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous intéressent. Si Skype entreprise Server 2015 n’est pas configuré ou s’il est configuré de manière incorrecte, votre simulation de charge risque de ne pas fonctionner. Grâce à l’outil de stress et de performances de Skype entreprise Server 2015, nous proposons des exemples de scripts et de fichiers de ressources de base de Skype entreprise [](https://www.microsoft.com/download/details.aspx?id=50367)Server Management Server. Ils peuvent servir de point de départ pour configurer votre déploiement de Skype entreprise Server. Cet article décrit les exemples Windows PowerShell proposés.
  
> [!NOTE]
> Dans cette rubrique, vous ne pourrez pas décrire la configuration de Skype entreprise Server 2015 en règle générale, nous avons d’autres rubriques de planification et de déploiement pour cela. Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype entreprise Server 2015, voir la documentation Skype entreprise Server Management Shell dans la section insérer une présentation ici. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>À propos de l’utilisation de scripts de gestion de Skype entreprise Server

Nous vous proposons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer votre simulation de charge. Dans la mesure où ces scripts sont destinés à une simulation de charge, vous pouvez les rendre plus simples et permissifs. Qui n’est pas approprié pour votre environnement de production. Dans de nombreux cas, nous faisons en sorte que ces scripts soient des exemples, vous devez les revoir et, dans de nombreux cas, apporter des modifications pertinentes à votre environnement avant de pouvoir les utiliser. Pour le moment, vous devez modifier le script de groupe de service de réponse (RSG) en tenant compte de votre topologie (pour spécifier les agents affectés aux groupes d’agents). Toutefois, vous n’avez pas besoin de l’exécuter, si ce n’est pas le cas.
  
> [!CAUTION]
> Prenez soin de revoir et de comprendre ces exemples. Les scripts écraseront tout paramètre existant dans la topologie lors de l’exécution. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Nom des versions du client de l’outil stress et performance

Vous devrez peut-être configurer la stratégie de vérification de la version du client si vous avez déjà modifié les paramètres des valeurs par défaut. Si vous n’êtes pas sûr de cela, consultez la [documentation relative à la version du client](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
L’outil stress and performance utilise par défaut les versions d’agent utilisateur suivantes lors de la communication avec Skype entreprise Server 2015:
  
- LSPT/15.0.0.0 (outil de stress et de performance de Skype entreprise Server 2015)
    
- OCPHONE/.0.522
    
Pour le client Mobility (UCWA) dans LyncPerfTool:
  
- Outil de performance/conférence Web UCWA
    
- Outil perf UCWA/mobile
    

