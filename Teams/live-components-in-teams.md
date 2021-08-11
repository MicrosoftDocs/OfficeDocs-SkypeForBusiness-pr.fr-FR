---
title: Gérer les composants en direct dans Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
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
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305016"
---
# <a name="manage-live-components-in-teams"></a>Gérer les composants en direct dans Teams

Les composants en direct Teams conversation instantanée offrent un nouveau moyen d’idée, de création et de prise de décisions ensemble. Envoyez un composant(par ex., un tableau, une liste de tâches ou un paragraphe) dans lequel tous les éléments de votre conversation peuvent être modifiés en ligne et voir les modifications telles qu’elles sont apportées. Cela signifie que vous pouvez recueillir des idées et des commentaires de votre équipe tout en tenant moins de réunions et en réduisant le besoin de threads de conversation longue.

**Faites les tâches plus rapidement ensemble.** Recherchez un agenda, suivez les éléments d’action d’un groupe ou prenez des notes collectivement. Il ne s’agit que de quelques scénarios facilités avec les composants en direct.

**Partager des composants.** Dans cette version, vous pouvez partager des composants en direct dans différentes Teams conversations. Les destinataires peuvent modifier où qu’ils soient et voir instantanément les mises à jour, quel que soit l’endroit où les modifications ont été apportées. Dans les prochaines publication, les composants en direct seront pris en charge dans Teams notes et canaux de réunion, Outlook, et finalement dans toutes les applications Microsoft 365.

**Démarrez dans la conversation, créez à partir de là.** Chaque composant que vous créez à partir Teams conversation est automatiquement enregistré dans un fichier dans OneDrive. Ainsi, vous pouvez commencer à collaborer dans la conversation, puis vous déplacer ultérieurement vers le fichier, où vous avez un espace visuel plus important pour la modification et pouvez ajouter autant de composants que vous le souhaitez.

## <a name="clients-and-platforms"></a>Clients et plateformes

Disponible sur Teams applications sur Windows, Mac, Linux, iOS et Android.

À compter du début de septembre, les composants en direct seront disponibles globalement. Fin septembre, il sera disponible pour Cloud de la communauté du secteur public Mod (Cloud de la communauté du secteur public).

## <a name="settings-management"></a>Paramètres gestion des données

Les composants Live sont créés avec Infrastructure Microsoft Fluid pris en charge dans Microsoft 365 suite et contrôlés à partir de SharePoint Online et non à partir Teams centre d’administration.

Vous aurez besoin de la dernière version du [module PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) SharePoint Online pour activer ou désactiver toutes les expériences fluides sur votre Office 365 client. Infrastructure Microsoft Fluid par défaut sur **ON** pour tous les locataires de version ciblée. Étant donné que les composants en direct sont conçus pour la collaboration, les composants sont toujours partagés en tant que modifiables par d’autres personnes, même si votre client est définie par défaut sur l’affichage seul pour les autres types de fichiers. Pour plus **d’informations,** voir le lien En savoir plus en regard du paramètre.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Vérification si le Infrastructure Fluid est activé via l’SharePoint Cmdlet PowerShell en ligne

