---
title: Migration des périphériques analogiques
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
description: Skype Entreprise Server assure la prise en charge des périphériques analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation de périphériques analogiques dans votre environnement Skype Entreprise Server. Après avoir migré vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés aux périphériques analogiques. Utilisez Skype Entreprise Server Management Shell pour d’abord récupérer tous les objets contact associés aux périphériques analogiques hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752826"
---
# <a name="migrate-analog-devices"></a>Migration des périphériques analogiques

Skype Entreprise Server assure la prise en charge des périphériques analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation de périphériques analogiques dans votre environnement Skype Entreprise Server. Après avoir migré vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés aux périphériques analogiques. Utilisez Skype Entreprise Server Management Shell pour d’abord récupérer tous les objets contact associés aux périphériques analogiques hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.

### <a name="to-migrate-analog-devices"></a>Pour migrer des périphériques analogiques

1. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**

2. Sur la ligne de commande, tapez :

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Vérifiez que tous les objets contact ont été déplacés vers le pool Skype Entreprise Server 2019. Sur la ligne de commande, tapez :

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Vérifiez que tous les objets contact sont désormais associés au pool Skype Entreprise Server 2019.


