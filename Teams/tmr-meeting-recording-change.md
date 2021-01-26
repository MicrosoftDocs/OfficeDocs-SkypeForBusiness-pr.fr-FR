---
title: Utiliser OneDrive Entreprise et SharePoint pour les enregistrements de réunion
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment passer de Stream à OneDrive Entreprise et au stockage d’enregistrements des réunions SharePoint dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3b7a3917f47bd07bd5d66ce5fdb524b91b0299e
ms.sourcegitcommit: d5732f043b7b5aa9b889aae185a7bc7e6ffad409
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49979751"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Utiliser OneDrive Entreprise et SharePoint ou Stream pour les enregistrements de réunion

> [!Note]
> La transition de l’utilisation de Microsoft Stream à OneDrive Entreprise et de Microsoft SharePoint pour les enregistrements des réunions sera progressive.

|<div style="width:290px">Date&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 octobre 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Vous pouvez activer la stratégie de réunion Teams pour que les enregistrements des réunions soit enregistrés dans OneDrive Entreprise et SharePoint au lieu de Microsoft Stream (classique)|
|Déploiement à partir du 7 janvier 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tous les enregistrements des nouvelles réunions Teams seront enregistrés dans OneDrive Entreprise et SharePoint, sauf si vous reportez cette modification en modifiant les stratégies de réunion Teams de votre organisation et en les setting explicitement sur **Stream.** Le signalement de stratégies comme Étant un flux n’est pas suffisant. Vous devez définir explicitement la valeur de la stratégie sur **Stream.**|
|Déploiement à partir du 11 janvier 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC uniquement**<br> Si les clients du gcc peuvent se dés désesser à partir du 5 octobre, vous ne pouvez pas choisir de le faire. Cette fonctionnalité sera déployée à tous les clients du service GCC à compter du 11 janvier 2021, sauf si vous avez choisi de le faire.<br>  <br>À compter du 11 janvier 2021, tous les nouveaux enregistrements de réunions Teams des clients GCC seront enregistrés dans OneDrive Entreprise et SharePoint, sauf si vous reportez cette modification en modifiant les stratégies de réunion Teams de votre organisation et en les settingant explicitement sur **Stream.** <br><br>Si vous avez choisi de ne pas le faire, mais que vous êtes prêt à activer cette fonctionnalité, vous pouvez définir votre stratégie de réunion Teams de manière explicite sur **OneDrive Entreprise.** |
|Déploiement à partir du 1er mars 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clients Entreprise & GCC**<br>Aucun nouvel enregistrement de réunion ne peut être enregistré dans Microsoft Stream (classique) ; tous les clients auront automatiquement des enregistrements de réunion enregistrés dans OneDrive Entreprise et **SharePoint, même s’ils** ont modifié leurs stratégies de réunion Teams sur Stream.<br><br> Nous recommandons aux clients de déployer cette fonctionnalité avant cette date afin qu’ils contrôlent le minutage de la publication. |
|Déploiement à partir du 7 juillet 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clients Éducation**<br>Aucun nouvel enregistrement de réunion ne peut être enregistré dans Microsoft Stream (classique) ; tous les clients auront automatiquement des enregistrements de réunion enregistrés dans OneDrive Entreprise et **SharePoint, même s’ils** ont modifié leurs stratégies de réunion Teams sur Stream.<br><br> Nous recommandons aux clients de déployer cette fonctionnalité avant cette date afin qu’ils contrôlent le minutage de la publication. Nous avons mis à jour ce planning pour offrir aux clients de l’enseignement la possibilité de terminer des semestres en cours. |

> [!Note]
> Pour mieux contrôler le changement dans votre organisation, nous recommandons aux clients Entreprise et Éducation de s’y prendre à l’aise au lieu d’attendre que cela se produise.

