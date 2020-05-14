---
title: Tester les paramètres de configuration de jonction SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. '
ms.openlocfilehash: bed342de3f602499f16b9f27ee0726f10d2c867e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "42048187"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Tester les paramètres de configuration de jonction SIP dans Skype entreprise Server

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

- L’activation ou non du contournement de média sur les jonctions.
- Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).
- L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration de jonction SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande [test-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en un nombre pouvant être géré par la passerelle.

Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande Test-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

**Pour tester les paramètres de configuration de jonction SIP**

Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir de façon correcte le numéro composé 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
