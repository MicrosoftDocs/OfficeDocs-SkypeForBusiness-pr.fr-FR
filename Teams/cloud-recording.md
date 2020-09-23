---
title: Enregistrement de réunion cloud Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Conseils pratiques pour le déploiement de fonctionnalités vocales Cloud dans teams pour enregistrer les réunions d’équipes et les appels de groupe pour capturer les activités audio, vidéo et de partage d’écran.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b19cb5fe0ac89f800904bea4346cc185d9b822a8
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203967"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de réunion cloud Teams

Dans Microsoft Teams, les utilisateurs peuvent enregistrer leurs réunions et appels de groupe Teams pour capturer les activités audio, vidéo et de partage d’écran. Il existe également une option pour les enregistrements qui permet une transcription automatique, afin que les utilisateurs puissent regarder les enregistrements de réunion avec des sous-titres et rechercher des éléments de discussion importants dans la transcription. L’enregistrement se fait dans le cloud et est sauvegardé dans [Microsoft Stream](https://docs.microsoft.com/stream/) pour permettre aux utilisateurs de le partager en toute sécurité au sein de leur organisation.

En relation avec la [Réunion Teams de qui enregistre la documentation de l’utilisateur final](https://aka.ms/recordmeeting)

>[!Note]
> Les modifications apportées à l’aide de Microsoft Stream to [OneDrive entreprise et de SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) seront une approche progressive. Au moment de l’exécution, vous serez en mesure de vous abonner à cette expérimentation en novembre, si vous voulez continuer à utiliser le flux de travail et que, à un 2021 moment donné, nous aurons besoin de tous les utilisateurs de OneDrive entreprise et de SharePoint pour les enregistrements de réunion.

> [!NOTE]
> Pour plus d’informations sur l’utilisation des rôles dans les réunions teams et sur la modification des rôles des utilisateurs, voir [rôles d’une réunion teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions préalables pour l’enregistrement de réunion cloud Teams

Pour que les réunions d’un utilisateur d’équipes puissent être enregistrées, Microsoft Stream doit être activé pour le client. De plus, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et la personne qui lance l’enregistrement :

- L’utilisateur dispose d’Office 365 E1, E3, E5, a1, a3, a5, Microsoft 365 Business Premium, Business standard ou Business basique<sup>1</sup>
- L’utilisateur doit avoir une licence pour Microsoft Stream<sup>2</sup> 
- L’utilisateur doit disposer des autorisations nécessaires au chargement des vidéos Microsoft Stream
- L’utilisateur doit avoir accepté les directives de l’entreprise configurées par l’administrateur, le cas échéant.
- L’utilisateur doit disposer de l’espace de stockage suffisant dans Microsoft Stream pour sauvegarder les enregistrements
- L’utilisateur a le paramètre TeamsMeetingPolicy-AllowCloudRecording défini sur true
- L’utilisateur ne doit pas être un utilisateur anonyme, invité ou fédéré de la réunion
- Pour activer la transcription de la réunion d’un utilisateur, la stratégie de réunion teams à laquelle vous êtes affecté doit avoir le paramètre-AllowTranscription défini sur true.

<sup>1</sup> à compter du 20 août 2020, l’accès au fichier d’enregistrement de la réunion expire après 21 jours pour les utilisateurs avec a1. Pour plus d’informations, voir [charger un enregistrement de réunion Microsoft teams dans un flux](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording).

<sup>2</sup> l’utilisateur doit être titulaire d’une licence pour télécharger et télécharger des réunions dans/à partir de Microsoft Stream, mais il n’est pas nécessaire d’enregistrer une réunion. Si vous souhaitez empêcher un utilisateur d’enregistrer une réunion Microsoft Teams, vous devez accorder une TeamsMeetingPolicy dont AllowCloudRecording a la valeur $False.

> [!IMPORTANT] 
> Les utilisateurs n’ont pas besoin d’une attribution de licence Microsoft Stream si vous voulez qu’ils enregistrent et téléchargent uniquement les enregistrements. Cela signifie que les enregistrements ne sont pas stockés dans Microsoft Stream mais sont stockés dans Azure Media Services (AMS) avec une limite de 21 jours avant d’être supprimés. À ce stade, un administrateur n’est pas habilité à contrôler ou gérer, et même supprimer un enregistrement.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurer l’Enregistrement de réunion cloud Teams pour les utilisateurs de votre organisation

Cette section vous explique comment configurer et planifier l'enregistrement des réunions Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Activer Microsoft Stream pour les utilisateurs de l’Organisation

Microsoft Stream est disponible dans le cadre des abonnements Microsoft 365 et Office 365 admissibles ou en tant que service autonome.  Pour plus d’informations, consultez la [Vue d’ensemble des licences Stream](https://docs.microsoft.com/stream/license-overview).  Microsoft Stream est désormais inclus dans Microsoft 365 entreprise, Microsoft 365 Business standard et Microsoft 365 entreprise Basic.

Apprenez-en davantage sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans microsoft 365 ou Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) pour permettre aux utilisateurs d’accéder à Microsoft Stream. Assurez-vous que le flux Microsoft n’est pas bloqué pour les utilisateurs, tel qu’il est défini dans la fenêtre [inscription de bloc pour Microsoft Stream](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>S’assurer que les utilisateurs ont des autorisations de téléchargement de vidéo dans Microsoft Stream

Par défaut, tous les membres de l’entreprise peuvent créer du contenu dans Stream, une fois Stream activé et la licence affectée à l’utilisateur. Un administrateur Microsoft Stream peut [restreindre les employés à créer du contenu](https://docs.microsoft.com/stream/restrict-uploaders) en continu. Les utilisateurs figurant dans cette liste restreinte ne pourront pas enregistrer de réunions.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Informez les employés pour qu’ils acceptent les instructions de la société dans Microsoft Stream

Si un administrateur Microsoft Stream a [configuré la stratégie de la société](https://docs.microsoft.com/stream/company-policy-and-consent) et nécessite que les employés acceptent cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent le faire avant de procéder à l’enregistrement dans Microsoft Teams. Avant de déployer la fonctionnalité d’enregistrement dans l’organisation, assurez-vous que les utilisateurs ont reçu une invitation à la stratégie.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activer ou désactiver l’enregistrement dans le cloud

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si les réunions des utilisateurs peuvent être enregistrées.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser l’enregistrement dans le cloud** dans la stratégie de réunion. Pour plus d’informations, voir [Gérer les stratégies de réunion Teams](meeting-policies-in-teams.md#allow-cloud-recording).

À l’aide de PowerShell, vous configurez le paramètre AllowCloudRecording dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Notez que l’organisateur de la réunion et l’initiateur de l’enregistrement doivent avoir les autorisations d’enregistrement pour enregistrer la réunion. À moins que vous n’ayez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs obtiennent la stratégie globale, qui a AllowCloudRecording activée par défaut.

> [!NOTE]
> Pour plus d’informations sur l’utilisation des rôles d’équipes pour configurer les personnes autorisées à enregistrer une réunion, voir [rôles dans une réunion teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
</br>
</br>


|                                                                 Scénario                                                                 |                                                                                                                                                                         Étapes                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Je souhaite que tous les utilisateurs de mon entreprise puissent enregistrer leurs réunions                                    |                                                                     <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Vrai<li>Tous les utilisateurs ont la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai </ol>                                                                     |
| Je veux que la plupart des utilisateurs puissent enregistrer leurs réunions, mais désactiver de façon sélective des utilisateurs spécifiques qui ne sont pas autorisés à enregistrer |        <ol><li>Confirmer que la stratégie GlobalCsTeamsMeeting a AllowCloudRecording = Vrai<li>La plupart des utilisateurs ont la stratégie CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Faux</ol>         |
|                                                   Je souhaite que l’enregistrement soit 100% désactivé                                                   |                                                                <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux<li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux                                                                 |
|      Je souhaite que l’enregistrement soit désactivé pour la plupart des utilisateurs, mais il autorise sélectivement les utilisateurs spécifiques autorisés à enregistrer       | <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux<li>La plupart des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Où sont stockées vos Enregistrements de réunions

Les enregistrements de réunion sont stockés dans le stockage cloud Microsoft Stream. Les enregistrements sont conservés et disponibles pour affichage et téléchargement pendant 21 jours. Pour l’instant, la fonctionnalité d’enregistrement de la réunion est désactivée pour les clients dont les données d’équipe sont stockées dans le pays si Microsoft Stream n’est pas disponible dans la zone de résidence des données dans le pays où sont stockées les données. Dans le futur, la fonctionnalité d’enregistrement de réunions Teams sera activée pour les clients dont les données d’équipe sont stockées dans le pays, même si Microsoft Stream n’est pas disponible dans la zone de résidence des données dans le pays.

Lorsque cette modification prend effet, les enregistrements de réunion sont stockés par défaut dans la zone géographique plus proche pour Microsoft Stream. Si vos données Teams sont stockées dans le pays et que vous préférez stocker les enregistrements de réunions dans le pays, nous vous conseillons de désactiver la fonctionnalité, puis de les activer une fois Microsoft Stream déployé sur votre pays ou région de résidence dans le pays. Pour désactiver la fonctionnalité pour tous les utilisateurs de votre organisation, désactivez le paramètre **autoriser l’enregistrement Cloud** dans la stratégie de réunion global Teams, qui se trouve dans le centre d’administration Microsoft Teams.

Voici un résumé de ce qui se produit lorsque vous activez l’enregistrement de la réunion lorsque cette modification prend effet :

|Si vous activez les enregistrements de réunion...|Les enregistrements de réunion sont stockés... |
|---|---|
|Pour que Microsoft Stream soit disponible dans votre région de résidence des données dans le pays |Dans la région de flux Microsoft la plus proche|
|Lorsque Microsoft Stream est disponible dans votre région de résidence des données dans le pays |Dans votre région de résidence des données dans le pays|

Pour les clients nouveaux et existants qui n’ont pas encore activé l’enregistrement de la réunion, les nouveaux enregistrements sont stockés dans le pays une fois Microsoft Stream disponible dans la zone de résidence des données dans le pays. Néanmoins, tout client qui active l’enregistrement de la réunion avant que Microsoft Stream soit disponible dans la région de résidence des données dans le pays continue d’utiliser le stockage de flux Microsoft pour les enregistrements existants et nouveaux, même si Microsoft Stream est disponible dans la région de résidence des données dans le pays.

Pour rechercher la région dans laquelle vos données Microsoft Stream sont stockées, dans Microsoft Stream, cliquez sur **?** dans le coin supérieur droit, cliquez sur **À propos de Microsoft Stream**, puis sur **Vos données sont stockées dans**.  Pour en savoir plus sur les régions dans lesquelles Microsoft Stream stocke les données, consultez la rubrique [FAQ Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Pour en savoir plus sur l’emplacement de stockage des données entre les services dans Microsoft 365 ou Office 365, voir [où se trouvent vos données ?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activer ou désactiver la transcription de l’enregistrement

Ce paramètre détermine si les légendes et les fonctionnalités de transcription sont disponibles lors de la lecture des enregistrements de réunion. Si vous désactivez cette fonctionnalité, les options **Rechercher** et **CC** ne seront pas disponibles lors de la lecture de l’enregistrement d’une réunion. Ce paramètre doit être activé pour la personne qui a créé l’enregistrement.

> [!NOTE]
> Pour le moment, cette transcription pour les réunions enregistrées est uniquement prise en charge pour les utilisateurs qui disposent de la langue dans teams pour les équipes définies en anglais et lorsque l’anglais est parlé dans la réunion. Ils sont stockés conjointement avec les enregistrements de la réunion dans le stockage cloud de Microsoft Stream.

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si l’initiateur d’enregistrement peut transcrire le choix de transcrire l’enregistrement de la réunion.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser la transcription** dans la stratégie de réunion. Pour plus d’informations, voir [Gérer les stratégies de réunion Teams](meeting-policies-in-teams.md#allow-transcription).

À l’aide de PowerShell, vous configurez le paramètre AllowTranscription dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowTranscription est désactivée par défaut.

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```
</br>
</br>

|Scénario|Étapes |
|---|---|
|Je souhaite que tous les utilisateurs de ma société soient en mesure de transcrire lors du lancement de l’enregistrement d’une réunion |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowTranscription = Vrai <li>Tous les utilisateurs ont la stratégie globale csTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = Vrai. </ol>|
|Je veux que la plupart des utilisateurs puissent transcrire les enregistrements de réunion, mais désactiver de façon sélective des utilisateurs spécifiques qui ne sont pas autorisés à transcrire |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowTranscription = Vrai <li>La plupart des utilisateurs ont la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = Vrai. <li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowTranscription = Faux </ol>|
|Je souhaite que la transcription de l’enregistrement soit 100 % désactivée |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowTranscription = Faux <li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = Faux </ol>|
|Je souhaite que la transcription soit désactivé pour la plupart des utilisateurs, mais qu’il autorise de façon sélective les utilisateurs autorisés à transcrire |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux <li>La plupart des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux <li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai </ol>|
|||

### <a name="planning-for-storage"></a>Planification pour stockage

La taille d’un enregistrement de 1 heure est de 400 Mo. Assurez-vous que vous comprenez la capacité requise pour les fichiers enregistrés et disposez d’un espace de stockage suffisant disponible dans Microsoft Stream.  Consultez la [rubrique vue d’ensemble des licences Microsoft Stream](https://docs.microsoft.com/stream/license-overview) pour connaître le stockage de base inclus dans l’abonnement et l’achat d’un espace de stockage supplémentaire.

## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunions

Les enregistrements de réunion sont considérés comme du contenu appartenant au locataire. Si le propriétaire de l’enregistrement quitte l’entreprise, l’administrateur peut ouvrir l’URL de la vidéo d’enregistrement dans Microsoft Stream en mode administrateur. L’administrateur peut supprimer l’enregistrement, mettre à jour les métadonnées d’enregistrement ou modifier les autorisations de la vidéo d’enregistrement. En savoir plus sur les [fonctionnalités d’administration de dans Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Pour plus d’informations sur la gestion des enregistrements et l’accès utilisateur, consultez [Gérer les données utilisateur dans Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) et [Autorisations et confidentialité dans Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformité et eDiscovery pour les enregistrements de réunions

Les enregistrements de la réunion sont stockés dans Microsoft Stream, qui est compatible avec Microsoft 365 et Office 365 Tier-C. Pour prendre en charge les demandes d’e-Discovery pour les administrateurs de conformité qui sont intéressés par les enregistrements de réunion ou d’appels pour Microsoft Streams, le message enregistrement terminé est disponible dans la fonctionnalité de recherche de contenu de conformité pour Microsoft Teams. Les administrateurs de conformité peuvent rechercher le mot clé « enregistrement » dans la ligne d’objet de l’élément dans le cadre de la recherche de contenu de conformité et découvrir les enregistrements de réunions et d’appels au sein de l’organisation. Une condition préalable pour qu’elles puissent afficher tous les enregistrements est qu’ils doivent être configurés dans Microsoft Stream avec accès administrateur. En savoir plus sur les [affectations d’autorisations d’administrateur dans Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
