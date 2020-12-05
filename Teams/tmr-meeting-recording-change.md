---
title: Utiliser OneDrive entreprise et les enregistrements SharePoint pour les réunions
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
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46d3b53f62a3bb497f173c9efd418b7ed88444c7
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578507"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Utiliser OneDrive entreprise et SharePoint ou un flux pour les enregistrements de réunion

> [!Note]
> Le changement de l’utilisation de Microsoft Stream sur OneDrive entreprise et Microsoft SharePoint pour les enregistrements de réunion sera une approche progressive.

|<div style="width:290px">Période&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 octobre 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Vous pouvez activer la stratégie de réunion teams pour que les enregistrements de réunion soient enregistrés dans OneDrive entreprise et SharePoint au lieu de Microsoft Stream (standard).|
|Déploiement à partir du 11 janvier 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Toutes les nouvelles réunions d’équipes seront enregistrées dans OneDrive entreprise et SharePoint, sauf si vous retardez cette modification en modifiant les stratégies de réunion teams de votre organisation et en définissant explicitement celles-ci en **continu**. L’affichage des rapports de stratégie en tant que flux n’est pas suffisant. Vous devez définir explicitement la valeur de la stratégie sur **Stream**.|
|Déploiement à partir du 1er mars 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clients entreprise**<br>Aucun enregistrement de nouvelle réunion ne peut être enregistré dans Microsoft Stream (classique); tous les clients disposent automatiquement d’enregistrements de réunion enregistrés dans OneDrive entreprise et SharePoint, même s’ils ont changé leurs politiques de réunion en **flux**. Nous recommandons aux clients de dérouler cette fonction avant cette date pour pouvoir contrôler le minutage de la publication. |
|Déploiement à partir du 7 juillet 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clients éducation**<br>Aucun enregistrement de nouvelle réunion ne peut être enregistré dans Microsoft Stream (classique); tous les clients disposent automatiquement d’enregistrements de réunion enregistrés dans OneDrive entreprise et SharePoint, même s’ils ont changé leurs politiques de réunion en **flux**. Nous recommandons aux clients de dérouler cette fonction avant cette date pour pouvoir contrôler le minutage de la publication. Nous avons mis à jour ce planning pour permettre aux clients de l’éducation de compléter les semestres en cours. |

> [!Note]
> Nous recommandons aux clients entreprise et éducation de mieux contrôler le changement de votre organisation, si vous le souhaitez, si vous êtes à l’aise avec la modification au lieu d’attendre qu’elle ne se produise.