Microsoft Teams offre une nouvelle méthode pour enregistrer les enregistrements des réunions. Comme première phase d’une transition de Microsoft Stream classique vers le nouveau [Stream,](https://docs.microsoft.com/stream/streamnew/new-stream)cette méthode stocke les enregistrements sur Microsoft OneDrive Entreprise et SharePoint dans Microsoft 365 et offre de nombreux avantages.

L’utilisation de OneDrive Entreprise et SharePoint pour stocker des enregistrements permet notamment les avantages suivants :

- Stratégies de rétention pour l’enregistrement de réunion Teams (TMR) (étiquettes deretention automatique S+C E5)
- Tirer parti de la gouvernance des informations de OneDrive Entreprise et SharePoint
- Définir facilement les autorisations et le partage
- Partager des enregistrements avec des invités (utilisateurs externes) avec partage explicite uniquement
- Demander le flux d’accès
- Fournir des liens partagés OneDrive Entreprise et SharePoint
- Quota accru
- Les enregistrements de réunion sont disponibles plus rapidement
- **Prise en charge du** client local
- Prise en charge multigé géographique : les enregistrements sont stockés dans une région spécifique de cet utilisateur
- Apportez votre propre clé (BYOK)
- Amélioration de la qualité de la transcription et de l’attribution du haut-parleur

Il existe certaines limitations à prendre en compte :

- Il y aura des sous-titres et des transcriptions en anglais uniquement.
- Vous ne pourrez pas effectuer de recherche dans les transcriptions ni dans leur contenu.
- Vous ne pourrez pas modifier les transcriptions, mais vous pourrez l’éteindre/les.
- Vous pouvez contrôler la personne avec laquelle vous partagez l’enregistrement, mais vous ne pouvez pas empêcher les personnes ayant un accès partagé de télécharger l’enregistrement.
- Vous ne recevrez pas d’e-mail lorsque l’enregistrement sera terminé, mais l’enregistrement apparaîtra dans la conversation de réunion une fois celui-ci terminé. Cela se produira beaucoup plus rapidement qu’auparavant dans Stream

Pour plus d’informations, regardez « Enregistrement de la réunion ».

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurer l’option d’enregistrement de la réunion pour OneDrive Entreprise et SharePoint

L’option d’enregistrement de la réunion est un paramètre au niveau de la stratégie Teams. L’exemple suivant montre comment définir la stratégie globale. Veillez à définir l’option d’enregistrement de la réunion pour la ou les stratégies que vous avez affectées à vos utilisateurs.

> [!Note]
> La propagation des modifications de la stratégie de réunion Teams prend un certain temps. Resocher après quelques heures de configuration, puis se connectez-vous à nouveau.

1. Installez Skype Entreprise Online PowerShell.
**Remarque**: Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent. Si vous utilisez la dernière version publique de Teams PowerShell, vous n’avez pas besoin d’installer Skype Entreprise Online Connector. Consultez [Gérer Skype Entreprise Online avec PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. Téléchargez [Skype Entreprise Online PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. Suivez les invites pour l’installer.

    c. Redémarrez votre ordinateur.

2. Lancer PowerShell en tant qu’administrateur

3. Importez le connecteur SkypeOnline et connectez-vous en tant qu’administrateur Teams.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Utilisez [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) pour définir une stratégie de réunion Teams pour passer du stockage de flux à OneDrive Entreprise et SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si certains de vos utilisateurs ont affecté une stratégie par organisateur ou par utilisateur, vous devez définir ce paramètre sur cette stratégie si vous souhaitez qu’ils stockent également les enregistrements de la réunion dans OneDrive Entreprise et SharePoint. Pour plus d’informations, voir [Gérer les stratégies de réunion dans Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Dés son retrait de OneDrive Entreprise et SharePoint pour continuer à utiliser Stream

Même si une stratégie indique qu’elle est définie sur **Stream,** il est possible qu’elle ne soit pas définie. En règle générale, si la stratégie n’est pas définie, le paramètre par défaut est **Stream.** Toutefois, avec cette nouvelle modification, si vous souhaitez ne plus utiliser SharePoint ou OneDrive Entreprise, vous devez réinitialiser la stratégie sur **Stream** pour vous assurer que **Stream** est la valeur par défaut.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorisations ou accès en fonction du rôle

> [!Note]
> Nous recommandons au destinataire d’être connecté lors du partage des enregistrements de réunion Teams. Sélectionnez **l’option Personnes dans (votre organisation)** lorsque vous partagez le fichier tel qu’il est documenté dans des fichiers [ou dossiers SharePoint SharePoint.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) Le partage externe n’est pas conçu pour la distribution de fichiers de grande taille ou d’un grand nombre de fichiers. Afin d’éviter les fraudes et les abus, vous pouvez être victime de problèmes lors du partage d’une grande quantité de données à des utilisateurs externes.

|Type de réunion                               | Qui a cliqué sur Enregistrer ?| Où se trouve le lieu de l’enregistrement ?                               |Qui y a accès ? R/W, R, ou partage                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Appel à deux avec des parties internes             |Appelant                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant est le propriétaire et dispose des droits complets. <br /><br />L’appelant (dans le même client) dispose d’un accès en lecture seule. Pas d’accès au partage. <br /><br /> Appelé (si dans un autre client) n’a pas accès. L’appelant doit le partager avec le bénéficiaire de l’appel.|
|Appel à deux avec des parties internes             |Appelé                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant en est le propriétaire et dispose des droits complets. <br /><br />Appelant (si dans le même client dispose d’un accès en lecture seule. Pas d’accès au partage. <br /><br />L’appelant (s’il se présente dans un autre client) n’a pas accès. L’appelant doit le partager avec l’appelant.|
|Appel à deux avec un appel externe             |Appelant                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant est le propriétaire et dispose des droits complets.<br /> <br />Personne n’a accès à l’appel. L’appelant doit le partager avec le bénéficiaire de l’appel.|
|Appel à deux avec un appel externe             |Appelé                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant en est le propriétaire et dispose des droits complets.<br /><br />L’appelant n’a pas accès. L’appelant doit le partager avec l’appelant.|
|Appel de groupe                                 |N’importe quel membre de l’appel |Membre ayant cliqué sur le compte OneDrive Entreprise d’enregistrement  |Le membre qui a cliqué sur l’enregistrement dispose des droits complets. <br /><br /> Les autres membres du même client ont des droits de lecture. <br /><br /> Les autres membres d’un client différent n’y ont aucun droit.|
|Adhoc/Réunion programmée                    |Organisateur              |Compte OneDrive Entreprise de l’organisateur                     |L’organisateur dispose des droits complets sur l’enregistrement. <br /><br /> Tous les autres membres de la réunion ont un accès en lecture.|
|Adhoc/Réunion programmée                    |Autre membre de la réunion   |Membre ayant cliqué sur l’enregistrement                                  |Le membre qui a cliqué sur Enregistrer dispose des droits complets sur l’enregistrement. <br /><br />L’organisateur dispose de droits de modification et peut partager des informations.<br /><br /> Tous les autres membres ont un accès en lecture.|
|Réunion Adhoc/Scheduled avec des utilisateurs externes|Organisateur              |Compte OneDrive Entreprise de l’organisateur                     |L’organisateur dispose des droits complets sur l’enregistrement.<br /> <br /> Tous les autres membres de la réunion du même client que l’organisateur ont un accès en lecture. <br /><br /> Tous les autres membres externes n’y ont pas accès et l’Organisateur doit le partager avec eux.|
|Réunion Adhoc/Scheduled avec des utilisateurs externes|Autre membre de la réunion   |Membre ayant cliqué sur l’enregistrement                                  |Le membre qui a cliqué sur Enregistrer dispose des droits complets sur l’enregistrement. L’organisateur dispose de droits de modification et peut partager des informations. <br /><br /> Tous les autres membres de la réunion du même client que l’organisateur ont un accès en lecture. <br /><br />Tous les autres membres externes n’y ont pas accès et l’Organisateur doit le partager avec eux.|
|Réunion de canal                            |Membre du canal         |Emplacement SharePoint de Teams pour ce canal                   |Le membre qui a cliqué sur Enregistrer dispose de droits de modification sur l’enregistrement. <br /> <br />Les autorisations de chaque membre sur deux sont basées sur les autorisations De Canal SharePoint.|

## <a name="frequently-asked-questions"></a>Foire aux questions

**Où l’enregistrement de la réunion sera-t-il stocké ?**

- Pour les réunions hors canal, l’enregistrement est  stocké dans un dossier nommé Enregistrements au niveau supérieur de OneDrive Entreprise qui appartient à la personne qui a démarré l’enregistrement de la réunion. Exemple :

  <i>OneDrive Entreprise de l’enregistreur</i> / **Enregistrements**

- Pour les réunions de canal, l’enregistrement est stocké dans la bibliothèque de documentation du site Teams dans un dossier nommé **Enregistrements.** Exemple :

  <i>Nom de Teams - Nom du canal</i> / **Documents** / **Enregistrements**

**Quand des fichiers Stream (tels que des enregistrements) sont stockés dans SharePoint/OneDrive, comment a-t-on décidé où ils sont stockés ? L’administrateur a-t-il la possibilité de modifier la direction vers laquelle il va ?**

Par défaut, tous les fichiers d’enregistrement sont enregistrés sur le compte OneDrive de l’utilisateur qui a sélectionné **Enregistrer.** Pour les réunions de canal, l’enregistrement sera toujours sur le site SharePoint du canal. L’administrateur ne peut pas modifier l’endroit où est stocké l’enregistrement.

**Comment gérer les enregistrements d’anciens employés ?**

Comme les vidéos sont comme n’importe quel autre fichier dans OneDrive Entreprise et SharePoint, la gestion de la propriété et de la rétention après le départ d’un employé suit le processus OneDrive Entreprise et [SharePoint normal.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Qui a les autorisations pour afficher l’enregistrement de la réunion ?**

- Pour les réunions hors canal, tous les invités de la réunion, à l’exception des utilisateurs externes, obtiennent automatiquement un lien partagé personnellement. Les utilisateurs externes doivent être explicitement ajoutés à la liste partagée par l’organisateur de la réunion ou la personne ayant démarré l’enregistrement de la réunion.

- Pour les réunions de canal, les autorisations sont héritées des propriétaires et des membres de la liste dans le canal.

**Comment gérer les transcriptions ?**

Les clients optant pour cette prévisualisation ne disposent pas de sous-titres dans leurs enregistrements de réunion Teams migrés vers OneDrive Entreprise et SharePoint.Nous travaillons à l’ajout d’un sous-titrage, à partir de sous-titres en anglais, aux enregistrements de réunion au cours du 4e trimestre 2020.

Des sous-titres seront disponibles dans les enregistrements de réunion Teams pour les clients qui ont choisi d’autoriser les transcriptions, comme décrit dans les enregistrements [cloud Teams.](cloud-recording.md)

Les légendes permettent de créer du contenu accessible aux utilisateurs, qu’ils sont ou non. En tant que propriétaire, vous pouvez masquer les légendes, bien que la transcription reste disponible dans Teams, sauf si vous supprimez les sous-titres dans Teams. Découvrez [comment activer ou désactiver les enregistrements des réunions.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Les sous-titres sont pris en charge pour les enregistrements de réunion Teams pendant 60 jours à partir de la fin de l’enregistrement de la réunion.

Les sous-titres ne sont pas entièrement pris en charge si l’enregistrement de réunion Teams est déplacé ou copié à partir de son emplacement d’origine sur OneDrive Entreprise ou SharePoint.

**Quel sera l’impact sur mon quota de stockage ?**

Les fichiers d’enregistrement de réunion Teams en direct dans OneDrive Entreprise et SharePoint sont inclus dans votre quota pour ces services. Consultez [quota SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) [et quota OneDrive Entreprise.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Vous obtenez davantage de stockage avec [OneDrive Entreprise](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) par rapport à Stream et un stockage plus continu avec SharePoint.

**Comment lire l’enregistrement d’une réunion Teams ?**

Votre vidéo est lée sur le lecteur vidéo de OneDrive Entreprise ou SharePoint en fonction de l’endroit où vous accédez au fichier.

**Si vous envisagez de ne plus être ajouté à Stream, les vidéos existantes resteront-elles telles quelles et pendant combien de temps ?**

La diffusion en continu en tant que plateforme ne sera pas dépréciée dans un futur proche. Les vidéos qui sont actuellement en direct dans Stream y resteront jusqu’au début de la migration. Lors de la migration, ces vidéos sont également migrées vers OneDrive Entreprise ou SharePoint. Pour plus [d’informations, consultez](https://docs.microsoft.com/stream/streamnew/classic-migration) la migration classique de Flux.

**Comment appliquer une étiquette de rétention ?**

Découvrez [comment appliquer automatiquement une étiquette de rétention.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Comment attribuer des stratégies à mes utilisateurs dans Microsoft Teams et quelles stratégies sont prioritaire ?**

Voir [quelle stratégie prend le pas ?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)
