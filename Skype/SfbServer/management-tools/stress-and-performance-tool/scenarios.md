---
title: Scénarios de performances pour l’outil de contrainte et de performances de Skype entreprise Server 2015
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
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Les tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 pour effectuer des tests de performances et de chargement à l’aide de l’outil stress and performance.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983849"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Scénarios de performances pour l’outil de contrainte et de performances de Skype entreprise Server 2015
 
Les tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 pour effectuer des tests de performances et de chargement à l’aide de l’outil stress and performance.
  
Pour exécuter l’outil de contrainte et de performances de Skype entreprise Server 2015 (LyncPerfTool), la topologie de Skype entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous concernent. Si Skype entreprise Server 2015 n’est pas configuré ou qu’il est configuré de manière incorrecte, votre simulation de charge risque d’échouer. Avec l’outil de contrainte et de performances de Skype entreprise Server 2015, nous fournissons des exemples de scripts Skype entreprise Server Management Shell et des fichiers de ressources de base dans le cadre du téléchargement de l' [outil](https://www.microsoft.com/download/details.aspx?id=50367). Ces éléments peuvent être utilisés comme point de départ pour la configuration de votre déploiement de Skype entreprise Server. Cet article décrit les exemples Windows PowerShell fournis.
  
> [!NOTE]
> Cette rubrique ne vous aidera pas à décrire la configuration de Skype entreprise Server 2015 généralement, nous avons d’autres rubriques de planification et de déploiement pour cela. Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype entreprise Server 2015, reportez-vous à la documentation de Skype entreprise Server Management Shell dans insérer Introduction ici. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>À propos de l’exécution de scripts Skype entreprise Server Management Shell

Nous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour vous préparer à vos simulations de charge. Étant donné que ces scripts sont destinés à la simulation de charge, vous les trouverez comme simples et permissants. Cela n’est peut-être pas approprié pour votre environnement de production. À nouveau, nous insistons sur le fait que ces scripts sont des exemples, que vous devez les examiner et, dans de nombreux cas, effectuer des modifications pertinentes pour votre environnement avant de pouvoir les utiliser. Au minimum, il est nécessaire de modifier le script de groupe de service de réponse (RSG) en tenant compte de votre topologie (pour spécifier les agents affectés aux groupes d’agents). Toutefois, si vous n’avez pas besoin de le faire, il n’est pas nécessaire de l’exécuter.
  
> [!CAUTION]
> Veillez à examiner et à comprendre ces exemples. Les scripts remplaceront les paramètres existants dans la topologie lors de l’exécution. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Noms des versions du client outil de stress et de performances

Vous devrez peut-être configurer la stratégie de vérification de la version du client si vous avez déjà modifié les valeurs par défaut des paramètres. Si vous n’êtes pas sûr de ce sujet, consultez la documentation de vérification de la [version du client](https://msdn.microsoft.com/vsto/jj923060).
  
L’outil stress and performance utilise par défaut les versions suivantes de l’agent utilisateur lors de la communication avec Skype entreprise Server 2015 :
  
- LSPT/15.0.0.0 (outil de contrainte et de performances de Skype entreprise Server 2015)
    
- OCPHONE/.0.522
    
Pour le client Mobility (UCWA) dans LyncPerfTool :
  
- Outil perf UCWA/conférence Web
    
- Outil de performances UCWA/mobile
    

