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
description: Découvrez comment gérer la fonctionnalité Musique en attente dans le système téléphonique.
ms.openlocfilehash: 9e2a2aa352a1fd65955b35d4175b831653c694cb
ms.sourcegitcommit: 52450514880fe72af0d0b2fab1419eadfc3a583f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68499448"
---
# <a name="music-on-hold"></a>Musique en attente

Lorsqu’un utilisateur Microsoft Teams met un appel entrant en attente, l’appelant peut écouter la musique sélectionnée.

La musique qui est lue est soit la musique par défaut fournie par Microsoft, soit la musique personnalisée que vous chargez et configurez. En tant qu’administrateur client, vous configurez si Music on Hold est disponible en créant une stratégie d’appel Teams et en affectant la stratégie à l’utilisateur Teams.

La musique par défaut fournie dans les scénarios d’appel Microsoft Teams est exempte de redevances payables par votre organisation.

Notez que les appelants peuvent également écouter de la musique en attente dans d’autres scénarios; par exemple, lorsqu’ils appellent dans une file d’attente d’appels cloud ou lorsque leur appel est garé par un utilisateur Microsoft Teams. Ces scénarios ne sont pas couverts ou contrôlés par les fonctionnalités mentionnées dans cet article.

## <a name="configure-music-on-hold"></a>Configurer la musique en attente

Pour configurer Music on Hold :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez aux **stratégies d’appel > voix**.

2. Sous l’onglet **Gérer les stratégies** , sélectionnez l’une des stratégies existantes ou créez-en une.

3. Dans le champ **Musique en attente pour les appelants RTC** , sélectionnez **Activé** dans le menu déroulant.

Vous pouvez également configurer Music on Hold à l’aide du module Teams PowerShell. Dans TeamsCallingPolicy, remplacez le paramètre MusicOnHoldEnabledType par Activé, puis accordez cette instance de stratégie à un ou plusieurs utilisateurs.

Si un utilisateur Teams a une stratégie d’appel Teams avec La musique en attente définie sur Désactivé, aucune musique n’est lue lorsque l’utilisateur Teams met l’appel en attente.

## <a name="configure-custom-music"></a>Configurer la musique personnalisée

En plus de lire de la musique par défaut pour les appelants, vous pouvez charger un fichier audio personnalisé avec de la musique ou d’autres contenus audio et configurer ce fichier audio à lire sur l’appelant.
Par exemple, un service ou une organisation peut vouloir lire une annonce personnalisée ou de la musique personnalisée lorsque des appelants RTC externes sont mis en attente.

La configuration est effectuée à l’aide de stratégies de conservation des appels.

> [!NOTE]
> Vous êtes responsable de l’effacement et de la sécurisation indépendants de tous les droits et autorisations nécessaires pour utiliser n’importe quel fichier audio ou musique avec votre service Microsoft Teams. Cela peut inclure la propriété intellectuelle et d’autres droits dans la musique, les effets sonores, l’audio, les marques, les noms et autres contenus contenus dans le fichier audio de tous les titulaires de droits pertinents. Les titulaires peuvent inclure des artistes, des acteurs, des interprètes, des musiciens, des auteurs-compositeurs, des compositeurs, des maisons de disques, des éditeurs de musique, des syndicats, des corporations, des sociétés de droits, des organisations de gestion collective et toute autre partie qui détient, contrôle ou concéde les droits d’auteur de la musique, les effets sonores, l’audio et d’autres droits de propriété intellectuelle.

### <a name="use-the-teams-admin-center"></a>Utiliser le Centre d’administration Teams
Vous pouvez utiliser le Centre d’administration Teams pour configurer la musique personnalisée en attente pour vos utilisateurs en créant ou en modifiant des stratégies de conservation des appels.

Pour configurer une nouvelle stratégie de conservation des appels :

1. Dans le Centre d’administration Teams, accédez aux **stratégies de conservation des appels** **vocaux** > .

2. Sélectionnez l’onglet **Ajouter** .

3. Donnez un nom et une description à la stratégie.

4. Sélectionnez **Charger le fichier** pour charger le fichier audio de musique personnalisé.

