---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype entreprise Server prend en charge les appareils analogiques. Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: 486c49c0ace00b798520ebae939c0c2070a99783
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238038"
---
# <a name="migrate-analog-devices"></a>Migrer des périphériques analogiques

Skype entreprise Server prend en charge les appareils analogiques. Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.

### <a name="to-migrate-analog-devices"></a>Pour migrer des périphériques analogiques

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. À partir de la ligne de commande, tapez :

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Vérifiez que tous les objets de contact ont été déplacés vers le pool Skype entreprise Server 2019. À partir de la ligne de commande, tapez :

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Vérifiez que tous les objets de contact sont désormais associés au pool 2019 de Skype entreprise Server.


