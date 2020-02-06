---
title: Surveiller l’utilisation du service de mobilité et de UCWA dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : gestion du service de mobilité (MCX) et de l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817683"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Surveiller l’utilisation du service de mobilité et de UCWA dans Skype entreprise Server
 
**Résumé :** Gestion du service de mobilité (MCX) et de l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
D’un point de vue continu, vous devez surveiller l’unité centrale et la mémoire utilisée par le service de mobilité Skype entreprise Server (MCX) et l’API Web de communications unifiées (UCWA). Pour cela, vous pouvez utiliser l’un des éléments suivants :
  
 **Pour l’API web de communications unifiées (UCWA) :**
  
- Processus de travail **LyncUcwa** dans le gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %. L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire du serveur dans Skype entreprise Server](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **Ls : limitations sur le Web et Authentication\WEB : total des demandes de traitement**, qui indique le nombre de demandes Web en attente sur le serveur. Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **ASP.NET\Requests Queued** (doit toujours être égal à zéro).
    
> [!NOTE]
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web. 
  
 **Pour le service de mobilité (Mcx) :**
  
- Processus du travailleur **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;
    
- les compteurs de performances **UC** et **Processeur**.
    
Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %. L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire du serveur dans Skype entreprise Server](server-memory-capacity-limits.md).
  
Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :
  
- **ASP.NET v2.0.50727\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur. Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».
    
- **ASP.NET\Requests Queued** (doit toujours être égal à zéro).
    
> [!NOTE]
> Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web. 

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
## <a name="see-also"></a>Voir aussi

[Surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server](server-memory-capacity-limits.md)