5. Sélectionnez **Appliquer**.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>Affecter une stratégie de conservation des appels personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>Utiliser PowerShell
Pour configurer la musique personnalisée en attente, utilisez les applets de commande PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy et Import/Get/Remove/Export-CsOnlineAudioFile dans le module Teams PowerShell 3.0.0 ou version ultérieure.

Pour connaître les formats audio pris en charge et la taille maximale du fichier, consultez [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Assurez-vous que l’utilisateur Teams a la fonctionnalité Musique en attente pour les appelants RTC définie sur Activé dans la stratégie d’appel Teams. 

2. Chargez le fichier audio personnalisé.

3. Créez une stratégie de suspension des appels Teams référençant le fichier audio personnalisé et affectez-la à l’utilisateur Teams.

### <a name="upload-the-custom-audio-file"></a>Charger le fichier audio personnalisé

La configuration de musique personnalisée en attente commence par le chargement du fichier audio. Vous utilisez l’applet de commande PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) à cet effet.

Vous trouverez ci-dessous un exemple de chargement d’un fichier audio MP3 à l’aide de Windows PowerShell 5.1. Pour d’autres exemples, consultez [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = [System.IO.File]::ReadAllBytes('C:\tmp\customMoH1.mp3')
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Référencer le fichier audio dans une stratégie de suspension des appels Teams

Une fois que vous avez chargé le fichier audio, vous devez référencer le fichier dans une stratégie de conservation des appels Teams à l’aide de l’ID du fichier lorsque vous créez ou définissez une stratégie de conservation des appels Teams. Par exemple :

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Une fois que vous avez créé la nouvelle stratégie d’attente des appels Teams, vous pouvez l’accorder à vos utilisateurs à l’aide de Grant-CsTeamsCallHoldPolicy comme suit :

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Pour obtenir des informations sur vos fichiers audio chargés, utilisez l’applet de commande Get-CsOnlineAudioFile.

Pour supprimer un fichier audio chargé, utilisez l’applet de commande Remove-CsOnlineAudioFile. Avant de supprimer un fichier audio, vérifiez que vous n’utilisez pas ce fichier audio dans teamsCallHoldPolicy.

Pour exporter un fichier audio chargé, utilisez l’applet de commande Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilité des fonctionnalités

Le tableau suivant indique les fonctionnalités sur lesquelles les clients et appareils prennent en charge la musique en attente et la musique personnalisée en attente. Microsoft continue d’ajouter la prise en charge des fonctionnalités. Par conséquent, revenez souvent en arrière pour obtenir une disponibilité supplémentaire.

| Fonctionnalité | Bureau <br> Système d’exploitation Windows/Mac | Navigateur | Mobile <br> iOS | Mobile <br> Android | Téléphone Teams |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Maintenir l’appel RTC 1:1 | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente |
| Maintenir l’appel teams 1:1 | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente |
| Suspension du transfert lors de l’appel RTC 1:1 | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | | |
| Suspension du transfert lors de l’appel teams 1:1 | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente| | | |
| Suspension du transfert consultatif lors de l’appel RTC 1:1 |-Musique en attente<br>-Musique personnalisée en attente || -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente |
| Suspension du transfert consultatif lors de l’appel 1:1 Teams |-Musique en attente<br>-Musique personnalisée en attente || -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente | -Musique en attente<br>-Musique personnalisée en attente |

## <a name="restrictions"></a>Restrictions

- La musique en attente est disponible uniquement dans les instances cloud commerciales et GCC.

- La musique en attente est disponible uniquement lorsque l’utilisateur est en mode TeamsOnly.

- Si l’utilisateur Teams appelé est activé pour Location-Based routage, seule la musique standard en attente est lue à l’appelant.

- La musique personnalisée en attente n’est pas disponible pour les utilisateurs configurés pour l’apparence de ligne partagée (délégation) et lorsque le parc d’appels est utilisé. La musique standard en attente sera jouée.

- Dans certains scénarios, un appel de contournement de média de routage direct est converti en contournement non multimédia pour la lecture de musique en attente et l’appel reste en tant que contournement non multimédia jusqu’à ce que l’appel soit arrêté.

## <a name="related-topics"></a>Rubriques connexes

- [Affecter des stratégies aux utilisateurs](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
