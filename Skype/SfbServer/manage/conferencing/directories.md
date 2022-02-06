---
title: Créer des annuaires des conférences dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Résumé : Découvrez comment créer des annuaires des conférences dans Skype Entreprise Server.'
---

# <a name="create-conference-directories-in-skype-for-business-server"></a>Créer des annuaires des conférences dans Skype Entreprise Server
 
**Résumé :** Découvrez comment créer des annuaires des conférences dans Skype Entreprise Server.
  
Les annuaires des conférences conservent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lors de l’utilisation de Skype Entreprise et l’ID de conférence numérique uniquement qu’un participant à une conférence rendez-vous utilise pour participer à la conférence. 
  
## <a name="create-a-conference-directory"></a>Créer un annuaire des conférences

La création de plusieurs annuaires des conférences garantit que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences soit créée. 
  
Dans une organisation avec un nombre typique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour 999 utilisateurs dans le pool. À l’aide de cette recommandation, les ID de conférence peuvent généralement rester petits. Toutefois, une fois que le nombre d’annuaires des conférences (dans les pools) dépasse 9, la longueur de l’ID de conférence augmente pour prendre en charge des conférences supplémentaires.
  
Le format d’un ID de conférence est le suivant : 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Pour créer un annuaire des conférences, utilisez l’cmdlet **New-CsConferenceDirectory** . Par exemple, la commande suivante crée un annuaire de conférences avec l’identité 42, hébergé sur le pool atl-cs-001.litwareinc.com :
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Pour plus d’informations, [voir New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