Microsoft teams dispose d’une nouvelle méthode pour l’enregistrement des enregistrements de réunion. Comme la première phase d’une transition à partir du flux Microsoft classique vers le [nouveau flux](https://docs.microsoft.com/stream/streamnew/new-stream), cette méthode stocke les enregistrements sur Microsoft OneDrive entreprise et SharePoint dans Microsoft 365 et offre de nombreux avantages.

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

L’option d’enregistrement de la réunion est un paramètre au niveau de la stratégie d’équipe. L’exemple suivant montre comment définir la stratégie globale. Assurez-vous de définir l’option d’enregistrement de la réunion pour la ou les stratégies que vous avez affectées à vos utilisateurs.

> [!Note]
> Les modifications de la stratégie de réunion teams prennent un certain temps. Consultez de nouveau après quelques heures de configuration et déconnectez-vous, puis reconnectez-vous.

1. Installez PowerShell Skype entreprise online.
**Remarque**: le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la dernière version publique de teams PowerShell, vous n’avez pas besoin d’installer le connecteur Skype entreprise online. Reportez-vous à la rubrique [gestion de Skype entreprise Online avec PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    a. Téléchargez [Skype entreprise Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    b. Suivez les invites pour l’installer.

    c. Redémarrez votre ordinateur.

2. Lancer PowerShell en tant qu’administrateur

3. Importez le connecteur SkypeOnline et connectez-vous en tant qu’administrateur Teams.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Utilisez [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) pour définir une stratégie de réunion équipes pour passer du stockage en flux à OneDrive entreprise et SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si certains de vos utilisateurs ont affecté une stratégie par organisateur ou par utilisateur, vous devez définir ce paramètre sur cette stratégie si vous souhaitez qu’ils stockent également les enregistrements de la réunion dans OneDrive entreprise et SharePoint. Pour plus d’informations, consultez [gérer les stratégies de réunion dans Microsoft teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Désactiver OneDrive entreprise et SharePoint pour continuer à utiliser le flux

Même si une stratégie indique qu’il est défini sur **Stream**, il est possible qu’elle ne soit pas définie. En règle générale, si la stratégie n’est pas définie, le paramètre par défaut est **flux**. Toutefois, si vous souhaitez annuler votre utilisation de SharePoint ou OneDrive entreprise, vous devez réinitialiser la stratégie sur **flux** pour vous assurer qu’elle est la valeur par défaut.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorisations ou accès en fonction du rôle

> [!Note]
> Nous vous recommandons d’avoir besoin d’être connecté à un utilisateur connecté lors du partage d’équipes. Pour cela, il suffit de sélectionner l’option **personnes dans (votre organisation)** lors du partage du fichier, comme indiqué dans [partager des fichiers ou des dossiers SharePoint](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US). Le partage externe n’est pas conçu pour la distribution de fichiers volumineux ou d’un grand nombre de fichiers. Afin d’éviter les situations de fraude et d’abus, il est possible que vous rencontriez des problèmes lors du partage d’un grand volume de données à des utilisateurs externes.

|Type de réunion                               | Qui a cliqué sur l’enregistrement ?| Où l’enregistrement s’affiche-t-il ?                               |Qui a accès ? R/W, R ou partage                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|appel 1:1 avec les parties internes             |Appelant                 |Compte OneDrive entreprise de l’appelant                        |L’appelant est propriétaire et dispose de droits complets. <br /><br />L’appelant (s’il se trouve dans le même client) dispose d’un accès en lecture seule. Aucun accès de partage. <br /><br /> Un appelé (si dans un client différent) n’a pas accès. L’appelant doit le partager avec l’appelant.|
|appel 1:1 avec les parties internes             |Appelé                 |Compte OneDrive entreprise de l’appelant                        |L’appel est propriétaire et dispose de droits complets. <br /><br />Appelant (si le client dispose d’un accès en lecture seule. Aucun accès de partage. <br /><br />L’appelant (si ce n’est pas le même client) n’a pas accès. Le correspondant doit le partager avec l’appelant.|
|appel 1:1 avec un appel externe             |Appelant                 |Compte OneDrive entreprise de l’appelant                        |L’appelant est propriétaire et dispose de droits complets.<br /> <br />L’appelant n’est pas en accès. L’appelant doit le partager avec l’appelant.|
|appel 1:1 avec un appel externe             |Appelé                 |Compte OneDrive entreprise de l’appelant                        |L’appel est propriétaire et dispose de droits complets.<br /><br />L’appelant n’est pas autorisé à accéder. Le correspondant doit le partager avec l’appelant.|
|Appel de groupe                                 |Tout membre de l’appel |Membre sur lequel vous avez cliqué sur le compte OneDrive entreprise de l’enregistrement  |Le membre qui a cliqué sur l’enregistrement dispose de droits complets. <br /><br /> Les autres membres du même client disposent de droits de lecture. <br /><br /> Les autres membres de chaque client n’y ont aucun droit.|
|Réunion adhoc/programmée                    |Organisateur              |Compte OneDrive entreprise de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement. <br /><br /> Tous les autres participants à la réunion disposent d’un accès en lecture.|
|Réunion adhoc/programmée                    |Autre membre de la réunion   |Membre sur lequel vous avez cliqué sur l’enregistrement                                  |Le membre qui a cliqué sur l’enregistrement dispose de droits complets sur l’enregistrement. <br /><br />L’organisateur dispose de droits de modification et peut partager.<br /><br /> Tous les autres membres ont un accès en lecture.|
|Réunion adhoc/programmée avec des utilisateurs externes|Organisateur              |Compte OneDrive entreprise de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement.<br /> <br /> Tous les autres participants à la réunion à partir du même client que l’organisateur disposent d’un accès en lecture. <br /><br /> Les autres membres externes n’ont pas accès et l’organisateur doit les partager.|
|Réunion adhoc/programmée avec des utilisateurs externes|Autre membre de la réunion   |Membre sur lequel vous avez cliqué sur l’enregistrement                                  |Le membre qui a cliqué sur l’enregistrement dispose de droits complets sur l’enregistrement. L’organisateur dispose de droits de modification et peut partager. <br /><br /> Tous les autres participants à la réunion à partir du même client que l’organisateur disposent d’un accès en lecture. <br /><br />Les autres membres externes n’ont pas accès et l’organisateur doit les partager.|
|Réunion de canal                            |Membre du canal         |Emplacement SharePoint teams pour ce canal                   |Le membre qui a cliqué sur l’enregistrement dispose de droits de modification sur l’enregistrement. <br /> <br />Les autorisations des autres membres sont basées sur les autorisations SharePoint du canal.|

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

**Où l’enregistrement de la réunion sera-t-il stocké ?**

- Pour les réunions hors canal, l’enregistrement est stocké dans un dossier intitulé **enregistrements** qui se trouve au niveau supérieur de l’espace de travail de la réunion. Example

  <i>OneDrive entreprise</i> / de l’enregistreur **Enregistrements**

- Pour les réunions de canal, l’enregistrement est stocké dans la bibliothèque de documents du site d’équipe dans un dossier nommé **enregistrements**. Example

  <i>Nom de l’équipe-nom du canal</i> / Des **documents** / ; **Enregistrements**

**Comment gérer les enregistrements d’anciens employés ?**

Étant donné que les vidéos sont similaires à n’importe quel autre fichier dans OneDrive entreprise et SharePoint, la gestion de la propriété et de la rétention à l’issue d’un employé va suivre le [processus OneDrive entreprise et SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)normal.

**Qui dispose des autorisations pour afficher l’enregistrement de la réunion ?**

- Pour les réunions hors-canal, tous les participants à la réunion, à l’exception des utilisateurs externes, sont automatiquement liés à un lien. Les utilisateurs externes devront être explicitement ajoutés à la liste partagée par l’organisateur de la réunion ou la personne qui a démarré l’enregistrement de la réunion.

- Pour les réunions de canal, les autorisations sont héritées de la liste propriétaires et membres du canal.

**Comment gérer les transcriptions ?**

Les clients qui choisissent de bénéficier de cette version d’évaluation ne disposent pas de sous-titres disponibles dans leurs enregistrements de réunion teams migrés vers OneDrive entreprise et SharePoint.Nous travaillons pour ajouter des sous-titres, en commençant par des sous-titres en anglais, pour les enregistrements des réunions du 4e CY2020.

Les sous-titres seront disponibles dans les enregistrements de réunion teams pour les clients qui ont choisi d’autoriser les transcriptions comme décrit dans la rubrique [enregistrements Cloud teams](cloud-recording.md) .

Les légendes permettent de créer du contenu inclusive pour les visualiseurs de toutes les aptitudes. En tant que propriétaire, vous pouvez masquer les sous-titres, même si la transcription reste disponible dans les équipes, sauf si vous supprimez les sous-titres de teams. Découvrir [Comment activer ou désactiver les enregistrements de réunion](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Les sous-titres sont pris en charge pour les enregistrements des réunions teams pendant 60 jours à compter de la date d’enregistrement de la réunion.

Les sous-titres ne sont pas entièrement pris en charge si l’enregistrement de la réunion teams est déplacé ou copié à partir de son emplacement d’origine dans OneDrive entreprise ou SharePoint.

**Comment le quota de stockage sera-t-il affecté ?**

Les fichiers d’enregistrements de réunion teams résident dans OneDrive entreprise et SharePoint inclus dans votre quota de ces services. Voir [quotas SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) et [quota OneDrive entreprise](https://docs.microsoft.com/onedrive/set-default-storage-space).

Vous bénéficiez d’un espace de stockage supplémentaire avec [OneDrive entreprise](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) par rapport au flux et au stockage fungible avec SharePoint.

**Comment lire l’enregistrement d’une réunion teams ?**

Votre vidéo sera lue sur le lecteur vidéo de OneDrive entreprise ou SharePoint, selon l’endroit où vous accédez au fichier.

**Si vous envisagez d’utiliser l’ajout au flux, les vidéos existantes resteront-elles aussi longtemps que possible.**

Le flux en tant que plateforme ne sera pas déconseillé dans un avenir proche. Les vidéos actuellement actives dans le flux resteront là jusqu’à ce que la migration soit entamée. Lors de la migration, ces vidéos sont également migrées vers OneDrive entreprise ou SharePoint. Pour plus d’informations, consultez [ici](https://docs.microsoft.com/stream/streamnew/classic-migration) .

**Comment puis-je Appliquer une étiquette de conservation ?**

Découvrez [comment appliquer automatiquement une étiquette de rétention](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

**Comment attribuer des stratégies aux utilisateurs de Microsoft teams et quelles stratégies sont prioritaires ?**

[Déterminez quelle stratégie est prioritaire ?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).
