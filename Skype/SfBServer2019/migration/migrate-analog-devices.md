---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour Business Server prend en charge pour les périphériques analogiques. Plus précisément, les périphériques analogiques pris en charge sont des téléphones audio analogiques et télécopieurs analogiques. Vous pouvez configurer les passerelles complets pour prendre en charge l’utilisation de périphériques analogiques dans votre Skype pour un environnement de serveur d’entreprise. Après avoir migré vers Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec les périphériques analogiques. Utiliser Skype pour Business Server Management Shell pour premier récupérer tous les contacts associés les périphériques analogiques hérités, puis déplacer ces objets vers le Skype pour Business Server 2019 pool.
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889965"
---
# <a name="migrate-analog-devices"></a>Migrer des périphériques analogiques

Skype pour Business Server prend en charge pour les périphériques analogiques. Plus précisément, les périphériques analogiques pris en charge sont des téléphones audio analogiques et télécopieurs analogiques. Vous pouvez configurer les passerelles complets pour prendre en charge l’utilisation de périphériques analogiques dans votre Skype pour un environnement de serveur d’entreprise. Après avoir migré vers Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec les périphériques analogiques. Utiliser Skype pour Business Server Management Shell pour premier récupérer tous les contacts associés les périphériques analogiques hérités, puis déplacer ces objets vers le Skype pour Business Server 2019 pool.

### <a name="to-migrate-analog-devices"></a>Pour migrer des périphériques analogiques

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.

2. À partir de la ligne de commande, tapez :

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Vérifiez que tous les objets contact ont été déplacés vers le Skype pour Business Server 2019 pool. À partir de la ligne de commande, tapez :

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Vérifiez que tous les objets contact sont désormais associé à la Skype pour Business Server 2019 pool.


