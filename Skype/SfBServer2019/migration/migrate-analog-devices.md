---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype entreprise Server prend en charge les appareils analogiques. Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280842"
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


