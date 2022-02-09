---
title: 'Skype Entreprise Server : tester les paramètres de configuration d’une trunk SIP'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Résumé : Découvrez comment tester les paramètres de configuration de la trunk SIP à l’aide de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: dd79e60b81bb5e9f0edbd93a9ddda96edfdee218
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396026"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype Entreprise Server : tester les paramètres de configuration d’une trunk SIP
 
**Résumé :** Découvrez comment tester les paramètres de configuration de la trunk SIP à l’aide de Skype Entreprise Server Management Shell.
  
Les paramètres de configuration de la trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX (IP-Public Branch eXchange) ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :
  
- Si le contournement de média doit être activé sur les trunks
    
- Conditions dans lesquelles les paquets RTCP (Realtime Transport Control Protocol) sont envoyés
    
- Si le chiffrement SRTP (Secure Realtime Transport Protocol) est requis sur chaque trunk
    
Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections de paramètres personnalisées au niveau de l’étendue Site ou Service (pour le service de passerelle PSTN uniquement). Les administrateurs peuvent également utiliser la cmdlet Test-CsTrunkConfiguration pour vérifier qu’une connexion peut convertir un numéro composé par un utilisateur en un numéro que la passerelle peut gérer.
  
Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration). Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Skype Entreprise Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Pour tester les paramètres de configuration de la trunk SIP

- Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir de façon correcte le numéro composé 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
