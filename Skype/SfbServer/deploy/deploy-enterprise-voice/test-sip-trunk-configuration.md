---
title: Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Résumé : Découvrez comment tester les paramètres de configuration du Trunk SIP à l’aide de Skype entreprise Server Management Shell.'
ms.openlocfilehash: 7f0d4f4046a5bffbde4267b5de8ae651a35a2add
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001974"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server
 
**Résumé :** Découvrez comment tester les paramètres de configuration du Trunk SIP à l’aide de Skype entreprise Server Management Shell.
  
Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :
  
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
    
- les conditions dans lesquelles les paquets RTCP sont envoyés ;
    
- si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.
    
Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande Test-CsTrunkConfiguration pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en numéro pouvant être traité par la passerelle.
  
Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Ce cmdlet peut être exécuté à partir de Skype entreprise Server Management Shell ou d’une session à distance de Skype entreprise Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Pour tester les paramètres de configuration des jonctions SIP

- Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


