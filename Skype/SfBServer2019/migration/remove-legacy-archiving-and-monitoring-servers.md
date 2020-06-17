---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si votre déploiement hérité contenait un serveur d’archivage ou un serveur de surveillance, après avoir effectué une migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, sous réserve que tous les utilisateurs aient été supprimés des autres pools hérités. Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre. La principale condition est que tous les utilisateurs aient été supprimés de tous les pools hérités restants.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752166"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Suppression des serveurs d’archivage et de surveillance hérités

Si votre déploiement hérité contient un serveur d’archivage ou un serveur de surveillance, après la migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs aient été supprimés de tous les autres pools hérités. Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre. La principale condition est que tous les utilisateurs aient été supprimés de tous les pools hérités restants.
  
Vous pouvez déplacer des utilisateurs vers Skype entreprise Server 2019 en suivant les procédures décrites dans la [phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).
  
Une fois que vous avez vérifié que tous les utilisateurs ont été supprimés de tous les pools restants, decommision le serveur et supprimez les rôles. Un exemple daté, mais pertinent, est le suivant : « désinstallation de Microsoft Lync Server et suppression des rôles serveur », qui peut être téléchargé à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .
  

