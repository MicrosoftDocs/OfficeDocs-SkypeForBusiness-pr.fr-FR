---
title: Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server
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
description: 'Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. '
ms.openlocfilehash: 911947b33f0e609b4dd532ec5cc2c3d56a08618c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816934"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server

Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. Ces paramètres spécifient, par exemple :

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.
- Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.

Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de [contrôle test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) pour vérifier qu’un Trunk peut convertir un nombre comme composé par un utilisateur sur un numéro qui peut être géré par la passerelle.

Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande Test-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

**Pour tester les paramètres de configuration des jonctions SIP**

Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
