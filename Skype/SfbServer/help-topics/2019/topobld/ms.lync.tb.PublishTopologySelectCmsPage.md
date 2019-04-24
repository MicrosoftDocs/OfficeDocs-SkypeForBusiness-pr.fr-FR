---
title: 'Publier la topologie : page Sélectionner un CMS'
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Vous publiez la topologie que vous avez configurées à l’aide du Générateur de topologie. Vous êtes invité à sélectionner à partir d’une liste pool frontal ou serveur frontal assumeront le rôle de contenir le magasin Central de gestion. Qu’un seul pool frontal ou serveur frontal peut contenir ce rôle à un moment donné.
ms.openlocfilehash: 0c80fa30721fe47fc3bc4725ca4f50f8a75f7009
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201692"
---
# <a name="publish-topology-select-cms-page"></a>Publier la topologie : page Sélectionner un CMS
 
Vous publiez la topologie que vous avez configurées à l’aide du Générateur de topologie. Vous êtes invité à sélectionner à partir d’une liste pool frontal ou serveur frontal assumeront le rôle de contenir le magasin Central de gestion. Qu’un seul pool frontal ou serveur frontal peut contenir ce rôle à un moment donné. 
  
### <a name="about-the-central-management-server"></a>Sur le serveur d’administration centrale
Le serveur de gestion centrale est un système maître/plusieurs réplicas, où la copie en lecture/écriture de la base de données est détenue par le serveur frontal qui contient le serveur d’administration centrale. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin Central de gestion de la base de SQL Server (appelée RTCLOCAL par défaut) installée sur l’ordinateur pendant l’installation et déploiement. La base de données local reçoit des mises à jour du réplica par l’Agent réplicateur d’utilisateurs Lync Server réplica qui s’exécute en tant que service sur tous les ordinateurs. Le nom de la base de données sur le serveur de gestion centrale et du réplica local est XDS, qui est composée des fichiers xds.mdf et xds.ldf. L’emplacement de la base de données master est référencé par un point de contrôle de service (SCP) dans les Services de domaine Active Directory. Tous les outils qui utilisent le serveur d’administration centrale pour gérer et configurer Lync Server utilisent le SCP pour localiser le magasin Central de gestion.
  
## <a name="see-also"></a>Voir aussi

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
