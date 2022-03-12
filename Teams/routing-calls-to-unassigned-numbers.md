---
title: Routage des appels vers des numéros non instanés
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez comment router des appels vers des numéros non insignés dans votre organisation.
ms.openlocfilehash: f53e83b3d4f26123feed70bdecad32cb45bc5588
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442792"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Routage des appels vers des numéros non instanés

En tant qu’administrateur, vous pouvez router les appels vers des numéros non insignés dans votre organisation. Par exemple, vous souhaitez peut-être router les appels vers des numéros non insignés comme suit : 

- Routez tous les appels vers un numéro non attribué donné vers une annonce personnalisée.

- Routez tous les appels vers un numéro non attribué donné vers le tableau général principal.

Vous pouvez router des appels vers des numéros non affectationés vers un utilisateur, un compte de ressource associé à une Standard automatique ou à une file d’attente d’appels, ou vers un service d’annonces qui liera un fichier audio personnalisé à l’appelant.

## <a name="configuration"></a>Configuration

Pour router les appels vers un numéro non utilisé, utilisez la cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponible dans Teams Module PowerShell 2.5.1 ou une date ultérieure.

Vous devez spécifier le numéro ou la plage de numéros appelés et le routage associé pour les appels vers ces numéros. Par exemple, la commande suivante spécifie que tous les appels vers le numéro +1 (555) 222-3333 seront acheminés vers le compte de ressource pour aa@contoso.com :

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

L’exemple suivant spécifie que tous les appels vers la plage de numéro +1 (555) 333-0000 à +1 (555) 333-9999 seront acheminés vers le service d’annonces, qui liera le fichier audio MainAnnouncement.wav à l’appelant.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Remarques

- En cas de routage vers une annonce, le fichier audio est liffé une seule fois vers l’appelant.

- Pour router les appels vers des numéros d’abonnés Microsoft Calling Plan non attribues, votre client doit avoir des [crédits de communication disponibles](what-are-communications-credits.md).

- Pour router les appels vers des numéros de service Microsoft Calling Plan non insignés, votre client doit avoir au moins une licence Système téléphonique - Utilisateur virtuel.

- Les formats de fichier audio personnalisés pris en charge sont WAV (non compressé, linéaire PCM avec une profondeur 8/16/32 bits en mono ou stéréo), WMA (mono uniquement) et MP3. Le contenu du fichier audio ne peut pas avoir une taille plus de 5 Mo.

## <a name="related-topics"></a>Voir aussi

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
