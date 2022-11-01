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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez comment acheminer les appels vers des numéros non attribués dans votre organisation.
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795516"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Routage des appels vers des numéros non attribués

En tant qu’administrateur, vous pouvez router les appels vers des numéros non attribués dans votre organisation. Par exemple, vous souhaiterez peut-être router les appels vers des numéros non attribués comme suit : 

- Router tous les appels vers un numéro non attribué donné vers une annonce personnalisée.

- Acheminez tous les appels vers un numéro non attribué donné vers le standard principal.

Vous pouvez acheminer les appels vers des numéros non attribués à un utilisateur, vers un compte de ressource associé à un standard automatique ou à une file d’attente d’appels, ou vers un service d’annonce qui lira un fichier audio personnalisé à l’appelant.

Vous pouvez configurer le routage des numéros non attribués à l’aide du Centre d’administration Teams ou de PowerShell.

## <a name="use-teams-admin-center"></a>Utiliser le Centre d’administration Teams

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Numéros de téléphone vocaux** > .

2. Sous l’onglet **Règles de routage** , cliquez sur **Ajouter**.

3. Donnez un nom et une description à la règle et spécifiez l’ordre d’évaluation de la règle.

4. Déterminez le type de règle que vous souhaitez ajouter. Vous pouvez sélectionner des règles pour lesquelles le modèle de type de numéro de téléphone est préconfiguré et vous complétez le modèle et l’option de routage. Vous pouvez également sélectionner configuration avancée, où vous entrez directement l’expression régulière pour le modèle de numéro de téléphone et l’option de routage.

5. Sélectionnez **Enregistrer**.

Vous pouvez également créer une règle de routage directement pour un numéro de téléphone non attribué.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Numéros de téléphone vocaux** > .

2. Sous l’onglet **Nombres** , sélectionnez un numéro de téléphone non attribué, puis cliquez sur **Itinéraire** en haut de l’affichage.

4. Donnez un nom et une description à la règle et spécifiez l’ordre d’évaluation de la règle.

4. Sélectionnez l’option de routage.

5. Sélectionnez **Enregistrer**.

Vous pouvez tester vos règles de routage à l’aide de la fonctionnalité Numéro de test.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Numéros de téléphone vocaux** > .

2. Sous l’onglet **Règles de routage** , cliquez sur **Numéro de test**.

3. Entrez un numéro de téléphone directement ou cliquez sur **Sélectionner un numéro** et sélectionnez l’un de vos numéros de téléphone non attribués dans la liste déroulante.

4. Sélectionnez **Tester**.


## <a name="use-powershell"></a>Utiliser PowerShell

Pour acheminer les appels vers un numéro non attribué, utilisez l’applet de commande New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponible dans le module PowerShell Teams 2.5.1 ou ultérieur.

Vous devez spécifier le numéro ou la plage de numéros appelés et le routage associé pour les appels à ces numéros. Par exemple, la commande suivante spécifie que tous les appels au numéro +1 (555) 222-3333 seront routés vers le compte de ressource aa@contoso.com :

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

L’exemple suivant spécifie que tous les appels à la plage de numéros +1 (555) 333-0000 à +1 (555) 333-9999 seront acheminés vers le service d’annonce, qui lira le fichier audio MainAnnouncement.wav à l’appelant.

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Remarques

- Si vous effectuez un routage vers une annonce, le fichier audio est lu une fois à l’appelant.

- Pour acheminer les appels vers des numéros d’abonnés du plan d’appels Microsoft non attribués, votre locataire doit disposer [de crédits de communication](what-are-communications-credits.md) disponibles.

- Pour acheminer les appels vers des numéros de service de plan d’appels Microsoft non attribués, votre locataire doit disposer d’au moins une **licence de compte de ressource Téléphonie Microsoft Teams**.

- Les formats de fichiers audio personnalisés pris en charge sont WAV (pcm linéaire non compressé avec profondeur 8/16/32 bits en mono ou stéréo), WMA (mono uniquement) et MP3. Le contenu du fichier audio ne peut pas être supérieur à 5 Mo.

> [!NOTE]
> Vous êtes responsable de l’effacement et de la sécurisation de tous les droits et autorisations nécessaires pour utiliser tout fichier audio ou musical avec votre service Microsoft Teams. Cela peut inclure la propriété intellectuelle et d’autres droits sur toute musique, effets sonores, audio, marques, noms et autres contenus dans le fichier audio de tous les titulaires de droits pertinents. Les titulaires peuvent inclure des artistes, des acteurs, des interprètes, des musiciens, des auteurs-compositeurs, des compositeurs, des maisons de disques, des éditeurs de musique, des syndicats, des guildes, des sociétés de droits, des organisations de gestion collective, et toute autre partie qui possède, contrôle ou concédent les droits d’auteur, effets sonores, audio et autres droits de propriété intellectuelle.

- Tant les appels entrants vers Microsoft Teams que les appels sortants de Microsoft Teams auront le numéro appelé vérifié par rapport à la plage de numéros non attribués.

- Si un modèle/plage spécifié contient des numéros de téléphone attribués à un compte d’utilisateur ou de ressource dans le locataire, les appels à ces numéros de téléphone sont acheminés vers la cible appropriée et non acheminés vers le traitement de numéro non attribué spécifié. Il n’y a pas d’autres vérifications des nombres dans la plage. Si la plage contient un numéro de téléphone externe valide, les appels sortants de Microsoft Teams vers ce numéro de téléphone sont routés en fonction du traitement.


## <a name="related-topics"></a>Rubriques connexes

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
