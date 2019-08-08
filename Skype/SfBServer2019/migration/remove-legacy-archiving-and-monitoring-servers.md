---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si votre déploiement héritait d’un serveur d’archivage ou d’un serveur de surveillance après la migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs aient été supprimés de tous les pools hérités. Vous pouvez supprimer le serveur d’archivage ou la surveillance du serveur dans n’importe quelle séquence. La clé requise est que tous les utilisateurs ont été supprimés de tous les groupes hérités restants.
ms.openlocfilehash: 06d6287438e4b470017b00601b1e2ab472bea9b6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244227"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>Suppression des serveurs d’archivage et de surveillance hérités

Si votre déploiement héritait d’un serveur d’archivage ou d’un serveur de surveillance après la migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs aient été supprimés de tous les pools hérités. Vous pouvez supprimer le serveur d’archivage ou la surveillance du serveur dans n’importe quelle séquence. La clé requise est que tous les utilisateurs ont été supprimés de tous les groupes hérités restants.
  
Vous pouvez déplacer des utilisateurs vers Skype entreprise Server 2019 en suivant les procédures décrites dans la [phase 4: déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md).
  
Après avoir vérifié que tous les utilisateurs ont été supprimés de tous les pools restants, decommision le serveur et supprimez les rôles. Un exemple de date, mais pertinent, est «la désinstallation de Microsoft Lync Server et la suppression des rôles de serveur», [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)qui peut être téléchargé à l’adresse.
  

