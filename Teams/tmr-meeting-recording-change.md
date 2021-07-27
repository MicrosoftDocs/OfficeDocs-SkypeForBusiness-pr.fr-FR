---
title: Utiliser OneDrive Entreprise et SharePoint Online pour les enregistrements de réunion
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment passer de Stream à OneDrive Entreprise stockage SharePoint d’enregistrement des réunions en ligne dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486134"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Utiliser OneDrive Entreprise et SharePoint Online ou Stream pour les enregistrements de réunion

> [!Note]
> La transition de l’utilisation de Microsoft Stream au OneDrive Entreprise et Microsoft Office SharePoint Online des enregistrements de réunion sera progressive.

|<div style="width:290px">Date&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 octobre 2020<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Vous activez la stratégie Teams réunion pour que les enregistrements de réunion soit enregistrés dans OneDrive Entreprise et SharePoint Online au lieu de Microsoft Stream (classique)|
|Déploiement à compter du 7 janvier 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tous les enregistrements des réunions Teams sont enregistrés sur OneDrive Entreprise et SharePoint Online, sauf si vous reportez cette modification en modifiant les stratégies de réunion Teams de votre organisation et en les configurationnant explicitement sur **Stream.** Il ne suffit pas de voir les comptes-rendus de stratégie sous la forme Stream. Vous devez définir explicitement la valeur de la stratégie sur **Stream**.|
|Déploiement à compter du 11 janvier 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Cloud de la communauté du secteur public uniquement**<br> Alors les clients du Cloud de la communauté du secteur public peuvent refuser cette option à compter du 5 octobre, vous n’avez pas le choix. Nous déploierons cette fonctionnalité à tous les clients du Cloud de la communauté du secteur public à compter du 11 janvier 2021, sauf si vous avez refusé.<br>  <br>À compter du 11 janvier 2021, tous les nouveaux enregistrements des réunions Teams des clients Cloud de la communauté du secteur public seront enregistrés sur OneDrive Entreprise et SharePoint Online, sauf si vous reportez cette modification en modifiant les stratégies de réunion Teams de votre organisation et en les configurationnant explicitement pour la diffusion en **continu.** <br><br>Si vous avez refusé mais souhaitez activer cette fonctionnalité, vous pouvez le faire en choisissant de définir explicitement votre stratégie de réunion Teams sur **OneDrive Entreprise**. |
|Déploiement à compter du 1er mars 2021 <br> *(Terminé)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High et DoD uniquement**<br> Les clients peuvent à présent activer pour la première fois les enregistrements de réunions cloud dans leurs systèmes Microsoft Teams. Ces enregistrements sont stockés et lés par défaut sur OneDrive et SharePoint Online. |
|Déploiement à partir du 7 juillet 2021<br> *(Terminé)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tous les clients (Entreprise, Éducation et Cloud de la communauté du secteur public)**<br> Pour une réunion Teams enregistrée sur OneDrive et SharePoint Online et transcrite en direct pendant la réunion, vous pouvez à présent rechercher dans Recherche Microsoft le fichier d’enregistrement de la réunion en fonction de la transcription. |
|Déploiement incrémentielle à partir du 16 août 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tous les clients (Entreprise, Éducation et Cloud de la communauté du secteur public)**<br>Aucun nouvel enregistrement de réunion ne peut être enregistré dans Microsoft Stream (classique) ; Tous les clients auront automatiquement enregistré les enregistrements de réunion sur OneDrive Entreprise et SharePoint Online, même s’ils ont changé leurs stratégies Teams réunion en Flux.<br><br> Nous recommandons aux clients, pour mieux contrôler la modification dans votre organisation, de s’y prendre à l’aise au lieu d’attendre qu’elle se produise. |

Microsoft Teams offre une nouvelle méthode d’enregistrement des réunions. Comme première phase d’une transition de Microsoft Stream classique vers le nouveau [Stream,](/stream/streamnew/new-stream)cette méthode stocke les enregistrements sur Microsoft OneDrive Entreprise et SharePoint Online dans Microsoft 365 et offre de nombreux avantages.

