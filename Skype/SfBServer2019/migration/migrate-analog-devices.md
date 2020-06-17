---
title: Migrer des périphériques analogiques
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
description: Skype entreprise Server prend en charge les appareils analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après avoir effectué la migration vers Skype entreprise Server 2019, vous devez également migrer les objets contact associés aux appareils analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets contact associés aux appareils analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752826"
---
# <a name="migrate-analog-devices"></a>Migrer des périphériques analogiques

Skype entreprise Server prend en charge les appareils analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après avoir effectué la migration vers Skype entreprise Server 2019, vous devez également migrer les objets contact associés aux appareils analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets contact associés aux appareils analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.

### <a name="to-migrate-analog-devices"></a>Pour migrer des périphériques analogiques

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.

2. Sur la ligne de commande, tapez :

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Vérifiez que tous les objets contact ont été déplacés vers le pool Skype entreprise Server 2019. Sur la ligne de commande, tapez :

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Vérifiez que tous les objets contact sont désormais associés au pool Skype entreprise Server 2019.


