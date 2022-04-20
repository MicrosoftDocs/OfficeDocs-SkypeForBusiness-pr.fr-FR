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
ms.custom: ''
description: Découvrez comment gérer la fonctionnalité Musique en attente dans Système téléphonique.
ms.openlocfilehash: 3e3e9c12eb459fdf52506be4577dfea88943ffa7
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922655"
---
# <a name="music-on-hold"></a>Musique en attente

Lorsqu’un utilisateur Microsoft Teams place un appel entrant en attente, l’appelant peut écouter la musique sélectionnée.

La musique qui est lue est soit la musique par défaut fournie par Microsoft, soit la musique personnalisée que vous chargez et configurez. En tant qu’administrateur client, vous configurez si Musique en attente est disponible en créant une stratégie d’appel Teams et en affectant la stratégie à l’utilisateur Teams.

La musique par défaut fournie dans Microsoft Teams scénarios d’appel est exempte de redevances payables par votre organisation.

Notez que les appelants peuvent également écouter Musique en attente dans d’autres scénarios; par exemple, lorsqu’ils appellent dans une file d’attente d’appels cloud ou lorsque leur appel est garé par un utilisateur Microsoft Teams. Ces scénarios ne sont pas couverts ou contrôlés par les fonctionnalités mentionnées dans cet article.

## <a name="configure-music-on-hold"></a>Configurer Musique en attente

Pour configurer Musique en attente :

1.  Dans le volet de navigation gauche du centre d’administration Teams, accédez aux **stratégies Voice > Calling**.

2.  Sous l’onglet **Gérer les stratégies** , sélectionnez l’une des stratégies existantes ou créez-en une.

3.  Dans le **Musique en attente pour le champ Appelants RTC**, **sélectionnez Activé** dans le menu déroulant.

Vous pouvez également configurer Musique en attente à l’aide du module PowerShell Teams. Dans TeamsCallingPolicy, remplacez le paramètre MusicOnHoldEnabledType par Activé, puis accordez cette instance de stratégie à un ou plusieurs utilisateurs.

Si un utilisateur Teams a une stratégie d’appel Teams avec Musique en attente définie sur Désactivé, aucune musique n’est lue lorsque l’utilisateur Teams met l’appel en attente.

## <a name="configure-custom-music"></a>Configurer la musique personnalisée

En plus de lire de la musique par défaut pour les appelants, vous pouvez charger un fichier audio personnalisé avec de la musique ou d’autres contenus audio et configurer ce fichier audio à lire sur l’appelant.
Par exemple, un service ou une organisation peut vouloir lire une annonce personnalisée ou de la musique personnalisée lorsque des appelants RTC externes sont mis en attente.  

> [!NOTE]
> Vous êtes responsable de l’effacement indépendant et de la sécurisation de tous les droits et autorisations nécessaires pour utiliser n’importe quel fichier audio ou de musique avec votre service Microsoft Teams. Cela peut inclure la propriété intellectuelle et d’autres droits dans la musique, les effets sonores, l’audio, les marques, les noms et autres contenus contenus dans le fichier audio de tous les titulaires de droits pertinents. Les titulaires peuvent inclure des artistes, des acteurs, des interprètes, des musiciens, des auteurs-compositeurs, des compositeurs, des maisons de disques, des éditeurs de musique, des syndicats, des corporations, des sociétés de droits, des organisations de gestion collective et toute autre partie qui détient, contrôle ou concéde les droits d’auteur de la musique, les effets sonores, l’audio et d’autres droits de propriété intellectuelle.

Pour configurer des Musique personnalisés en attente, utilisez les applets de commande PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy et Import/Get/Remove/Export-CsOnlineAudioFile dans Teams module PowerShell 3.0.0 ou ultérieur.

Pour connaître les formats audio pris en charge et la taille maximale du fichier, consultez [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)


1. Vérifiez que l’utilisateur Teams a Musique en attente pour les appelants RTC définis sur Activé dans la stratégie d’appel Teams. 

2. Télécharger le fichier audio personnalisé.

3. Créez une Teams stratégie de conservation des appels référençant le fichier audio personnalisé et affectez-le à l’utilisateur Teams.

### <a name="upload-the-custom-audio-file"></a>Télécharger le fichier audio personnalisé

La configuration des Musique personnalisés en attente commence par le chargement du fichier audio. Vous utilisez l’applet de commande PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) à cet effet.

Voici un exemple de chargement d’un fichier audio MP3 à l’aide de l’interface PowerShell :

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Référencer le fichier audio dans une Teams stratégie d’attente des appels

Une fois que vous avez chargé le fichier audio, vous devez référencer le fichier dans une Teams stratégie d’attente des appels à l’aide de l’ID du fichier lorsque vous créez ou définissez une Teams stratégie d’attente des appels. Par exemple :

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Une fois que vous avez créé la nouvelle stratégie Teams d’attente des appels, vous pouvez l’accorder à vos utilisateurs à l’aide de Grant-CsTeamsCallHoldPolicy comme suit :

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Pour obtenir des informations sur vos fichiers audio chargés, utilisez l’applet de commande Get-CsOnlineAudioFile.

Pour supprimer un fichier audio chargé, utilisez l’applet de commande Remove-CsOnlineAudioFile. Avant de supprimer un fichier audio, vérifiez que vous n’utilisez pas ce fichier audio dans teamsCallHoldPolicy.

Pour exporter un fichier audio chargé, utilisez l’applet de commande Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilité des fonctionnalités

Le tableau suivant indique les fonctionnalités sur lesquelles les clients et les appareils prennent en charge les Musique en attente et les Musique personnalisés en attente. Microsoft continue d’ajouter la prise en charge des fonctionnalités. Par conséquent, revenez souvent en arrière pour obtenir une disponibilité supplémentaire.


| Fonctionnalité | Bureau <br> Windows/Mac OS | Navigateur | Mobile <br> iOS | Mobile <br> Android | Teams Téléphone |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Maintenir l’appel RTC 1:1 | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente |
| Maintenez la touche 1:1 Teams appel | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente |
| Suspension du transfert consultatif lors de l’appel RTC 1:1 |-Musique en attente<br>-Musique personnalisé en attente || -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente |
| Suspension du transfert consultatif le 1er Teams appel |-Musique en attente<br>-Musique personnalisé en attente || -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente | -Musique en attente<br>-Musique personnalisé en attente |

## <a name="restrictions"></a>Restrictions

- Musique en attente est disponible uniquement dans les instances cloud commerciales et Cloud de la communauté du secteur public.

- Musique en attente est disponible uniquement lorsque l’utilisateur est en mode TeamsOnly.

- Si l’utilisateur Teams appelé est activé pour le routage Location-Based, Musique en attente ne peut pas être lu sur l’appelant.

- Les Musique personnalisés en attente ne sont pas disponibles pour les utilisateurs configurés pour l’apparence de ligne partagée (délégation) et lorsque le parc d’appels est utilisé. La Musique standard en attente sera jouée.

- Dans certains scénarios, un appel de contournement de média de routage direct est converti en contournement non multimédia pour la lecture Musique en attente et l’appel reste comme contournement non multimédia jusqu’à ce que l’appel soit arrêté.

## <a name="related-topics"></a>Voir aussi

- [Affecter des stratégies aux utilisateurs](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)
