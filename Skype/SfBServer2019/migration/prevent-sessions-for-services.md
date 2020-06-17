---
title: Empêcher l’exécution de sessions de services
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
description: Vous pouvez utiliser le panneau de configuration des installations héritées pour empêcher les nouvelles sessions de tous les services hérités en cours d’exécution sur un ordinateur spécifique ou pour empêcher l’exécution de nouvelles sessions pour un service hérité spécifique.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752286"
---
# <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

Vous pouvez utiliser le panneau de configuration des installations héritées pour empêcher les nouvelles sessions de tous les services hérités en cours d’exécution sur un ordinateur spécifique ou pour empêcher l’exécution de nouvelles sessions pour un service hérité spécifique.
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>Pour empêcher l’activation de nouvelles sessions pour les services sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server 2019.
    
2. Ouvrez le panneau de configuration Skype entreprise.
    
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
    
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur. 
    
5. Cliquez sur **Action**.
    
6. Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher l’exécution de nouvelles sessions d’un service spécifique

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server 2019.
    
2. Ouvrez le panneau de configuration Skype entreprise.
    
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
    
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur. 
    
5. Cliquez sur **Propriétés**.
    
6. Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.
    
7. Cliquez sur **Action**.
    
8. Cliquez sur **Empêcher de nouvelles sessions pour le service**.
    
9. Cliquez sur **Fermer**.
    

