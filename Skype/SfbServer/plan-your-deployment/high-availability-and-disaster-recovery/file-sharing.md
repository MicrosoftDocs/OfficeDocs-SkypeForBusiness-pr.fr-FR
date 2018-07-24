---
title: Partage de fichiers haute disponibilité dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Découvrez comment assurer la haute disponibilité de vos partages de fichiers dans Skype pour Business Server, à l’aide de DFS.
ms.openlocfilehash: 645aa70ffc0c42cddb6941c9766cb91bed898dc8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989908"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Partage de fichiers haute disponibilité dans Skype pour Business Server
 
Découvrez comment assurer la haute disponibilité de vos partages de fichiers dans Skype pour Business Server, à l’aide de DFS.
  
Pour garantir une haute disponibilité pour le partage de fichiers dans votre Skype pour le déploiement de serveur d’entreprise, vous pouvez utiliser le système de fichiers distribués (DFS). DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données. Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS. Pour plus d’informations sur DFS dans Windows Server 2012, voir [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Pour plus d’informations sur le système DFS sur Windows Server 2008, voir [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
Selon la taille de votre réseau et la quantité de résistance que vous le souhaitez, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers dans un site ou utiliser une paire par pool frontal.
  
DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié. Un basculement entre les serveurs DFS doit être effectué rapidement, mais le délai de réplication de données peut empêcher les utilisateurs de pouvoir continuer le travail en cours lorsque le basculement se produit.
  
Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est crucial, vous devez sauvegarder fréquemment les partages de fichiers, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.
  

