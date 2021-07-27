---
title: Utiliser OneDrive Entreprise et SharePoint pour les enregistrements de réunion
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment passer de Stream à OneDrive Entreprise et au stockage d’enregistrement des réunions SharePoint dans Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506323"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Utiliser OneDrive Entreprise et SharePoint Online ou Stream pour les enregistrements de réunion

> [!Note]
> Le passage de l’utilisation de Microsoft Stream à OneDrive Entreprise et Microsoft Office SharePoint Online pour les enregistrements de réunions sera une approche progressive.

|<div style="width:290px">Date&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 octobre 2020<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Vous activez la stratégie de réunion Teams pour enregistrer les enregistrements de réunion dans OneDrive Entreprise et SharePoint Online au lieu de Microsoft Stream (Classic)|
|Déploiement à compter du 7 janvier 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tous les nouveaux enregistrements de réunion Teams seront enregistrés dans OneDrive Entreprise et SharePoint Online, sauf si vous retardez cette modification en modifiant les stratégies de réunion Teams de votre organisation et en les définissant explicitement sur **Stream**. Il ne suffit pas de voir les comptes-rendus de stratégie sous la forme Stream. Vous devez définir explicitement la valeur de la stratégie sur **Stream**.|
|Déploiement à compter du 11 janvier 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Cloud de la communauté du secteur public uniquement**<br> Alors les clients du Cloud de la communauté du secteur public peuvent refuser cette option à compter du 5 octobre, vous n’avez pas le choix. Nous déploierons cette fonctionnalité à tous les clients du Cloud de la communauté du secteur public à compter du 11 janvier 2021, sauf si vous avez refusé.<br>  <br>À compter du 11 janvier 2021, tous les nouveaux enregistrements de réunion Teams pour les clients GCC seront enregistrés dans OneDrive Entreprise et SharePoint Online, sauf si vous retardez cette modification en modifiant les stratégies de réunion Teams de votre organisation et en les définissant explicitement sur **Stream**. <br><br>Si vous avez refusé mais souhaitez activer cette fonctionnalité, vous pouvez le faire en choisissant de définir explicitement votre stratégie de réunion Teams sur **OneDrive Entreprise**. |
|Déploiement à compter du 1er mars 2021 <br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High et DoD uniquement**<br> Les clients peuvent à présent activer pour la première fois les enregistrements de réunions cloud dans leurs systèmes Microsoft Teams. Ces enregistrements seront stockés et lus sur OneDrive et SharePoint Online par défaut. |
|Déploiement à partir du 7 juillet 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tous les clients (Entreprise, Éducation et GCC)**<br> Pour une réunion Teams enregistrée dans OneDrive et SharePoint Online et qui a également été transcrite en direct pendant la réunion, vous pouvez désormais effectuer une recherche dans la Recherche Microsoft pour trouver le fichier d’enregistrement de réunion basé sur la transcription. |
|Déploiement incrémentiel à compter du 16 juillet 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tous les clients (Entreprise, Éducation et GCC)**<br>Aucun nouvel enregistrement de réunion ne peut être enregistré dans Microsoft Stream (Classic) ; Tous les clients auront automatiquement enregistré les enregistrements de réunion dans OneDrive Entreprise et SharePoint Online, même s’ils ont modifié leurs stratégies de réunion Teams en Stream.<br><br> Pour mieux contrôler le changement dans votre organisation, nous recommandons aux clients de choisir cette fonctionnalité dès qu’ils maîtrisent bien le changement plutôt que d’attendre qu’il se produise. |

Microsoft Teams offre une nouvelle méthode d’enregistrement des réunions. En tant que première phase d’une transition de Microsoft Stream (Classic) vers la [nouvelle version de Stream](/stream/streamnew/new-stream), cette méthode stocke les enregistrements sur Microsoft OneDrive Entreprise et SharePoint Online dans Microsoft 365 et offre de nombreux avantages.