Le flux (classique) en tant que plateforme ne sera pas supprimé prochainement. Les vidéos actuellement en direct dans Stream (classique) seront disponibles jusqu’à ce qu’un nouvel outil de migration soit disponible pour les déplacer vers OneDrive et SharePoint Online. Pour plus [d’informations](/stream/streamnew/classic-migration) sur nos plans futurs, consultez la migration classique stream.

> [!NOTE]
> Si le chargement d’une réunion Teams échoue sur OneDrive/SharePoint Online, l’enregistrement est enregistré temporairement dans Azure Media Services (AMS). Une fois stocké dans AMS, aucune nouvelle tentative n’est faite pour télécharger automatiquement l’enregistrement sur OneDrive/SharePoint Online ou Stream.

Les enregistrements de réunion stockés dans AMS sont disponibles pendant 21 jours avant d’être supprimés automatiquement. Les utilisateurs peuvent télécharger la vidéo à partir d’AMS s’ils ont besoin d’en conserver une copie.

L’utilisation d’OneDrive Entreprise et SharePoint Online pour le stockage d’enregistrements comprend les avantages suivants :

- Stratégies de rétention pour l’enregistrement des réunions Teams (TMR) (étiquettes de rétention automatique S+C E5)
- Tirer parti de OneDrive Entreprise et SharePoint gouvernance des informations en ligne
- Définition des autorisations et du partage en toute facilité
- Partage d’enregistrements avec des invités (utilisateurs externes) avec partage explicite uniquement
- Possibilité de demander des flux d’accès
- Fournir des OneDrive Entreprise et des SharePoint partagés en ligne
- Les enregistrements de réunion sont disponibles plus rapidement
- Transcription de base de la recherche enregistrée dans votre réunion
- Prise en charge des clients **Go local**
- Prise en charge multigéographique : les enregistrements résident dans une région spécifique de cet utilisateur
- Prise en charge de Bring Your Own Key (BYOK)

Consultez la liste complète des [fonctionnalités disponibles aujourd’hui et ce à quoi vous pouvez vous attendre au fil du temps.](/stream/streamnew/features-new-version-stream)

Pour plus d’informations, regardez « Nouveautés Microsoft Teams enregistrements de réunion ».

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configurer l’option d’enregistrement de la réunion OneDrive Entreprise et SharePoint Online

L’option d’enregistrement de la réunion est un paramètre au niveau de la stratégie Teams. L’exemple suivant montre comment définir la stratégie globale. Veillez à définir l’option d’enregistrement de la réunion pour les stratégies que vous avez affectées à vos utilisateurs.

> [!Note]
> Teams modifications de la stratégie de réunion prennent un certain temps. Vérifiez de nouveau après quelques heures de configuration, puis connectez-vous à l’application bureautique Teams nouveau ou redémarrez simplement votre ordinateur.

1. Installez Teams PowerShell PowerShell.

   > [!NOTE]
   > Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector. Si vous souhaitez en savoir plus, veuillez consulter la rubrique [Gestion de Skype Entreprise Online avec PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Lancez PowerShell en tant qu’administrateur.

3. Installez [Teams module PowerShell.](./teams-powershell-install.md)

4. Importez le module MicrosoftTeams et connectez-vous en tant Teams administrateur.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Utilisez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour définir une stratégie de réunion Teams transition du stockage stream vers OneDrive Entreprise et SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si certains de vos utilisateurs ont affecté une stratégie par organisateur ou par utilisateur, vous devez définir ce paramètre sur cette stratégie si vous souhaitez qu’ils stockent également les enregistrements de la réunion dans OneDrive Entreprise et SharePoint Online. Si vous souhaitez en savoir plus d’informations, veuillez consulter la rubrique [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>En savoir plus

Pour en savoir plus sur Teams’enregistrement d’une réunion dans le cloud, voir [Teams’enregistrement de la réunion dans le cloud.](cloud-recording.md) Cet article vous permet d’en savoir plus sur la configuration, la gestion, la gouvernance, les autorisations et le stockage des enregistrements.
