---
title: Gérer les composants en direct dans Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment gérer les composants en direct dans Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6be8db0fdde7509f5721277b4ee631f7a814171d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830218"
---
# <a name="manage-live-components-in-teams"></a>Gérer les composants en direct dans Teams

Les composants en direct Teams conversation instantanée offrent une nouvelle façon de donner une idée, de créer et de prendre des décisions ensemble. Envoyez un composant (tableau, liste de tâches ou paragraphe) dans lequel chaque personne de votre conversation peut modifier le texte et voir les modifications à mesure qu’elle est apportée. Cela signifie que vous pouvez recueillir des idées et des commentaires de votre équipe tout en limitant le nombre de réunions et en réduisant le besoin de discussions longues.

**Accomplir des tâches plus rapidement ensemble.** Sourcez un ordre du jour, suivez les éléments d’action d’un groupe ou prenez des notes collectivement. Voici quelques scénarios encore plus faciles à rendre grâce aux composants en direct.

**Partager des composants.** Dans cette version, vous pouvez partager des composants en direct dans différentes Teams conversations. Les destinataires peuvent apporter des modifications où qu’ils soient et voir instantanément les mises à jour, quel que soit l’endroit où ont été apportées les modifications. Dans les prochaines publication, les composants en direct seront pris en charge dans Teams notes et canaux de réunion, Outlook et, finalement, dans toutes Microsoft 365 applications.

**Démarrez la conversation, créez à partir de là.** Chaque composant que vous créez à partir Teams conversation est automatiquement enregistré dans un fichier dans OneDrive. Par exemple, vous pouvez commencer à collaborer dans une conversation, puis vous déplacer plus tard vers le fichier, où vous avez un espace visuel plus grand pour la modification et pouvez ajouter autant de composants que vous le souhaitez.

## <a name="clients-and-platforms"></a>Clients et plateformes

Disponible sur Teams applications sur Windows, Mac, Linux, iOS et Android.

À compter de début septembre, les composants en direct seront disponibles dans le monde monde. Fin septembre, il sera disponible pour Cloud de la communauté du secteur public Mod (Cloud de la communauté du secteur public).

## <a name="settings-management"></a>Paramètres gestion des projets

Les composants Live Sont conçus avec des Infrastructure Microsoft Fluid pris en charge dans Microsoft 365 suite et contrôlés à partir de SharePoint Online et non à partir du Teams d’administration.

Vous aurez besoin de la dernière version du [module SharePoint PowerShell Online](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) pour activer ou désactiver toutes les expériences fluides au sein de Office 365 client. Infrastructure Microsoft Fluid par défaut **sur ON pour** tous les locataires de publication ciblée. Les composants en direct étant conçus pour la collaboration, ils sont toujours partagés comme modifiables par d’autres personnes, même si votre client est définie par défaut sur Afficher uniquement pour les autres types de fichiers. Pour plus **d’informations,** voir le lien En savoir plus en regard du paramètre.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Vérifier si l’Infrastructure Fluid est activée via l’SharePoint Cmdlet PowerShell online

