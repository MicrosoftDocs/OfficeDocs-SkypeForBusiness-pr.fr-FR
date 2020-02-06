---
title: 'Publier la topologie : page Sélectionner un CMS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Vous publiez la topologie que vous avez configurée à l’aide du générateur de topologie. Vous êtes invité à effectuer une sélection dans une liste avec le serveur frontal ou le pool frontal qui assumera le rôle de conservation du magasin central de gestion. Un seul serveur frontal ou pool frontal ne peut accueillir ce rôle qu’à un moment donné.
ms.openlocfilehash: cae0f79b9787458ae1dd24077dfdd46689378414
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795415"
---
# <a name="publish-topology-select-cms-page"></a>Publier la topologie : page Sélectionner un CMS
 
Vous publiez la topologie que vous avez configurée à l’aide du générateur de topologie. Vous êtes invité à effectuer une sélection dans une liste avec le serveur frontal ou le pool frontal qui assumera le rôle de conservation du magasin central de gestion. Un seul serveur frontal ou pool frontal ne peut accueillir ce rôle qu’à un moment donné. 
  
### <a name="about-the-central-management-server"></a>À propos du serveur de gestion central
Le serveur de gestion central est un système de réplication maître/multiple unique, où la copie en lecture/écriture de la base de données est stockée par le serveur frontal qui contient le serveur de gestion central. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion central, dispose d’une copie en lecture seule de la base de données centrale de gestion de la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et développement. La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Lync Server exécuté en tant que service sur tous les ordinateurs. Le nom de la base de données réelle du serveur de gestion central et du réplica local est XDS, qui est constitué des fichiers XDS. mdf et XDS. ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory (AD DS). Tous les outils qui utilisent le serveur de gestion central pour gérer et configurer Lync Server utilisent le SCP pour trouver le magasin de gestion central.
  
## <a name="see-also"></a>Voir aussi

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
