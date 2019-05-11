---
title: Tester les paramètres de configuration de jonction SIP dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. '
ms.openlocfilehash: 1caf96e9979936c8fb9ff61d9b28b613fb09ce7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902263"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Tester les paramètres de configuration de jonction SIP dans Skype pour Business Server

Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. Ces paramètres spécifient, par exemple :

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.
- Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.

Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) pour vérifier qu’une jonction permettre convertir un numéro composé par un utilisateur vers un numéro qui peut être géré par la passerelle.

Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande Test-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

**Pour tester les paramètres de configuration des jonctions SIP**

Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
