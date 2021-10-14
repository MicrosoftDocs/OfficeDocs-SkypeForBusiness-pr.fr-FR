---
title: Musique en attente
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 5e28aa4774d105b687551601ba89657d91a08170
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356552"
---
# <a name="music-on-hold"></a>Musique en attente

Lorsqu’un Microsoft Teams place un appel entrant en provenance du réseau téléphonique public commuté (PSTN) en attente, l’appelant PSTN peut écouter la musique sélectionnée.

La musique lie est soit la musique par défaut fournie par Microsoft, soit la musique personnalisée que vous téléchargez et configurez. En tant qu’administrateur client, vous configurez si Musique mise en attente est disponible en créant une stratégie d’appel Teams et en attribuant la stratégie à l Teams utilisateur. 

Notez que les appelants PSTN peuvent également écouter Musique en attente dans d’autres scénarios. par exemple, lorsqu’il appelle une file d’attente d’appels cloud ou quand son appel est mis en Microsoft Teams utilisateur. Ces scénarios ne sont pas couverts ni contrôlés par les fonctionnalités mentionnées dans cet article. 

## <a name="configure-music-on-hold"></a>Configurer l’Musique en attente

Pour configurer une Musique en attente :

1.  Dans le panneau de navigation de gauche du Teams d’administration, allez dans stratégies d> **d’appel voice.**

2.  Sous **l’onglet Gérer les** stratégies, sélectionnez une des stratégies existantes ou créez-en une.

3.  Dans la Musique en attente pour les appelants **PSTN,** sélectionnez **Activé dans** le menu déroulant.

Vous pouvez également configurer les Musique en attente à l’aide du module Teams PowerShell. Dans TeamsCallingPolicy, modifiez le paramètre MusicOnHoldEnabledType sur Activé, puis accordez cette instance de stratégie à un ou plusieurs utilisateurs.

Si un utilisateur Teams a une stratégie d’appel Teams avec l’Musique en attente définie sur Désactivée, aucun musique n’est joué quand l’utilisateur Teams place l’appel en attente.

## <a name="configure-custom-music"></a>Configurer une musique personnalisée

> [!NOTE]
> Cette fonctionnalité est disponible en version d’aperçu public.

En plus de lire de la musique par défaut pour les appelants PSTN, vous pouvez télécharger un fichier audio personnalisé avec de la musique ou tout autre contenu audio et configurer la lecture de ce fichier audio pour l’appelant PSTN.
Par exemple, un service ou une organisation peut être désireux de lire une annonce personnalisée ou une musique personnalisée lorsque des appelants PSTN externes sont mis en attente.  

> [!NOTE]
> Vous êtes responsable de la suppression et de la sécurisation indépendantes de tous les droits et autorisations nécessaires pour utiliser tout fichier audio ou audio avec votre service Microsoft Teams musique. Cela peut inclure la propriété intellectuelle et d’autres droits sur la musique, les effets sonores, l’audio, les marques, les noms et tout autre contenu du fichier audio de tous les titulaires des droits concernés. Les titulaires de droits peuvent inclure des artistes, des acteurs, des acteurs, des film, des musiques, des étiquettes d’enregistrement, des éditeurs de musique, des musiques, des garde, des droits, des organisations de gestion collectives et toute autre partie qui possède, contrôle ou licence les droits d’auteur, les effets sonores, les droits audio et autres droits de propriété intellectuelle.

Pour configurer des Musique personnalisées en attente, utilisez les cmdlets PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy et Import/Get/Remove-CsOnlineAudioFile dans Teams PowerShell module 2.5.0 ou une ultérieure.


1. Assurez-vous que l Teams un utilisateur Musique mise en attente pour les appelants PSTN définie sur Activé dans la stratégie Teams d’appel. 

2. Télécharger fichier audio personnalisé.

3. Créez une stratégie Teams de hold-in d’appels référaçant le fichier audio personnalisé et attribuez-la à l Teams utilisateur.

### <a name="upload-the-custom-audio-file"></a>Télécharger fichier audio personnalisé

La configuration de l’Musique mise en attente commence par le téléchargement du fichier audio. À cet effet, vous utilisez l'Import-CsOnlineAudioFile de cmdlet PowerShell. Voici un exemple de chargement d’un fichier audio MP3 à l’aide de l’interface PowerShell :

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Référencer le fichier audio dans une stratégie de Teams d’appel

Après avoir téléchargé le fichier audio, vous devez référencer le fichier dans une stratégie de mise en attente d’appel Teams à l’aide de l’ID du fichier lorsque vous créez ou définissez une stratégie de mise en attente d’appel Teams. Par exemple :

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Après avoir créé la nouvelle stratégie de Teams d’appel, vous pouvez l’accorder à vos utilisateurs en Grant-CsTeamsCallHoldPolicy de la façon suivante :

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Pour obtenir des informations sur vos fichiers audio téléchargés, utilisez la cmdlet Get-CsOnlineAudioFile fichiers.

Pour supprimer un fichier audio chargé, utilisez la cmdlet Remove-CsOnlineAudioFile fichiers. Avant de supprimer un fichier audio, vérifiez que vous n’utilisez pas ce fichier audio dans TeamsCallHoldPolicy.

## <a name="feature-availability"></a>Disponibilité des fonctionnalités

Le tableau suivant indique les fonctionnalités sur quels clients et appareils qui Musique en attente et les Musique personnalisées en attente. Microsoft continue d’ajouter la prise en charge des fonctionnalités. Vérifiez donc régulièrement si d’autres fonctionnalités sont disponibles.


| Fonctionnalité | Bureau <br> Windows/Mac OS | Navigateur | Mobile <br> iOS | Mobile <br> Android | Teams Téléphone |
| :------------| :------- | :------- | :------- | :------- | :------- |
| En attente lors d’un appel PSTN 1:1 | -Musique en attente<br>-Personnalisation Musique attente | -Musique en attente<br>-Personnalisation Musique attente | -Musique en attente<br>-Personnalisation Musique attente | Musique en attente | Musique en attente |
| Mettre en attente le transfert consultatif le 1:1 appel PSTN |-Musique en attente<br>-Personnalisation Musique attente | | | | |

## <a name="restrictions"></a>Restrictions

- Musique attente n’est disponible que dans le cloud commercial.

- Musique attente n’est disponible que lorsque l’utilisateur est en mode TeamsOnly.

- Si l’Teams d’appels est activé pour lLocation-Based routage des appels, l’Musique est en attente ne peut pas être joué à l’appelant.

- Vous ne pouvez pas exporter le fichier audio une fois qu’il a été téléchargé. vous pouvez uniquement le supprimer.

- Les Musique en attente personnalisée ne sont pas disponibles pour les utilisateurs configurés pour l’apparence de ligne partagée (délégation) et lorsque le parc d’appel est utilisé. L’Musique en attente standard est ledée.

- Dans certains cas, un appel de dérivation média de routage direct sera converti en contournement multimédia non multimédia pour la lecture de Musique en attente et l’appel restera comme une dérivation non multimédia jusqu’à la fin de l’appel.


## <a name="related-topics"></a>Sujets associés

- [Attribuer des stratégies aux utilisateurs](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





