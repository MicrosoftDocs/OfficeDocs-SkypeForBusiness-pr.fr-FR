---
title: Forte disponibilité du partage de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: En savoir plus sur la façon de garantir une haute disponibilité des partages de fichiers dans Skype entreprise Server, à l’aide du système de fichiers DFS.
ms.openlocfilehash: 56a6e1008935bc0d38d65e2355826634709aed27
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297476"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Forte disponibilité du partage de fichiers dans Skype entreprise Server
 
En savoir plus sur la façon de garantir une haute disponibilité des partages de fichiers dans Skype entreprise Server, à l’aide du système de fichiers DFS.
  
Pour garantir une haute disponibilité du partage de fichiers dans votre déploiement Skype entreprise Server, vous pouvez utiliser le système de fichiers DFS. DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données. Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS. Pour plus d’informations sur le système de fichiers DFS dans [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)Windows Server 2012, voir. Pour plus d’informations sur le système de fichiers DFS [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)sur Windows Server 2008, voir.
  
En fonction de la taille de votre réseau et de la capacité de résilience souhaitée, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers dans un site, ou utiliser une paire par pool frontal.
  
DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié. Un basculement entre serveurs DFS doit être effectué rapidement, mais un délai de réplication des données peut empêcher les utilisateurs de continuer à travailler en cours lorsque le basculement a lieu.
  
Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est crucial, vous devez sauvegarder fréquemment les partages de fichiers, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.
  

