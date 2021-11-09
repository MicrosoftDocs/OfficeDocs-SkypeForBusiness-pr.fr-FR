---
title: 'Skype Entreprise Server : Tester les paramètres de configuration d’une trunk SIP'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: 'Résumé : Découvrez comment tester les paramètres de configuration des trunks SIP à l’aide de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: 59f246abfc4ef27ad75ab45cccaedc6f5236c98e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829508"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype Entreprise Server : Tester les paramètres de configuration d’une trunk SIP
 
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
