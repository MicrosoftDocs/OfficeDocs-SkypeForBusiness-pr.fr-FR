---
title: Créer des annuaires de conférences dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Résumé: Découvrez comment créer des répertoires de conférences dans Skype entreprise Server.'
ms.openlocfilehash: d2962e7e01ba5bb73ce82de9b5c0ff85550fbe99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306495"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Créer des annuaires de conférences dans Skype entreprise Server
 
**Résumé:** Apprenez à créer des annuaires de conférences dans Skype entreprise Server.
  
Les annuaires de conférences maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lorsque vous utilisez Skype entreprise et l’ID de conférence numérique uniquement utilisé par un participant à la Conférence rendez-vous pour participer à la Conférence. 
  
## <a name="create-a-conference-directory"></a>Création d’un annuaire de conférences

La création de plusieurs annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences ait été créée. 
  
Dans une organisation avec un nombre type de conférences par utilisateur, nous recommandons de créer un annuaire de conférences pour chaque tranche de 999 utilisateurs. Le respect de cette consigne permet, en général, de limiter la longueur des ID de conférence. Toutefois, dès que le nombre d’annuaires de conférences (pour les pools) dépasse 9, la longueur de l’ID de conférence augmente pour prendre en charge d’autres conférences.
  
Le format d’un ID de conférence est le suivant : 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Pour créer un annuaire de conférences, utilisez l’applet de commande **New-CsConferenceDirectory**. Par exemple, la commande ci-dessous permet de créer un annuaire de conférence avec l’identité 42, hébergé sur le pool atl-cs-001.litwareinc.com :
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Pour plus d’informations, reportez-vous à [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