Stream (Classic) en tant que plateforme ne sera pas déprécié dans un avenir proche. Les vidéos qui résident actuellement dans Stream (Classic) y resteront jusqu’à ce qu’un outil de migration ultérieur soit disponible pour les déplacer vers OneDrive et SharePoint Online. Pour plus d’informations sur nos futurs plans, consulter la rubrique [Migration de Stream (Classic)](/stream/streamnew/classic-migration).

> [!NOTE]
> Si un enregistrement de réunion Teams ne parvient pas à être téléchargé sur OneDrive/SharePoint Online, l’enregistrement est enregistré temporairement dans Azure Media Services (AMS). Une fois stocké dans AMS, aucune nouvelle tentative n’est effectuée pour charger automatiquement l’enregistrement sur OneDrive/SharePoint Online ou Stream.

Les enregistrements de réunion stockés dans AMS sont disponibles pendant 21 jours avant d’être automatiquement supprimés. Les utilisateurs peuvent télécharger la vidéo à partir d’AMS s’ils doivent conserver une copie.

Les avantages de l’utilisation de OneDrive Entreprise et SharePoint Online pour le stockage des enregistrements sont les suivants :

- Stratégies de rétention pour l’enregistrement de réunion Teams (TMR) (étiquettes de réretention automatique S+C E5)
- Tirer parti de OneDrive Entreprise et de la gouvernance des informations SharePoint Online
- Définition des autorisations et du partage en toute facilité
- Partage d’enregistrements avec des invités (utilisateurs externes) avec partage explicite uniquement
- Possibilité de demander des flux d’accès
- Offre des liens partagés OneDrive Entreprise et les sites SharePoint
- Les enregistrements de réunion sont disponibles plus rapidement
- Transcription de la base de recherche enregistrée dans votre réunion
- Prise en charge des clients **Go local**
- Prise en charge multigéographique : les enregistrements résident dans une région spécifique de cet utilisateur
- Prise en charge de Bring Your Own Key (BYOK)

Consultez la liste complète des [fonctionnalités disponibles aujourd’hui et à quoi s’attendre au fil du temps](/stream/streamnew/features-new-version-stream).

Pour plus d’informations, regardez « Nouveautés des enregistrements de réunion Microsoft Teams ».

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configurer l’option d’enregistrement de réunion pour OneDrive Entreprise et SharePoint Online

L’option d’enregistrement de la réunion est un paramètre au niveau de la stratégie Teams. L’exemple suivant montre comment définir la stratégie globale. Veillez à définir l’option d’enregistrement de la réunion pour les stratégies que vous avez affectées à vos utilisateurs.

> [!Note]
> La propagation des modifications de stratégie de réunion Teams prend un certain temps. Revenez au bout de quelques heures après l’avoir défini, puis déconnectez-vous et reconnectez-vous à l’application de bureau Teams ou redémarrez simplement votre ordinateur.

1. Installez Teams PowerShell.

   > [!NOTE]
   > Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector. Si vous souhaitez en savoir plus, veuillez consulter la rubrique [Gestion de Skype Entreprise Online avec PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Lancez PowerShell en tant qu’administrateur.

3. Installez le [module Teams PowerShell](./teams-powershell-install.md).

4. Importez le module Microsoft Teams et connectez-vous en tant qu’administrateur Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Utilisez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour définir une stratégie de réunion Teams afin de passer du stockage Stream à OneDrive Entreprise et SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si certains de vos utilisateurs ont attribué une stratégie par organisateur ou par utilisateur, vous devez définir ce paramètre sur cette stratégie si vous souhaitez qu’ils stockent également les enregistrements de réunion dans OneDrive Entreprise et SharePoint Online. Pour plus d’informations, consultez [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>En savoir plus

Pour en savoir plus sur l’enregistrement de réunions cloud Teams, consultez [enregistrement de réunions cloud Teams](cloud-recording.md). Dans cet article, vous pouvez en savoir plus sur la configuration, la gestion, la gouvernance, les autorisations et le stockage des enregistrements.