1. [Connecter à SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Vérifiez si Infrastructure Fluid est activé en exécutant l'Get-SPOTenant cmdlet sans aucun argument.

3. Vérifiez que la valeur de IsFluidEnabled est **true**.

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Activation du Infrastructure Fluid via l’SharePoint Cmdlet PowerShell en ligne 

1. [Connecter à SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Activer fluid à l’aide de la cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   La modification prendra un court moment pour s’appliquer à votre location. 

La fonctionnalité sera disponible sur Teams Windows Bureau, Mac, iOS, Android. Lorsqu’il est activé, les utilisateurs voient une nouvelle option permettant d’insérer des composants en direct dans l’expérience de composition de message pour ces clients.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Désactivation de Infrastructure Fluid via SharePoint cmdlet PowerShell en ligne

1. [Connecter à SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. Désactivez Fluid à l’aide Set-SPOTenant cmdlet Set-SPOTenant -IsFluidEnabled $false. 

   La modification prendra un court moment pour s’appliquer à votre location. 

Si vous devez ré-activer cette fonctionnalité, vous pouvez utiliser SharePoint cmdlets PowerShell en ligne.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Limitations connues

- La création d’une table ou d’une liste de tâches en tant que premier composant après le redémarrage Teams’application peut prendre plus de temps.

- Les autres membres de conversation recevront une notification par courrier électronique lorsqu’ils seront mentionnés avec un symbole at (@). (Les notifications avec mentions dans le flux Teams’activité seront bientôt disponibles.)

- La recherche de composants en direct dans Teams recherche retourne un lien vers le composant dans office.com, et non le message de conversation proprement dit.

- Les composants Live sont désactivés dans les conversations fédérées et activés pour les conversations régulières avec un compte Invité à l’aide d’Azure B2B.

- Bien que vous pouvez partager un composant dans des canaux Teams et d’autres Microsoft 365, les destinataires obtiennent actuellement un lien dans la plupart des endroits. La modification inline est prévue pour d’autres expériences à l’avenir.

## <a name="storage-of-fluid-files"></a>Stockage de `.fluid` fichiers

**Comment `.fluid` sont stockés ?**

Les composants Live créés dans Teams sont stockés dans un fichier stocké dans `.fluid` l’OneDrive Entreprise. Le fait d’être un fichier OneDrive Entreprise signifie que les utilisateurs peuvent créer, découvrir et gérer des composants actifs (fichiers) aussi facilement que `.fluid` n’importe quel document Office document.

Les utilisateurs peuvent rechercher du contenu dans `.fluid` des fichiers Office.com et OneDrive Entreprise.
`.fluid` les fichiers fonctionnent avec des fonctionnalités de gouvernance des données telles que la découverte électronique, l’audit, les rapports et la archive légale.

`.fluid`les fichiers s’affichent Office.com et OneDrive Entreprise, par exemple dans les zones Récent et Recommandé.
`.fluid`les fichiers peuvent être restaurés vers des versions antérieures à partir OneDrive Entreprise.

Les participants à la conversation doivent avoir un OneDrive pour créer des composants en direct. Sans un compte OneDrive valide, les participants à la conversation peuvent toujours collaborer sur un composant créé par d’autres utilisateurs qui ont un compte OneDrive valide, mais ne peuvent pas créer leur propre compte.

[Le](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) déplacement d’un fichier OneDrive vers un site SharePoint’un site web entraîne l’échec du chargement du composant en direct `.fluid` dans Teams conversation.

**Que se passe-t-il si le propriétaire du fichier quitte l’entreprise ?**

[OneDrive stratégies de rétention](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) s’appliquent aux fichiers comme à d’autres contenus `.fluid` créés par l’utilisateur.

**Comment les fichiers `.fluid` sont-ils partagés ?**

Les composants live peuvent être insérés dans Teams conversation instantanée ou copiés d’une conversation à une autre. (Les composants Live ne sont pas encore pris en charge dans les canaux.) Ils utilisent par défaut les autorisations existantes du client, mais les utilisateurs peuvent modifier les autorisations avant l’envoi pour s’assurer que tout le monde y a accès.

L’ouverture de composants Teams conversation instantanée dans Office.com offre des fonctionnalités de partage en haut de la fenêtre, semblables aux options de partage proposées pour les autres documents Office documents.

**Que se `.fluid` passe-t-il si un fichier est endommagé ou endommagé ?**

L’historique des versions vous permet de passer en revue et de copier des versions précédentes du fichier.

**Quelles applications peuvent ouvrir et modifier des `.fluid` fichiers ?**

`.fluid`Les fichiers ne peuvent être ouverts que sous la mesure de liens dans votre navigateur, tels que Office.com, et en tant que composants en direct dans Teams conversation. S’ils sont téléchargés, ils ne peuvent pas être ouverts à nouveau sans les avoir téléchargés vers OneDrive Entreprise ou SharePoint Online.
