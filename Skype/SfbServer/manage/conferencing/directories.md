---
title: Créer des annuaires de conférences dans Skype entreprise Server
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
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Résumé : Découvrez comment créer des répertoires de conférences dans Skype entreprise Server.'
ms.openlocfilehash: be8983b25937b2a1c068c9629a0f44fd06d494d6
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888673"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Créer des annuaires de conférences dans Skype entreprise Server
 
**Résumé :** Apprenez à créer des annuaires de conférences dans Skype entreprise Server.
  
Les annuaires de conférences maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lorsque vous utilisez Skype entreprise et l’ID de conférence numérique uniquement utilisé par un participant à la Conférence rendez-vous pour participer à la Conférence. 
  
## <a name="create-a-conference-directory"></a>Création d’un annuaire de conférences

La création de plusieurs annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences ait été créée. 
  
Dans une organisation avec un nombre type de conférences par utilisateur, nous recommandons de créer un annuaire de conférences pour chaque tranche de 999 utilisateurs. Le respect de cette consigne permet, en général, de limiter la longueur des ID de conférence. Toutefois, dès que le nombre d’annuaires de conférences (pour les pools) dépasse 9, la longueur de l’ID de conférence augmente pour prendre en charge d’autres conférences.
  
Le format d’un ID de conférence est le suivant : 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Pour créer un annuaire de conférences, utilisez l’applet de commande **New-CsConferenceDirectory**. Par exemple, la commande ci-dessous permet de créer un annuaire de conférence avec l’identité 42, hébergé sur le pool atl-cs-001.litwareinc.com :
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Pour plus d’informations, reportez-vous à [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

