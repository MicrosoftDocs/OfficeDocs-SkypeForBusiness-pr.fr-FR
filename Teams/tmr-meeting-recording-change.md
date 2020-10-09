---
title: Utiliser OneDrive et SharePoint pour les enregistrements de réunion
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment basculer du flux vers OneDrive entreprise et le stockage d’enregistrements de réunion SharePoint dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a42c46cf9592c64676d153e1885357a4ee8ec7b
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389932"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Utiliser OneDrive entreprise et SharePoint ou un flux pour les enregistrements de réunion

> [!Note]
> Les modifications apportées à l’utilisation de Microsoft Stream pour OneDrive Entreprise et SharePoint pour les enregistrements de réunion auront une approche progressive. Au démarrage, les administrateurs de clients peuvent choisir cette nouvelle option de flux de travail dès aujourd’hui et commencer à voir les enregistrements téléchargés automatiquement dans OneDrive entreprise et SharePoint en octobre 2020. En novembre, vous devrez annuler votre abonnement si vous voulez continuer à utiliser le flux et à quelques instants dans les 2021 au début, nous aurons besoin de tous les clients d’utiliser OneDrive entreprise et SharePoint pour les nouveaux enregistrements de réunion.

Microsoft teams dispose d’une nouvelle méthode pour l’enregistrement des enregistrements de réunion. Comme la première phase d’une transition à partir du flux Microsoft classique vers le [nouveau flux](https://docs.microsoft.com/stream/streamnew/new-stream), cette méthode stocke les enregistrements sur Microsoft OneDrive et SharePoint dans Microsoft 365 et offre de nombreux avantages.

Les avantages de l’utilisation de OneDrive entreprise et SharePoint pour le stockage d’enregistrements sont les suivants :

- Stratégies de rétention pour l’enregistrement des réunions Teams (TMR)
- Avantages de OneDrive entreprise et de la gouvernance des informations de SharePoint
- Simplification de la définition des autorisations et du partage
- Partager des enregistrements avec des invités (utilisateurs externes) avec le partage explicite uniquement
- Demander un flux d’accès
- Fournir des liens OneDrive entreprise et SharePoint partagés
- Quota accru
- Les enregistrements de réunion sont disponibles plus vite
- **Accéder** au support client local
- Prise en charge de plusieurs géographiques : les enregistrements sont stockés dans une zone spécifique à cet utilisateur.
- Mettre en place votre propre clé (BYOK)
- Amélioration de la qualité de transcription et de l’intervenant

Certaines limitations sont à prendre en compte :

- Il s’agit de sous-titres et de transcriptions en anglais uniquement.
- Vous ne serez pas en mesure de rechercher des transcriptions ou leur contenu.
- Vous ne serez pas en mesure de modifier les transcriptions, mais vous pourrez activer/désactiver les légendes.
- Vous pouvez contrôler les personnes avec lesquelles vous partagez l’enregistrement, mais vous ne pouvez pas bloquer les utilisateurs disposant d’un accès partagé pour télécharger l’enregistrement.
- Vous ne recevrez pas d’e-mail à la fin de l’enregistrement, mais l’enregistrement s’affichera dans la conversation de la réunion une fois que vous avez terminé. Cela se produit beaucoup plus rapidement qu’auparavant dans le flux

Regardez « enregistrement de la réunion » pour plus d’informations.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurer l’option d’enregistrement de la réunion pour OneDrive entreprise et SharePoint

1. Installez la console d’administration PowerShell de Skype entreprise online.

    a. Téléchargez [Skype entreprise Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).

    b. Suivez les invites pour l’installer.

    c. Redémarrez votre ordinateur.

2. Lancer PowerShell en tant qu’administrateur

3. Importez le connecteur SkypeOnline et connectez-vous en tant qu’administrateur Teams.

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. Utilisez [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour définir une stratégie de réunion équipes pour passer du stockage de flux à ODSP.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Désactiver OneDrive entreprise et SharePoint pour continuer à utiliser le flux

Même si une stratégie indique qu’il est défini sur **Stream**, il est possible qu’elle ne soit pas définie. En règle générale, si la stratégie n’est pas définie, le paramètre par défaut est **flux**. Toutefois, si vous souhaitez annuler votre utilisation de SharePoint ou OneDrive, vous devez réinitialiser la stratégie sur **flux** pour vous assurer qu’elle est définie sur la valeur par défaut.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

**Où l’enregistrement de la réunion sera-t-il stocké ?**

- Pour les réunions hors-canal, l’enregistrement est stocké dans un dossier intitulé **enregistrements** qui se trouve au niveau supérieur du OneDrive qui appartient à la personne qui a démarré l’enregistrement de la réunion. Example

  <i>OneDrive entreprise</i> / de l’enregistreur **Enregistrements**

- Pour les réunions de canal, l’enregistrement est stocké dans la bibliothèque de documents du site d’équipe dans un dossier nommé **enregistrements**. Example

  <i>Nom de l’équipe-nom du canal</i> / Des **documents** / ; **Enregistrements**

**Comment gérer les enregistrements d’anciens employés ?**

Étant donné que les vidéos sont similaires à n’importe quel autre fichier dans OneDrive et SharePoint, la gestion de la propriété et de la rétention après le départ d’un employé va suivre le [processus OneDrive et SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)normal.

**Qui dispose des autorisations pour afficher l’enregistrement de la réunion ?**

- Pour les réunions hors-canal, tous les participants à la réunion, à l’exception des utilisateurs externes, sont automatiquement liés à un lien. Les utilisateurs externes devront être explicitement ajoutés à la liste partagée par l’organisateur de la réunion ou la personne qui a démarré l’enregistrement de la réunion.

- Pour les réunions de canal, les autorisations sont héritées de la liste propriétaires et membres du canal.

**Comment gérer les transcriptions ?**

Les clients qui choisissent de bénéficier de cette version d’évaluation ne disposent pas de sous-titres disponibles dans leurs enregistrements de réunion teams migrés vers OneDrive et SharePoint.Nous travaillons à l’ajout de sous-titres, en commençant par des sous-titres en anglais, et des enregistrements de réunion en octobre 2020.

Les sous-titres seront disponibles dans les enregistrements de réunion teams pour les clients qui ont choisi d’autoriser les transcriptions comme décrit dans la rubrique [enregistrements Cloud teams](cloud-recording.md) .

Les légendes permettent de créer du contenu inclusive pour les visualiseurs de toutes les aptitudes. En tant que propriétaire, vous pouvez masquer les sous-titres, même si la transcription reste disponible dans les équipes, sauf si vous supprimez les sous-titres de teams. Découvrir [Comment activer ou désactiver les enregistrements de réunion](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Les sous-titres sont pris en charge pour les enregistrements des réunions teams pendant 60 jours à compter de la date d’enregistrement de la réunion.

**Comment le quota de stockage sera-t-il affecté ?**

Les fichiers d’enregistrements de réunion teams résident dans OneDrive entreprise et SharePoint inclus dans votre quota de ces services. Voir [quota SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) et [quota OneDrive entreprise] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**Comment lire l’enregistrement d’une réunion teams ?**

Votre vidéo sera lue sur le lecteur vidéo de OneDrive entreprise ou SharePoint, selon l’endroit où vous accédez au fichier.

**Si vous envisagez d’utiliser l’ajout au flux, les vidéos existantes resteront-elles aussi longtemps que possible.**

Le flux en tant que plateforme ne sera pas déconseillé dans un avenir proche. Les vidéos actuellement actives dans le flux resteront là jusqu’à ce que la migration soit entamée. Lors de la migration, ces vidéos seront migrées vers ODSP également. Pour plus d’informations, consultez [ici](https://docs.microsoft.com/stream/streamnew/classic-migration) .
