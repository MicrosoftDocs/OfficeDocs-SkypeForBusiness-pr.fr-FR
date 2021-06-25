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
description: Découvrez comment passer de Stream au stockage d’enregistrements de réunion OneDrive Entreprise et SharePoint dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72c65de4892a25889fb456c73406126d34335f9a
ms.sourcegitcommit: a07040d1527692b4dbde7bd2c21994377ad0a92e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114013"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Utiliser OneDrive Entreprise et SharePoint ou Stream pour les enregistrements de réunion

> [!Note]
> Le passage de Microsoft Stream à OneDrive Entreprise et SharePoint pour les enregistrements de réunion sera une approche progressive.

|<div style="width:290px">Date&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 octobre 2020<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Vous activez la stratégie Réunion Teams pour enregistrer les enregistrements de réunion dans OneDrive Entreprise et SharePoint au lieu de Microsoft Stream (classique)|
|Déploiement à compter du 7 janvier 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tous les nouveaux enregistrements des réunions Teams s’effectueront dans OneDrive Entreprise et SharePoint, sauf si vous retardez ce changement en modifiant les stratégies de réunion Teams de votre organisation et en les définissant explicitement sur **Stream**. Il ne suffit pas de voir les comptes-rendus de stratégie sous la forme Stream. Vous devez définir explicitement la valeur de la stratégie sur **Stream**.|
|Déploiement à compter du 11 janvier 2021<br> *(Complet)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Cloud de la communauté du secteur public uniquement**<br> Alors les clients du Cloud de la communauté du secteur public peuvent refuser cette option à compter du 5 octobre, vous n’avez pas le choix. Nous déploierons cette fonctionnalité à tous les clients du Cloud de la communauté du secteur public à compter du 11 janvier 2021, sauf si vous avez refusé.<br>  <br>À compter du 11 janvier 2021, tous les nouveaux enregistrements des réunions Teams pour les clients du Cloud de la communauté du secteur public s’effectueront dans OneDrive Entreprise et SharePoint, sauf si vous retardez ce changement en modifiant les stratégies de réunion Teams de votre organisation et en les définissant explicitement sur **Stream**. <br><br>Si vous avez refusé mais souhaitez activer cette fonctionnalité, vous pouvez le faire en choisissant de définir explicitement votre stratégie de réunion Teams sur **OneDrive Entreprise**. |
|Déploiement à compter du 1er mars 2021 <br> *(Terminé)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High et DoD uniquement**<br> Les clients peuvent à présent activer pour la première fois les enregistrements de réunions cloud dans leurs systèmes Microsoft Teams. Le stockage et la lecture de ces enregistrements s’effectueront sur OneDrive et SharePoint par défaut. |
|Déploiement incrémentielle à partir du 16 août 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tous les clients (Entreprise, Éducation et Cloud de la communauté du secteur public)**<br>Aucun nouvel enregistrement de réunion ne peut s’effectuer dans Microsoft Stream (Classique) ; tous les clients enregistrent automatiquement leurs réunions dans OneDrive Entreprise et SharePoint, même s’ils ont redéfini leur stratégie de réunion Teams sur Stream.<br><br> Nous recommandons aux clients, pour mieux contrôler le changement dans votre organisation, de s’y prendre à l’aise au lieu d’attendre qu’elle se produise. |

Microsoft Teams offre une nouvelle méthode d’enregistrement des réunions. Comme première phase d’une transition du système Microsoft Stream classique vers la [nouvelle version de Stream](/stream/streamnew/new-stream), cette méthode stocke les enregistrements sur Microsoft OneDrive Entreprise et SharePoint dans Microsoft 365, puis offre de nombreux avantages.

> [!NOTE]
> Si le chargement d’Teams d’une réunion échoue sur OneDrive/SharePoint, l’enregistrement est enregistré temporairement dans Azure Media Services (AMS). Une fois stocké dans AMS, aucune nouvelle tentative n’est faite pour télécharger automatiquement l’enregistrement sur OneDrive/SharePoint stream.

Les enregistrements de réunion stockés dans AMS sont disponibles pendant 21 jours avant d’être supprimés automatiquement. Les utilisateurs peuvent télécharger la vidéo à partir d’AMS s’ils ont besoin de conserver une copie.

