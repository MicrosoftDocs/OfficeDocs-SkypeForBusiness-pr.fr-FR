---
title: 'Publier la topologie : page Sélectionner un CMS'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Vous publiez la topologie que vous avez configurée à l’aide du Générateur de topologies. Vous êtes invité à choisir dans une liste le serveur frontal ou le pool frontal qui assumera le rôle de gestion du magasin central de gestion. Un seul serveur frontal ou pool frontal peut contenir ce rôle à un moment donné.
ms.openlocfilehash: 4f4658b13a634d5f1d231d4e8fe7683b3fc38b8f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860561"
---
# <a name="publish-topology-select-cms-page"></a>Publier la topologie : page Sélectionner un CMS
 
Vous publiez la topologie que vous avez configurée à l’aide du Générateur de topologies. Vous êtes invité à choisir dans une liste le serveur frontal ou le pool frontal qui assumera le rôle de gestion du magasin central de gestion. Un seul serveur frontal ou pool frontal peut contenir ce rôle à un moment donné. 
  
### <a name="about-the-central-management-server"></a>À propos du serveur central de gestion
Le serveur central de gestion est un système de réplicas maître/multiple unique, où la copie en lecture/écriture de la base de données est détenue par le serveur frontal qui contient le serveur central de gestion. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur central de gestion, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et du déploiement. La base de données locale reçoit les mises à jour de réplicas par le moyen de l’agent réplicateur de réplicas Lync Server qui s’exécute en tant que service sur tous les ordinateurs. Le nom de la base de données réelle sur le serveur central de gestion et du réplica local est XDS, qui est composé des fichiers xds.mdf et xds.ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory. Tous les outils qui utilisent le serveur central de gestion pour gérer et configurer Lync Server utilisent le SCP pour localiser le magasin central de gestion.
  
## <a name="see-also"></a>Voir aussi

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)