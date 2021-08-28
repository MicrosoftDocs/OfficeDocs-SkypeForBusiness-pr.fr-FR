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
ms.localizationpriority: medium
description: Vous pouvez utiliser le Panneau de contrôle des installation héritées pour empêcher l’exécution de nouvelles sessions pour tous les services hérités sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service hérité spécifique.
ms.openlocfilehash: 2f65d9453eab4548d9b4b94a5c6d38673d3ebd54
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595008"
---
# <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

Vous pouvez utiliser le Panneau de contrôle des installation héritées pour empêcher l’exécution de nouvelles sessions pour tous les services hérités sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service hérité spécifique.
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>Pour empêcher de nouvelles sessions pour les services sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur du réseau sur lequel vous avez déployé Skype Entreprise Server 2019.
    
2. Ouvrez Skype Entreprise panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
    
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur. 
    
5. Cliquez sur **Action**.
    
6. Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher l’exécution de nouvelles sessions d’un service spécifique

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur du réseau sur lequel vous avez déployé Skype Entreprise Server 2019.
    
2. Ouvrez Skype Entreprise panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
    
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur. 
    
5. Cliquez sur **Propriétés**.
    
6. Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.
    
7. Cliquez sur **Action**.
    
8. Cliquez sur **Empêcher de nouvelles sessions pour le service**.
    
9. Cliquez sur **Fermer**.
    