L’utilisation de OneDrive Entreprise et SharePoint pour le stockage d’enregistrements comporte notamment les avantages suivants :

- Stratégies de rétention pour l’enregistrement des réunions Teams (TMR) (étiquettes de rétention automatique S+C E5)
- Gouvernance des informations de OneDrive Entreprise et de SharePoint
- Définition des autorisations et du partage en toute facilité
- Partage d’enregistrements avec des invités (utilisateurs externes) avec partage explicite uniquement
- Possibilité de demander des flux d’accès
- Offre des liens partagés OneDrive Entreprise et les sites SharePoint
- Les enregistrements de réunion sont disponibles plus rapidement
- Prise en charge des clients **Go local**
- Prise en charge multigéographique : les enregistrements résident dans une région spécifique de cet utilisateur
- Prise en charge de Bring Your Own Key (BYOK)

Consultez la liste complète des [fonctionnalités disponibles aujourd’hui et ce à quoi vous pouvez vous attendre au fil du temps.](/stream/streamnew/features-new-version-stream) 

Pour plus d’informations, regardez « Nouveautés Microsoft Teams enregistrements de réunion ».

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurer l’option d’enregistrement de la réunion pour OneDrive Entreprise et SharePoint

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

5. Utilisez [set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour définir une stratégie de réunion Teams de transition du stockage Stream vers OneDrive Entreprise et SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si certains de vos utilisateurs ont affecté une stratégie par organisateur ou par utilisateur et s’ils doivent également stocker les enregistrements de réunion dans OneDrive Entreprise et SharePoint, vous devez définir ce paramètre sur cette stratégie. Si vous souhaitez en savoir plus d’informations, veuillez consulter la rubrique [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Désactiver OneDrive Entreprise et SharePoint pour continuer à utiliser Stream

Même si le programme indique une stratégie définie sur **Stream**, elle n’est sans doute pas définie. En règle générale, si la stratégie n’est pas définie, le paramètre par défaut est **Stream**. Toutefois, avec ce nouveau changement, si vous préférez ne plus utiliser SharePoint ou OneDrive Entreprise, vous devez réinitialiser la stratégie sur **Stream** pour que **Stream** soit la stratégie par défaut.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorisations ou accès en fonction du rôle

> [!Note]
> Nous recommandons au destinataire d’être un utilisateur connecté lors du partage des enregistrements de réunion Teams. Sélectionnez l’option **Personnes dans (votre organisation)** lorsque vous partagez le fichier comme documenté dans [Partager des fichiers ou dossiers SharePoint](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US). Le partage externe n’est pas conçu pour la distribution de fichiers volumineux ou d’un grand nombre de fichiers. Pour éviter des scénarios de fraude et de mauvaise utilisation, vous risquez de rencontrer des problèmes lors du partage d’une grande quantité de données avec des utilisateurs externes.

|Type de réunion                               | Qui a cliqué sur Enregistrement ?| Où arrive l’enregistrement ?                               |Qui a accès ? En lecture et en écriture, lecture seule ou partage                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Appel individuel avec des parties internes             |Appelant                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant est propriétaire et dispose de tous les droits. <br /><br />Le destinataire de l’appel (s’il est dans le même client) dispose d’un accès en lecture seule. Aucun accès en partage. <br /><br /> Le destinataire de l’appel (s’il est dans un client différent) ne dispose d’aucun accès. L’appelant doit partager le document avec le destinataire de l’appel.|
|Appel individuel avec des parties internes             |Destinataire de l’appel                 |Compte OneDrive Entreprise du destinataire de l’appel                        |Le destinataire de l’appel est propriétaire et dispose de tous les droits. <br /><br />L’appelant (s’il est dans le même client) dispose d’un accès en lecture seule. Aucun accès en partage. <br /><br />L’appelant (s’il est dans un client différent) ne dispose d’aucun accès. Le destinataire de l’appel doit partager le document avec l’appelant.|
|Appel individuel avec des parties externes             |Appelant                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant est propriétaire et dispose de tous les droits.<br /> <br />Le destinataire de l’appel ne dispose d’aucun accès. L’appelant doit partager le document avec le destinataire de l’appel.|
|Appel individuel avec des parties externes             |Destinataire de l’appel                 |Compte OneDrive Entreprise du destinataire de l’appel                        |Le destinataire de l’appel est propriétaire et dispose de tous les droits.<br /><br />L’appelant ne dispose d’aucun accès. Le destinataire de l’appel doit partager le document avec l’appelant.|
|Appel de groupe                                 |Tout membre de l’appel |Membre du groupe ayant cliqué sur le compte d’OneDrive Entreprise d’enregistrement  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits. <br /><br /> Les autres membres du même client disposent de droits en lecture. <br /><br /> Les autres membres du groupe de différents locataires n’y ont aucun droit.|
|Réunion ad hoc/planifiée                    |Organisateur              |Compte OneDrive Entreprise de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement. <br /><br /> Tous les autres membres de la réunion disposent d’un accès en lecture.|
|Réunion ad hoc/planifiée                    |Autre membre de la réunion   |Membre de la réunion ayant cliqué sur Enregistrer                                  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits d’accès à l’enregistrement. <br /><br />L’organisateur dispose de droits de modification et de partage.<br /><br /> Tous les autres membres de la réunion ont un accès en lecture.|
|Réunion ad hoc/planifiée avec des utilisateurs externes|Organisateur              |Compte OneDrive Entreprise de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement.<br /> <br /> Tous les autres membres de la réunion provenant du même client que l’organisateur disposent d’un accès en lecture. <br /><br /> Tous les autres membres externes n’ont pas d’accès, et l’organisateur doit le partager avec eux.|
|Réunion ad hoc/planifiée avec des utilisateurs externes|Autre membre de la réunion   |Membre qui a cliqué sur Enregistrement                                  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits d’accès à l’enregistrement. L’organisateur dispose de droits de modification et de partage. <br /><br /> Tous les autres membres de la réunion provenant du même client que l’organisateur disposent d’un accès en lecture. <br /><br />Tous les autres membres externes n’ont pas d’accès, et l’organisateur doit le partager avec eux.|
|Réunion de canal                            |Membre du canal         |Emplacement SharePoint de Teams pour ce canal                   |Le membre qui a cliqué sur Enregistrement a le droit de modifier l’enregistrement. <br /> <br />Les autorisations de tous les autres membres sont basées sur le canal SharePoint’autorisations.|

## <a name="frequently-asked-questions"></a>Forum aux questions

**Où l’enregistrement de la réunion sera-t-il stocké ?**

- Pour les réunions autres que de canal, l’enregistrement réside dans un dossier nommé **Enregistrements** qui est au niveau supérieur du système OneDrive Entreprise appartenant à la personne qui a démarré l’enregistrement de la réunion. Exemple :

  <i>Enregistrements OneDrive Entreprise</i>/**de l’enregistreur**

- Pour les réunions du canal, l’enregistrement réside dans la bibliothèque de documentation du site Teams dans un dossier nommé **Enregistrements**. Exemple :

  <i>Nom Teams - Nom du canal</i>/**Documents**/**Enregistrements**

**Lorsque des fichiers Stream (tels que des enregistrements) résident dans SharePoint/OneDrive, comment leur destination est-elle déterminée ? L’administrateur peut-il modifier son niveau d’accès ?**

Par défaut, tous les fichiers d’enregistrement arrivent sur le compte OneDrive de l’utilisateur qui a sélectionné **Enregistrement**. Pour les réunions de canal, l’enregistrement arrive toujours sur le site SharePoint du canal. L’administrateur ne peut pas modifier l’emplacement de stockage de l’enregistrement.

**Comment gérer les enregistrements d’anciens employés ?**

Étant donné que les vidéos sont comme n’importe quel autre fichier dans OneDrive Entreprise et SharePoint, la gestion de la propriété et de la rétention après le départ d’un employé suit le [processus OneDrive Entreprise et SharePoint](/onedrive/retention-and-deletion#the-onedrive-deletion-process) normal.

**Qui est autorisé à afficher l’enregistrement de la réunion ?**

- Pour les réunions autres que de canal, tous les invités, sauf les utilisateurs externes, obtiennent automatiquement un lien partagé personnellement. L’organisateur de la réunion ou la personne qui a démarré l’enregistrement de la réunion devra ajouter explicitement les utilisateurs externes à la liste partagée.

- Pour les réunions de canal, les autorisations sont héritées de la liste des propriétaires et des membres dans le canal.

> [!NOTE]
> Vous ne recevrez pas d’e-mail à la fin de l’enregistrement, mais celui-ci s’affiche dans la conversation de réunion une fois qu’il est terminé. Cela se produit beaucoup plus rapidement qu’auparavant dans Stream.

**Comment gérer les légendes ?**

Les sous-titres Teams enregistrements des réunions ne seront disponibles lors de la lecture que si la transcription était désactivée au moment de l’enregistrement. Les administrateurs doivent [activer la transcription d’enregistrement via](/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) une stratégie pour s’assurer que leurs utilisateurs ont la possibilité d’enregistrer les réunions avec transcription.

Les sous-titres permettent de créer du contenu accessible à tous les viewers, quelles que soient leurs capacités. En tant que propriétaire, vous pouvez masquer des sous-titres dans l’enregistrement de la réunion, bien que la transcription de la réunion reste disponible sur Teams sauf si vous l’y supprimez. 

Nous prenons en charge les sous-titres codés pour les enregistrements de réunion Teams pendant 60 jours à compter de la date d’enregistrement de la réunion.

Nous ne prenons pas entièrement en charge les sous-titres codés si vous déplacez ou copiez l’enregistrement de réunion Teams depuis son emplacement d’origine sur OneDrive Entreprise ou SharePoint.

> [!NOTE]
> Il y aura des sous-titres en anglais uniquement (la transcription des réunions n’est pas encore disponible dans Cloud de la communauté du secteur public).

**Quel sera l’impact sur mon quota de stockage ?**

Les fichiers d’enregistrement de réunion Teams résident dans OneDrive Entreprise et SharePoint. Ils font partie de votre quota pour ces services. Si vous souhaitez en savoir plus, veuillez consulter les rubriques [Quota Sharepoint](/sharepoint/sites/plan-site-maintenance-and-management#quotas) et [Quota OneDrive Entreprise](/onedrive/set-default-storage-space).

[OneDrive Entreprise](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) offre davantage d’espace de stockage que Stream, et SharePoint offre davantage d’espace de stockage fongible.

**Comment lire un enregistrement de réunion Teams ?**

Vous pouvez lire votre vidéo est sur le lecteur vidéo de OneDrive Entreprise ou de SharePoint, selon l’endroit où vous accédez au fichier.

**Si vous envisagez de déconseiller l’ajout à Stream, les vidéos existantes resteront-elles toujours en l’état, et pendant combien de temps ?**

Nous ne déconseillerons pas Stream en tant que plateforme dans un avenir proche. Les vidéos qui résident actuellement dans Stream y resteront jusqu’au début de la migration. Lors de la migration, ces vidéos migreront également vers OneDrive Entreprise ou SharePoint. Si vous souhaitez en savoir plus, veuillez consulter la rubrique [Migration classique de Stream](/stream/streamnew/classic-migration).

**Comment puis-je appliquer une étiquette de rétention à Microsoft Teams enregistrements de réunion ?**

Si vous souhaitez en savoir plus, veuillez consulter la rubrique [Application automatique d’étiquettes de rétention](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

**Comment attribuer des stratégies à mes utilisateurs dans Microsoft Teams et quelles sont les stratégies prioritaires ?**

Si vous souhaitez en savoir plus, veuillez consulter la rubrique [Which policy takes precedence?](./assign-policies.md#which-policy-takes-precedence) (Quelle est la stratégie prioritaire ?).

**Où se trouve l’enregistrement si l’utilisateur ne OneDrive Entreprise pas SharePoint stockage, ou si le quota de stockage est plein ?**

L’enregistrement sera placé dans notre emplacement de stockage temporaire où il sera placé pendant 21 jours. Pendant ce temps, l’organisateur doit télécharger l’enregistrement. Si l’enregistrement n’est pas téléchargé dans les 21 jours, il est supprimé.
