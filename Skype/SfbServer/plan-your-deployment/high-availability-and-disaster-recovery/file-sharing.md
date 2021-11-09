---
title: Haute disponibilité du partage de fichiers dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Découvrez comment garantir la haute disponibilité de vos partages de fichiers dans Skype Entreprise Server, à l’aide de DFS.
ms.openlocfilehash: e0af97da0bfc5a6ddb07284943640511e0dc06ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859871"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Haute disponibilité du partage de fichiers dans Skype Entreprise Server
 
Découvrez comment garantir la haute disponibilité de vos partages de fichiers dans Skype Entreprise Server, à l’aide de DFS.
  
Pour garantir la haute disponibilité du partage de fichiers dans Skype Entreprise Server déploiement, vous pouvez utiliser le système de fichiers distribués (DFS). DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données. Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés qui sont associés à l’aide de DFS. Pour plus d’informations sur DFS dans Windows Server 2012, voir [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) . Pour plus d’informations sur DFS Windows Server 2008, voir [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .
  
En fonction de la taille de votre réseau et du niveau de résistance souhaité, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers d’un site, ou utiliser une paire de serveurs par pool frontal.
  
DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié. Un failover entre les serveurs DFS doit être effectué rapidement, mais le délai de réplication des données peut empêcher les utilisateurs de poursuivre le travail en cours lorsque le retentage se produit.
  
Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est essentiel, vous devez les stocker fréquemment, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers tombe en panne et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur qui est associé à ce serveur à présent indisponible.