1. [Connecter à SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Vérifiez si Infrastructure Fluid est activé en exécutant l'Get-SPOTenant cmdlet sans aucun argument.

3. Vérifiez que la valeur d’Is AutoDesidEnabled est **vraie.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Activation du Infrastructure Fluid via l’SharePoint Cmdlet PowerShell Online 

1. [Connecter à SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Activer le fluidité à l’aide de l'Set-SPOTenant-IsIlidEnabled $true 
   
   L’application de la modification à votre locataire prend un court moment. 

La fonctionnalité sera disponible sur Teams Windows bureau, Mac, iOS, Android. Lorsqu’elle est activée, les utilisateurs voient une nouvelle option pour insérer des composants en direct dans l’expérience de composition de messages pour ces clients.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Désactivation de Infrastructure Fluid’SharePoint cmdlet PowerShell Online

1. [Connecter à SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Désactivez le fluid à l’aide Set-SPOTenant'Set-SPOTenant de cmdlet -IsIlidEnabled $false. 

   L’application de la modification à votre locataire prend un court moment. 

Si vous avez besoin de ré-activer cette fonctionnalité, vous pouvez utiliser SharePoint cmdlets PowerShell en ligne.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Limitations connues

- La création d’une table ou d’une liste des tâches comme premier composant après Teams redémarrage de l’application peut prendre du temps.

- Les autres membres de la conversation recevront une notification par courrier électronique lorsqu’ils sont mentionnés avec le symbole @ (@). (Les notifications @mentions dans le flux Teams’activités seront bientôt disponibles.)

- La recherche de composants en direct au sein Teams recherche retourne un lien vers le composant dans office.com et non le message de conversation proprement dit.

- Les composants Live sont désactivés dans les conversations fédérées et activés pour les conversations régulières avec un compte Invité à l’aide d’Azure B2B.

- Bien que vous pouvez partager un composant dans Teams canaux et d’autres Microsoft 365 applications, les destinataires obtiennent un lien dans la plupart des lieux à ce moment-là. La modification en ligne est prévue pour d’autres expériences à l’avenir.

## <a name="storage-of-fluid-files"></a>Stockage de `.fluid` fichiers

**Comment `.fluid` sont stockés ?**

Les composants en direct Teams sont dosés par un fichier stocké dans la base de `.fluid` données du créateur OneDrive Entreprise. Le fait d’être un fichier OneDrive Entreprise signifie que les utilisateurs peuvent créer, découvrir et gérer des composants (fichiers) aussi facilement que n’importe `.fluid` quel Office document.

Les utilisateurs peuvent rechercher du contenu dans `.fluid` des fichiers depuis Office.com et OneDrive Entreprise.
`.fluid` les fichiers fonctionnent avec les fonctionnalités de gouvernance des données telles que la découverte électronique, l’audit, les rapports et les contrôles juridiques.

`.fluid`les fichiers apparaîtront désormais sur Office.com et OneDrive Entreprise, par exemple dans les zones récents et recommandés.
`.fluid`des fichiers peuvent être restaurés vers des versions antérieures d’OneDrive Entreprise.

Les participants à la conversation doivent avoir OneDrive compte pour créer des composants en direct. Sans compte OneDrive valide, les participants à la conversation peuvent toujours collaborer sur un composant créé par d’autres utilisateurs qui possèdent un compte OneDrive valide, mais ne peuvent pas créer leur propre compte.

[Le](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) déplacement d’un fichier OneDrive vers un site SharePoint’échec du composant en direct lors du chargement de `.fluid` Teams conversation.

**Que se passe-t-il si le propriétaire du fichier quitte l’entreprise ?**

[OneDrive stratégies de rétention](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) s’appliquent aux fichiers comme aux `.fluid` autres contenus créés par l’utilisateur.

**Comment les fichiers `.fluid` sont-ils partagés ?**

Les composants en direct peuvent être insérés dans Teams conversation instantanée ou copiés d’une conversation à l’autre. (Les composants en direct ne sont pas encore pris en charge dans les canaux.) Elles utilisent par défaut les autorisations existantes du client, mais les utilisateurs peuvent modifier les autorisations avant l’envoi pour s’assurer que tout le monde y a accès.

L’ouverture de composants à partir Teams conversation dans Office.com propose des fonctionnalités de partage en haut de la fenêtre, similaires aux options de partage proposées pour d’Office documents.

**Que se `.fluid` passe-t-il si un fichier est endommagé ?**

L’historique des versions vous permet de passer en revue et de copier des versions précédentes du fichier.

**Quelles applications peuvent ouvrir et modifier des `.fluid` fichiers ?**

`.fluid`les fichiers peuvent uniquement être ouverts en tant que liens dans votre navigateur, comme Office.com, et en tant que composants en direct dans Teams conversation. Si elles sont téléchargées, elles ne peuvent pas être ouvertes à nouveau sans les avoir téléchargées au départ sur OneDrive Entreprise ou SharePoint Online.
