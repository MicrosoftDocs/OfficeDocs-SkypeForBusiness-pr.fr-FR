---
title: Routage des appels vers des numéros non attribués
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
description: Découvrez comment router les appels vers des numéros non attribués dans votre organisation.
ms.openlocfilehash: f092cf5501d723dabb4336d648387833dd376e9b
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304056"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Routage des appels vers des numéros non attribués

En tant qu’administrateur, vous pouvez acheminer les appels vers des numéros non attribués dans votre organisation. Par exemple, vous souhaiterez peut-être acheminer les appels vers des numéros non attribués comme suit : 

- Routez tous les appels vers un numéro non attribué donné vers une annonce personnalisée.

- Routez tous les appels vers un numéro non attribué donné vers le tableau de bord principal.

Vous pouvez acheminer les appels vers des numéros non attribués à un utilisateur, vers un compte de ressource associé à un standard automatique ou à une file d’attente d’appels, ou à un service d’annonce qui va lire un fichier audio personnalisé à l’appelant.

## <a name="configuration"></a>Configuration

Pour acheminer les appels vers un numéro non attribué, utilisez l’applet de commande New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponible dans Teams module PowerShell 2.5.1 ou version ultérieure.

Vous devez spécifier le nombre ou la plage de nombres appelés et le routage associé pour les appels à ces numéros. Par exemple, la commande suivante spécifie que tous les appels au numéro +1 (555) 222-3333 seront routées vers le compte de ressource aa@contoso.com :

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

L’exemple suivant spécifie que tous les appels à la plage de nombres +1 (555) 333-0000 à +1 (555) 333-9999 seront acheminés vers le service d’annonce, qui lirea le fichier audio MainAnnouncement.wav à l’appelant.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Remarques

- Si vous effectuez le routage vers une annonce, le fichier audio est lu une seule fois sur l’appelant.

- Pour acheminer les appels vers des numéros d’abonnés du plan d’appels Microsoft non attribués, votre locataire doit disposer de [crédits de communication](what-are-communications-credits.md) disponibles.

- Pour acheminer les appels vers des numéros de service de plan d’appel Microsoft non attribués, votre locataire doit disposer d’au moins un Système téléphonique : licence d’utilisateur virtuel.

- Les formats pris en charge par le fichier audio personnalisé sont WAV (PCM linéaire non compressé avec une profondeur de 8/16/32 bits en mono ou stéréo), WMA (mono uniquement) et MP3. Le contenu du fichier audio ne peut pas dépasser 5 Mo.

- Les appels entrants à Microsoft Teams et les appels sortants de Microsoft Teams verront le numéro appelé vérifié par rapport à la plage de numéros non attribués.

- Si un modèle/plage spécifié contient des numéros de téléphone affectés à un compte d’utilisateur ou de ressource dans le locataire, les appels à ces numéros de téléphone sont acheminés vers la cible appropriée et non routés vers le traitement de numéros non attribués spécifié. Il n’y a pas d’autres vérifications des nombres dans la plage. Si la plage contient un numéro de téléphone externe valide, les appels sortants de Microsoft Teams vers ce numéro de téléphone seront acheminés en fonction du traitement.

## <a name="related-topics"></a>Voir aussi

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
